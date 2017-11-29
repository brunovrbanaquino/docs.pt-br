---
title: '&lt;remover&gt; elemento para &lt;ouvintes&gt; para &lt;fonte&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6170c02296859d9c47e5288f287a4371d7cb0c56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="ad066-102">&lt;remover&gt; elemento para &lt;ouvintes&gt; para &lt;fonte&gt;</span><span class="sxs-lookup"><span data-stu-id="ad066-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="ad066-103">Remove um ouvinte da coleção `Listeners` de uma origem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ad066-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="ad066-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ad066-104">\<configuration></span></span>  
<span data-ttu-id="ad066-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="ad066-105">\<system.diagnostics></span></span>  
<span data-ttu-id="ad066-106">\<fontes ></span><span class="sxs-lookup"><span data-stu-id="ad066-106">\<sources></span></span>  
<span data-ttu-id="ad066-107">\<origem ></span><span class="sxs-lookup"><span data-stu-id="ad066-107">\<source></span></span>  
<span data-ttu-id="ad066-108">\<ouvintes ></span><span class="sxs-lookup"><span data-stu-id="ad066-108">\<listeners></span></span>  
<span data-ttu-id="ad066-109">\<Remover ></span><span class="sxs-lookup"><span data-stu-id="ad066-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad066-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ad066-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad066-111">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ad066-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ad066-112">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="ad066-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad066-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="ad066-113">Attributes</span></span>  
  
|<span data-ttu-id="ad066-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="ad066-114">Attribute</span></span>|<span data-ttu-id="ad066-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="ad066-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ad066-116">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ad066-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ad066-117">O nome do ouvinte a remova o `Listeners` coleção.</span><span class="sxs-lookup"><span data-stu-id="ad066-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad066-118">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ad066-118">Child Elements</span></span>  
 <span data-ttu-id="ad066-119">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ad066-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad066-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ad066-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ad066-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad066-121">Element</span></span>|<span data-ttu-id="ad066-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="ad066-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ad066-123">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad066-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ad066-124">Especifica os ouvintes de rastreamento que coletam, armazenam e roteiam mensagens e o nível em que uma opção de rastreamento é definida.</span><span class="sxs-lookup"><span data-stu-id="ad066-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="ad066-125">Contém as origens de rastreamento que iniciam as mensagens de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ad066-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="ad066-126">Especifica uma origem de rastreamento que inicia as mensagens de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ad066-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="ad066-127">Especifica os ouvintes que coletarem, armazenam e rotear mensagens.</span><span class="sxs-lookup"><span data-stu-id="ad066-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad066-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="ad066-128">Remarks</span></span>  
 <span data-ttu-id="ad066-129">O `<remove>` elemento remove um ouvinte especificado do `Listeners` coleção para uma origem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ad066-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="ad066-130">Você pode remover um elemento o `Listeners` coleção para uma origem de rastreamento programaticamente, chamando o <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> método no <xref:System.Diagnostics.TraceSource.Listeners%2A> propriedade do <xref:System.Diagnostics.TraceSource> instância.</span><span class="sxs-lookup"><span data-stu-id="ad066-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="ad066-131">Esse elemento pode ser usado no arquivo de configuração de máquina (Machine. config) e o arquivo de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad066-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad066-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ad066-132">Example</span></span>  
 <span data-ttu-id="ad066-133">O exemplo a seguir mostra como usar o `<remove>` elemento antes de usar o `<add>` elemento para adicionar o ouvinte `console` para o `Listeners` coleção para a origem de rastreamento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="ad066-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="ad066-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ad066-134">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="ad066-135">Esquema de configurações de rastreamento e depuração</span><span class="sxs-lookup"><span data-stu-id="ad066-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="ad066-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="ad066-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [<span data-ttu-id="ad066-137">Ouvintes de rastreamento</span><span class="sxs-lookup"><span data-stu-id="ad066-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)