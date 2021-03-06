---
title: Diretiva x:Members
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e76f539e713f3d21751de18c86cc2dcebf99f570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="xmembers-directive"></a>Diretiva x:Members
Contém um conjunto de membros que estão definidos na marcação, que se aplicam à classe: x do elemento pai.  
  
## <a name="xaml-attribute-usage"></a>Uso do Atributo XAML  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`className`|Nome da classe de backup ou classe parcial para a produção de XAML. Consulte Observações.|  
|`oneOrMoreMembers`|Um ou mais elementos de objeto que representa as definições de membro. Normalmente, esses são `x:Property` elementos de objeto. Consulte Observações.|  
  
## <a name="remarks"></a>Comentários  
 Na implementação de serviços XAML do .NET Framework, não há backup classe ou implementação subjacente do membro para `x:Members`. `x:Members`é um membro XAML especial que pode existir como um membro em qualquer tipo. Em um fluxo do nó XAML, `x:Members` é representado como um membro chamado `Members`, do namespace XAML de linguagem XAML. O membro `Members` contém uma lista somente leitura genérica de `Member` objetos. Na marcação típica, os membros individuais são especificados como `x:Property` elementos de propriedade. `x:Property`é um tipo mais preciso especificamente para propriedades de tipos e pode ser atribuído a `x:Member`. Para obter mais informações, consulte [diretiva X:property](../../../docs/framework/xaml-services/x-property-directive.md).  
  
 Para dar suporte a um uso prático de `x:Members` como um meio para especificar definições de membro na marcação, os membros devem ser associados uma classe que pode ser modificada. O modelo desejado é que `x:Members` existe como um membro de um tipo que especifica um `x:Class`. No entanto, o mecanismo para a associação de tipos e membros ou para a produção de definições de membro dinâmico não tem suporte no nível de serviços XAML do .NET Framework. Isso é da esquerda para estruturas individuais que têm modelos de aplicativos que dão suporte a definições de membro de XAML. Normalmente, as ações de compilação MSBUILD que a compilação de marcação XAML e um integração-lo com code-behind ou produzir somente de XAML assemblies são necessários para dar suporte a esse recurso.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>x: membros para Windows Workflow Foundation  
 Para Windows Workflow Foundation, `x:Members` contém os membros de uma atividade personalizada composta inteiramente em XAML ou XAML – definido membros dinâmicos para um designer de atividade com code-behind. `x:Class`também deve ser especificado no elemento raiz da produção XAML. Isso não é um requisito no nível de serviços XAML do .NET Framework, mas se torna um requisito quando a produção de XAML é carregada pelas ações de compilação do MSBUILD que dão suporte a atividades personalizadas e XAML do Windows Workflow Foundation em geral. `x:Members`deve ser o primeiro elemento filho na marcação do elemento de objeto que declara o `x:Class`.
