---
title: Como compartilhar propriedades de dimensionamento entre grades
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
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8f80d93f9625ff962a3e3fab1f6647678ecf32f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Como compartilhar propriedades de dimensionamento entre grades
Este exemplo mostra como compartilhar os dados de dimensionamento de colunas e linhas entre <xref:System.Windows.Controls.Grid> elementos para manter um dimensionamento consistente.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir apresenta dois <xref:System.Windows.Controls.Grid> elementos como elementos filho de um pai <xref:System.Windows.Controls.DockPanel>. O <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> anexado a propriedade de <xref:System.Windows.Controls.Grid> é definido no pai <xref:System.Windows.Controls.DockPanel>.  
  
 O exemplo manipula o valor da propriedade usando dois <xref:System.Windows.Controls.Button> elementos; cada elemento representa um dos valores de propriedade booliano. Quando o <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> o valor da propriedade é definido como `true`, cada membro de coluna ou linha de uma <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> compartilha informações de dimensionamento, independentemente do conteúdo de uma linha ou coluna.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 O seguinte exemplo de code-behind trata os métodos que o botão <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gera eventos. O exemplo grava os resultados dessas chamadas de método para <xref:System.Windows.Controls.TextBlock> elementos relacionados ao uso obtém métodos para os novos valores de propriedade como cadeias de caracteres de saída.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [Visão geral de painéis](../../../../docs/framework/wpf/controls/panels-overview.md)
