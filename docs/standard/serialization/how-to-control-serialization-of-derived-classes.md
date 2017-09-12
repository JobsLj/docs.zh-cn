---
title: "如何：控制派生类的序列化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: caa92596-9e15-4d91-acbe-56911ef47a84
caps.latest.revision: 3
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: f09584345d10cece014da9604ffbfe01ad08d10f
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-control-serialization-of-derived-classes"></a><span data-ttu-id="31190-102">如何：控制派生类的序列化</span><span class="sxs-lookup"><span data-stu-id="31190-102">How to: Control Serialization of Derived Classes</span></span>
<span data-ttu-id="31190-103">使用 XmlElementAttribute 属性更改 XML 元素的名称不是自定义对象序列化的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="31190-103">Using the **XmlElementAttribute** attribute to change the name of an XML element is not the only way to customize object serialization.</span></span> <span data-ttu-id="31190-104">您还可以自定义 XML 流，具体方法为从现有类派生以及指示 <xref:System.Xml.Serialization.XmlSerializer> 实例如何序列化新类。</span><span class="sxs-lookup"><span data-stu-id="31190-104">You can also customize the XML stream by deriving from an existing class and instructing the <xref:System.Xml.Serialization.XmlSerializer> instance how to serialize the new class.</span></span>  
  
 <span data-ttu-id="31190-105">例如，假设有一个 `Book` 类，您可以从该类派生，并创建一个具有多个属性的 `ExpandedBook` 类。</span><span class="sxs-lookup"><span data-stu-id="31190-105">For example, given a `Book` class, you can derive from it and create an `ExpandedBook` class that has a few more properties.</span></span> <span data-ttu-id="31190-106">然而，序列化或反序列化时，必须指导 XmlSerializer 接受派生类型。</span><span class="sxs-lookup"><span data-stu-id="31190-106">However, you must instruct the **XmlSerializer** to accept the derived type when serializing or deserializing.</span></span> <span data-ttu-id="31190-107">可以通过创建一个 <xref:System.Xml.Serialization.XmlElementAttribute> 实例并将其 Type 属性设置为派生类类型来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="31190-107">This can be done by creating a <xref:System.Xml.Serialization.XmlElementAttribute> instance and setting its **Type** property to the derived class type.</span></span> <span data-ttu-id="31190-108">将 XmlElementAttribute 添加到 <xref:System.Xml.Serialization.XmlAttributes> 实例。</span><span class="sxs-lookup"><span data-stu-id="31190-108">Add the **XmlElementAttribute** to a <xref:System.Xml.Serialization.XmlAttributes> instance.</span></span> <span data-ttu-id="31190-109">再将 XmlAttributes 添加到 <xref:System.Xml.Serialization.XmlAttributeOverrides> 实例，指定被重写的类型和接受派生类型的成员名。</span><span class="sxs-lookup"><span data-stu-id="31190-109">Then add the **XmlAttributes** to a <xref:System.Xml.Serialization.XmlAttributeOverrides> instance, specifying the type being overridden and the name of the member that accepts the derived class.</span></span> <span data-ttu-id="31190-110">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="31190-110">This is shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31190-111">示例</span><span class="sxs-lookup"><span data-stu-id="31190-111">Example</span></span>  
  
```vb  
Public Class Orders  
    public Books() As Book  
End Class     
  
Public Class Book  
    public ISBN As String   
End Class  
  
Public Class ExpandedBook  
    Inherits Book  
    public NewEdition As Boolean  
End Class  
  
Public Class Run  
    Shared Sub Main()  
        Dim t As Run = New Run()  
        t.SerializeObject("Book.xml")  
        t.DeserializeObject("Book.xml")  
    End Sub  
  
    Public Sub SerializeObject(filename As String)  
        ' Each overridden field, property, or type requires   
        ' an XmlAttributes instance.   
        Dim attrs As XmlAttributes = New XmlAttributes()  
  
        ' Creates an XmlElementAttribute instance to override the   
        ' field that returns Book objects. The overridden field  
        ' returns Expanded objects instead.  
        Dim attr As XmlElementAttribute = _  
        New XmlElementAttribute()  
        attr.ElementName = "NewBook"  
        attr.Type = GetType(ExpandedBook)  
  
        ' Adds the element to the collection of elements.  
        attrs.XmlElements.Add(attr)  
  
        ' Creates the XmlAttributeOverrides.  
        Dim attrOverrides As XmlAttributeOverrides = _  
        New XmlAttributeOverrides()  
  
        ' Adds the type of the class that contains the overridden   
        ' member, as well as the XmlAttributes instance to override it   
        ' with, to the XmlAttributeOverrides instance.   
        attrOverrides.Add(GetType(Orders), "Books", attrs)  
  
        ' Creates the XmlSerializer using the XmlAttributeOverrides.  
        Dim s As XmlSerializer  = _  
        New XmlSerializer(GetType(Orders), attrOverrides)  
  
        ' Writing the file requires a TextWriter instance.  
        Dim writer As TextWriter = New StreamWriter(filename)  
  
        ' Creates the object to be serialized.  
        Dim myOrders As Orders = New Orders()  
  
        ' Creates an object of the derived type.  
        Dim b As ExpandedBook = New ExpandedBook()  
        b.ISBN= "123456789"  
        b.NewEdition = True  
        myOrders.Books = New ExpandedBook(){b}  
  
        ' Serializes the object.  
        s.Serialize(writer,myOrders)  
        writer.Close()  
    End Sub  
  
    Public Sub DeserializeObject(filename As String)  
        Dim attrOverrides As XmlAttributeOverrides = _  
        New XmlAttributeOverrides()  
        Dim attrs As XmlAttributes = New XmlAttributes()  
  
        ' Creates an XmlElementAttribute to override the   
        ' field that returns Book objects. The overridden field  
        ' returns Expanded objects instead.   
        Dim attr As XmlElementAttribute = _  
        New XmlElementAttribute()  
        attr.ElementName = "NewBook"  
        attr.Type = GetType(ExpandedBook)  
  
        ' Adds the XmlElementAttribute to the collection of objects.  
        attrs.XmlElements.Add(attr)  
  
        attrOverrides.Add(GetType(Orders), "Books", attrs)  
  
        ' Creates the XmlSerializer using the XmlAttributeOverrides.  
        Dim s As XmlSerializer = _  
        New XmlSerializer(GetType(Orders), attrOverrides)  
  
        Dim fs As FileStream = New FileStream(filename, FileMode.Open)  
        Dim myOrders As Orders = CType( s.Deserialize(fs), Orders)  
        Console.WriteLine("ExpandedBook:")  
  
        ' The difference between deserializing the overridden   
        ' XML document and serializing it is this: To read the derived   
        ' object values, you must declare an object of the derived type   
        ' and cast the returned object to it.   
        Dim expanded As ExpandedBook   
        Dim b As Book  
        for each b  in myOrders.Books  
            expanded = CType(b, ExpandedBook)  
            Console.WriteLine(expanded.ISBN)  
            Console.WriteLine(expanded.NewEdition)  
        Next  
    End Sub  
End Class  
```  
  
```csharp  
public class Orders  
{  
    public Book[] Books;  
}      
  
public class Book  
{  
    public string ISBN;  
}  
  
public class ExpandedBook:Book  
{  
    public bool NewEdition;  
}  
  
public class Run  
{  
    public void SerializeObject(string filename)  
    {  
        // Each overridden field, property, or type requires   
        // an XmlAttributes instance.  
        XmlAttributes attrs = new XmlAttributes();  
  
        // Creates an XmlElementAttribute instance to override the   
        // field that returns Book objects. The overridden field  
        // returns Expanded objects instead.  
        XmlElementAttribute attr = new XmlElementAttribute();  
        attr.ElementName = "NewBook";  
        attr.Type = typeof(ExpandedBook);  
  
        // Adds the element to the collection of elements.  
        attrs.XmlElements.Add(attr);  
  
        // Creates the XmlAttributeOverrides instance.  
        XmlAttributeOverrides attrOverrides = new XmlAttributeOverrides();  
  
        // Adds the type of the class that contains the overridden   
        // member, as well as the XmlAttributes instance to override it   
        // with, to the XmlAttributeOverrides.  
        attrOverrides.Add(typeof(Orders), "Books", attrs);  
  
        // Creates the XmlSerializer using the XmlAttributeOverrides.  
        XmlSerializer s =   
        new XmlSerializer(typeof(Orders), attrOverrides);  
  
        // Writing the file requires a TextWriter instance.  
        TextWriter writer = new StreamWriter(filename);  
  
        // Creates the object to be serialized.  
        Orders myOrders = new Orders();  
  
        // Creates an object of the derived type.  
        ExpandedBook b = new ExpandedBook();  
        b.ISBN= "123456789";  
        b.NewEdition = true;  
        myOrders.Books = new ExpandedBook[]{b};  
  
        // Serializes the object.  
        s.Serialize(writer,myOrders);  
        writer.Close();  
    }  
  
    public void DeserializeObject(string filename)  
    {  
        XmlAttributeOverrides attrOverrides =   
            new XmlAttributeOverrides();  
        XmlAttributes attrs = new XmlAttributes();  
  
        // Creates an XmlElementAttribute to override the   
        // field that returns Book objects. The overridden field  
        // returns Expanded objects instead.  
        XmlElementAttribute attr = new XmlElementAttribute();  
        attr.ElementName = "NewBook";  
        attr.Type = typeof(ExpandedBook);  
  
        // Adds the XmlElementAttribute to the collection of objects.  
        attrs.XmlElements.Add(attr);  
  
        attrOverrides.Add(typeof(Orders), "Books", attrs);  
  
        // Creates the XmlSerializer using the XmlAttributeOverrides.  
        XmlSerializer s =   
        new XmlSerializer(typeof(Orders), attrOverrides);  
  
        FileStream fs = new FileStream(filename, FileMode.Open);  
        Orders myOrders = (Orders) s.Deserialize(fs);  
        Console.WriteLine("ExpandedBook:");  
  
        // The difference between deserializing the overridden   
        // XML document and serializing it is this: To read the derived   
        // object values, you must declare an object of the derived type   
        // and cast the returned object to it.  
        ExpandedBook expanded;  
        foreach(Book b in myOrders.Books)   
        {  
            expanded = (ExpandedBook)b;  
            Console.WriteLine(  
            expanded.ISBN + "\n" +   
            expanded.NewEdition);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="31190-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31190-112">See Also</span></span>  
 <span data-ttu-id="31190-113"><xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="31190-113"><xref:System.Xml.Serialization.XmlSerializer></span></span>   
 <span data-ttu-id="31190-114"><xref:System.Xml.Serialization.XmlElementAttribute></span><span class="sxs-lookup"><span data-stu-id="31190-114"><xref:System.Xml.Serialization.XmlElementAttribute></span></span>   
 <span data-ttu-id="31190-115"><xref:System.Xml.Serialization.XmlAttributes></span><span class="sxs-lookup"><span data-stu-id="31190-115"><xref:System.Xml.Serialization.XmlAttributes></span></span>   
 <span data-ttu-id="31190-116"><xref:System.Xml.Serialization.XmlAttributeOverrides></span><span class="sxs-lookup"><span data-stu-id="31190-116"><xref:System.Xml.Serialization.XmlAttributeOverrides></span></span>   
 <span data-ttu-id="31190-117">[XML 和 SOAP 序列化](../../../docs/standard/serialization/xml-and-soap-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="31190-117">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md) </span></span>  
 <span data-ttu-id="31190-118">[如何：序列化对象](../../../docs/standard/serialization/how-to-serialize-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="31190-118">[How to: Serialize an Object](../../../docs/standard/serialization/how-to-serialize-an-object.md) </span></span>  
 [<span data-ttu-id="31190-119">如何：指定 XML 流的替代元素名称</span><span class="sxs-lookup"><span data-stu-id="31190-119">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
