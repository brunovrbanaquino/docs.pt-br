---
title: Como criar uma forma usando um PathGeometry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 784a8df792ca4dc05e36f5b7e9ec93b02e0e639f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Como criar uma forma usando um PathGeometry
Este exemplo mostra como criar uma forma usando o <xref:System.Windows.Media.PathGeometry> classe. <xref:System.Windows.Media.PathGeometry>objetos são compostos de um ou mais <xref:System.Windows.Media.PathFigure> objetos; cada <xref:System.Windows.Media.PathFigure> representa uma forma ou diferente "Figura". Cada <xref:System.Windows.Media.PathFigure> é composto de um ou mais <xref:System.Windows.Media.PathSegment> objetos, cada um representando uma parte conectada da figura ou forma. Tipos de segmento incluem <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, e <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa um <xref:System.Windows.Media.PathGeometry> para criar um triângulo. O <xref:System.Windows.Media.PathGeometry> é exibido usando um <xref:System.Windows.Shapes.Path> elemento.  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 A ilustração a seguir mostra a forma criada no exemplo anterior.  
  
 ![Um PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Um triângulo criado com um PathGeometry  
  
 O exemplo anterior mostrou como criar uma forma relativamente simples: um triângulo. Um <xref:System.Windows.Media.PathGeometry> também pode ser usado para criar formas mais complexas, incluindo arcos e curvas. Para obter exemplos, veja [Criar um arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Criar uma curva de Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md) e [Criar uma curva de Bézier quadrática](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Este exemplo faz parte de um exemplo maior; para ver o exemplo completo, confira o [Exemplo de geometrias](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Visão geral de geometria](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Exemplo de geometrias](http://go.microsoft.com/fwlink/?LinkID=159989)
