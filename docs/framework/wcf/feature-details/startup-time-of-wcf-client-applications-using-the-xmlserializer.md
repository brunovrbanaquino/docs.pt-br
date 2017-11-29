---
title: "Como melhorar o tempo de inicialização dos aplicativos do cliente WCF usando o XmlSerializer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3087dd479b386036d62df2ef9f792a1582d696c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="090a3-102">Como melhorar o tempo de inicialização dos aplicativos do cliente WCF usando o XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="090a3-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="090a3-103">Os serviços e os aplicativos cliente que usam tipos de dados que são serializados usando <xref:System.Xml.Serialization.XmlSerializer> geram e compilam o código de serialização para esses tipos de dados em tempo de execução, o que pode levar a um desempenho de inicialização lento.</span><span class="sxs-lookup"><span data-stu-id="090a3-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="090a3-104">O código de serialização pré-gerado somente pode ser usado em aplicativos cliente e não em serviços.</span><span class="sxs-lookup"><span data-stu-id="090a3-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="090a3-105">O [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) pode melhorar o desempenho de inicialização para esses aplicativos por meio da geração de código de serialização necessários dos assemblies compilados para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="090a3-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="090a3-106">Svcutil.exe gera o código de serialização para todos os tipos de dados usados em contratos de serviço no assembly compilado do aplicativo que pode ser serializado usando o <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="090a3-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="090a3-107">Contratos de serviço e operação que usam o <xref:System.Xml.Serialization.XmlSerializer> são marcados com o <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="090a3-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="090a3-108">Para gerar o código de serialização de XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="090a3-108">To generate XmlSerializer serialization code</span></span>  
  
1.  <span data-ttu-id="090a3-109">Compile seu código de serviço ou cliente em um ou mais assemblies.</span><span class="sxs-lookup"><span data-stu-id="090a3-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2.  <span data-ttu-id="090a3-110">Abra um prompt de comando do SDK.</span><span class="sxs-lookup"><span data-stu-id="090a3-110">Open an SDK command prompt.</span></span>  
  
3.  <span data-ttu-id="090a3-111">No prompt de comando, inicie a ferramenta Svcutil.exe usando o seguinte formato.</span><span class="sxs-lookup"><span data-stu-id="090a3-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="090a3-112">O `assemblyPath` argumento especifica o caminho para um assembly que contém os tipos de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="090a3-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="090a3-113">Svcutil.exe gera o código de serialização para todos os tipos de dados usados em contratos de serviço no assembly compilado do aplicativo que pode ser serializado usando o <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="090a3-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="090a3-114">Svcutil.exe só pode gerar o código de serialização do c#.</span><span class="sxs-lookup"><span data-stu-id="090a3-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="090a3-115">Um arquivo de código fonte é gerado para cada assembly de entrada.</span><span class="sxs-lookup"><span data-stu-id="090a3-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="090a3-116">Não é possível usar o **/idioma** switch para alterar o idioma do código gerado.</span><span class="sxs-lookup"><span data-stu-id="090a3-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="090a3-117">Para especificar o caminho para assemblies dependentes, use o **/Reference** opção.</span><span class="sxs-lookup"><span data-stu-id="090a3-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4.  <span data-ttu-id="090a3-118">Verifique o código de serialização gerado disponíveis para seu aplicativo usando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="090a3-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1.  <span data-ttu-id="090a3-119">Compilar o código de serialização gerado em um assembly separado com o nome [*assembly original*]. XmlSerializers.dll (por exemplo, MyApp.XmlSerializers.dll).</span><span class="sxs-lookup"><span data-stu-id="090a3-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="090a3-120">Seu aplicativo deve ser capaz de carregar o assembly, que deve ser assinado com a mesma chave do assembly original.</span><span class="sxs-lookup"><span data-stu-id="090a3-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="090a3-121">Se você recompile o assembly original, você deve gerar novamente o assembly de serialização.</span><span class="sxs-lookup"><span data-stu-id="090a3-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2.  <span data-ttu-id="090a3-122">Compilar o código de serialização gerado em um assembly separado e usar o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> no contrato de serviço que usa o <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="090a3-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="090a3-123">Definir o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> ou <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> propriedades para apontar para o assembly de serialização compilados.</span><span class="sxs-lookup"><span data-stu-id="090a3-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3.  <span data-ttu-id="090a3-124">Compile o código de serialização gerado no seu assembly de aplicativo e adicione o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> ao contrato de serviço que usa o <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="090a3-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="090a3-125">Não defina o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> ou <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> propriedades.</span><span class="sxs-lookup"><span data-stu-id="090a3-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="090a3-126">O assembly de serialização padrão é considerado o assembly atual.</span><span class="sxs-lookup"><span data-stu-id="090a3-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="090a3-127">Para gerar o código de serialização de XmlSerializer no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="090a3-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1.  <span data-ttu-id="090a3-128">Crie o serviço do WCF e o cliente projetos no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="090a3-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="090a3-129">Em seguida, adicione uma referência de serviço para o projeto de cliente.</span><span class="sxs-lookup"><span data-stu-id="090a3-129">Then, add a service reference to the client project.</span></span>  
  
2.  <span data-ttu-id="090a3-130">Adicionar uma <xref:System.ServiceModel.XmlSerializerFormatAttribute> ao contrato de serviço a *reference.cs* arquivo no projeto de aplicativo cliente em **serviceReference** -> **svcmap** .</span><span class="sxs-lookup"><span data-stu-id="090a3-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="090a3-131">Observe que você precisa mostrar todos os arquivos em **Solution Explorer** para ver esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="090a3-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3.  <span data-ttu-id="090a3-132">Compile o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="090a3-132">Build the client app.</span></span>  
  
4.  <span data-ttu-id="090a3-133">Use o [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para criar um serializador pré-gerado *. CS* arquivo usando o comando:</span><span class="sxs-lookup"><span data-stu-id="090a3-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="090a3-134">O argumento assemblyPath Especifica o caminho para o assembly de cliente do WCF.</span><span class="sxs-lookup"><span data-stu-id="090a3-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="090a3-135">Como:</span><span class="sxs-lookup"><span data-stu-id="090a3-135">Such as:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="090a3-136">O *WCFClient.XmlSerializers.dll.cs* arquivo será gerado.</span><span class="sxs-lookup"><span data-stu-id="090a3-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5.  <span data-ttu-id="090a3-137">Compile o assembly de serialização gerado previamente.</span><span class="sxs-lookup"><span data-stu-id="090a3-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="090a3-138">Com base no exemplo na etapa anterior, o comando de compilação seria o seguinte:</span><span class="sxs-lookup"><span data-stu-id="090a3-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="090a3-139">Certifique-se de gerado *WCFClient.XmlSerializers.dll* está no mesmo diretório que o aplicativo cliente, que é *WCFClient.exe* nesse caso.</span><span class="sxs-lookup"><span data-stu-id="090a3-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6.  <span data-ttu-id="090a3-140">Execute o aplicativo cliente como de costume.</span><span class="sxs-lookup"><span data-stu-id="090a3-140">Run the client app as usual.</span></span> <span data-ttu-id="090a3-141">O assembly de serialização gerado será usado.</span><span class="sxs-lookup"><span data-stu-id="090a3-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="090a3-142">Exemplo</span><span class="sxs-lookup"><span data-stu-id="090a3-142">Example</span></span>  
 <span data-ttu-id="090a3-143">O comando a seguir gera os tipos de serialização para `XmlSerializer` tipos de contratos de qualquer serviço do uso de assembly.</span><span class="sxs-lookup"><span data-stu-id="090a3-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="090a3-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="090a3-144">See Also</span></span>  
 <span data-ttu-id="090a3-145">[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) [Ferramenta de utilitário de metadados ServiceModel (Svcutil.exe)]</span><span class="sxs-lookup"><span data-stu-id="090a3-145">[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)</span></span>