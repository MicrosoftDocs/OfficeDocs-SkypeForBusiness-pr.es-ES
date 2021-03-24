---
title: Crear o eliminar un anuncio en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Cree o elimine anuncios para la aplicación Announcement en Skype Empresarial Server Telefonía IP empresarial. Esto afecta al modo en que se controlan las llamadas a números sin signo.
ms.openlocfilehash: 571dce52366430c0e13f442de4917a2c51ed056f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093288"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="b9b1d-104">Crear o eliminar un anuncio en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b9b1d-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="b9b1d-105">Cree o elimine anuncios para la aplicación Announcement en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="b9b1d-106">Esto afecta al modo en que se controlan las llamadas a números sin signo.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="b9b1d-p103">Cuando configura anuncios, en realidad está configurando la forma en que desea administrar las llamadas a números no asignados. Reproduzca un mensaje, que puede tratarse de un archivo de audio o de un archivo de texto a voz (TTS), o bien transferir la llamada a un destino determinado sin reproducir ningún mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="b9b1d-p104">Cree los anuncios antes de definir la tabla de números sin asignar. Ejecute este paso para todos los anuncios que usan un mensaje de audio, un mensaje TTS o no tienen mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="b9b1d-111">En este tema se describe cómo importar y crear anuncios.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="b9b1d-112">Para obtener información sobre la asignación de anuncios en la tabla de números no asignados, consulte [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).</span><span class="sxs-lookup"><span data-stu-id="b9b1d-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="b9b1d-113">Crear un nuevo anuncio para números sin signo</span><span class="sxs-lookup"><span data-stu-id="b9b1d-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="b9b1d-114">Para crear un anuncio, debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b9b1d-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="b9b1d-115">Para mensajes de audio, grabe el archivo de audio con su aplicación de grabación de audio preferida.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="b9b1d-116">Para mensajes de audio, ejecute el cmdlet **Import-CsAnnouncementFile** para importar el contenido del archivo de audio al almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="b9b1d-117">Ejecute el cmdlet **New-CsAnnouncement** para crear y asignar un nombre al anuncio.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="b9b1d-118">Lleve a cabo este paso para crear anuncios con un mensaje de audio, con un mensaje TTS o sin mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="b9b1d-119">Puede que le interese crear un anuncio sin mensaje; por ejemplo, si quiere transferir las llamadas a un destino específico sin reproducir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="b9b1d-120">Asigne el nuevo anuncio a un intervalo de números en la tabla de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="b9b1d-121">Para crear un anuncio</span><span class="sxs-lookup"><span data-stu-id="b9b1d-121">To create a new announcement</span></span>

1. <span data-ttu-id="b9b1d-122">Para mensajes de audio, cree el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="b9b1d-123">Inicie sesión en el equipo donde skype empresarial Server Management Shell está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="b9b1d-124">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="b9b1d-125">Para mensajes de audio, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b9b1d-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="b9b1d-126">Ejecute: </span><span class="sxs-lookup"><span data-stu-id="b9b1d-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="b9b1d-p107">Para transferir llamadas al correo de voz, escriba el parámetro SIPAddress en el formato sip:nombre_usuario@nombre_dominio;opaque=app:voicemail (por ejemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir llamadas a un número de teléfono, escriba el parámetro SIPAddress en el formato sip:número@nombre_dominio;user=phone (por ejemplo, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="b9b1d-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="b9b1d-129">Por ejemplo, para especificar un mensaje de audio:</span><span class="sxs-lookup"><span data-stu-id="b9b1d-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="b9b1d-130">Por ejemplo, para especificar un mensaje TTS:</span><span class="sxs-lookup"><span data-stu-id="b9b1d-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="b9b1d-131">Para obtener más información acerca de estos cmdlets y ver una lista de los códigos de idioma que se usarán en el parámetro **TextToSpeechPrompt,** vea [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b9b1d-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="b9b1d-132">Eliminar un anuncio para números sin signo</span><span class="sxs-lookup"><span data-stu-id="b9b1d-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="b9b1d-133">Para eliminar un anuncio</span><span class="sxs-lookup"><span data-stu-id="b9b1d-133">To delete an announcement</span></span>

1. <span data-ttu-id="b9b1d-134">Inicie sesión en el equipo donde skype empresarial Server Management Shell está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="b9b1d-135">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="b9b1d-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="b9b1d-p108">Muestre todos los anuncios de su organización. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b9b1d-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="b9b1d-p109">En la lista resultante, busque el anuncio que desea eliminar, y copie el GUID. A continuación, en la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b9b1d-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="b9b1d-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9b1d-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="b9b1d-141">Para obtener más información sobre más opciones, [vea Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) y [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b9b1d-141">For details about more options, see [Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9b1d-142">Ver también</span><span class="sxs-lookup"><span data-stu-id="b9b1d-142">See also</span></span>

[<span data-ttu-id="b9b1d-143">Crear o eliminar un anuncio en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b9b1d-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="b9b1d-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="b9b1d-144">Import-CsAnnouncementFile</span></span>](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="b9b1d-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="b9b1d-145">New-CsAnnouncement</span></span>](/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="b9b1d-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="b9b1d-146">Remove-CsAnnouncement</span></span>](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="b9b1d-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="b9b1d-147">Get-CsAnnouncement</span></span>](/powershell/module/skype/get-csannouncement?view=skype-ps)