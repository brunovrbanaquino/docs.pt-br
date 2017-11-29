---
title: Interface1 ICorDebugILFrame2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2
helpviewer_keywords: ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 759232d5c1e5bdf00c85145fa0fc3d69743c13f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="98e8e-102">Interface1 ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="98e8e-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="98e8e-103">Uma extensão lógica da interface ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="98e8e-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98e8e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="98e8e-104">Methods</span></span>  
  
|<span data-ttu-id="98e8e-105">Método</span><span class="sxs-lookup"><span data-stu-id="98e8e-105">Method</span></span>|<span data-ttu-id="98e8e-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="98e8e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98e8e-107">Método EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="98e8e-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="98e8e-108">Obtém um objeto ICorDebugTypeEnum que contém o <xref:System.Type> parâmetros nesse quadro.</span><span class="sxs-lookup"><span data-stu-id="98e8e-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="98e8e-109">Método RemapFunction</span><span class="sxs-lookup"><span data-stu-id="98e8e-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="98e8e-110">Remapeia uma função editada, especificando o novo deslocamento MSIL.</span><span class="sxs-lookup"><span data-stu-id="98e8e-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98e8e-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="98e8e-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98e8e-112">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="98e8e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98e8e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98e8e-113">Requirements</span></span>  
 <span data-ttu-id="98e8e-114">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98e8e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98e8e-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98e8e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98e8e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98e8e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98e8e-117">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98e8e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e8e-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="98e8e-118">See Also</span></span>  
 [<span data-ttu-id="98e8e-119">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="98e8e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)