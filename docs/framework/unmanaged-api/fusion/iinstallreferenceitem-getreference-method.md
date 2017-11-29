---
title: "IInstallReferenceItem::GetReference 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceItem.GetReference
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8686e27e63d7363e61bf4c8f1898b71d21fda52b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="8bae2-102">IInstallReferenceItem::GetReference 方法</span><span class="sxs-lookup"><span data-stu-id="8bae2-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="8bae2-103">获取一个指向[FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)结构由此[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="8bae2-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bae2-104">语法</span><span class="sxs-lookup"><span data-stu-id="8bae2-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bae2-105">参数</span><span class="sxs-lookup"><span data-stu-id="8bae2-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="8bae2-106">[out]返回`FUSION_INSTALL_REFERENCE`指针。</span><span class="sxs-lookup"><span data-stu-id="8bae2-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8bae2-107">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="8bae2-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8bae2-108">`dwFlags`必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="8bae2-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8bae2-109">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="8bae2-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8bae2-110">`pvReserved`必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="8bae2-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bae2-111">要求</span><span class="sxs-lookup"><span data-stu-id="8bae2-111">Requirements</span></span>  
 <span data-ttu-id="8bae2-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bae2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bae2-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8bae2-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8bae2-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bae2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bae2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bae2-115">See Also</span></span>  
 [<span data-ttu-id="8bae2-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="8bae2-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="8bae2-117">FUSION_INSTALL_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="8bae2-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)