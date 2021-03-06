---
title: Como criar um elemento de grade
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30fdd89a46e5d2027e9c525b0ca8cfcfb1d11ed2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-grid-element"></a>Como criar um elemento de grade
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como criar e usar uma instância de <xref:System.Windows.Controls.Grid> usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ou código. Este exemplo usa três <xref:System.Windows.Controls.ColumnDefinition> objetos e três <xref:System.Windows.Controls.RowDefinition> objetos criar uma grade que tem nove células, como em uma planilha. Cada célula contém um <xref:System.Windows.Controls.TextBlock> elemento que representa a data e a linha superior contém um <xref:System.Windows.Controls.TextBlock> com o <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propriedade aplicada. Para mostrar os limites de cada célula, o <xref:System.Windows.Controls.Grid.ShowGridLines%2A> propriedade está habilitada.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Controls.Grid>  
 [Visão geral de painéis](../../../../docs/framework/wpf/controls/panels-overview.md)
