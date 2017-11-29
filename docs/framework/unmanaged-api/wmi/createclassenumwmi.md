---
title: "CreateClassEnumWmi 函数 （非托管 API 参考）"
description: "CreateClassEnumWmi 函数将返回满足指定的条件的所有类的枚举数。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateClassEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateClassEnumWmi
helpviewer_keywords: CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbfee6f8e98d04a591c58560e6d50044e716a1f
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="b4f5e-103">CreateClassEnumWmi 函数</span><span class="sxs-lookup"><span data-stu-id="b4f5e-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="b4f5e-104">返回满足指定的选择条件的所有类的枚举数。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b4f5e-105">语法</span><span class="sxs-lookup"><span data-stu-id="b4f5e-105">Syntax</span></span>  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="b4f5e-106">参数</span><span class="sxs-lookup"><span data-stu-id="b4f5e-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="b4f5e-107">[in]如果不是`null`或留空，指定的名称的父类; 枚举器返回仅的此类的子类。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="b4f5e-108">如果它是`null`或空白和`lFlags`为 WBEM_FLAG_SHALLOW，则返回仅顶级类 （与任何父类的类）。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="b4f5e-109">如果它是`null`或空白和`lFlags`是`WBEM_FLAG_DEEP`，命名空间中返回所有类。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="b4f5e-110">[in]影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="b4f5e-111">在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="b4f5e-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="b4f5e-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="b4f5e-112">Constant</span></span>  |<span data-ttu-id="b4f5e-113">值</span><span class="sxs-lookup"><span data-stu-id="b4f5e-113">Value</span></span>  |<span data-ttu-id="b4f5e-114">描述</span><span class="sxs-lookup"><span data-stu-id="b4f5e-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="b4f5e-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="b4f5e-115">0x20000</span></span> | <span data-ttu-id="b4f5e-116">如果集，该函数检索当前连接的区域设置的本地化命名空间中存储的修正的限定符。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="b4f5e-117">如果未设置，函数将检索存储在即时命名空间限定符。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="b4f5e-118">0</span><span class="sxs-lookup"><span data-stu-id="b4f5e-118">0</span></span> | <span data-ttu-id="b4f5e-119">枚举在层次结构，但不是此类包含所有子类。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="b4f5e-120">1</span><span class="sxs-lookup"><span data-stu-id="b4f5e-120">1</span></span> | <span data-ttu-id="b4f5e-121">枚举包括的此类仅纯实例，并排除的子类，可提供此类中找不到属性的所有实例。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="b4f5e-122">0x10</span><span class="sxs-lookup"><span data-stu-id="b4f5e-122">0x10</span></span> | <span data-ttu-id="b4f5e-123">标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="b4f5e-124">0x20</span><span class="sxs-lookup"><span data-stu-id="b4f5e-124">0x20</span></span> | <span data-ttu-id="b4f5e-125">该函数返回的只进的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="b4f5e-126">通常，只进的枚举器速度更快和使用的内存少于传统枚举器，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="b4f5e-127">0</span><span class="sxs-lookup"><span data-stu-id="b4f5e-127">0</span></span> | <span data-ttu-id="b4f5e-128">WMI 将保留指向 enumration 中的对象的指针，直到它们被释放为止。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="b4f5e-129">建议的标志是`WBEM_FLAG_RETURN_IMMEDIATELY`和`WBEM_FLAG_FORWARD_ONLY`为了获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="b4f5e-130">[in]通常，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="b4f5e-131">否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-131">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="b4f5e-132">[out]接收枚举数的指针。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="b4f5e-133">[in]授权级别中。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-133">[in] The authorization level.</span></span>

<span data-ttu-id="b4f5e-134">`impLevel`[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="b4f5e-135">[in]指向的指针[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)对象，表示当前的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-135">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="b4f5e-136">[in]用户名。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-136">[in] The user name.</span></span> <span data-ttu-id="b4f5e-137">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="b4f5e-138">[in]密码。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-138">[in] The password.</span></span> <span data-ttu-id="b4f5e-139">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="b4f5e-140">[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-140">[in] The domain name of the user.</span></span> <span data-ttu-id="b4f5e-141">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4f5e-142">返回值</span><span class="sxs-lookup"><span data-stu-id="b4f5e-142">Return value</span></span>

<span data-ttu-id="b4f5e-143">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="b4f5e-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b4f5e-144">返回的常量</span><span class="sxs-lookup"><span data-stu-id="b4f5e-144">Constant</span></span>  |<span data-ttu-id="b4f5e-145">值</span><span class="sxs-lookup"><span data-stu-id="b4f5e-145">Value</span></span>  |<span data-ttu-id="b4f5e-146">描述</span><span class="sxs-lookup"><span data-stu-id="b4f5e-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="b4f5e-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="b4f5e-147">0x80041003</span></span> | <span data-ttu-id="b4f5e-148">用户没有权限查看一个或多个函数可以返回的类。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="b4f5e-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b4f5e-149">0x80041001</span></span> | <span data-ttu-id="b4f5e-150">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="b4f5e-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="b4f5e-151">0x80041010</span></span> | <span data-ttu-id="b4f5e-152">`strSuperClass` 不存在。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b4f5e-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b4f5e-153">0x80041008</span></span> | <span data-ttu-id="b4f5e-154">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b4f5e-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b4f5e-155">0x80041006</span></span> | <span data-ttu-id="b4f5e-156">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="b4f5e-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="b4f5e-157">0x80041033</span></span> | <span data-ttu-id="b4f5e-158">WMI 时可能已停止和重新启动。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="b4f5e-159">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="b4f5e-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="b4f5e-160">0x80041015</span></span> | <span data-ttu-id="b4f5e-161">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b4f5e-162">0</span><span class="sxs-lookup"><span data-stu-id="b4f5e-162">0</span></span> | <span data-ttu-id="b4f5e-163">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b4f5e-164">备注</span><span class="sxs-lookup"><span data-stu-id="b4f5e-164">Remarks</span></span>

<span data-ttu-id="b4f5e-165">此函数包装对的调用[iwbemservices:: Createclassenum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-165">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b4f5e-166">如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4f5e-167">要求</span><span class="sxs-lookup"><span data-stu-id="b4f5e-167">Requirements</span></span>  
 <span data-ttu-id="b4f5e-168">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f5e-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f5e-169">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b4f5e-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b4f5e-170">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f5e-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f5e-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4f5e-171">See also</span></span>  
[<span data-ttu-id="b4f5e-172">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="b4f5e-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)