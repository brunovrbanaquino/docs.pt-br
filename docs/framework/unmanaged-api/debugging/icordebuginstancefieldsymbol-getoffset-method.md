---
title: "Método ICorDebugInstanceFieldSymbol::GetOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 534e3238a4b20e390c4f2168629e0ba93620f55a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="5dad9-102">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="5dad9-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="5dad9-103">Obtém o deslocamento de bytes deste campo de instância em sua classe pai.</span><span class="sxs-lookup"><span data-stu-id="5dad9-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dad9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5dad9-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5dad9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5dad9-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="5dad9-106">Um ponteiro para o número de bytes que este campo de instância é deslocado em sua classe pai.</span><span class="sxs-lookup"><span data-stu-id="5dad9-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dad9-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="5dad9-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dad9-108">Esse método só está disponível com o .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5dad9-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dad9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dad9-109">Requirements</span></span>  
 <span data-ttu-id="5dad9-110">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dad9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dad9-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5dad9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5dad9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dad9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5dad9-113">**Versões do .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dad9-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dad9-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5dad9-114">See Also</span></span>  
 [<span data-ttu-id="5dad9-115">Interface ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="5dad9-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="5dad9-116">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="5dad9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)