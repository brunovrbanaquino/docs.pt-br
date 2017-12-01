---
title: "Considerações de segurança no WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
caps.latest.revision: "49"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c0af5a5d96f20b2ba5118909a3f0c5ba405bdb11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="5a022-102">Considerações de segurança no WCF</span><span class="sxs-lookup"><span data-stu-id="5a022-102">Security Considerations in WCF</span></span>
<span data-ttu-id="5a022-103">Os tópicos nesta seção listam vários itens relacionados à segurança a serem considerados durante a criação de um [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5a022-103">The topics in this section list various security-related items to consider when designing a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a022-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5a022-104">In This Section</span></span>  
 [<span data-ttu-id="5a022-105">Divulgação de informações</span><span class="sxs-lookup"><span data-stu-id="5a022-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="5a022-106">Discute as várias maneiras que informações podem ser divulgadas ou atacadas e como mitigar isso.</span><span class="sxs-lookup"><span data-stu-id="5a022-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="5a022-107">Elevação de privilégio</span><span class="sxs-lookup"><span data-stu-id="5a022-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="5a022-108">Discute os efeitos de conceder permissões de autorização um invasor além daquelas concedidas inicialmente e como mitigar isso.</span><span class="sxs-lookup"><span data-stu-id="5a022-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="5a022-109">Negação de serviço</span><span class="sxs-lookup"><span data-stu-id="5a022-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="5a022-110">Discute o que acontece quando um sistema não pode processar mensagens adequadamente e como resolvê-la.</span><span class="sxs-lookup"><span data-stu-id="5a022-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="5a022-111">Violação</span><span class="sxs-lookup"><span data-stu-id="5a022-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="5a022-112">Discute a alteração de mensagens ou a entrega de mensagens e como resolvê-la.</span><span class="sxs-lookup"><span data-stu-id="5a022-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="5a022-113">Ataques de repetição</span><span class="sxs-lookup"><span data-stu-id="5a022-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="5a022-114">Discute o que acontece quando um invasor copia um fluxo de mensagens entre duas partes e repete o fluxo para um ou mais partes e como mitigar isso.</span><span class="sxs-lookup"><span data-stu-id="5a022-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="5a022-115">Considerações sobre segurança para sessões seguras</span><span class="sxs-lookup"><span data-stu-id="5a022-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="5a022-116">Discute os seguintes itens que afetam a segurança ao implementar sessões seguras.</span><span class="sxs-lookup"><span data-stu-id="5a022-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="5a022-117">Cenários sem suporte</span><span class="sxs-lookup"><span data-stu-id="5a022-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="5a022-118">Lista os vários cenários que não oferecem suporte a um aspecto específico de segurança e devem ser evitados ou considerados.</span><span class="sxs-lookup"><span data-stu-id="5a022-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5a022-119">Referência</span><span class="sxs-lookup"><span data-stu-id="5a022-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="5a022-120">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="5a022-120">Related Sections</span></span>  
 [<span data-ttu-id="5a022-121">Orientações de segurança e práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="5a022-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="5a022-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5a022-122">See Also</span></span>  
 [<span data-ttu-id="5a022-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="5a022-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)