---
title: "Visão geral da classe SoundPlayer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b6df44df3582ed806d338e2d4565c5c11f69ce21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="52eda-102">Visão geral da classe SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="52eda-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="52eda-103">A classe <xref:System.Media.SoundPlayer> permite que você inclua facilmente sons em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="52eda-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="52eda-104">O <xref:System.Media.SoundPlayer> classe pode reproduzir arquivos de som no formato. wav, a partir de um recurso ou UNC ou locais HTTP.</span><span class="sxs-lookup"><span data-stu-id="52eda-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="52eda-105">Além disso, a <xref:System.Media.SoundPlayer> classe permite que você carregue ou reproduza sons de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="52eda-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="52eda-106">Você também pode usar o <xref:System.Media.SystemSounds> classe para reproduzir sons do sistema comum, incluindo um bipe.</span><span class="sxs-lookup"><span data-stu-id="52eda-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="52eda-107">Propriedades, métodos e eventos normalmente usados</span><span class="sxs-lookup"><span data-stu-id="52eda-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="52eda-108">Nome</span><span class="sxs-lookup"><span data-stu-id="52eda-108">Name</span></span>|<span data-ttu-id="52eda-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="52eda-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="52eda-110">Propriedade <xref:System.Media.SoundPlayer.SoundLocation%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="52eda-111">O caminho do arquivo ou o endereço Web do som.</span><span class="sxs-lookup"><span data-stu-id="52eda-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="52eda-112">Os valores aceitáveis podem ser HTTP ou UNC.</span><span class="sxs-lookup"><span data-stu-id="52eda-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="52eda-113">Propriedade <xref:System.Media.SoundPlayer.LoadTimeout%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="52eda-114">O número de milissegundos que o programa irá esperar para carregar um som antes que ele gere uma exceção.</span><span class="sxs-lookup"><span data-stu-id="52eda-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="52eda-115">O padrão é 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="52eda-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="52eda-116">Propriedade <xref:System.Media.SoundPlayer.IsLoadCompleted%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="52eda-117">Um valor booliano que indica se o som terminou de ser carregado.</span><span class="sxs-lookup"><span data-stu-id="52eda-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="52eda-118">Método <xref:System.Media.SoundPlayer.Load%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="52eda-119">Carrega um som de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="52eda-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="52eda-120">Método <xref:System.Media.SoundPlayer.LoadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="52eda-121">Começa a carregar um som de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="52eda-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="52eda-122">Quando o carregamento for concluído, ele gera o <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> evento.</span><span class="sxs-lookup"><span data-stu-id="52eda-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="52eda-123">Método <xref:System.Media.SoundPlayer.Play%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="52eda-124">Toca o som especificado no <xref:System.Media.SoundPlayer.SoundLocation%2A> ou <xref:System.Media.SoundPlayer.Stream%2A> propriedade em um novo thread.</span><span class="sxs-lookup"><span data-stu-id="52eda-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="52eda-125">Método <xref:System.Media.SoundPlayer.PlaySync%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="52eda-126">Toca o som especificado no <xref:System.Media.SoundPlayer.SoundLocation%2A> ou <xref:System.Media.SoundPlayer.Stream%2A> propriedade no thread atual.</span><span class="sxs-lookup"><span data-stu-id="52eda-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="52eda-127">Método <xref:System.Media.SoundPlayer.Stop%2A></span><span class="sxs-lookup"><span data-stu-id="52eda-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="52eda-128">Interrompe qualquer som que está em reprodução no momento.</span><span class="sxs-lookup"><span data-stu-id="52eda-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="52eda-129">Evento <xref:System.Media.SoundPlayer.LoadCompleted></span><span class="sxs-lookup"><span data-stu-id="52eda-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="52eda-130">Gerado depois que o carregamento de um som é tentado.</span><span class="sxs-lookup"><span data-stu-id="52eda-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52eda-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="52eda-131">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>