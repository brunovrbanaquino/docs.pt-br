---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47a7d0984a5fafa7f03a589570e2a1aa2546dd8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceactivationsgt"></a>&lt;serviceActivations&gt;
Um elemento de configuração que permite adicionar configurações que definem as configurações de ativação de serviços virtuais que são mapeados para seus [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tipos de serviço. Isso torna possível para ativar serviços hospedados no WAS / IIS sem um arquivo. svc.  
  
 \<sistema. ServiceModel >  
\<serviceHostingEnvironment >  
\<serviceActivations >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
 nenhuma.  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Adiciona um elemento de configuração que especifica a ativação de um aplicativo de serviço.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Define o tipo que o ambiente de hospedagem de serviço instancia para um transporte particular.|  
  
## <a name="remarks"></a>Comentários  
 O exemplo a seguir mostra como definir as configurações de ativação em seu arquivo Web. config.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 Usando esta configuração, você pode ativar o GreetingService sem usar um arquivo. svc.  
  
 Observe que `<serviceHostingEnvironment>` é uma configuração de nível de aplicativo. Você precisa colocar a `web.config` que contém a configuração abaixo da raiz do aplicativo virtual. Além disso, `serviceHostingEnvironment` uma seção herdáveis machinetoApplication. Se você registrar um único serviço na raiz da máquina, cada serviço no aplicativo herdará esse serviço.  
  
 Ativação baseada em configuração oferece suporte à ativação pelo protocolo http e não http. Ele requer extensões no relatativeAddress ou seja,. svc,. xoml ou .xamlx. Você pode mapear suas próprias extensões para o buildProviders sabe, que, em seguida, permite que você ative o serviço em qualquer extensão. Em conflito, a `<serviceActivations>` seção substitui registros. svc.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
