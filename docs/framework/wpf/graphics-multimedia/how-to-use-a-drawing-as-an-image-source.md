---
title: Como usar um desenho como uma origem de imagem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e0fe8f7d3633143348693c95d92dd2715bd0442
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>Como usar um desenho como uma origem de imagem
Este exemplo mostra como usar um <xref:System.Windows.Media.Drawing> como o <xref:System.Windows.Controls.Image.Source%2A> para um <xref:System.Windows.Controls.Image> controle. Para exibir um <xref:System.Windows.Media.Drawing> com um <xref:System.Windows.Controls.Image> controlar, use um <xref:System.Windows.Media.DrawingImage> como o <xref:System.Windows.Controls.Image> do controle <xref:System.Windows.Controls.Image.Source%2A> e defina o <xref:System.Windows.Media.DrawingImage> do objeto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> propriedade ao desenho que você deseja exibir.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa uma <xref:System.Windows.Media.DrawingImage> e um <xref:System.Windows.Controls.Image> controle para exibir um <xref:System.Windows.Media.GeometryDrawing>. Este exemplo gera a seguinte saída:  
  
 ![Um GeometryDrawing de duas elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Uma DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Desenhar uma imagem usando ImageDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [Visão geral dos objetos de desenho](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Visão geral de objetos congeláveis](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Atributo PresentationOptions:Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
