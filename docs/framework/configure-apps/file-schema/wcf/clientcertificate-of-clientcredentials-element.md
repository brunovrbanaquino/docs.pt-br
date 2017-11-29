---
title: '&lt;clientCertificate&gt; de &lt;clientCredentials&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 961e745f15b4c7b7ae489a8b2b3128c1a64c6eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcertificategt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="a527f-102">&lt;clientCertificate&gt; de &lt;clientCredentials&gt; Element</span><span class="sxs-lookup"><span data-stu-id="a527f-102">&lt;clientCertificate&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="a527f-103">Define um certificado x. 509 usado para autenticar um cliente para um serviço.</span><span class="sxs-lookup"><span data-stu-id="a527f-103">Defines an X.509 certificate used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="a527f-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a527f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a527f-105">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="a527f-105">\<behaviors></span></span>  
<span data-ttu-id="a527f-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a527f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a527f-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="a527f-107">\<behavior></span></span>  
<span data-ttu-id="a527f-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="a527f-108">\<clientCredentials></span></span>  
<span data-ttu-id="a527f-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="a527f-109">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a527f-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a527f-110">Syntax</span></span>  
  
```xml  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a527f-111">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a527f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a527f-112">As seções a seguir descrevem os elementos pai de atributos e elementos filho</span><span class="sxs-lookup"><span data-stu-id="a527f-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a527f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a527f-113">Attributes</span></span>  
  
|<span data-ttu-id="a527f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a527f-114">Attribute</span></span>|<span data-ttu-id="a527f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="a527f-115">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="a527f-116">Uma cadeia de caracteres que contém o valor para pesquisar no repositório de certificados x. 509.</span><span class="sxs-lookup"><span data-stu-id="a527f-116">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a527f-117">O tipo contido no atributo deve satisfazer os requisitos do `X509FindType` valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="a527f-117">The type contained in the attribute must satisfy the requirements of the `X509FindType` attribute value.</span></span> <span data-ttu-id="a527f-118">O padrão é uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="a527f-118">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="a527f-119">Especifica o local do certificado x. 509 que o cliente usa para se autenticar para o serviço.</span><span class="sxs-lookup"><span data-stu-id="a527f-119">Specifies the location of the X.509 certificate that the client uses to authenticate itself to the service.</span></span> <span data-ttu-id="a527f-120">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a527f-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a527f-121">-LocalMachine: o repositório de certificados atribuído ao computador local.</span><span class="sxs-lookup"><span data-stu-id="a527f-121">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="a527f-122">-CurrentUser: o repositório de certificados atribuído ao usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a527f-122">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a527f-123">O padrão é LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="a527f-123">The default is LocalMachine.</span></span> <span data-ttu-id="a527f-124">Esse atributo é do tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="a527f-124">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|`storeName`|<span data-ttu-id="a527f-125">Especifica o nome do repositório de certificados x. 509 para pesquisar.</span><span class="sxs-lookup"><span data-stu-id="a527f-125">Specifies the name of the X.509 certificate store to search.</span></span> <span data-ttu-id="a527f-126">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a527f-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a527f-127">-Catálogo de endereços: O repositório de certificados para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="a527f-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a527f-128">-AuthRoot: Repositório de terceiros para autoridades de certificação (CAs) do certificado.</span><span class="sxs-lookup"><span data-stu-id="a527f-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="a527f-129">-CertificateAuthority: Repositório de certificados intermediários para autoridades de certificação (CAs).</span><span class="sxs-lookup"><span data-stu-id="a527f-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="a527f-130">-Proibido: Repositório de certificados revogados de certificados.</span><span class="sxs-lookup"><span data-stu-id="a527f-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a527f-131">-My: Repositório de certificados pessoais do certificado.</span><span class="sxs-lookup"><span data-stu-id="a527f-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a527f-132">-Raiz: O repositório de certificados raiz confiável para autoridades de certificação (CAs).</span><span class="sxs-lookup"><span data-stu-id="a527f-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="a527f-133">-TrustedPeople: Repositório de certificados pessoas confiáveis diretamente e recursos.</span><span class="sxs-lookup"><span data-stu-id="a527f-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="a527f-134">-TrustedPublisher: Repositório de certificados para editores diretamente confiáveis.</span><span class="sxs-lookup"><span data-stu-id="a527f-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="a527f-135">O padrão é meu.</span><span class="sxs-lookup"><span data-stu-id="a527f-135">The default is My.</span></span> <span data-ttu-id="a527f-136">Esse atributo é do tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span><span class="sxs-lookup"><span data-stu-id="a527f-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="a527f-137">X509FindType</span><span class="sxs-lookup"><span data-stu-id="a527f-137">X509FindType</span></span>|<span data-ttu-id="a527f-138">Define o tipo de pesquisa x. 509 a ser executado.</span><span class="sxs-lookup"><span data-stu-id="a527f-138">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="a527f-139">O tipo contido o `findValue` atributo deve satisfazer os requisitos desse atributo.</span><span class="sxs-lookup"><span data-stu-id="a527f-139">The type contained in the `findValue` attribute must satisfy the requirements of this attribute.</span></span> <span data-ttu-id="a527f-140">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a527f-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a527f-141">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="a527f-141">-   FindByThumbPrint</span></span><br /><span data-ttu-id="a527f-142">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="a527f-142">-   FindBySubjectName</span></span><br /><span data-ttu-id="a527f-143">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a527f-143">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a527f-144">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a527f-144">-   FindByIssuerName</span></span><br /><span data-ttu-id="a527f-145">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a527f-145">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a527f-146">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="a527f-146">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a527f-147">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a527f-147">-   FindByTimeValid</span></span><br /><span data-ttu-id="a527f-148">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a527f-148">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a527f-149">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="a527f-149">-   FindByTemplateName</span></span><br /><span data-ttu-id="a527f-150">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a527f-150">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a527f-151">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="a527f-151">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a527f-152">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="a527f-152">-   FindByExtension</span></span><br /><span data-ttu-id="a527f-153">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="a527f-153">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a527f-154">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="a527f-154">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a527f-155">O valor padrão é FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="a527f-155">The default value is FindBySubjectDistinguishedName.</span></span> <span data-ttu-id="a527f-156">Esse atributo é do tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="a527f-156">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a527f-157">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a527f-157">Child Elements</span></span>  
 <span data-ttu-id="a527f-158">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a527f-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a527f-159">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a527f-159">Parent Elements</span></span>  
  
|<span data-ttu-id="a527f-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="a527f-160">Element</span></span>|<span data-ttu-id="a527f-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="a527f-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a527f-162">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="a527f-162">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="a527f-163">Especifica as credenciais usadas para autenticar o cliente para um serviço.</span><span class="sxs-lookup"><span data-stu-id="a527f-163">Specifies the credentials used to authenticate the client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a527f-164">Comentários</span><span class="sxs-lookup"><span data-stu-id="a527f-164">Remarks</span></span>  
 <span data-ttu-id="a527f-165">Este elemento de configuração especifica o certificado usado para autenticar o cliente com esse elemento.</span><span class="sxs-lookup"><span data-stu-id="a527f-165">This configuration element specifies the certificate used to authenticate the client with this element.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="a527f-166">[Como: especificar valores de credencial de cliente](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span><span class="sxs-lookup"><span data-stu-id="a527f-166"> [How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a527f-167">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a527f-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [<span data-ttu-id="a527f-168">Comportamentos de segurança</span><span class="sxs-lookup"><span data-stu-id="a527f-168">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="a527f-169">[How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md) (Como especificar valores de credenciais do cliente)</span><span class="sxs-lookup"><span data-stu-id="a527f-169">[How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)</span></span>  
 <span data-ttu-id="a527f-170">[Securing Clients](../../../../../docs/framework/wcf/securing-clients.md) (Protegendo clientes)</span><span class="sxs-lookup"><span data-stu-id="a527f-170">[Securing Clients](../../../../../docs/framework/wcf/securing-clients.md)</span></span>  
 [<span data-ttu-id="a527f-171">Trabalhar com certificados</span><span class="sxs-lookup"><span data-stu-id="a527f-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a527f-172">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="a527f-172">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)