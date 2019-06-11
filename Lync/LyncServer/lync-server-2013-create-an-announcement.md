---
title: 'Lync Server 2013: crear un anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80210787a8261d122fa7508807ab995279c7d0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="6c9c5-102">Crear un anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c9c5-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c9c5-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6c9c5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6c9c5-104">Para crear un anuncio, debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6c9c5-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="6c9c5-105">Para mensajes de audio, grabe el archivo de audio con su aplicación de grabación de audio preferida.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="6c9c5-106">Para mensajes de audio, ejecute el cmdlet **Import-CsAnnouncementFile** para importar el contenido del archivo de audio al almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="6c9c5-107">Ejecute el cmdlet **New-CsAnnouncement** para crear y asignar un nombre al anuncio.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="6c9c5-108">Lleve a cabo este paso para crear anuncios con un mensaje de audio, con un mensaje TTS o sin mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="6c9c5-109">Puede que le interese crear un anuncio sin mensaje; por ejemplo, si quiere transferir las llamadas a un destino específico sin reproducir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="6c9c5-110">Asigne el nuevo anuncio a un intervalo de números en la tabla de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="6c9c5-111">En este tema se describe cómo importar y crear anuncios.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="6c9c5-112">Para obtener más información sobre la asignación de anuncios en la tabla de números sin asignar, consulte [configurar la tabla de números sin asignar en Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="6c9c5-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="6c9c5-113">Para crear un anuncio</span><span class="sxs-lookup"><span data-stu-id="6c9c5-113">To create a new announcement</span></span>

1.  <span data-ttu-id="6c9c5-114">Para mensajes de audio, cree el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="6c9c5-115">Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6c9c5-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="6c9c5-116">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6c9c5-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="6c9c5-117">Para mensajes de audio, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c9c5-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="6c9c5-118">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c9c5-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="6c9c5-p103">Para transferir llamadas al correo de voz, escriba el parámetro SIPAddress en el formato sip:nombre_usuario@nombre_dominio;opaque=app:voicemail (por ejemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir llamadas a un número de teléfono, escriba el parámetro SIPAddress en el formato sip:número@nombre_dominio;user=phone (por ejemplo, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="6c9c5-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="6c9c5-121">Por ejemplo, para especificar un mensaje de audio:</span><span class="sxs-lookup"><span data-stu-id="6c9c5-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="6c9c5-122">Por ejemplo, para especificar un mensaje TTS:</span><span class="sxs-lookup"><span data-stu-id="6c9c5-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="6c9c5-123">Para obtener más información sobre estos cmdlets y para ver una lista de los códigos de idioma que se usan en el parámetro **TextToSpeechPrompt** , vea [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="6c9c5-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c9c5-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c9c5-124">See Also</span></span>


[<span data-ttu-id="6c9c5-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="6c9c5-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="6c9c5-126">Nuevo: CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="6c9c5-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="6c9c5-127">Configurar la tabla de números sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c9c5-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

