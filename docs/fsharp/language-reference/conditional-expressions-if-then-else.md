---
title: "条件表达式：if... then...else (F#)"
description: "了解如何编写 F # 可执行代码的不同分支中的条件的表达式。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e1871c-4d4d-4691-9ab2-bd2c6f65589a
ms.openlocfilehash: 3531a112eb53657d5e9102d5e5f3be988360b76e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="b644e-104">条件表达式：`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="b644e-104">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="b644e-105">`if...then...else`表达式运行代码的不同分支，还可以计算为不同的值，具体取决于给定的布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="b644e-105">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="b644e-106">语法</span><span class="sxs-lookup"><span data-stu-id="b644e-106">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="b644e-107">备注</span><span class="sxs-lookup"><span data-stu-id="b644e-107">Remarks</span></span>
<span data-ttu-id="b644e-108">在上述语法中， *expression1*运行时的布尔表达式的计算结果为`true`; 否则为*expression2*运行。</span><span class="sxs-lookup"><span data-stu-id="b644e-108">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="b644e-109">与其他语言版本，`if...then...else`构造是一个表达式，而不是语句。</span><span class="sxs-lookup"><span data-stu-id="b644e-109">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="b644e-110">这意味着它生成一个值，即执行的分支中的最后一个表达式的值。</span><span class="sxs-lookup"><span data-stu-id="b644e-110">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="b644e-111">每个分支中生成的值的类型必须匹配。</span><span class="sxs-lookup"><span data-stu-id="b644e-111">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="b644e-112">如果没有显式`else`分支，其类型是`unit`。</span><span class="sxs-lookup"><span data-stu-id="b644e-112">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="b644e-113">因此，如果的一种`then`分支是任何类型，而不`unit`，必须有`else`分支以及相同的返回类型。</span><span class="sxs-lookup"><span data-stu-id="b644e-113">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="b644e-114">在将链接时`if...then...else`表达式组合在一起，可以使用关键字`elif`而不是`else if`; 它们是等效的。</span><span class="sxs-lookup"><span data-stu-id="b644e-114">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="b644e-115">示例</span><span class="sxs-lookup"><span data-stu-id="b644e-115">Example</span></span>
<span data-ttu-id="b644e-116">下面的示例演示如何使用`if...then...else`表达式。</span><span class="sxs-lookup"><span data-stu-id="b644e-116">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
John
910 is less than 20
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="b644e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b644e-117">See Also</span></span>
[<span data-ttu-id="b644e-118">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b644e-118">F# Language Reference</span></span>](index.md)
