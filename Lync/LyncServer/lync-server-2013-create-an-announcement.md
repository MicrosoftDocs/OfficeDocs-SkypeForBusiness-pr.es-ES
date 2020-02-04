---
title: 'Lync Server 2013: crear un anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a>Crear un anuncio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Para crear un anuncio, debe seguir estos pasos:

1.  Para mensajes de audio, grabe el archivo de audio con su aplicación de grabación de audio preferida.

2.  Para mensajes de audio, ejecute el cmdlet **Import-CsAnnouncementFile** para importar el contenido del archivo de audio al almacén de archivos.

3.  Ejecute el cmdlet **New-CsAnnouncement** para crear y asignar un nombre al anuncio. Lleve a cabo este paso para crear anuncios con un mensaje de audio, con un mensaje TTS o sin mensaje.
    
    <div>
    

    > [!TIP]  
    > Puede que le interese crear un anuncio sin mensaje; por ejemplo, si quiere transferir las llamadas a un destino específico sin reproducir un mensaje.

    
    </div>

4.  Asigne el nuevo anuncio a un intervalo de números en la tabla de números no asignados.

En este tema se describe cómo importar y crear anuncios. Para obtener más información sobre la asignación de anuncios en la tabla de números sin asignar, consulte [configurar la tabla de números sin asignar en Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

<div>

## <a name="to-create-a-new-announcement"></a>Para crear un anuncio

1.  Para mensajes de audio, cree el archivo de audio.

2.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

3.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

4.  Para mensajes de audio, ejecute:
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Ejecute:
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Para transferir llamadas al correo de voz, escriba el parámetro SIPAddress en el formato sip:nombre_usuario@nombre_dominio;opaque=app:voicemail (por ejemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir llamadas a un número de teléfono, escriba el parámetro SIPAddress en el formato sip:número@nombre_dominio;user=phone (por ejemplo, sip:+ 14255550121@contoso.com;user=phone).
    
    Por ejemplo, para especificar un mensaje de audio:
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Por ejemplo, para especificar un mensaje TTS:
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Para obtener más información sobre estos cmdlets y para ver una lista de los códigos de idioma que se usan en el parámetro **TextToSpeechPrompt** , vea [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).

</div>

<div>

## <a name="see-also"></a>Vea también


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[Nuevo: CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Configurar la tabla de números sin asignar en Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

