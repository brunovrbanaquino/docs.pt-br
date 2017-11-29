---
title: "Extensão de marcação StaticResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 821cd152ccb7a02dda5338d6a3ec44d6625c0097
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="staticresource-markup-extension"></a><span data-ttu-id="d741b-102">Extensão de marcação StaticResource</span><span class="sxs-lookup"><span data-stu-id="d741b-102">StaticResource Markup Extension</span></span>
<span data-ttu-id="d741b-103">Fornece um valor para qualquer atributo de propriedade [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pesquisando uma referência a um recurso já definido.</span><span class="sxs-lookup"><span data-stu-id="d741b-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="d741b-104">O comportamento de pesquisa para esse recurso é análogo à pesquisa de tempo de carga, que procurará os recursos que foram previamente carregados da marcação da página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atual, bem como outras fontes de aplicativo, e gerará esse valor de recurso como o valor da propriedade nos objetos de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d741b-104">Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page as well as other application sources, and will generate that resource value as the property value in the run-time objects.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d741b-105">Uso do Atributo XAML</span><span class="sxs-lookup"><span data-stu-id="d741b-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="d741b-106">Uso de elemento Object do XAML</span><span class="sxs-lookup"><span data-stu-id="d741b-106">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d741b-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="d741b-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="d741b-108">A chave para o recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="d741b-108">The key for the requested resource.</span></span> <span data-ttu-id="d741b-109">Essa chave foi inicialmente atribuída pelo [diretiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) se um recurso foi criado na marcação ou foi fornecido como o `key` parâmetro ao chamar <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> se o recurso foi criado em código.</span><span class="sxs-lookup"><span data-stu-id="d741b-109">This key was initially assigned by the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d741b-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="d741b-110">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d741b-111">Um `StaticResource` não deve tentar fazer uma referência direta a um recurso que está definido lexicalmente mais à frente no arquivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d741b-111">A `StaticResource` must not attempt to make a forward reference to a resource that is defined lexically further within the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="d741b-112">Não há suporte para a tentativa de fazer isso, e mesmo se tal referência não falhar, tentar a referência provocará uma penalidade de desempenho de tempo de carga quando as tabelas internas de hash que representa um <xref:System.Windows.ResourceDictionary> serão pesquisados.</span><span class="sxs-lookup"><span data-stu-id="d741b-112">Attempting to do so is not supported, and even if such a reference does not fail, attempting the forward reference will incur a load time performance penalty when the internal hash tables representing a <xref:System.Windows.ResourceDictionary> are searched.</span></span> <span data-ttu-id="d741b-113">Para obter melhores resultados, ajuste a composição de seus dicionários de recursos de forma a evitar referências adiante.</span><span class="sxs-lookup"><span data-stu-id="d741b-113">For best results, adjust the composition of your resource dictionaries such that forward references can be avoided.</span></span> <span data-ttu-id="d741b-114">Se você não puder evitar uma referência à frente, use [Extensão de marcação DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d741b-114">If you cannot avoid a forward reference, use [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) instead.</span></span>  
  
 <span data-ttu-id="d741b-115">Especificado <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> devem corresponder a um recurso existente, identificada com um [diretiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) em algum nível na sua página, aplicativo, os temas de controle disponíveis e recursos externos ou recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="d741b-115">The specified <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> should correspond to an existing resource, identified with an [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources.</span></span> <span data-ttu-id="d741b-116">A pesquisa de recursos ocorre nessa ordem.</span><span class="sxs-lookup"><span data-stu-id="d741b-116">The resource lookup occurs in that order.</span></span> <span data-ttu-id="d741b-117">Para obter mais informações sobre o comportamento de pesquisa de recursos para recursos estáticos e dinâmicos, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="d741b-117">For more information about resource lookup behavior for static and dynamic resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="d741b-118">Uma tecla de recurso pode ser qualquer cadeia de caracteres definida na [Gramática XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="d741b-118">A resource key can be any string defined in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="d741b-119">Uma chave de recurso também pode ser outros tipos de objeto, como um <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="d741b-119">A resource key can also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="d741b-120">Um <xref:System.Type> chave é fundamental para como os controles podem ser estilizados por temas, por meio de uma chave de estilo implícita.</span><span class="sxs-lookup"><span data-stu-id="d741b-120">A <xref:System.Type> key is fundamental to how controls can be styled by themes, through an implicit style key.</span></span> <span data-ttu-id="d741b-121">Para obter mais informações, consulte [Visão geral da criação de controle](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d741b-121">For more information, see [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="d741b-122">O meio declarativo alternativo de referenciar um recurso é como uma [Extensão de Marcação DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d741b-122">The alternative declarative means of referencing a resource is as a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="d741b-123">A sintaxe de atributo é a sintaxe mais comum usada com essa extensão de marcação.</span><span class="sxs-lookup"><span data-stu-id="d741b-123">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="d741b-124">O token da cadeia de caracteres fornecido após a cadeia de caracteres identificadora `StaticResource` é atribuído como o valor <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> da classe de extensão subjacente <xref:System.Windows.StaticResourceExtension>.</span><span class="sxs-lookup"><span data-stu-id="d741b-124">The string token provided after the `StaticResource` identifier string is assigned as the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.StaticResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="d741b-125">`StaticResource` pode ser usado na sintaxe de elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="d741b-125">`StaticResource` can be used in object element syntax.</span></span> <span data-ttu-id="d741b-126">Nesse caso, especificando o valor de <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> propriedade é necessária.</span><span class="sxs-lookup"><span data-stu-id="d741b-126">In this case, specifying the value of the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="d741b-127">`StaticResource` também pode ser usado em um atributo detalhado que especifica a propriedade <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> como sendo o par propriedade=valor:</span><span class="sxs-lookup"><span data-stu-id="d741b-127">`StaticResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="d741b-128">O uso detalhado geralmente é útil para as extensões que têm mais de uma propriedade configurável, ou caso algumas propriedades sejam opcionais.</span><span class="sxs-lookup"><span data-stu-id="d741b-128">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="d741b-129">Como `StaticResource` tem apenas uma propriedade configurável, que é necessária, esse uso detalhado não é típico.</span><span class="sxs-lookup"><span data-stu-id="d741b-129">Because `StaticResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="d741b-130">No [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementação do processador, o tratamento para esta extensão de marcação é definida pelo <xref:System.Windows.StaticResourceExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="d741b-130">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.StaticResourceExtension> class.</span></span>  
  
 <span data-ttu-id="d741b-131">`StaticResource` é uma extensão da marcação.</span><span class="sxs-lookup"><span data-stu-id="d741b-131">`StaticResource` is a markup extension.</span></span> <span data-ttu-id="d741b-132">Extensões de marcação são tipicamente implementadas quando existe um requisito que permite que valores de atributo sejam diferentes de valores literais ou nomes de manipuladores, e o requisito é mais global do que simplesmente colocar conversores de tipo em certos tipos ou propriedades.</span><span class="sxs-lookup"><span data-stu-id="d741b-132">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="d741b-133">Todas as extensões de marcação em [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usam os caracteres { e } na sintaxe de atributo, que é a convenção pela qual um processador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconhece que uma extensão de marcação deve processar o atributo.</span><span class="sxs-lookup"><span data-stu-id="d741b-133">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="d741b-134">Para obter mais informações, consulte [Extensões de marcação e XAML do WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d741b-134">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d741b-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d741b-135">See Also</span></span>  
 [<span data-ttu-id="d741b-136">Estilo e modelagem</span><span class="sxs-lookup"><span data-stu-id="d741b-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d741b-137">Visão geral de XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d741b-137">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="d741b-138">Extensões de marcação e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="d741b-138">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="d741b-139">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="d741b-139">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="d741b-140">Recursos e código</span><span class="sxs-lookup"><span data-stu-id="d741b-140">Resources and Code</span></span>](../../../../docs/framework/wpf/advanced/resources-and-code.md)