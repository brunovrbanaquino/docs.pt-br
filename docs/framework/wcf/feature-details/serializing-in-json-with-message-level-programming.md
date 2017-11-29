---
title: "Serialização em Json com programação de nível de mensagem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 33337f75032031ccfc81173f188f4ff7695ffd40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="bd697-102">Serialização em Json com programação de nível de mensagem</span><span class="sxs-lookup"><span data-stu-id="bd697-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="bd697-103">O WCF dá suporte a serialização de dados no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="bd697-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="bd697-104">Este tópico descreve como saber WCF para serializar seus tipos usando a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bd697-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="bd697-105">Programação de mensagem tipada</span><span class="sxs-lookup"><span data-stu-id="bd697-105">Typed Message Programming</span></span>  
 <span data-ttu-id="bd697-106">O <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> é usado quando o <xref:System.ServiceModel.Web.WebGetAttribute> ou <xref:System.ServiceModel.Web.WebInvokeAttribute> é aplicado a uma operação de serviço.</span><span class="sxs-lookup"><span data-stu-id="bd697-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="bd697-107">Ambos os atributos permitem que você especifique o `RequestFormat` e `ResponseFormat`.</span><span class="sxs-lookup"><span data-stu-id="bd697-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="bd697-108">Para usar JSON para solicitações e respostas, defina ambos como `WebMessageFormat.Json`.</span><span class="sxs-lookup"><span data-stu-id="bd697-108">To use JSON for requests and responses set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="bd697-109">Para usar JSON, você deve usar o <xref:System.ServiceModel.WebHttpBinding> que configura automaticamente o <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="bd697-109">In order to use JSON you must use the <xref:System.ServiceModel.WebHttpBinding> which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="bd697-110">Para obter mais informações sobre a serialização WCF, consulte: [serialização e desserialização](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [serialização no Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd697-110">For more information about WCF serialization, see: [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialization in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span></span> <span data-ttu-id="bd697-111">Para obter mais informações sobre JSON e WCF, consulte [uma introdução aos serviços RESTfull com WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [habilitados por JSON criando serviços WCF com o .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), e [visão geral do REST no WCF](http://msdn.microsoft.com/netframework/dd547388).</span><span class="sxs-lookup"><span data-stu-id="bd697-111">For more information about JSON and WCF see [An Introduction to RESTfull Services with WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Creating JSON-enabled WCF Services in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), and [Overview of REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd697-112">Usar JSON requer o uso de <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior> que não oferecem suporte a comunicação de SOAP.</span><span class="sxs-lookup"><span data-stu-id="bd697-112">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="bd697-113">Serviços que se comunicam com o <xref:System.ServiceModel.WebHttpBinding> não oferecem suporte a expondo os metadados de serviço e você não poderá usar a funcionalidade Adicionar referência de serviço do Visual Studio ou a ferramenta de linha de comando svcutil para gerar um proxy do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="bd697-113">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="bd697-114">Para obter mais informações, como você pode chamar programaticamente os serviços que usam <xref:System.ServiceModel.WebHttpBinding>, consulte [como consumir serviços REST com WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd697-114">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="bd697-115">Programação sem tipo de mensagem</span><span class="sxs-lookup"><span data-stu-id="bd697-115">Untyped Message Programming</span></span>  
 <span data-ttu-id="bd697-116">Ao trabalhar diretamente com objetos de mensagem não tipados, você deve definir explicitamente as propriedades na mensagem não tipada para serializá-lo como JSON.</span><span class="sxs-lookup"><span data-stu-id="bd697-116">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="bd697-117">O trecho de código a seguir mostra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="bd697-117">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd697-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bd697-118">See Also</span></span>  
 [<span data-ttu-id="bd697-119">Integração de AJAX e suporte a JSON</span><span class="sxs-lookup"><span data-stu-id="bd697-119">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="bd697-120">Serialização JSON autônoma</span><span class="sxs-lookup"><span data-stu-id="bd697-120">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="bd697-121">Serialização JSON</span><span class="sxs-lookup"><span data-stu-id="bd697-121">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)