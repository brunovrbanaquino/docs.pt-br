---
title: "Método IMetaDataEmit::MergeEnd"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.MergeEnd
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 57fbecd05f0eaee48e9dc8a599e3174ac97033f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="9cab7-102">Método IMetaDataEmit::MergeEnd</span><span class="sxs-lookup"><span data-stu-id="9cab7-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="9cab7-103">Todos os escopos de metadados especificados por uma ou mais chamadas anteriores para o escopo mesclagens em atual [Imetadataemit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="9cab7-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cab7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9cab7-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cab7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9cab7-105">Parameters</span></span>  
 <span data-ttu-id="9cab7-106">Esse método não usa nenhum parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9cab7-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cab7-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="9cab7-107">Remarks</span></span>  
 <span data-ttu-id="9cab7-108">Esta rotina aciona a mesclagem real de metadados, de todos os importar escopo especificado, precedendo chamadas para `IMetaDataEmit::Merge`, para o escopo de saída atual.</span><span class="sxs-lookup"><span data-stu-id="9cab7-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="9cab7-109">As seguintes condições especiais se aplicam a mala direta:</span><span class="sxs-lookup"><span data-stu-id="9cab7-109">The following special conditions apply to the merge:</span></span>  
  
-   <span data-ttu-id="9cab7-110">Um identificador de versão de módulo (MVID) nunca é importado, porque ele é exclusivo para os metadados no escopo de importação.</span><span class="sxs-lookup"><span data-stu-id="9cab7-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
-   <span data-ttu-id="9cab7-111">Nenhuma propriedade de todo o módulo existente é substituída.</span><span class="sxs-lookup"><span data-stu-id="9cab7-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="9cab7-112">Se as propriedades do módulo já foram definidas para o escopo atual, nenhuma propriedade do módulo é importada.</span><span class="sxs-lookup"><span data-stu-id="9cab7-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="9cab7-113">No entanto, se as propriedades do módulo não tem sido definidas no escopo atual, eles serão importados apenas uma vez, quando eles são encontrados pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="9cab7-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="9cab7-114">Se as propriedades do módulo são encontradas novamente, eles são duplicatas.</span><span class="sxs-lookup"><span data-stu-id="9cab7-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="9cab7-115">Se os valores de todas as propriedades de módulo (exceto MVID) são comparados e sem duplicatas forem encontradas, um erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="9cab7-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
-   <span data-ttu-id="9cab7-116">Para obter definições de tipo (`TypeDef`), não há duplicatas são mescladas no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="9cab7-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="9cab7-117">`TypeDef`objetos são verificados para duplicatas em relação a cada *nome totalmente qualificado do objeto* + *GUID* + *o número de versão*.</span><span class="sxs-lookup"><span data-stu-id="9cab7-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="9cab7-118">Se houver uma correspondência no nome ou o GUID e qualquer um dos dois elementos é diferente, um erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="9cab7-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="9cab7-119">Caso contrário, se corresponderem a todos os três itens, `MergeEnd` faz uma verificação básica para garantir que as entradas são realmente duplicatas; caso contrário, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="9cab7-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="9cab7-120">Essa verificação superficial procura:</span><span class="sxs-lookup"><span data-stu-id="9cab7-120">This cursory check looks for:</span></span>  
  
    -   <span data-ttu-id="9cab7-121">As declarações de membro mesmo, que ocorrem na mesma ordem.</span><span class="sxs-lookup"><span data-stu-id="9cab7-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="9cab7-122">Membros que são sinalizados como `mdPrivateScope` (consulte a [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeração) não estão incluídos nessa verificação; elas são mescladas especialmente.</span><span class="sxs-lookup"><span data-stu-id="9cab7-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    -   <span data-ttu-id="9cab7-123">O mesmo layout de classe.</span><span class="sxs-lookup"><span data-stu-id="9cab7-123">The same class layout.</span></span>  
  
     <span data-ttu-id="9cab7-124">Isso significa que um `TypeDef` objeto deve sempre ser totalmente e consistente definido em cada escopo de metadados no qual ela é declarada, se suas implementações de membro (para uma classe) são distribuídas entre várias unidades de compilação, a definição completa é considerada presente em cada escopo e não incrementais a cada escopo.</span><span class="sxs-lookup"><span data-stu-id="9cab7-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="9cab7-125">Por exemplo, se os nomes de parâmetro são relevantes para o contrato, eles devem ser emitidos da mesma maneira em cada escopo. Se não forem relevantes, eles não devem ser emitidos nos metadados.</span><span class="sxs-lookup"><span data-stu-id="9cab7-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="9cab7-126">A exceção é que um `TypeDef` objeto pode ter membros incrementais sinalizados como `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="9cab7-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="9cab7-127">Encontrar esses, `MergeEnd` incrementalmente adiciona ao escopo atual sem levar em consideração duplicatas.</span><span class="sxs-lookup"><span data-stu-id="9cab7-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="9cab7-128">Como o compilador compreende o escopo particular, o compilador deve ser responsável pela aplicação de regras.</span><span class="sxs-lookup"><span data-stu-id="9cab7-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
-   <span data-ttu-id="9cab7-129">Endereços virtuais relativos (RVAs) não são importados ou mesclados. o compilador deve emitir novamente essas informações.</span><span class="sxs-lookup"><span data-stu-id="9cab7-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
-   <span data-ttu-id="9cab7-130">Atributos personalizados são mesclados apenas quando o item ao qual eles estão conectados é mesclado.</span><span class="sxs-lookup"><span data-stu-id="9cab7-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="9cab7-131">Por exemplo, os atributos personalizados associados a uma classe são mesclados quando a classe é encontrada pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="9cab7-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="9cab7-132">Se os atributos personalizados estão associados um `TypeDef` ou `MemberDef` que é específico à unidade de compilação (como o carimbo de hora da compilação de um membro), elas não são mescladas e cabe ao compilador para remover ou atualizar esses metadados.</span><span class="sxs-lookup"><span data-stu-id="9cab7-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cab7-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cab7-133">Requirements</span></span>  
 <span data-ttu-id="9cab7-134">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cab7-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cab7-135">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9cab7-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cab7-136">**Biblioteca:** usado como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="9cab7-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cab7-137">**Versões do .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cab7-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cab7-138">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9cab7-138">See Also</span></span>  
 [<span data-ttu-id="9cab7-139">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9cab7-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9cab7-140">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9cab7-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)