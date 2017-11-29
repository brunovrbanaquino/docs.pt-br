---
title: "Tipos de dados e funções"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683413c5-0312-4e60-8619-9a97bdc6e62a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 809fc9290070deb304c44018102874d6a56fdd11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-and-functions"></a><span data-ttu-id="5e415-102">Tipos de dados e funções</span><span class="sxs-lookup"><span data-stu-id="5e415-102">Data Types and Functions</span></span>
<span data-ttu-id="5e415-103">Os tópicos listados na tabela a seguir descrevem o suporte LINQ to SQL para membros, construções e conversões do CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="5e415-103">The topics listed in the following table describe LINQ to SQL support for members, constructs, and casts of the common language runtime (CLR).</span></span> <span data-ttu-id="5e415-104">Os membros e as construções com suporte estão disponíveis para uso em suas consultas LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="5e415-104">Supported members and constructs are available to use in your LINQ to SQL queries.</span></span>  
  
 <span data-ttu-id="5e415-105">Um item sem suporte na tabela significa que LINQ to SQL não pode converter o membro CLR, a construção ou conversão para execução no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e415-105">An unsupported item in the table means that LINQ to SQL cannot translate the CLR member, construct, or cast for execution on the SQL Server.</span></span> <span data-ttu-id="5e415-106">Você pode ainda ser capaz de usá-los em seu código, mas eles devem ser avaliados antes de a consulta ser convertida para o Transact-SQL ou após os resultados terem sido recuperados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5e415-106">You may still be able to use them in your code, but they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
|<span data-ttu-id="5e415-107">Tópico</span><span class="sxs-lookup"><span data-stu-id="5e415-107">Topic</span></span>|<span data-ttu-id="5e415-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e415-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5e415-109">Mapeamento de tipo CLR do SQL</span><span class="sxs-lookup"><span data-stu-id="5e415-109">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)|<span data-ttu-id="5e415-110">Fornece uma matriz detalhada de mapeamentos entre os tipos de CLR e SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e415-110">Provides a detailed matrix of mappings between CLR types and SQL Server types.</span></span>|  
|[<span data-ttu-id="5e415-111">Tipos de dados básicos</span><span class="sxs-lookup"><span data-stu-id="5e415-111">Basic Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/basic-data-types.md)|<span data-ttu-id="5e415-112">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-112">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-113">Tipos de dados booliano</span><span class="sxs-lookup"><span data-stu-id="5e415-113">Boolean Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/boolean-data-types.md)|<span data-ttu-id="5e415-114">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-114">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-115">Semântica nula</span><span class="sxs-lookup"><span data-stu-id="5e415-115">Null Semantics</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/null-semantics.md)|<span data-ttu-id="5e415-116">Fornece links para os tópicos do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que discutem problemas de nulo e anulável.</span><span class="sxs-lookup"><span data-stu-id="5e415-116">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] topics that discuss null and nullable issues.</span></span>|  
|[<span data-ttu-id="5e415-117">Numérico e operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="5e415-117">Numeric and Comparison Operators</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/numeric-and-comparison-operators.md)|<span data-ttu-id="5e415-118">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-118">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-119">Operadores de sequência</span><span class="sxs-lookup"><span data-stu-id="5e415-119">Sequence Operators</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sequence-operators.md)|<span data-ttu-id="5e415-120">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-120">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-121">Métodos de System. Convert</span><span class="sxs-lookup"><span data-stu-id="5e415-121">System.Convert Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-convert-methods.md)|<span data-ttu-id="5e415-122">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-122">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-123">Métodos de System. DateTime</span><span class="sxs-lookup"><span data-stu-id="5e415-123">System.DateTime Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md)|<span data-ttu-id="5e415-124">Descreve suporte do LINQ to SQL para membros de estrutura <xref:System.DateTime?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5e415-124">Describes LINQ to SQL support for members of the <xref:System.DateTime?displayProperty=nameWithType> structure.</span></span>|  
|[<span data-ttu-id="5e415-125">Métodos de System. DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5e415-125">System.DateTimeOffset Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-datetimeoffset-methods.md)|<span data-ttu-id="5e415-126">Descreve suporte do LINQ to SQL para membros de estrutura <xref:System.DateTimeOffset?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5e415-126">Describes LINQ to SQL support for members of the <xref:System.DateTimeOffset?displayProperty=nameWithType> structure.</span></span>|  
|[<span data-ttu-id="5e415-127">Métodos de System. Math</span><span class="sxs-lookup"><span data-stu-id="5e415-127">System.Math Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-math-methods.md)|<span data-ttu-id="5e415-128">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-128">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-129">Métodos de System. Object</span><span class="sxs-lookup"><span data-stu-id="5e415-129">System.Object Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-object-methods.md)|<span data-ttu-id="5e415-130">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-130">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-131">Métodos de System. String</span><span class="sxs-lookup"><span data-stu-id="5e415-131">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="5e415-132">Resume as diferenças de comportamento do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-132">Summarizes differences in behavior from the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5e415-133">Métodos de System. TimeSpan</span><span class="sxs-lookup"><span data-stu-id="5e415-133">System.TimeSpan Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md)|<span data-ttu-id="5e415-134">Descreve suporte do LINQ to SQL para membros de estrutura <xref:System.TimeSpan?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5e415-134">Describes LINQ to SQL support for members of the <xref:System.TimeSpan?displayProperty=nameWithType> structure.</span></span>|  
|[<span data-ttu-id="5e415-135">Funcionalidade sem suporte</span><span class="sxs-lookup"><span data-stu-id="5e415-135">Unsupported Functionality</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/unsupported-functionality.md)|<span data-ttu-id="5e415-136">Descreve a funcionalidade que não tem suporte no [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e415-136">Describes functionality that is not supported in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e415-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5e415-137">See Also</span></span>  
 [<span data-ttu-id="5e415-138">Incompatibilidade de tipo CLR do SQL</span><span class="sxs-lookup"><span data-stu-id="5e415-138">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)  
 [<span data-ttu-id="5e415-139">Referência</span><span class="sxs-lookup"><span data-stu-id="5e415-139">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="5e415-140">Biblioteca de classes do .NET framework no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5e415-140">.NET Framework Class Library in Visual Studio</span></span>](http://msdn.microsoft.com/en-us/a03e374c-3d5c-4169-937b-49857ab273ae)