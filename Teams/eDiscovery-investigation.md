---
title: Realizar una investigación de exhibición de documentos electrónicos del contenido
description: Obtenga información sobre qué hacer cuando necesita realizar eDiscovery, por ejemplo, cuando necesita enviar toda la información almacenada electrónicamente para un procedimiento legal.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- ediscovery
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a44245d31e6fc9f4b58c17832e596c6d73b56635
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046660"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Realizar una investigación de eDiscovery en Microsoft Teams

Las grandes empresas suelen estar expuestas a procedimientos judiciales de alta sanción que exigen la presentación de toda la información almacenada electrónicamente (ESI). El contenido de Microsoft Teams se puede buscar y usar durante las investigaciones de exhibición de documentos electrónicos.

## <a name="overview"></a>Información general

Todos los chats grupales o de Microsoft Teams 1:1 se realizan en diario en los buzones de los respectivos usuarios. Todos los mensajes de canal estándar se pasan por el buzón de grupo que representa el equipo. Los archivos cargados en canales estándar están cubiertos por la funcionalidad de exhibición de documentos electrónicos para SharePoint Online y OneDrive para la Empresa.

eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels. Para obtener más información, vea [eDiscovery of private channels (Exhibición de canales privados](#ediscovery-of-private-and-shared-channels)).

No todo el contenido de Teams es eDiscoverable. En la tabla siguiente se muestran los tipos de contenido que puede buscar con las herramientas de exhibición de documentos electrónicos de Microsoft:

|**Tipo de contenido**|**Notas**|
|:---------------|:--------|
|Grabaciones de audio||
|Contenido de la tarjeta|Vea [Buscar contenido de tarjeta](#search-for-card-content) para obtener más información.|
|Vínculos de chat||
|Mensajes de chat|Esto incluye el contenido de los canales estándar de Teams, los chats individuales, los chats grupales 1:N y los chats con los participantes invitados.|
|Fragmentos de código||
|Mensajes editados|Si el usuario está en espera, también se conservan las versiones anteriores de los mensajes editados.|
|Emojis, GIF y adhesivos||
|Imágenes alineadas||
|Componentes de bucle|El contenido de un componente de bucle se guarda en un archivo .fluid que se almacena en el OneDrive para la Empresa cuenta del usuario que envía el componente de bucle. Esto significa que tiene que incluir OneDrive como origen de datos al buscar contenido en componentes de bucle.|
|Conversaciones de mensajería instantánea de la reunión||
|Metadatos<sup>de reunión 1</sup>||
|Nombre del canal||
|Presupuestos|El contenido entrecomillado se puede buscar. Sin embargo, los resultados de la búsqueda no indican que se ha citado el contenido.|
|Reacciones (como me gusta, corazones y otras reacciones)|Las reacciones son compatibles con todos los clientes comerciales después del 1 de junio de 2022. Las reacciones anteriores a esta fecha no están disponibles para eDiscovery. El soporte en la nube de la administración pública está previsto. No hay ningún apoyo legal para las reacciones.|
|Asunto||
|Mesas||
|Clip de vídeo de Teams (TVC)|Busca en TVC con la palabra clave "Video-Clip" y "guardar como" un archivo de .mp4 para cada archivo adjunto de TVC haciendo clic con el botón derecho en la vista previa (la búsqueda por palabra clave estará disponible en octubre de 2022). Los datos de TVC se pueden detectar en [conjuntos de revisión de exhibición](/microsoft-365/compliance/add-data-to-review-set) de documentos electrónicos.

<sup>1</sup> Los metadatos de reunión (y llamada) incluyen lo siguiente:

- Hora de inicio y finalización de la reunión y duración
- Unirse a la reunión y dejar eventos para cada participante
- Combinaciones/llamadas VOIP
- Combinaciones anónimas
- Combinaciones de usuarios federados
- Combinaciones de usuarios invitados

Este es un ejemplo de una conversación de chat entre participantes durante una reunión.

![Conversación entre participantes en Teams.](media/MeetingIMConversations.png)

Este es un ejemplo de la copia de cumplimiento de la misma conversación de chat vista en una herramienta de exhibición de documentos electrónicos.

![Conversación entre participantes en los resultados de búsqueda de eDiscovery.](media/MeetingImConversation2.png)

Aquí tiene un ejemplo de los metadatos de la reunión.

![Los metadatos de la reunión de la copia de cumplimiento.](media/conversationOption3.png)

Para obtener más información sobre cómo llevar a cabo una investigación de exhibición de documentos electrónicos, vea [Introducción a la exhibición de documentos electrónicos (estándar).](/microsoft-365/compliance/get-started-core-ediscovery)

Los datos de Microsoft Teams aparecerán como mensajería instantánea o conversaciones en el resultado de exportación de eDiscovery de Excel. Puede abrir el `.pst` archivo en Outlook para ver esos mensajes después de exportarlos.

Al ver el archivo .pst para el equipo, todas las conversaciones se encuentran en la carpeta Chat del equipo, en Historial de conversaciones. El título del mensaje contiene el nombre del equipo y el nombre del canal. Por ejemplo, la imagen siguiente muestra un mensaje de Bob que le envía un mensaje al canal estándar de Project 7 del equipo de Especificaciones de fabricación.

![Captura de pantalla de una carpeta de chat de equipo en el buzón de un usuario en Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Los chats privados en el buzón de un usuario se almacenan en la carpeta Chat de equipo, en Historial de conversaciones.

## <a name="ediscovery-of-private-and-shared-channels"></a>Exhibición de canales privados y compartidos

Las copias de cumplimiento de los mensajes en canales privados y compartidos se envían a diferentes buzones según el tipo de canal. Esto significa que tiene que buscar en diferentes ubicaciones de buzón en función del tipo de canal al que pertenece un usuario.

- **Canales privados**. Las copias de cumplimiento se envían al buzón de todos los miembros de los miembros del canal privado. Esto significa que tiene que buscar en el buzón de usuario al buscar contenido en mensajes de canal privado.

- **Canales compartidos**. Las copias de cumplimiento se envían a un buzón del sistema que está asociado con el equipo primario. Como Teams no admite una búsqueda de exhibición de documentos electrónicos de un único buzón del sistema para un canal compartido, tiene que buscar el buzón del equipo primario (seleccionando el nombre del buzón del equipo) al buscar contenido de mensajes en canales compartidos.

Cada canal privado y compartido tiene su propio sitio de SharePoint que es independiente del sitio de grupo primario. Esto significa que los archivos en canales privados y compartidos se almacenan en su propio sitio y se administran de forma independiente del equipo primario. Esto significa que debe identificar y buscar en el sitio específico asociado a un canal al buscar contenido en archivos y datos adjuntos de mensajes de canal.

Use las siguientes secciones para identificar el canal privado o compartido que se va a incluir en la búsqueda de exhibición de documentos electrónicos.

### <a name="identifying-the-members-of-a-private-channel"></a>Identificación de los miembros de un canal privado

Use el procedimiento descrito en esta sección para identificar los miembros de un canal privado, de modo que pueda usar herramientas de exhibición de documentos electrónicos para buscar contenido en el buzón del miembro en mensajes de canal privado.

Antes de realizar estos pasos, asegúrese de que tiene instalada la [versión más reciente del módulo PowerShell de Teams](teams-powershell-overview.md) .

1. Ejecute el siguiente comando para obtener el id. de grupo del equipo que contiene los canales compartidos que desea buscar.

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > Ejecute el cmdlet **Get-Team** sin ningún parámetro para mostrar una lista de todos los equipos de su organización. La lista contiene los nombres de grupo Id. y DisplayName de cada equipo.

2. Ejecute el siguiente comando para obtener una lista de canales privados en el equipo primario. Use el id. de grupo para el equipo que obtuvo en el paso 1.

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. Ejecute el siguiente comando para obtener una lista de propietarios y miembros del canal privado para un canal privado específico.

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. Incluya los buzones de propietarios y miembros de un canal privado como parte de la consulta de búsqueda de exhibición de documentos [electrónicos en eDiscovery (Estándar)](/microsoft-365/compliance/search-for-content-in-core-ediscovery) o al [identificar y recopilar contenido custodio en eDiscovery (Premium).](/microsoft-365/compliance/add-custodians-to-case)

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>Identificar el sitio de SharePoint para canales privados y compartidos

Como se ha explicado anteriormente, los archivos compartidos en canales privados y compartidos (y archivos adjuntos a los mensajes del canal) se almacenan en la colección de sitios asociada con el canal. Use el procedimiento descrito en esta sección para identificar la dirección URL del sitio asociado a un canal privado o compartido específico. Después, puede usar herramientas de exhibición de documentos electrónicos para buscar contenido en el sitio.

Antes de realizar estos pasos, [instale el Shell de administración de SharePoint Online y conéctese a SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Si lo desea, ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas con canales compartidos en el equipo primario.

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > La convención de nomenclatura de la dirección URL de un sitio asociado con canales privados y compartidos es `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`. Por ejemplo, la dirección URL del canal compartido denominado "Colaboración con partners", que se encuentra en el equipo primario "Equipo de ingenieros" de la organización Contoso es `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`.

2. Ejecute los siguientes comandos de PowerShell para mostrar la dirección URL de todos los sitios de SharePoint asociados con los canales privados y compartidos de su organización. El resultado del script también incluye el id. de grupo del equipo primario, que necesita para ejecutar los comandos en el paso 3.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > Los sitios de SharePoint para canales privados creados antes del 28 de junio de 2021 usan el valor `"TEAMCHANNEL#0"` para el id. de plantilla personalizada. Para mostrar los canales privados creados después de esta fecha, use el valor `"TEAMCHANNEL#1"` al ejecutar los dos scripts anteriores. Los canales compartidos solo usan el valor de `"TEAMCHANNEL#1"`.

3. Para cada equipo primario, ejecute los siguientes comandos de PowerShell para identificar los sitios del canal privado y compartido, donde `$groupID` se encuentra el id. de grupo del equipo primario.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. Incluya el sitio asociado a un canal privado o compartido como parte de la [consulta de búsqueda de exhibición de documentos electrónicos en eDiscovery (Estándar)](/microsoft-365/compliance/search-for-content-in-core-ediscovery) o al [identificar y recopilar contenido custodio en eDiscovery (Premium).](/microsoft-365/compliance/add-custodians-to-case)

## <a name="search-for-content-for-guest-users"></a>Buscar contenido para usuarios invitados

Puede usar las herramientas de exhibición de documentos electrónicos para buscar contenido de Teams relacionado con los usuarios invitados de su organización. El contenido de chat de Teams asociado a un usuario invitado se conserva en una ubicación de almacenamiento basada en la nube y se puede buscar con eDiscovery. Esto incluye la búsqueda de contenido en conversaciones de chat 1:1 y 1:N en las que un usuario invitado es un participante con otros usuarios de su organización. También puede buscar mensajes de canal privados en los que un usuario invitado sea un participante y buscar contenido en conversaciones de *chat invitado:invitado* donde los únicos participantes son usuarios invitados.

Para buscar contenido para los usuarios invitados:

1. Conéctese a PowerShell de Azure AD. Para obtener instrucciones, consulte la sección "Conectarse con PowerShell de Azure Active Directory" en [Conectarse a Microsoft 365 con PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Asegúrese de completar los pasos 1 y 2 del artículo anterior.

2. Después de conectarse correctamente a PowerShell de Azure AD, ejecute el siguiente comando para mostrar el nombre principal de usuario (UPN) para todos los usuarios invitados de la organización. Debe usar el UPN del usuario invitado al crear la búsqueda en el paso 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > En lugar de mostrar una lista de nombres principales de usuario en la pantalla del equipo, puede redirigir la salida del comando a un archivo de texto. Para ello, anexe `> filename.txt` al comando anterior. El archivo de texto con los nombres principales de usuario se guardará en la carpeta actual.

3. En una ventana de Windows PowerShell diferente, conéctese a PowerShell del Centro de cumplimiento de & seguridad. Para obtener instrucciones, consulte [Conectarse a PowerShell del Centro de cumplimiento & seguridad](/powershell/exchange/connect-to-scc-powershell). Puede conectarse con o sin usar la autenticación multifactor.

4. Cree una búsqueda de contenido que busque todo el contenido (como mensajes de chat y mensajes de correo electrónico) en el que el usuario invitado especificado era participante mediante la ejecución del siguiente comando.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Por ejemplo, para buscar contenido asociado con la usuario invitada Sara Davis, ejecute el siguiente comando.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Para obtener más información sobre el uso de PowerShell para crear búsquedas de contenido, vea [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Ejecute el siguiente comando para iniciar la búsqueda de contenido que creó en el paso 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com) continuación, haga clic en **Mostrar toda** >  la **búsqueda de contenido**.

7. En la lista de búsquedas, seleccione la búsqueda que creó en el paso 4 para mostrar la página del control flotante.

8. En la página del control flotante, puede hacer lo siguiente:

   - Haga clic en **Ver resultados** para ver los resultados de la búsqueda y obtener una vista previa del contenido.

   - Junto al campo **Consulta** , haga clic en **Editar** para editar y vuelva a ejecutar la búsqueda. Por ejemplo, puede agregar una consulta de búsqueda para restringir los resultados.

   - Haga clic en **Exportar resultados** para exportar y descargar los resultados de búsqueda.

## <a name="search-for-card-content"></a>Buscar contenido de tarjeta

El contenido de la tarjeta generado por las aplicaciones en los canales de Teams, los chats uno a uno y los chats 1xN se almacena en los buzones y se puede buscar. Una *tarjeta* es un contenedor de la interfaz de usuario para fragmentos cortos de contenido. Las tarjetas pueden tener varias propiedades y datos adjuntos, y pueden incluir botones que pueden desencadenar acciones de tarjeta. Para obtener más información, vea [Tarjetas](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Al igual que otros contenidos de Teams, el lugar donde se almacena el contenido de la tarjeta se basa en el lugar donde se usó la tarjeta. El contenido de las tarjetas usadas en un canal de Teams se almacena en el buzón del grupo de Teams. El contenido de la tarjeta para los chats 1:1 y 1xN se almacena en los buzones de los participantes del chat.

Para buscar contenido de tarjeta, puede usar las `kind:microsoftteams` condiciones o `itemclass:IPM.SkypeTeams.Message` las condiciones de búsqueda. Al revisar los resultados de la búsqueda, el contenido de la tarjeta generado por los bots en un canal de Teams tiene la propiedad de correo electrónico **Remitente/Autor** como `<appname>@teams.microsoft.com`, donde `appname` se encuentra el nombre de la aplicación que generó el contenido de la tarjeta. Si el contenido de la tarjeta lo generó un usuario, el valor de **Remitente/Autor** identifica al usuario.

Al ver el contenido de la tarjeta en los resultados de búsqueda de contenido, el contenido aparece como datos adjuntos en el mensaje. El archivo adjunto se denomina `appname.html`, donde `appname` es el nombre de la aplicación que generó el contenido de la tarjeta. Las siguientes capturas de pantalla muestran cómo aparece el contenido de la tarjeta (para una aplicación llamada Asana) en Teams y en los resultados de una búsqueda.

### <a name="card-content-in-teams"></a>Contenido de tarjeta en Teams

![Contenido de la tarjeta en el mensaje del canal de Teams.](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>Contenido de la tarjeta en los resultados de búsqueda

![El mismo contenido de tarjeta en los resultados de una búsqueda de contenido.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Para mostrar imágenes del contenido de la tarjeta en los resultados de búsqueda en este momento (como las marcas de verificación de la captura de pantalla anterior), debe haber iniciado sesión en Teams (en <https://teams.microsoft.com>) en una pestaña diferente en la misma sesión del explorador que usa para ver los resultados de búsqueda. En caso contrario, se mostrarán los marcadores de posición de imagen.

## <a name="ediscovery-in-federated-and-non-federated-environments"></a>Exhibición de documentos electrónicos en entornos federados y no federados

Los administradores pueden usar eDiscovery para buscar contenido en mensajes de chats en una reunión de Teams en entornos federados (denominados *acceso externo*) y no federados ( *denominados acceso de invitado*) en función de las siguientes restricciones:

- **Federado**: en una reunión de Teams con usuarios de su organización y usuarios de una organización externa (que tienen acceso externo en su organización), los administradores de ambas organizaciones pueden buscar contenido en los mensajes de chat de la reunión.

- **No federado**: en una reunión de Teams con usuarios de su organización y usuarios invitados, solo los administradores de la organización que hospedan la reunión de Teams pueden buscar contenido en los mensajes de chat de la reunión.

## <a name="related-topics"></a>Temas relacionados

- [Soluciones de exhibición de documentos electrónicos de Microsoft 365](/microsoft-365/compliance/ediscovery)
- [Introducción a la exhibición de documentos electrónicos (estándar)](/microsoft-365/compliance/get-started-core-ediscovery)
- [Flujo de trabajo de Teams en eDiscovery (Premium)](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
