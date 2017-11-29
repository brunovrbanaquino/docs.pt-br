---
title: "Método ICorDebugStackWalk::SetContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.SetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374092c500d4263a172219c38cbc1b2f0ce293a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="53c82-102">Método ICorDebugStackWalk::SetContext</span><span class="sxs-lookup"><span data-stu-id="53c82-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="53c82-103">Conjuntos de [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) o contexto atual do objeto para um contexto válido para o thread.</span><span class="sxs-lookup"><span data-stu-id="53c82-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c82-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="53c82-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53c82-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="53c82-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="53c82-106">[in] Um [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) sinalizador que indica se o contexto é do quadro ativo na pilha ou um contexto obtido pela desenrolamento da pilha.</span><span class="sxs-lookup"><span data-stu-id="53c82-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="53c82-107">[in] O tamanho alocado do `CONTEXT` buffer.</span><span class="sxs-lookup"><span data-stu-id="53c82-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="53c82-108">[in] O `CONTEXT` buffer.</span><span class="sxs-lookup"><span data-stu-id="53c82-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53c82-109">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="53c82-109">Return Value</span></span>  
 <span data-ttu-id="53c82-110">Este método retorna a seguintes HRESULTs específicos, bem como o HRESULT erros que indicam falha do método.</span><span class="sxs-lookup"><span data-stu-id="53c82-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="53c82-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53c82-111">HRESULT</span></span>|<span data-ttu-id="53c82-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="53c82-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53c82-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="53c82-113">S_OK</span></span>|<span data-ttu-id="53c82-114">O `ICorDebugStackWalk` contexto do objeto foi definido com êxito.</span><span class="sxs-lookup"><span data-stu-id="53c82-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="53c82-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53c82-115">E_FAIL</span></span>|<span data-ttu-id="53c82-116">O `ICorDebugStackWalk` contexto do objeto não foi definido.</span><span class="sxs-lookup"><span data-stu-id="53c82-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="53c82-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="53c82-117">E_INVALIDARG</span></span>|<span data-ttu-id="53c82-118">O contexto é nulo.</span><span class="sxs-lookup"><span data-stu-id="53c82-118">The context is null.</span></span>|  
|<span data-ttu-id="53c82-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="53c82-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="53c82-120">O buffer de contexto é muito pequeno.</span><span class="sxs-lookup"><span data-stu-id="53c82-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="53c82-121">Exceções</span><span class="sxs-lookup"><span data-stu-id="53c82-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53c82-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="53c82-122">Remarks</span></span>  
 <span data-ttu-id="53c82-123">Este método não altera o contexto atual do thread.</span><span class="sxs-lookup"><span data-stu-id="53c82-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="53c82-124">Definir o contexto atual para um contexto inválido pode causar resultados imprevisíveis de movimentador de pilha.</span><span class="sxs-lookup"><span data-stu-id="53c82-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="53c82-125">Você pode recuperar uma cópia exata de bit a bit deste contexto chamando imediatamente o [Icordebugstackwalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="53c82-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53c82-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53c82-126">Requirements</span></span>  
 <span data-ttu-id="53c82-127">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53c82-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53c82-128">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53c82-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53c82-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53c82-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53c82-130">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53c82-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c82-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53c82-131">See Also</span></span>  
 [<span data-ttu-id="53c82-132">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="53c82-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="53c82-133">Depuração</span><span class="sxs-lookup"><span data-stu-id="53c82-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)