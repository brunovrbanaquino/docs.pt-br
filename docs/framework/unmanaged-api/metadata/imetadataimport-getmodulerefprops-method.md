---
title: "Método IMetaDataImport::GetModuleRefProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 907743481cf036b7febf57d69ce428a250752c30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="73b3c-102">Método IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="73b3c-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="73b3c-103">Obtém o nome do módulo referenciado pelo token de metadados especificado.</span><span class="sxs-lookup"><span data-stu-id="73b3c-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b3c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="73b3c-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73b3c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="73b3c-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="73b3c-106">[in] O token de metadados de ModuleRef que faz referência ao módulo para obter informações de metadados.</span><span class="sxs-lookup"><span data-stu-id="73b3c-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="73b3c-107">[out] Um buffer para armazenar o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="73b3c-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="73b3c-108">[in] O tamanho solicitado de `szName` em caracteres largos.</span><span class="sxs-lookup"><span data-stu-id="73b3c-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="73b3c-109">[out] O tamanho retornado de `szName` em caracteres largos.</span><span class="sxs-lookup"><span data-stu-id="73b3c-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73b3c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73b3c-110">Requirements</span></span>  
 <span data-ttu-id="73b3c-111">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73b3c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73b3c-112">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73b3c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73b3c-113">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="73b3c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73b3c-114">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73b3c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b3c-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="73b3c-115">See Also</span></span>  
 [<span data-ttu-id="73b3c-116">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="73b3c-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="73b3c-117">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="73b3c-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)