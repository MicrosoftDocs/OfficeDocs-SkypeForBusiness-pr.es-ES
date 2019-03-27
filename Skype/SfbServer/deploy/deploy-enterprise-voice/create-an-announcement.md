---
title: Crear o eliminar un anuncio en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Creación o eliminación de anuncios para la aplicación de anuncio en Skype para Business Server Enterprise Voice. Esto afecta a cómo se administran las llamadas a números sin asignar.
ms.openlocfilehash: cf6fc0ce754e30e4d52e968dc3a167bbe87a5a83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885578"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Crear o eliminar un anuncio en Skype para Business Server

Creación o eliminación de anuncios para la aplicación de anuncio en Skype para Business Server Enterprise Voice. Esto afecta a cómo se administran las llamadas a números sin asignar.

Cuando configura anuncios, en realidad está configurando la forma en que desea administrar las llamadas a números no asignados. Reproduzca un mensaje, que puede tratarse de un archivo de audio o de un archivo de texto a voz (TTS), o bien transferir la llamada a un destino determinado sin reproducir ningún mensaje.

Cree los anuncios antes de definir la tabla de números sin asignar. Ejecute este paso para todos los anuncios que usan un mensaje de audio, un mensaje TTS o no tienen mensaje.

En este tema se describe cómo importar y crear anuncios. Para obtener información sobre la asignación de anuncios en la tabla de números no asignados, consulte [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Crear un nuevo anuncio para números sin asignar

Para crear un anuncio, debe seguir estos pasos:

1. Para mensajes de audio, grabe el archivo de audio con su aplicación de grabación de audio preferida.

2. Para mensajes de audio, ejecute el cmdlet **Import-CsAnnouncementFile** para importar el contenido del archivo de audio al almacén de archivos.

3. Ejecute el cmdlet **New-CsAnnouncement** para crear y asignar un nombre al anuncio. Lleve a cabo este paso para crear anuncios con un mensaje de audio, con un mensaje TTS o sin mensaje.

    > [!TIP]
    > Puede que le interese crear un anuncio sin mensaje; por ejemplo, si quiere transferir las llamadas a un destino específico sin reproducir un mensaje.

4. Asigne el nuevo anuncio a un intervalo de números en la tabla de números no asignados.

### <a name="to-create-a-new-announcement"></a>Para crear un anuncio

1. Para mensajes de audio, cree el archivo de audio.

2. Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegar permisos de instalación**.

3. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

4. Para mensajes de audio, ejecute:

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Ejecute:

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Para transferir llamadas al correo de voz, escriba el parámetro SIPAddress en el formato sip:nombre_usuario@nombre_dominio;opaque=app:voicemail (por ejemplo, sip:bob@contoso.com;opaque=app:voicemail). Para transferir llamadas a un número de teléfono, escriba el parámetro SIPAddress en el formato sip:número@nombre_dominio;user=phone (por ejemplo, sip:+ 14255550121@contoso.com;user=phone).

    Por ejemplo, para especificar un mensaje de audio:

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Por ejemplo, para especificar un mensaje TTS:

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Para obtener más detalles acerca de estos cmdlets y para ver una lista de los códigos de idioma que usar en el parámetro **TextToSpeechPrompt** , consulte [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Eliminar un anuncio para números sin asignar

### <a name="to-delete-an-announcement"></a>Para eliminar un anuncio

1. Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegar permisos de instalación**.

2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

3. Muestre todos los anuncios de su organización. En la línea de comandos, ejecute:

   ```
   Get-CsAnnouncement
   ```

4. En la lista resultante, busque el anuncio que desea eliminar y copie el GUID. A continuación, en la línea de comandos, ejecute:

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Por ejemplo:

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Para obtener información detallada acerca de las opciones más, vea [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) y [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>Consulte también

[Crear o eliminar un anuncio en Skype para Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[Nueva CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

