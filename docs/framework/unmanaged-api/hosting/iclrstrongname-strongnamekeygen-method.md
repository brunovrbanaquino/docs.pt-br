---
title: "Método ICLRStrongName::StrongNameKeyGen"
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
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b434783d7537c5f6a3127183f66d4b0b3f77534
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>Método ICLRStrongName::StrongNameKeyGen
Cria um novo par de chaves pública/privada para uso de nome forte.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `wszKeyContainer`  
 [in] O nome do contêiner de chave solicitado. `wszKeyContainer`deve ser uma cadeia de caracteres não vazia ou null para gerar um nome temporário.  
  
 `dwFlags`  
 [in] Um valor que especifica se deve deixar a chave registrada. Há suporte para os seguintes valores:  
  
-   0x00000000 - usado quando `wszKeyContainer` é nulo para gerar um nome de contêiner de chave temporária.  
  
-   0x00000001 (`SN_LEAVE_KEY`)-Especifica que a chave deve ser registrada para a esquerda.  
  
 `ppbKeyBlob`  
 [out] O par de chaves pública/privada retornado.  
  
 `pcbKeyBlob`  
 [out] O tamanho, em bytes, de `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valor de retorno  
 `S_OK`Se o método foi concluída com êxito; Caso contrário, um valor HRESULT que indica uma falha (consulte [valores HRESULT comuns](http://go.microsoft.com/fwlink/?LinkId=213878) para obter uma lista).  
  
## <a name="remarks"></a>Comentários  
 O [Strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) método cria uma chave de 1024 bits. Após a chave de recuperação, você deve chamar o [Iclrstrongname](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar a memória alocada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost.h  
  
 **Biblioteca:** incluído como um recurso no MSCOREE  
  
 **Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Método StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [Interface ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
