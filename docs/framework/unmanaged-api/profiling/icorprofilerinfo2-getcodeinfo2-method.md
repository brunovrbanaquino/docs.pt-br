---
title: "Método ICorProfilerInfo2::GetCodeInfo2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetCodeInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6c2526c286e4014b32e63ec34f9d212a5f657756
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="04139-102">Método ICorProfilerInfo2::GetCodeInfo2</span><span class="sxs-lookup"><span data-stu-id="04139-102">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>
<span data-ttu-id="04139-103">Obtém as extensões de código nativo associado ao `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="04139-103">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04139-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="04139-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04139-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="04139-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="04139-106">[in] A ID da função à qual o código nativo está associado.</span><span class="sxs-lookup"><span data-stu-id="04139-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="04139-107">[in] O tamanho do `codeInfos` matriz.</span><span class="sxs-lookup"><span data-stu-id="04139-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="04139-108">[out] Um ponteiro para o número total de [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) estruturas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="04139-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="04139-109">[out] Um buffer fornecido pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="04139-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="04139-110">Depois que o método retorna, contém uma matriz de `COR_PRF_CODE_INFO` estruturas, cada um deles descreve um bloco de código nativo.</span><span class="sxs-lookup"><span data-stu-id="04139-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04139-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="04139-111">Remarks</span></span>  
 <span data-ttu-id="04139-112">As extensões são classificadas em ordem crescente deslocamento de linguagem intermediária (MSIL) do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04139-112">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="04139-113">Depois de `GetCodeInfo2` retorna, você deve verificar se o `codeInfos` buffer era grande o suficiente para conter todos o `COR_PRF_CODE_INFO` estruturas.</span><span class="sxs-lookup"><span data-stu-id="04139-113">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="04139-114">Para fazer isso, comparar o valor de `cCodeInfos` com o valor de `cchName` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="04139-114">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="04139-115">Se `cCodeInfos` dividida pelo tamanho de um `COR_PRF_CODE_INFO` estrutura é menor do que `pcCodeInfos`, alocar uma maior `codeInfos` buffer, atualize `cCodeInfos` com o novo tamanho maior e chame `GetCodeInfo2` novamente.</span><span class="sxs-lookup"><span data-stu-id="04139-115">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="04139-116">Como alternativa, você pode primeiro chamar `GetCodeInfo2` com um comprimento zero `codeInfos` buffer para obter o tamanho do buffer correto.</span><span class="sxs-lookup"><span data-stu-id="04139-116">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="04139-117">Você pode definir o `codeInfos` de buffer de tamanho para o valor retornado em `pcCodeInfos`, multiplicado pelo tamanho de um `COR_PRF_CODE_INFO` estrutura e chame `GetCodeInfo2` novamente.</span><span class="sxs-lookup"><span data-stu-id="04139-117">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04139-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04139-118">Requirements</span></span>  
 <span data-ttu-id="04139-119">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04139-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04139-120">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04139-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04139-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04139-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04139-122">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04139-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04139-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="04139-123">See Also</span></span>  
 [<span data-ttu-id="04139-124">Método GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="04139-124">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)  
 [<span data-ttu-id="04139-125">Interface ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="04139-125">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="04139-126">Interfaces de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="04139-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="04139-127">Criação de perfil</span><span class="sxs-lookup"><span data-stu-id="04139-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)