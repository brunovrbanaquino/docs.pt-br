---
title: "Como usar um ResourceDictionary para gerenciar recursos da cadeia de caracteres localizáveis"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38cfd687eadf31cc94dfdd2cbbf082bf80424cba
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="55c8e-102">Como usar um ResourceDictionary para gerenciar recursos da cadeia de caracteres localizáveis</span><span class="sxs-lookup"><span data-stu-id="55c8e-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="55c8e-103">Este exemplo mostra como usar um <xref:System.Windows.ResourceDictionary> para recursos de cadeia de caracteres localizáveis do pacote para [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplicativos.</span><span class="sxs-lookup"><span data-stu-id="55c8e-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="55c8e-104">Para usar um ResourceDictionary para gerenciar recursos de cadeia de caracteres localizáveis</span><span class="sxs-lookup"><span data-stu-id="55c8e-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="55c8e-105">Criar um <xref:System.Windows.ResourceDictionary> que contém as cadeias de caracteres que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="55c8e-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="55c8e-106">O código a seguir mostra um exemplo.</span><span class="sxs-lookup"><span data-stu-id="55c8e-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="55c8e-107">Esse código define um recurso de cadeia de caracteres, `localizedMessage`, do tipo <xref:System.String>, do <xref:System> namespace em mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="55c8e-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="55c8e-108">Adicionar o <xref:System.Windows.ResourceDictionary> para seu aplicativo, usando o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="55c8e-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="55c8e-109">Usar o recurso de cadeia de caracteres de marcação, usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] como a seguir.</span><span class="sxs-lookup"><span data-stu-id="55c8e-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="55c8e-110">Use o recurso de cadeia de caracteres de code-behind, usando código semelhante ao seguinte.</span><span class="sxs-lookup"><span data-stu-id="55c8e-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="55c8e-111">Localize o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="55c8e-111">Localize the application.</span></span> <span data-ttu-id="55c8e-112">Para obter mais informações, consulte [localizar um aplicativo](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="55c8e-112">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>