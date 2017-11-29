---
title: "Método IGCHost2::SetGCStartupLimitsEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae924447e38dfec8d365fe6cdc85e5dccb028714
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="497da-102">Método IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="497da-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="497da-103">Define o tamanho do segmento e o tamanho máximo de geração 0.</span><span class="sxs-lookup"><span data-stu-id="497da-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="497da-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="497da-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="497da-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="497da-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="497da-106">[in] O tamanho do segmento usado pelo sistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="497da-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="497da-107">[in] O tamanho máximo de geração 0.</span><span class="sxs-lookup"><span data-stu-id="497da-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="497da-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="497da-108">Remarks</span></span>  
 <span data-ttu-id="497da-109">Os valores que `SetGCStartupLimitsEx` conjuntos podem ser especificados apenas antes que o host é iniciado.</span><span class="sxs-lookup"><span data-stu-id="497da-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="497da-110">Esses valores não podem ser alterados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="497da-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="497da-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="497da-111">Requirements</span></span>  
 <span data-ttu-id="497da-112">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="497da-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="497da-113">**Cabeçalho:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="497da-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="497da-114">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="497da-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="497da-115">**Versões do .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="497da-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="497da-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="497da-116">See Also</span></span>  
 [<span data-ttu-id="497da-117">Interface IGCHost2</span><span class="sxs-lookup"><span data-stu-id="497da-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)