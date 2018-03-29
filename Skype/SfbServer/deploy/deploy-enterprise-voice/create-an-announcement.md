---
title: Crear o eliminar un anuncio de Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Crear o eliminar anuncios de aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server. Esto afecta a cómo se administran las llamadas a números sin asignar.
ms.openlocfilehash: 043b2a4b6552386b2a8b0b2fee1cdd0249fe7f21
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server-2015"></a><span data-ttu-id="950a2-104">Crear o eliminar un anuncio de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="950a2-104">Create or delete an announcement in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="950a2-105">Crear o eliminar anuncios de aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="950a2-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="950a2-106">Esto afecta a cómo se administran las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="950a2-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="950a2-p103">Cuando configura anuncios, en realidad está configurando la forma en que desea administrar las llamadas a números no asignados. Reproduzca un mensaje, que puede tratarse de un archivo de audio o de un archivo de texto a voz (TTS), o bien transferir la llamada a un destino determinado sin reproducir ningún mensaje.</span><span class="sxs-lookup"><span data-stu-id="950a2-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>
  
<span data-ttu-id="950a2-p104">Cree los anuncios antes de definir la tabla de números sin asignar. Ejecute este paso para todos los anuncios que usan un mensaje de audio, un mensaje TTS o no tienen mensaje.</span><span class="sxs-lookup"><span data-stu-id="950a2-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>
  
<span data-ttu-id="950a2-111">En este tema se describe cómo importar y crear anuncios.</span><span class="sxs-lookup"><span data-stu-id="950a2-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="950a2-112">Para obtener más información sobre la asignación de anuncios en la tabla de números sin asignar, vea [Configurar la tabla de número sin asignar](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="950a2-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>
  
## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="950a2-113">Crear un nuevo anuncio para números sin asignar</span><span class="sxs-lookup"><span data-stu-id="950a2-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="950a2-114">Para crear un anuncio, debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="950a2-114">To create a new announcement, you need to perform the following steps:</span></span> 
  
1. <span data-ttu-id="950a2-115">Para mensajes de audio, grabe el archivo de audio con su aplicación de grabación de audio preferida.</span><span class="sxs-lookup"><span data-stu-id="950a2-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>
    
2. <span data-ttu-id="950a2-116">Para mensajes de audio, ejecute el cmdlet **Import-CsAnnouncementFile** para importar el contenido del archivo de audio al almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="950a2-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>
    
3. <span data-ttu-id="950a2-117">Ejecute el cmdlet **New-CsAnnouncement** para crear y asignar nombre a la presentación.</span><span class="sxs-lookup"><span data-stu-id="950a2-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="950a2-118">Lleve a cabo este paso para crear anuncios con un mensaje de audio, con un mensaje TTS o sin mensaje.</span><span class="sxs-lookup"><span data-stu-id="950a2-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="950a2-119">Puede que le interese crear un anuncio sin mensaje; por ejemplo, si quiere transferir las llamadas a un destino específico sin reproducir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="950a2-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span> 
  
4. <span data-ttu-id="950a2-120">Asigne el nuevo anuncio a un intervalo de números en la tabla de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="950a2-120">Assign the new announcement to a number range in the unassigned number table.</span></span>
    
### <a name="to-create-a-new-announcement"></a><span data-ttu-id="950a2-121">Para crear un anuncio</span><span class="sxs-lookup"><span data-stu-id="950a2-121">To create a new announcement</span></span>

1. <span data-ttu-id="950a2-122">Para mensajes de audio, cree el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="950a2-122">For audio prompts, create the audio file.</span></span>
    
2. <span data-ttu-id="950a2-123">Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.</span><span class="sxs-lookup"><span data-stu-id="950a2-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
3. <span data-ttu-id="950a2-124">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="950a2-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
4. <span data-ttu-id="950a2-125">Para mensajes de audio, ejecute:</span><span class="sxs-lookup"><span data-stu-id="950a2-125">For audio prompts, run:</span></span>
    
   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="950a2-126">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="950a2-126">Run:</span></span>
    
   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="950a2-p107">Para transferir llamadas al correo de voz, escriba el parámetro SIPAddress en el formato sip:nombre_usuario@nombre_dominio;opaque=app:voicemail (por ejemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir llamadas a un número de teléfono, escriba el parámetro SIPAddress en el formato sip:número@nombre_dominio;user=phone (por ejemplo, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="950a2-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="950a2-129">Por ejemplo, para especificar un mensaje de audio:</span><span class="sxs-lookup"><span data-stu-id="950a2-129">For example, to specify an audio prompt:</span></span>
    
   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="950a2-130">Por ejemplo, para especificar un mensaje TTS:</span><span class="sxs-lookup"><span data-stu-id="950a2-130">For example, to specify a TTS prompt:</span></span>
    
   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  <span data-ttu-id="950a2-131">Para obtener más detalles acerca de estos cmdlets y ver una lista de los códigos de idioma para utilizar en el parámetro **TextToSpeechPrompt** , consulte [CsAnnouncement de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="950a2-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>
    
## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="950a2-132">Eliminar un anuncio para números sin asignar</span><span class="sxs-lookup"><span data-stu-id="950a2-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="950a2-133">Para eliminar un anuncio</span><span class="sxs-lookup"><span data-stu-id="950a2-133">To delete an announcement</span></span>

1. <span data-ttu-id="950a2-134">Inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios según se describe en **Configuración de permisos de delegado**.</span><span class="sxs-lookup"><span data-stu-id="950a2-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="950a2-135">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="950a2-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="950a2-p108">Muestre todos los anuncios de su organización. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="950a2-p108">List all the announcements in your organization. At the command line, run:</span></span>
     
   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="950a2-p109">En la lista resultante, busque el anuncio que desea eliminar y copie el GUID. A continuación, en la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="950a2-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
   ```

    <span data-ttu-id="950a2-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="950a2-140">For example:</span></span>
    
   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="950a2-141">Para obtener más información acerca de las opciones más, consulte [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) y [CsAnnouncement de quitar](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="950a2-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="950a2-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="950a2-142">See also</span></span>

#### 

[<span data-ttu-id="950a2-143">Crear o eliminar un anuncio de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="950a2-143">Create or delete an announcement in Skype for Business Server 2015</span></span>](create-an-announcement.md)
#### 

[<span data-ttu-id="950a2-144">CsAnnouncementFile de importación</span><span class="sxs-lookup"><span data-stu-id="950a2-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)
  
[<span data-ttu-id="950a2-145">Nueva CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="950a2-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)
  
[<span data-ttu-id="950a2-146">Quitar CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="950a2-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)
  
[<span data-ttu-id="950a2-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="950a2-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

