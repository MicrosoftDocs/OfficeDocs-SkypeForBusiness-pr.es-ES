---
title: Realizar una investigación de exhibición de documentos electrónicos sobre contenido
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre qué hacer cuando necesita realizar exhibición de documentos electrónicos, por ejemplo, cuando necesita enviar toda la información almacenada electrónicamente para los procedimientos legales.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b9010bb233438029d6e755cf1fcd8b78b7cba6eb
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486170"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Realizar una investigación de eDiscovery en Microsoft Teams

Las grandes empresas suelen estar expuestas a procedimientos legales con penas elevadas que exigen el envío de toda la información almacenada electrónicamente (ESI). Microsoft Teams contenido se puede buscar y usar durante las investigaciones de exhibición de documentos electrónicos.

## <a name="overview"></a>Información general

Todos Microsoft Teams chats de grupo o 1:1 se pasan por diario a los buzones de los usuarios respectivos. Todos los mensajes de canal estándar se envían en diario al buzón de grupo que representa al equipo. Los archivos cargados en canales estándar se cubren en la funcionalidad de exhibición de documentos electrónicos para SharePoint Online y OneDrive para la Empresa.

La exhibición de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, vea [Exhibición de documentos electrónicos de canales privados.](#ediscovery-of-private-channels)

No todo Teams contenido es eDiscoverable. En la tabla siguiente se muestran los tipos de contenido que puede buscar con herramientas de exhibición de documentos electrónicos de Microsoft:

| Tipo de contenido | eDiscoverable | Notas |
|:--- | :--- |:--- |
|Grabaciones de audio | No | |
|Contenido de la tarjeta|Sí|Vea [Buscar contenido de tarjeta](#search-for-card-content) para obtener más información.|
|Vínculos de chat | Sí | |
|Mensajes de chat | Sí |Esto incluye contenido en Teams, chats 1:1, chats grupales 1:N y chats con participantes de usuario invitado.  |
|Fragmentos de código | No | |
|Mensajes editados | Sí | Si el usuario está en espera, también se conservan las versiones anteriores de los mensajes editados. |
|Emojis, GIF y adhesivos | Sí | |
|Imágenes en línea | Sí | |
|Conversaciones de mensajería instantánea de reunión | Sí | |
|Metadatos de<sup>la reunión 1</sup> | Sí |  |
|Nombre del canal | No | |
|Mensajes de canal privado | Sí | |
|Comillas | Sí | Se puede buscar contenido entre comillas. Sin embargo, los resultados de la búsqueda no indican que el contenido se citó. |
|Reacciones (como me gusta, corazones y otras reacciones) | No | |
|Asunto | Sí | |
|Tablas | Sí | |
|Notificaciones de fuentes | No | |
|||

<sup>1 Los</sup> metadatos de reunión (y llamada) incluyen lo siguiente:

- Hora y duración de inicio y finalización de la reunión
- Reunión unirse y dejar eventos para cada participante
- VOIP join/calls
- Unirse anónimo
- Unión de usuarios federados
- Unirse al usuario invitado

  La imagen muestra un ejemplo de metadatos de reunión.

  > [!div class="mx-imgBorder"]
  > ![La imagen es de los metadatos de reunión de los registros CVR.](media/conversationOption3.png)

Este es un ejemplo de una conversación de mensajería instantánea entre los participantes durante la reunión.

![Conversación entre participantes en Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversación entre participantes en los resultados de búsqueda de exhibición de documentos electrónicos.](media/MeetingImConversation2.png)

Para obtener más información sobre cómo llevar a cabo una investigación de exhibición de documentos electrónicos, vea Introducción a [eDiscovery principal.](/microsoft-365/compliance/get-started-core-ediscovery)

Microsoft Teams datos aparecerán como mensajería instantánea o Conversaciones en el Excel de exportación de exhibición de documentos electrónicos. Puede abrir el `.pst` archivo en Outlook ver esos mensajes después de exportarlos.

Al ver el archivo .pst para el equipo, todas las conversaciones se encuentran en la carpeta Chat de grupo en Historial de conversaciones. El título del mensaje contiene el nombre del equipo y el nombre del canal. Por ejemplo, en la imagen siguiente se muestra un mensaje de Bob que envía un mensaje al canal Project 7 estándar del equipo de Especificaciones de fabricación.

![Captura de pantalla de una carpeta chat de grupo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Los chats privados en el buzón de un usuario se almacenan en la carpeta Chat de grupo en Historial de conversaciones.

## <a name="ediscovery-of-private-channels"></a>eDiscovery de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Dado que cada canal privado tiene su propio sitio de SharePoint independiente del sitio de grupo principal, los archivos de un canal privado se administran independientemente del equipo principal.

Teams no admite la búsqueda de exhibición de documentos electrónicos de un solo canal dentro de un equipo, por lo que se debe buscar a todo el equipo. Para realizar una búsqueda de exhibición de documentos electrónicos de contenido en un canal privado, busque en todo el equipo, la colección de sitios asociada con el canal privado (para incluir archivos) y los buzones de los miembros del canal privado (para incluir mensajes).

Siga estos pasos para identificar archivos y mensajes en un canal privado para incluirlos en la búsqueda de exhibición de documentos electrónicos.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir archivos de canal privado en una búsqueda de exhibición de documentos electrónicos

Antes de realizar estos pasos, instale SharePoint Shell de administración en línea [y conéctese a SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Ejecute lo siguiente para obtener una lista de todas SharePoint colecciones de sitios asociadas con canales privados en el equipo.

    ```PowerShell
    Get-SPOSite
    ```

2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios SharePoint asociadas con canales privados en el equipo y el id. de grupo de grupo principal.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Para cada id. de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado relevantes, donde $groupID es el id. de grupo del equipo.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensajes de canal privado en una búsqueda de exhibición de documentos electrónicos

Antes de realizar estos pasos, asegúrese de que tiene instalada la versión más reciente [Teams módulo de PowerShell.](teams-powershell-overview.md)

1. Ejecute el siguiente comando para obtener una lista de canales privados en el equipo.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Ejecute el siguiente comando para obtener una lista de los miembros del canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Incluya los buzones de todos los miembros de cada canal privado en el equipo como parte de la consulta [de búsqueda de exhibición de documentos electrónicos.](/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Buscar contenido para usuarios invitados

Puede usar herramientas de exhibición de documentos electrónicos para buscar Teams contenido relacionado con los usuarios invitados de su organización. Teams contenido de chat asociado a un usuario invitado se conserva en una ubicación de almacenamiento basada en la nube y se puede buscar con eDiscovery. Esto incluye buscar contenido en conversaciones de chat 1:1 y 1:N en las que un usuario invitado es un participante con otros usuarios de su organización. También puede buscar mensajes de canal privado en los que un usuario invitado es un participante y buscar contenido en conversaciones de chat de *invitado:invitado,* donde los únicos participantes son usuarios invitados.

Para buscar contenido para los usuarios invitados:

1. Conectar a Azure AD PowerShell. Para obtener instrucciones, vea la sección "Conectar con Azure Active Directory PowerShell" en Conectar para Microsoft 365 [con PowerShell.](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Asegúrese de completar los pasos 1 y 2 en el tema anterior.

2. Después de conectarse correctamente a Azure AD PowerShell, ejecute el siguiente comando para mostrar el nombre principal de usuario (UPN) para todos los usuarios invitados de su organización. Debe usar el UPN del usuario invitado al crear la búsqueda en el paso 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > En lugar de mostrar una lista de nombres principales de usuario en la pantalla del equipo, puede redirigir el resultado del comando a un archivo de texto. Puede hacerlo anexando al `> filename.txt` comando anterior. El archivo de texto con los nombres principales de usuario se guardará en la carpeta actual.

3. En otra ventana Windows PowerShell, conéctese a PowerShell del Centro de & cumplimiento. Para obtener instrucciones, [vea Conectar a PowerShell & Centro de cumplimiento](/powershell/exchange/connect-to-scc-powershell). Puede conectarse con o sin la autenticación multifactor.

4. Cree una búsqueda de contenido que busque todo el contenido (como mensajes de chat y mensajes de correo electrónico) en el que el usuario invitado especificado fuera un participante ejecutando el comando siguiente.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Por ejemplo, para buscar contenido asociado con la usuario invitada Sara Davis, ejecutaría el siguiente comando.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Para obtener más información sobre el uso de PowerShell para crear búsquedas de contenido, vea [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Ejecute el comando siguiente para iniciar la búsqueda de contenido que creó en el paso 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic **en Mostrar toda la búsqueda** de  >  **contenido.**

7. En la lista de búsquedas, seleccione la búsqueda que creó en el paso 4 para mostrar la página desplegable.

8. En la página desplegable, puede hacer lo siguiente:

   - Haga **clic en Ver resultados** para ver los resultados de la búsqueda y obtener una vista previa del contenido.

   - Junto al **campo Consulta,** haga clic **en Editar** para editar y, a continuación, vuelva a ejecutar la búsqueda. Por ejemplo, puede agregar una consulta de búsqueda para restringir los resultados.

   - Haga **clic en Exportar resultados** para exportar y descargar los resultados de búsqueda.

## <a name="search-for-card-content"></a>Buscar contenido de tarjeta

El contenido de la tarjeta generado por las aplicaciones en Teams canales, chats 1:1 y chats 1xN se almacena en buzones y se puede buscar. Una *tarjeta es* un contenedor de interfaz de usuario para fragmentos cortos de contenido. Las tarjetas pueden tener varias propiedades y datos adjuntos, y pueden incluir botones que pueden desencadenar acciones de tarjeta. Para obtener más información, vea [Tarjetas](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Al igual que Teams contenido, donde se almacena el contenido de la tarjeta se basa en el lugar donde se usó la tarjeta. El contenido de las tarjetas usadas en un canal Teams se almacena en el buzón Teams grupo. El contenido de la tarjeta para chats 1:1 y 1xN se almacena en los buzones de los participantes del chat.

Para buscar contenido de tarjeta, puede usar las `kind:microsoftteams` condiciones de búsqueda o `itemclass:IPM.SkypeTeams.Message` o. Al revisar los resultados de la búsqueda, el contenido de la tarjeta generado por los bots en un canal de Teams tiene la propiedad de correo electrónico **Remitente/Autor** como , donde está el nombre de la aplicación que generó el contenido `<appname>@teams.microsoft.com` de la `appname` tarjeta. Si un usuario generó contenido de tarjeta, el valor de **Remitente/Autor** identifica al usuario.

Al ver el contenido de la tarjeta en los resultados de búsqueda de contenido, el contenido aparece como datos adjuntos al mensaje. El archivo adjunto se denomina `appname.html` , donde está el nombre de la aplicación que `appname` generó el contenido de la tarjeta. Las siguientes capturas de pantalla muestran cómo aparece el contenido de la tarjeta (para una aplicación denominada Asana) en Teams y en los resultados de una búsqueda.

**Contenido de tarjeta en Teams**

![Contenido de la tarjeta en Teams de canal](media/CardContentTeams.png)

**Contenido de la tarjeta en los resultados de búsqueda**
  
![Mismo contenido de tarjeta en los resultados de una búsqueda de contenido](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Para mostrar imágenes del contenido de la tarjeta en los resultados de búsqueda en este momento (como las marcas de verificación de la captura de pantalla anterior), debe haber iniciado sesión en Teams (en una pestaña diferente en la misma sesión del explorador que usa para ver los resultados de https://teams.microsoft.com) búsqueda. En caso contrario, se mostrarán marcadores de posición de imagen.

## <a name="related-topics"></a>Temas relacionados

- [Microsoft 365 de exhibición de documentos electrónicos](/microsoft-365/compliance/ediscovery)
- [Introducción a eDiscovery principal](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams flujo de trabajo en Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
