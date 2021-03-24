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
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Crear o eliminar un anuncio en Skype Empresarial Server

Cree o elimine anuncios para la aplicación Announcement en Skype Empresarial Server Telefonía IP empresarial. Esto afecta al modo en que se controlan las llamadas a números sin signo.

Cuando configura anuncios, en realidad está configurando la forma en que desea administrar las llamadas a números no asignados. Reproduzca un mensaje, que puede tratarse de un archivo de audio o de un archivo de texto a voz (TTS), o bien transferir la llamada a un destino determinado sin reproducir ningún mensaje.

Cree los anuncios antes de definir la tabla de números sin asignar. Ejecute este paso para todos los anuncios que usan un mensaje de audio, un mensaje TTS o no tienen mensaje.

En este tema se describe cómo importar y crear anuncios. Para obtener información sobre la asignación de anuncios en la tabla de números no asignados, consulte [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Crear un nuevo anuncio para números sin signo

Para crear un anuncio, debe seguir estos pasos:

1. Para mensajes de audio, grabe el archivo de audio con su aplicación de grabación de audio preferida.

2. Para mensajes de audio, ejecute el cmdlet **Import-CsAnnouncementFile** para importar el contenido del archivo de audio al almacén de archivos.

3. Ejecute el cmdlet **New-CsAnnouncement** para crear y asignar un nombre al anuncio. Lleve a cabo este paso para crear anuncios con un mensaje de audio, con un mensaje TTS o sin mensaje.

    > [!TIP]
    > Puede que le interese crear un anuncio sin mensaje; por ejemplo, si quiere transferir las llamadas a un destino específico sin reproducir un mensaje.

4. Asigne el nuevo anuncio a un intervalo de números en la tabla de números no asignados.

### <a name="to-create-a-new-announcement"></a>Para crear un anuncio

1. Para mensajes de audio, cree el archivo de audio.

2. Inicie sesión en el equipo donde skype empresarial Server Management Shell está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegate Setup Permissions**.

3. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.

4. Para mensajes de audio, ejecute:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Ejecute: 

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Para transferir llamadas al correo de voz, escriba el parámetro SIPAddress en el formato sip:nombre_usuario@nombre_dominio;opaque=app:voicemail (por ejemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir llamadas a un número de teléfono, escriba el parámetro SIPAddress en el formato sip:número@nombre_dominio;user=phone (por ejemplo, sip:+ 14255550121@contoso.com;user=phone).

    Por ejemplo, para especificar un mensaje de audio:

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Por ejemplo, para especificar un mensaje TTS:

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Para obtener más información acerca de estos cmdlets y ver una lista de los códigos de idioma que se usarán en el parámetro **TextToSpeechPrompt,** vea [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Eliminar un anuncio para números sin signo

### <a name="to-delete-an-announcement"></a>Para eliminar un anuncio

1. Inicie sesión en el equipo donde skype empresarial Server Management Shell está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegate Setup Permissions**.

2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.

3. Muestre todos los anuncios de su organización. En la línea de comandos, ejecute:

   ```powershell
   Get-CsAnnouncement
   ```

4. En la lista resultante, busque el anuncio que desea eliminar, y copie el GUID. A continuación, en la línea de comandos, ejecute:

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Por ejemplo:

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Para obtener más información sobre más opciones, [vea Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) y [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>Ver también

[Crear o eliminar un anuncio en Skype Empresarial Server](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)