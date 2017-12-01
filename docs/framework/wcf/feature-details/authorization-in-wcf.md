---
title: "Autorização no WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0c2afafa1d645ec0e95b7b41ff8389873969c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="9f8cf-102">Autorização no WCF</span><span class="sxs-lookup"><span data-stu-id="9f8cf-102">Authorization in WCF</span></span>
<span data-ttu-id="9f8cf-103">A autorização é o processo de controle de acesso e direitos a recursos, como arquivos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="9f8cf-104">Os tópicos nesta seção mostram como executar essa tarefa básica no [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] em uma variedade de maneiras.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-104">The topics in this section show you how to perform this basic task in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f8cf-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9f8cf-105">In This Section</span></span>  
 [<span data-ttu-id="9f8cf-106">Mecanismos de controle de acesso</span><span class="sxs-lookup"><span data-stu-id="9f8cf-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="9f8cf-107">Fornece uma breve descrição dos mecanismos de autorização no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]e sugerida usa.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-107">Provides a brief outline of the authorization mechanisms in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and suggested uses.</span></span>  
  
 <span data-ttu-id="9f8cf-108">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md) (Como restringir o acesso com a classe PrincipalPermissionAttribute)</span><span class="sxs-lookup"><span data-stu-id="9f8cf-108">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)</span></span>  
 <span data-ttu-id="9f8cf-109">Mostra o processo de restringir o acesso a um serviço com o <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="9f8cf-110">Como: usar o provedor de função ASP.NET com um serviço</span><span class="sxs-lookup"><span data-stu-id="9f8cf-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="9f8cf-111">Explica a configuração de um serviço para habilitá-lo para usar o recurso de provedor de função do [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f8cf-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="9f8cf-112">Como: usar o provedor de função do Gerenciador de autorização ASP.NET com um serviço</span><span class="sxs-lookup"><span data-stu-id="9f8cf-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="9f8cf-113">pode usar o Gerenciador de autorização para gerenciar a autorização para um site da Web.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9f8cf-114">da mesma forma pode aproveitar o [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]combinação /Authorization Gerenciador de autorização de clientes.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-114"> can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="9f8cf-115">Gerenciando reivindicações e autorização com o modelo de identidade</span><span class="sxs-lookup"><span data-stu-id="9f8cf-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="9f8cf-116">Explica os conceitos básicos de como usar a infraestrutura do modelo de identidade para autorização baseada em declarações.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="9f8cf-117">Delegação e representação</span><span class="sxs-lookup"><span data-stu-id="9f8cf-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="9f8cf-118">Explica a diferença entre a delegação e representação.</span><span class="sxs-lookup"><span data-stu-id="9f8cf-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9f8cf-119">Referência</span><span class="sxs-lookup"><span data-stu-id="9f8cf-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="9f8cf-120">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="9f8cf-120">Related Sections</span></span>  
 [<span data-ttu-id="9f8cf-121">Autenticação</span><span class="sxs-lookup"><span data-stu-id="9f8cf-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f8cf-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9f8cf-122">See Also</span></span>  
 [<span data-ttu-id="9f8cf-123">Visão geral de segurança</span><span class="sxs-lookup"><span data-stu-id="9f8cf-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="9f8cf-124">Modelo de segurança para o Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="9f8cf-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)