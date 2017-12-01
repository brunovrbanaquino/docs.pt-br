---
title: Estrutura USER_THREAD
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: USER_THREAD
api_location: diasymreader.dll
api_type: COM
f1_keywords: USER_THREAD
helpviewer_keywords: USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d93002fe5460bfdb36d4e11c74410677b46a98d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="userthread-structure"></a><span data-ttu-id="0c6a3-102">Estrutura USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="0c6a3-102">USER_THREAD Structure</span></span>
<span data-ttu-id="0c6a3-103">Fornece informações para um depurador sobre um segmento.</span><span class="sxs-lookup"><span data-stu-id="0c6a3-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="0c6a3-104">Para obter mais informações, consulte o [Inotifysource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="0c6a3-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c6a3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c6a3-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="0c6a3-106">Membros</span><span class="sxs-lookup"><span data-stu-id="0c6a3-106">Members</span></span>  
  
|<span data-ttu-id="0c6a3-107">Membro</span><span class="sxs-lookup"><span data-stu-id="0c6a3-107">Member</span></span>|<span data-ttu-id="0c6a3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c6a3-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="0c6a3-109">Endereço do buffer de thread.</span><span class="sxs-lookup"><span data-stu-id="0c6a3-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="0c6a3-110">Comprimento do buffer de thread, em bytes.</span><span class="sxs-lookup"><span data-stu-id="0c6a3-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="0c6a3-111">ID do thread.</span><span class="sxs-lookup"><span data-stu-id="0c6a3-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c6a3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c6a3-112">Requirements</span></span>  
 <span data-ttu-id="0c6a3-113">**Cabeçalho:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0c6a3-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6a3-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0c6a3-114">See Also</span></span>  
 [<span data-ttu-id="0c6a3-115">Método SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="0c6a3-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="0c6a3-116">Estruturas de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0c6a3-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)