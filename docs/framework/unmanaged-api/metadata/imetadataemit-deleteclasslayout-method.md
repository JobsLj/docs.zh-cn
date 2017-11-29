---
title: "IMetaDataEmit::DeleteClassLayout 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeleteClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a35606f85e134886addd8b30c240442800a9109e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="4b11e-102">IMetaDataEmit::DeleteClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="4b11e-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="4b11e-103">销毁指定标记所表示的类型的类布局元数据签名。</span><span class="sxs-lookup"><span data-stu-id="4b11e-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b11e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b11e-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b11e-105">参数</span><span class="sxs-lookup"><span data-stu-id="4b11e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4b11e-106">[in]`mdTypeDef`表示类布局将删除为其类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4b11e-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b11e-107">要求</span><span class="sxs-lookup"><span data-stu-id="4b11e-107">Requirements</span></span>  
 <span data-ttu-id="4b11e-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b11e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b11e-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b11e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b11e-110">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4b11e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b11e-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b11e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b11e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b11e-112">See Also</span></span>  
 [<span data-ttu-id="4b11e-113">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="4b11e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="4b11e-114">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="4b11e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)