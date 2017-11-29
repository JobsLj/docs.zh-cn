---
title: "ICorDebugCode 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7813381c345db3d14318dddd93df1b491b46549e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode-interface1"></a><span data-ttu-id="a2689-102">ICorDebugCode 接口 1</span><span class="sxs-lookup"><span data-stu-id="a2689-102">ICorDebugCode Interface1</span></span>
<span data-ttu-id="a2689-103">表示 Microsoft 中间语言 (MSIL) 代码段或本机代码段。</span><span class="sxs-lookup"><span data-stu-id="a2689-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2689-104">方法</span><span class="sxs-lookup"><span data-stu-id="a2689-104">Methods</span></span>  
  
|<span data-ttu-id="a2689-105">方法</span><span class="sxs-lookup"><span data-stu-id="a2689-105">Method</span></span>|<span data-ttu-id="a2689-106">描述</span><span class="sxs-lookup"><span data-stu-id="a2689-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2689-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="a2689-108">指定的偏移量处创建断点。</span><span class="sxs-lookup"><span data-stu-id="a2689-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="a2689-109">GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="a2689-110">获取代码段的相对虚拟地址 (RVA)，这`ICorDebugCode`表示。</span><span class="sxs-lookup"><span data-stu-id="a2689-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="a2689-111">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="a2689-112">获取为指定的函数，为反汇编进行格式化的所有代码。</span><span class="sxs-lookup"><span data-stu-id="a2689-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="a2689-113">此方法已弃用;使用[icordebugcode2:: Getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="a2689-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="a2689-114">GetEnCRemapSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="a2689-115">未实现。</span><span class="sxs-lookup"><span data-stu-id="a2689-115">Not implemented.</span></span>|  
|[<span data-ttu-id="a2689-116">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="a2689-117">获取与此关联"ICorDebugFunction" `ICorDebugCode`。</span><span class="sxs-lookup"><span data-stu-id="a2689-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="a2689-118">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="a2689-119">获取表示从 MSIL 偏移量到本机偏移量的映射的"COR_DEBUG_IL_TO_NATIVE_MAP"实例的数组。</span><span class="sxs-lookup"><span data-stu-id="a2689-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="a2689-120">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="a2689-121">获取用字节表示，这表示的二进制代码的大小， `ICorDebugCode`。</span><span class="sxs-lookup"><span data-stu-id="a2689-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="a2689-122">GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="a2689-123">获取标识代码的版本的基于 1 的数字此`ICorDebugCode`表示。</span><span class="sxs-lookup"><span data-stu-id="a2689-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="a2689-124">IsIL 方法</span><span class="sxs-lookup"><span data-stu-id="a2689-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="a2689-125">获取一个值，该值指示是否这`ICorDebugCode`在 MSIL 中编译。</span><span class="sxs-lookup"><span data-stu-id="a2689-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2689-126">备注</span><span class="sxs-lookup"><span data-stu-id="a2689-126">Remarks</span></span>  
 <span data-ttu-id="a2689-127">`ICorDebugCode`可以表示 MSIL 或本机代码。</span><span class="sxs-lookup"><span data-stu-id="a2689-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="a2689-128">表示 MSIL 代码的"ICorDebugFunction"对象可以包含零个或一个`ICorDebugCode`与它关联的对象。</span><span class="sxs-lookup"><span data-stu-id="a2689-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="a2689-129">一个表示本机代码的"ICorDebugFunction"对象可以具有任意数量的`ICorDebugCode`与它关联的对象。</span><span class="sxs-lookup"><span data-stu-id="a2689-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2689-130">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a2689-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2689-131">要求</span><span class="sxs-lookup"><span data-stu-id="a2689-131">Requirements</span></span>  
 <span data-ttu-id="a2689-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2689-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2689-133">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2689-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2689-134">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2689-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2689-135">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2689-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2689-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2689-136">See Also</span></span>  
    
 [<span data-ttu-id="a2689-137">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="a2689-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="a2689-138">调试接口</span><span class="sxs-lookup"><span data-stu-id="a2689-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)