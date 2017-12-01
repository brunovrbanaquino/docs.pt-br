---
title: Como associar dados aos elementos do Windows Presentation Foundation (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0f0ff1bed93d534dea3a407f4923e13856d761d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a><span data-ttu-id="79491-102">Como associar dados aos elementos do Windows Presentation Foundation (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="79491-102">How to: Bind Data to Windows Presentation Foundation Elements (WCF Data Services)</span></span>
<span data-ttu-id="79491-103">Com [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], você pode associar os elementos do Windows Presentation Foundation (WPF), como um <xref:System.Windows.Controls.ListBox>' ou <xref:System.Windows.Controls.ComboBox> para uma instância de <xref:System.Data.Services.Client.DataServiceCollection%601>, que trata os eventos gerados pelos controles para manter o <xref:System.Data.Services.Client.DataServiceContext> sincronizadas com as alterações feitas nos dados em controles.</span><span class="sxs-lookup"><span data-stu-id="79491-103">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can bind Windows Presentation Foundation (WPF) elements such as a <xref:System.Windows.Controls.ListBox>``or <xref:System.Windows.Controls.ComboBox> to an instance of <xref:System.Data.Services.Client.DataServiceCollection%601>, which handles the events raised by the controls to keep the <xref:System.Data.Services.Client.DataServiceContext> synchronized with changes made to data in the controls.</span></span> <span data-ttu-id="79491-104">Para obter mais informações, consulte [vinculação de dados a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79491-104">For more information, see [Binding Data to Controls](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="79491-105">O exemplo deste tópico usa o serviço de dados de exemplo Northwind e as classes de serviço de dados do cliente geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="79491-105">The example in this topic uses the Northwind sample data service and autogenerated client data service classes.</span></span> <span data-ttu-id="79491-106">Esse serviço e as classes de dados do cliente são criadas quando você concluir o [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79491-106">This service and the client data classes are created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79491-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="79491-107">Example</span></span>  
 <span data-ttu-id="79491-108">O exemplo a seguir é da página code-behind de uma página da linguagem XAML que define a janela `SalesOrders` no WPF.</span><span class="sxs-lookup"><span data-stu-id="79491-108">The following example is from the code-behind page for an Extensible Application Markup Language (XAML) page that defines the `SalesOrders` window in WPF.</span></span> <span data-ttu-id="79491-109">Quando a janela é carregada, um <xref:System.Data.Services.Client.DataServiceCollection%601> é criado com base no resultado de uma consulta que retorna clientes, filtrados por país.</span><span class="sxs-lookup"><span data-stu-id="79491-109">When the window is loaded, a <xref:System.Data.Services.Client.DataServiceCollection%601> is created based on the result of a query that returns customers, filtered by country.</span></span> <span data-ttu-id="79491-110">Todas as páginas deste resultado paginado são carregadas, juntamente com os pedidos relacionados, e associadas à propriedade <xref:System.Windows.FrameworkElement.DataContext%2A> do <xref:System.Windows.Controls.StackPanel> que é o controle do layout raiz da janela WPF.</span><span class="sxs-lookup"><span data-stu-id="79491-110">All of the pages of this paged result are loaded, along with the related orders, and are bound to the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.StackPanel> that is the root layout control for the WPF window.</span></span> <span data-ttu-id="79491-111">Para obter mais informações, consulte [carregar conteúdo adiada](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79491-111">For more information, see [Loading Deferred Content](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).</span></span>  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a><span data-ttu-id="79491-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="79491-112">Example</span></span>  
 <span data-ttu-id="79491-113">O XAML a seguir define a janela `SalesOrders` no WPF do exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="79491-113">The following XAML defines the `SalesOrders` window in WPF for the previous example.</span></span>  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a><span data-ttu-id="79491-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="79491-114">Example</span></span>  
 <span data-ttu-id="79491-115">O exemplo a seguir é da página code-behind de uma página da linguagem XAML que define a janela `SalesOrders` no WPF.</span><span class="sxs-lookup"><span data-stu-id="79491-115">The following example is from the code-behind page for an Extensible Application Markup Language (XAML) page that defines the `SalesOrders` window in WPF.</span></span> <span data-ttu-id="79491-116">Quando a janela é carregada, um <xref:System.Data.Services.Client.DataServiceCollection%601> é criado com base no resultado de uma consulta que retorna clientes com objetos relacionados, filtrados por país.</span><span class="sxs-lookup"><span data-stu-id="79491-116">When the window is loaded, a <xref:System.Data.Services.Client.DataServiceCollection%601> is created based on the result of a query that returns customers with related objects, filtered by country.</span></span> <span data-ttu-id="79491-117">Esse resultado é associado à propriedade <xref:System.Windows.FrameworkElement.DataContext%2A> do <xref:System.Windows.Controls.StackPanel> que é o controle de layout raiz da janela WPF.</span><span class="sxs-lookup"><span data-stu-id="79491-117">This result is bound to the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.StackPanel> that is the root layout control for the WPF window.</span></span>  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a><span data-ttu-id="79491-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="79491-118">Example</span></span>  
 <span data-ttu-id="79491-119">O XAML a seguir define a janela `SalesOrders` no WPF do exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="79491-119">The following XAML defines the `SalesOrders` window in WPF for the previous example.</span></span>  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]