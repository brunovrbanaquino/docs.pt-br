---
title: "Método ICorDebugVirtualUnwinder::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61f7e5afc65019f1817b15ae84ca3f7b42e3ece9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvirtualunwindernext-method"></a>Método ICorDebugVirtualUnwinder::Next
Avança para o contexto do chamador.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a>Parâmetros  
 nenhuma.  
  
## <a name="return-value"></a>Valor de retorno  
 `S_OK`Se o desenrolamento ocorreu com êxito, ou `CORDBG_S_AT_END_OF_STACK` se o desenrolamento não pode ser concluído porque não há nenhum quadro mais.  
  
 Se uma falha de HRESULT é retornado, ICorDebug APIs retornarão `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Comentários  
 O movimentador de pilha deve garantir que ele faz assim que eventualmente progresso, uma chamada para `Next` retornará uma falha HRESULT ou `CORDBG_S_AT_END_OF_STACK`. Retornando `S_OK` indefinidamente pode causar um loop infinito.  
  
> [!NOTE]
>  Esse método só está disponível com o .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Interface ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [Depurando interfaces](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
