---
title: "multiplicidade da extremidade da associação"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3d6071b2dfab4a1f057c9e04b84e1163fb0a53c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="e299b-102">multiplicidade da extremidade da associação</span><span class="sxs-lookup"><span data-stu-id="e299b-102">association end multiplicity</span></span>
<span data-ttu-id="e299b-103">*Multiplicidade da extremidade da associação* define o número de [tipo de entidade](../../../../docs/framework/data/adonet/entity-type.md) instâncias que podem ser de uma extremidade de um [associação](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="e299b-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="e299b-104">Uma multiplicidade do final da associação pode ter um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e299b-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="e299b-105">um (1): Indica que exatamente uma instância do tipo de entidade existe no final da associação.</span><span class="sxs-lookup"><span data-stu-id="e299b-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="e299b-106">zero ou um 0..1 (:) Indica que essa instâncias de zero ou mais tipos de entidade existem no final da associação.</span><span class="sxs-lookup"><span data-stu-id="e299b-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="e299b-107">muitos (*): Indica que zero, uma, ou mais instâncias do tipo de entidade existem no final da associação.</span><span class="sxs-lookup"><span data-stu-id="e299b-107">many (*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="e299b-108">Uma associação é caracterizada frequentemente pelos multiplicities final da associação.</span><span class="sxs-lookup"><span data-stu-id="e299b-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="e299b-109">Por exemplo, se as extremidades de uma associação têm um multiplicities (1) e muitos (*), a associação é chamada de um para muitos associação.</span><span class="sxs-lookup"><span data-stu-id="e299b-109">For example, if the ends of an association have multiplicities one (1) and many (*), the association is called a one-to-many association.</span></span> <span data-ttu-id="e299b-110">No exemplo abaixo, a associação de `PublishedBy` é um para muitos associação (um editor publica muitos livros e um livro é publicado por um editor).</span><span class="sxs-lookup"><span data-stu-id="e299b-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="e299b-111">A associação de `WrittenBy` é um muitos para muitos associação (um livro pode ter vários autores e um autor pode escrever diversos livros).</span><span class="sxs-lookup"><span data-stu-id="e299b-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e299b-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e299b-112">Example</span></span>  
 <span data-ttu-id="e299b-113">O diagrama a seguir mostra um modelo conceitual com duas associações: `PublishedBy` e `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="e299b-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="e299b-114">Terminar a associação para associação de `PublishedBy` são os tipos de entidade de `Book` e de `Publisher` .</span><span class="sxs-lookup"><span data-stu-id="e299b-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="e299b-115">A multiplicidade do final de `Publisher` é um (1) e a multiplicidade do final de `Book` é muitas (*).</span><span class="sxs-lookup"><span data-stu-id="e299b-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*).</span></span>  
  
 <span data-ttu-id="e299b-116">![Modelo de exemplo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="e299b-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="e299b-117">O ADO.NET Entity Framework usa uma linguagem específica de domínio (DSL) chamada linguagem de definição de esquema conceitual ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir modelos conceituais.</span><span class="sxs-lookup"><span data-stu-id="e299b-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e299b-118">CSDL seguir define a associação de `PublishedBy` mostrada no diagrama anterior:</span><span class="sxs-lookup"><span data-stu-id="e299b-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e299b-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e299b-119">See Also</span></span>  
 [<span data-ttu-id="e299b-120">Conceitos chave do modelo de dados de entidade</span><span class="sxs-lookup"><span data-stu-id="e299b-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="e299b-121">Modelo de dados de entidade</span><span class="sxs-lookup"><span data-stu-id="e299b-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)