---
title: Como configurar o IIS 5.0 e o IIS 6.0 para implantar aplicativos WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: faff58f146aed7b309674157a5990cbce43dfb1f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="7df9e-102">Como configurar o IIS 5.0 e o IIS 6.0 para implantar aplicativos WPF</span><span class="sxs-lookup"><span data-stu-id="7df9e-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>
<span data-ttu-id="7df9e-103">Você pode implantar um aplicativo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] da maioria dos servidores Web, desde que eles sejam configurados com os devidos tipos [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] types.</span></span> <span data-ttu-id="7df9e-104">Por padrão, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] é configurado com esses tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)], mas [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] e [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] não são.</span><span class="sxs-lookup"><span data-stu-id="7df9e-104">By default, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] is configured with these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types, but [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] are not.</span></span>  
  
 <span data-ttu-id="7df9e-105">Este tópico descreve como configurar [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] e [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] para implantar aplicativos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-105">This topic describes how to configure [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>  
  
  
> [!NOTE]
>  <span data-ttu-id="7df9e-106">Você pode verificar a cadeia de caracteres *UserAgent* no Registro para determinar se um sistema tem [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="7df9e-106">You can check the *UserAgent* string in the registry to determine whether a system has [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installed.</span></span> <span data-ttu-id="7df9e-107">Para ver detalhes e um script que examina a cadeia de caracteres *UserAgent* para determinar se [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] está instalado em um sistema, consulte [Detectar se o .NET Framework 3.0 está instalado](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="7df9e-107">For details and a script that examines the *UserAgent* string to determine whether [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="7df9e-108">Ajustar a configuração de expiração de conteúdo</span><span class="sxs-lookup"><span data-stu-id="7df9e-108">Adjust the Content Expiration Setting</span></span>  
 <span data-ttu-id="7df9e-109">É recomendável ajustar a configuração de expiração de conteúdo para 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="7df9e-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="7df9e-110">O procedimento a seguir descreve como fazer isso com [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-110">The following procedure outlines how to do this with [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span>  
  
1.  <span data-ttu-id="7df9e-111">Clique no menu **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciador dos ISS (Serviços de Informações da Internet)**.</span><span class="sxs-lookup"><span data-stu-id="7df9e-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="7df9e-112">Você também pode iniciar este aplicativo da linha de comando com “%SystemRoot%\system32\inetsrv\iis.msc”.</span><span class="sxs-lookup"><span data-stu-id="7df9e-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>  
  
2.  <span data-ttu-id="7df9e-113">Expanda a árvore [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] até localizar o nó **Site da Web Padrão**.</span><span class="sxs-lookup"><span data-stu-id="7df9e-113">Expand the [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] tree until you find the **Default Web site** node.</span></span>  
  
3.  <span data-ttu-id="7df9e-114">Clique com o botão direito do mouse em **Site da Web padrão** e selecione **Propriedades** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="7df9e-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>  
  
4.  <span data-ttu-id="7df9e-115">Selecione a guia **Cabeçalhos HTTP** e clique em “Habilitar expiração de conteúdo”.</span><span class="sxs-lookup"><span data-stu-id="7df9e-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>  
  
5.  <span data-ttu-id="7df9e-116">Defina o conteúdo para expirar após um minuto.</span><span class="sxs-lookup"><span data-stu-id="7df9e-116">Set the content to expire after 1 minute.</span></span>  
  
<a name="register_mime_types"></a>   
## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="7df9e-117">Registrar os tipos MIME e extensões de arquivo</span><span class="sxs-lookup"><span data-stu-id="7df9e-117">Register MIME Types and File Extensions</span></span>  
 <span data-ttu-id="7df9e-118">Você deve registrar vários tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] e extensões de arquivo para que o navegador no sistema cliente possa carregar o manipulador correto.</span><span class="sxs-lookup"><span data-stu-id="7df9e-118">You must register several [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="7df9e-119">Você precisa adicionar os seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="7df9e-119">You need to add the following types:</span></span>  
  
|<span data-ttu-id="7df9e-120">Extensão</span><span class="sxs-lookup"><span data-stu-id="7df9e-120">Extension</span></span>|<span data-ttu-id="7df9e-121">Tipo MIME</span><span class="sxs-lookup"><span data-stu-id="7df9e-121">MIME Type</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="7df9e-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="7df9e-122">.manifest</span></span>|<span data-ttu-id="7df9e-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="7df9e-123">application/manifest</span></span>|  
|<span data-ttu-id="7df9e-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="7df9e-124">.xaml</span></span>|<span data-ttu-id="7df9e-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="7df9e-125">application/xaml+xml</span></span>|  
|<span data-ttu-id="7df9e-126">.application</span><span class="sxs-lookup"><span data-stu-id="7df9e-126">.application</span></span>|<span data-ttu-id="7df9e-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="7df9e-127">application/x-ms-application</span></span>|  
|<span data-ttu-id="7df9e-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="7df9e-128">.xbap</span></span>|<span data-ttu-id="7df9e-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="7df9e-129">application/x-ms-xbap</span></span>|  
|<span data-ttu-id="7df9e-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="7df9e-130">.deploy</span></span>|<span data-ttu-id="7df9e-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="7df9e-131">application/octet-stream</span></span>|  
|<span data-ttu-id="7df9e-132">.xps</span><span class="sxs-lookup"><span data-stu-id="7df9e-132">.xps</span></span>|<span data-ttu-id="7df9e-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="7df9e-133">application/vnd.ms-xpsdocument</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7df9e-134">Você não precisa registrar tipos ou extensões de arquivo [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] em sistemas cliente.</span><span class="sxs-lookup"><span data-stu-id="7df9e-134">You do not need to register [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types or file extensions on client systems.</span></span> <span data-ttu-id="7df9e-135">Eles são registrados automaticamente ao instalar o [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-135">They are registered automatically when you install [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)].</span></span>  
  
 <span data-ttu-id="7df9e-136">O exemplo [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)] a seguir adiciona automaticamente os tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] necessários a [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-136">The following [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)] sample automatically adds the necessary [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types to [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span> <span data-ttu-id="7df9e-137">Para usar o script, copie o código para um arquivo .vbs no seu servidor.</span><span class="sxs-lookup"><span data-stu-id="7df9e-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="7df9e-138">Em seguida, execute o script executando o arquivo na linha de comando ou clicando duas vezes no arquivo em [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>  
  
```  
' This script adds the necessary Windows Presentation Foundation MIME types   
' to an IIS Server.  
' To use this script, just double-click or execute it from a command line.  
' Running this script multiple times results in multiple entries in the IIS MimeMap.  
  
Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec  
Const ADS_PROPERTY_UPDATE = 2   
  
' Set the MIME types to be added  
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _  
    "application/xaml+xml", ".application", "application/x-ms-application", _  
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _  
    ".xps", "application/vnd.ms-xpsdocument")   
  
' Get the mimemap object   
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")  
  
' Call AddMimeType for every pair of extension/MIME type  
For counter = 0 to UBound(MimeTypesToAddArray) Step 2  
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)  
Next  
  
' Create a Shell object  
Set WshShell = CreateObject("WScript.Shell")  
  
' Stop and Start the IIS Service  
Set oExec = WshShell.Exec("net stop w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = WshShell.Exec("net start w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = Nothing  
  
' Report status to user  
WScript.Echo "Windows Presentation Foundation MIME types have been registered."  
  
' AddMimeType Sub  
Sub AddMimeType (Ext, MType)  
  
    ' Get the mappings from the MimeMap property.   
    MimeMapArray = MimeMapObj.GetEx("MimeMap")   
  
    ' Add a new mapping.   
    i = UBound(MimeMapArray) + 1   
    Redim Preserve MimeMapArray(i)   
    Set MimeMapArray(i) = CreateObject("MimeMap")   
    MimeMapArray(i).Extension = Ext   
    MimeMapArray(i).MimeType = MType   
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray  
    MimeMapObj.SetInfo  
  
End Sub  
```  
  
> [!NOTE]
>  <span data-ttu-id="7df9e-139">Executar esse script várias vezes cria várias entradas de mapa [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] na metabase [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] ou [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-139">Running this script multiple times creates multiple [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] map entries in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
 <span data-ttu-id="7df9e-140">Depois de executar esse script, você não poderá ver tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] adicionais do [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] ou [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-140">After you have run this script, you may not see additional [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types from the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span></span> <span data-ttu-id="7df9e-141">No entanto, esses tipos de [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] foram adicionados ao metabase [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] ou [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-141">However, these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types have been added to the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span> <span data-ttu-id="7df9e-142">O script a seguir exibirá todos os tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] no metabase [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] ou [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df9e-142">The following script will display all the [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
```  
' This script lists the MIME types for an IIS Server.  
' To use this script, just double-click or execute it from a command line   
' by calling cscript.exe  
  
dim mimeMapEntry, allMimeMaps  
  
' Get the mimemap object.  
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")  
allMimeMaps = mimeMapEntry.GetEx("MimeMap")  
  
' Display the mappings in the table.  
For Each mimeMap In allMimeMaps  
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")  
Next  
```  
  
 <span data-ttu-id="7df9e-143">Salve o script como um arquivo `.vbs` (por exemplo, `DiscoverIISMimeTypes.vbs`) e execute-o no prompt de comando usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7df9e-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>  
  
 `cscript DiscoverIISMimeTypes.vbs`