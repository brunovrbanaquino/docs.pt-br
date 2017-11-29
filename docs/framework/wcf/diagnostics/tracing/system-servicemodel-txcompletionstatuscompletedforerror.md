---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bce99f11ba5a18e80c24fc51e65b66de97f9e7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="76498-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="76498-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="76498-103">A transação especificada para a operação especificada foi concluída devido a uma exceção sem tratamento de execução.</span><span class="sxs-lookup"><span data-stu-id="76498-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="76498-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="76498-104">Description</span></span>  
 <span data-ttu-id="76498-105">Rastreada quando ocorre um erro durante uma tentativa de concluir a transação atual.</span><span class="sxs-lookup"><span data-stu-id="76498-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="76498-106">Isso ocorre antes de uma resposta ou falha é enviada para o chamador.</span><span class="sxs-lookup"><span data-stu-id="76498-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="76498-107">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="76498-107">Troubleshooting</span></span>  
 <span data-ttu-id="76498-108">Inspecione a mensagem de rastreamento para a mensagem de exceção e quaisquer itens acionáveis.</span><span class="sxs-lookup"><span data-stu-id="76498-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76498-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="76498-109">See Also</span></span>  
 [<span data-ttu-id="76498-110">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="76498-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="76498-111">Usando o rastreamento para solucionar problemas de seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="76498-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 <span data-ttu-id="76498-112">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md) (Administração e diagnósticos)</span><span class="sxs-lookup"><span data-stu-id="76498-112">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md)</span></span>