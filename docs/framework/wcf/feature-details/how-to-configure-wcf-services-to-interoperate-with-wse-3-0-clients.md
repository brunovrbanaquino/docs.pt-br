---
title: "Como configurar serviços do WCF para interoperar com clientes WSE 3.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 099fb059e375e0e76cffb5389191011d866b2d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="88653-102">Como configurar serviços do WCF para interoperar com clientes WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="88653-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="88653-103">os serviços são compatíveis com o nível de transmissão com 3.0 de aprimoramentos de serviços Web para clientes do Microsoft .NET (WSE) quando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviços estão configurados para usar a versão de agosto de 2004 da especificação WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="88653-103"> services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="88653-104">Para habilitar um serviço WCF interoperar com clientes WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="88653-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1.  <span data-ttu-id="88653-105">Definir uma associação personalizada para o [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span><span class="sxs-lookup"><span data-stu-id="88653-105">Define a custom binding for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
     <span data-ttu-id="88653-106">Para especificar que a versão de agosto de 2004 da especificação WS-Addressing é usada para codificação de mensagens, uma associação personalizada deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="88653-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1.  <span data-ttu-id="88653-107">Adicionar uma criança [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) para o [ \<associações >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) do arquivo de configuração do serviço.</span><span class="sxs-lookup"><span data-stu-id="88653-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2.  <span data-ttu-id="88653-108">Especifique um nome para a associação, adicionando um [ \<associação >](../../../../docs/framework/misc/binding.md) para o [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) e configuração de `name` atributo.</span><span class="sxs-lookup"><span data-stu-id="88653-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3.  <span data-ttu-id="88653-109">Especifique um modo de autenticação e a versão das especificações do WS-Security que são usadas para proteger as mensagens que são compatíveis com WSE 3.0, adicionando um filho [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) para o [ \<associação >](../../../../docs/framework/misc/binding.md).</span><span class="sxs-lookup"><span data-stu-id="88653-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="88653-110">Para definir o modo de autenticação, defina o `authenicationMode` atributo o [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="88653-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="88653-111">Um modo de autenticação é aproximadamente equivalente a uma asserção de segurança completa WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="88653-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="88653-112">A tabela a seguir mapeia os modos de autenticação na [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para declarações de segurança completa de WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="88653-112">The following table maps authentication modes in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="88653-113">Modo de autenticação do WCF</span><span class="sxs-lookup"><span data-stu-id="88653-113">WCF Authentication Mode</span></span>|<span data-ttu-id="88653-114">Asserção de segurança completa de WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="88653-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="88653-115">\*Uma das principais diferenças entre o `mutualCertificate10Security` e `mutualCertificate11Security` asserções de segurança completa é a versão da especificação WS-Security WSE usa para proteger as mensagens SOAP.</span><span class="sxs-lookup"><span data-stu-id="88653-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="88653-116">Para `mutualCertificate10Security`, WS-Security 1.0 for usada, enquanto 1.1 do WS-Security é usada para `mutualCertificate11Security`.</span><span class="sxs-lookup"><span data-stu-id="88653-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="88653-117">Para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], a versão da especificação WS-Security é especificada no `messageSecurityVersion` atributo o [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="88653-117">For [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="88653-118">Para definir a versão da especificação WS-Security que é usada para proteger mensagens SOAP, defina o `messageSecurityVersion` atributo o [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="88653-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="88653-119">Para interoperar com WSE 3.0, defina o valor da `messageSecurityVersion` atributo <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span><span class="sxs-lookup"><span data-stu-id="88653-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4.  <span data-ttu-id="88653-120">Especificar que a versão de agosto de 2004 da especificação WS-Addressing é usada pelo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adicionando um [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) e defina o `messageVersion` para seu valor como <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="88653-120">Specify that the August 2004 version of the WS-Addressing specification is used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="88653-121">Quando você estiver usando SOAP 1.2, defina o `messageVersion` atributo <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="88653-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2.  <span data-ttu-id="88653-122">Especifique que o serviço usa a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="88653-122">Specify that the service uses the custom binding.</span></span>  
  
    1.  <span data-ttu-id="88653-123">Definir o `binding` atributo do [ \<ponto de extremidade >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento `customBinding`.</span><span class="sxs-lookup"><span data-stu-id="88653-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2.  <span data-ttu-id="88653-124">Definir o `bindingConfiguration` atributo do [ \<ponto de extremidade >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento para o valor especificado no `name` atributo do [ \<associação >](../../../../docs/framework/misc/binding.md) para personalizado associação.</span><span class="sxs-lookup"><span data-stu-id="88653-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88653-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="88653-125">Example</span></span>  
 <span data-ttu-id="88653-126">O exemplo de código a seguir especifica que o `Service.HelloWorldService` usa uma associação personalizada para interoperar com clientes WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="88653-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="88653-127">A associação personalizada Especifica a versão de agosto de 2004 do WS-Addressing e o conjunto de 1.1 do WS-Security de especificações são usados para codificar as mensagens trocadas.</span><span class="sxs-lookup"><span data-stu-id="88653-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="88653-128">As mensagens são protegidas usando o <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="88653-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88653-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="88653-129">See Also</span></span>  
 [<span data-ttu-id="88653-130">Como: personalizar uma associação fornecida pelo sistema</span><span class="sxs-lookup"><span data-stu-id="88653-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)