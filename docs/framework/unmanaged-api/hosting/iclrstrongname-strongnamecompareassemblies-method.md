---
title: "Método ICLRStrongName::StrongNameCompareAssemblies"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 96fbeccf76de87a3582bf8c2084d0ca9ad7d27f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>Método ICLRStrongName::StrongNameCompareAssemblies
Determina se os dois assemblies diferem somente por suas assinaturas de nome forte.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `wszAssembly1`  
 [in] O caminho para o primeiro conjunto.  
  
 `wszAssembly2`  
 [in] O caminho para o segundo conjunto.  
  
 `pdwResult`  
 [out] Um dos seguintes valores:  
  
-   `SN_CMP_DIFFERENT`(0) - Especifica que os assemblies conterem dados diferentes.  
  
-   `SN_CMP_IDENTICAL`(1) - Especifica que os assemblies são exatamente iguais, incluindo suas assinaturas e a soma de verificação.  
  
-   `SN_CMP_SIGONLY`(2) - Especifica que os assemblies diferem somente por assinatura e soma de verificação.  
  
## <a name="return-value"></a>Valor de retorno  
 `S_OK`Se o método foi concluída com êxito; Caso contrário, um valor HRESULT que indica uma falha (consulte [valores HRESULT comuns](http://go.microsoft.com/fwlink/?LinkId=213878) para obter uma lista).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost.h  
  
 **Biblioteca:** incluído como um recurso no MSCOREE  
  
 **Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Comentários  
 A assinatura de um assembly de nome forte consiste em nome de texto, versão, cultura e token de chave pública do assembly.  
  
## <a name="see-also"></a>Consulte também  
 [Interface ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
