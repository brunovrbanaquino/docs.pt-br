---
title: "Cenários comuns de segurança"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9428c5d7c8c6cf0f571b05a8b9c33b96d073d7a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="common-security-scenarios"></a><span data-ttu-id="edd70-102">Cenários comuns de segurança</span><span class="sxs-lookup"><span data-stu-id="edd70-102">Common Security Scenarios</span></span>
<span data-ttu-id="edd70-103">Os tópicos nesta seção um número de cliente possíveis e as configurações de segurança do serviço de catálogo.</span><span class="sxs-lookup"><span data-stu-id="edd70-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="edd70-104">As configurações variam de acordo com uma série de fatores.</span><span class="sxs-lookup"><span data-stu-id="edd70-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="edd70-105">Por exemplo, se um cliente ou serviço estiver em uma intranet, ou se a segurança é fornecida pelo Windows ou o transporte (por exemplo, HTTPS).</span><span class="sxs-lookup"><span data-stu-id="edd70-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="edd70-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="edd70-106">In This Section</span></span>  
 [<span data-ttu-id="edd70-107">Serviço e cliente de Internet desprotegido</span><span class="sxs-lookup"><span data-stu-id="edd70-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="edd70-108">Um exemplo de um cliente público, segura e de serviço.</span><span class="sxs-lookup"><span data-stu-id="edd70-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="edd70-109">Serviço e cliente inseguro de intranet</span><span class="sxs-lookup"><span data-stu-id="edd70-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="edd70-110">Básico [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] serviço desenvolvido para fornecer informações em uma rede privada segura para um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplicativo.</span><span class="sxs-lookup"><span data-stu-id="edd70-110">A basic [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service developed to provide information on a secure private network to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span>  
  
 [<span data-ttu-id="edd70-111">Segurança de transporte com autenticação básica</span><span class="sxs-lookup"><span data-stu-id="edd70-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="edd70-112">O aplicativo permite que clientes façam logon usando a autenticação personalizada.</span><span class="sxs-lookup"><span data-stu-id="edd70-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="edd70-113">Segurança de transporte com autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="edd70-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="edd70-114">Mostra um cliente e o serviço protegidos pela segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="edd70-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="edd70-115">Segurança de transporte com um cliente anônimo</span><span class="sxs-lookup"><span data-stu-id="edd70-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="edd70-116">Esse cenário usa a segurança de transporte (como HTTPS) para garantir a integridade e confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="edd70-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="edd70-117">Segurança de transporte com autenticação de certificado</span><span class="sxs-lookup"><span data-stu-id="edd70-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="edd70-118">Mostra um cliente e protegida por um certificado de serviço.</span><span class="sxs-lookup"><span data-stu-id="edd70-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="edd70-119">Segurança de mensagem com um cliente anônimo</span><span class="sxs-lookup"><span data-stu-id="edd70-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="edd70-120">Mostra um cliente e o serviço protegido pelo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] segurança de mensagem.</span><span class="sxs-lookup"><span data-stu-id="edd70-120">Shows a client and service secured by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message security.</span></span>  
  
 [<span data-ttu-id="edd70-121">Segurança de mensagem com um nome de usuário cliente</span><span class="sxs-lookup"><span data-stu-id="edd70-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="edd70-122">O cliente é um aplicativo de formulários do Windows que permite que clientes façam logon usando um nome de usuário de domínio e uma senha.</span><span class="sxs-lookup"><span data-stu-id="edd70-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="edd70-123">Segurança de mensagem com um certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="edd70-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="edd70-124">Os servidores possuem certificados, e cada cliente tem um certificado.</span><span class="sxs-lookup"><span data-stu-id="edd70-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="edd70-125">Um contexto de segurança é estabelecido por meio de negociação de segurança de camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="edd70-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="edd70-126">Segurança de mensagem com um cliente do Windows</span><span class="sxs-lookup"><span data-stu-id="edd70-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="edd70-127">Uma variação do cliente de certificado.</span><span class="sxs-lookup"><span data-stu-id="edd70-127">A variation of the certificate client.</span></span> <span data-ttu-id="edd70-128">Os servidores possuem certificados, e cada cliente tem um certificado.</span><span class="sxs-lookup"><span data-stu-id="edd70-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="edd70-129">Um contexto de segurança é estabelecido por meio de negociação de TLS.</span><span class="sxs-lookup"><span data-stu-id="edd70-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="edd70-130">Segurança de mensagem com um cliente do Windows sem negociação de credencial</span><span class="sxs-lookup"><span data-stu-id="edd70-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="edd70-131">Mostra um cliente e o serviço protegido por um domínio do Kerberos.</span><span class="sxs-lookup"><span data-stu-id="edd70-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="edd70-132">Segurança de mensagem com certificados mútuos</span><span class="sxs-lookup"><span data-stu-id="edd70-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="edd70-133">Os servidores possuem certificados, e cada cliente tem um certificado.</span><span class="sxs-lookup"><span data-stu-id="edd70-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="edd70-134">O certificado do servidor é distribuído com o aplicativo e está disponível fora da banda.</span><span class="sxs-lookup"><span data-stu-id="edd70-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="edd70-135">Segurança de mensagem com Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="edd70-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="edd70-136">Segurança federada que permite o estabelecimento de uma relação de confiança entre domínios independentes.</span><span class="sxs-lookup"><span data-stu-id="edd70-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="edd70-137">Subsistema confiável</span><span class="sxs-lookup"><span data-stu-id="edd70-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="edd70-138">Um cliente acessa um ou mais serviços Web que são distribuídos em uma rede.</span><span class="sxs-lookup"><span data-stu-id="edd70-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="edd70-139">Os serviços da Web acesso a recursos adicionais (como bancos de dados ou outros serviços da Web) que devem ser protegidos.</span><span class="sxs-lookup"><span data-stu-id="edd70-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="edd70-140">Referência</span><span class="sxs-lookup"><span data-stu-id="edd70-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="edd70-141">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="edd70-141">Related Sections</span></span>  
 [<span data-ttu-id="edd70-142">Autorização</span><span class="sxs-lookup"><span data-stu-id="edd70-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="edd70-143">Visão geral de segurança</span><span class="sxs-lookup"><span data-stu-id="edd70-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="edd70-144">Segurança</span><span class="sxs-lookup"><span data-stu-id="edd70-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="edd70-145">Associações e segurança</span><span class="sxs-lookup"><span data-stu-id="edd70-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="edd70-146">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="edd70-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="edd70-147">Autenticação</span><span class="sxs-lookup"><span data-stu-id="edd70-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="edd70-148">Autorização</span><span class="sxs-lookup"><span data-stu-id="edd70-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="edd70-149">Federação e Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="edd70-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="edd70-150">A auditoria</span><span class="sxs-lookup"><span data-stu-id="edd70-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="edd70-151">Consulte também</span><span class="sxs-lookup"><span data-stu-id="edd70-151">See Also</span></span>  
 [<span data-ttu-id="edd70-152">Orientações de segurança e práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="edd70-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [<span data-ttu-id="edd70-153">Modelo de segurança para o Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="edd70-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)