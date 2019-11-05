---
title: Realizar una investigación de eDiscovery en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Conozca los pasos que debe seguir cuando necesite realizar una investigación de eDiscovery, como por ejemplo, cuando debe entregar toda la información almacenada electrónicamente para procedimientos legales.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27dac8bd72eaac581022431c3786b0f7487d137c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968051"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Realizar una investigación de eDiscovery en Microsoft Teams
============================

Las grandes empresas suelen estar expuestas a un procedimiento legal de alta multa que exige el envío de toda la información almacenada electrónicamente (ESI).

Todos los equipos 1:1 o chats grupales se registran en el diario de los buzones de los usuarios respectivos, y todos los mensajes de canal estándar se registran en el buzón del grupo que representa al equipo. Los archivos cargados en canales estándar están cubiertos por la funcionalidad de eDiscovery para SharePoint Online y OneDrive para la empresa.

> [!NOTE]
> eDiscovery de los mensajes y los archivos de los [canales privados](private-channels.md) funcionan de manera diferente que en los canales estándar. Para obtener más información, consulte [eDiscovery of Private Channels](#ediscovery-of-private-channels).

1.  Para realizar una investigación de eDiscovery con el contenido de Microsoft Teams, revise el paso 1 de [este](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) vínculo.

2.  Los datos de Microsoft Teams aparecerán como mensajes instantáneos o conversaciones en la salida de la exportación de eDiscovery de Excel, y puede montar el. PST en Outlook para ver los mensajes después de la exportación.

    Al montar el. PST para el equipo, tenga en cuenta que todas las conversaciones se guardan en la carpeta chat de equipo en historial de conversaciones. El título del mensaje se alinea con el equipo y el canal. Desde revisar la imagen a continuación, puede ver este mensaje de Bob que ha expuesto el canal de Project 7 Standard del equipo de especificaciones de fabricación.

    ![Captura de pantalla de una carpeta de chat de equipo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Para ver las conversaciones privadas en el buzón de un usuario, también se encuentran dentro de la carpeta chat de equipo en historial de conversaciones.

## <a name="ediscovery-of-guest-to-guest-chats"></a>eDiscovery de conversaciones de invitado a invitado

Sin un buzón de correo, los chats entre invitados (1xN chats en los que no hay usuarios de inquilinos domésticos) no se indizarán y, como resultado, no se incluirían en eDiscovery. Para facilitar la exhibición de mensajes instantáneos a los chats entre invitados, se crea un buzón de correo basado en la nube (o un buzón de correo fantasma) para almacenar los datos de 1xN. Una vez que los datos de la conversación de equipos se almacenan en el buzón basado en la nube, están indizados para eDiscovery y la búsqueda de contenido de cumplimiento.

En la ilustración siguiente se muestra cómo funciona eDiscovery para los chats entre invitados en los que no hay un buzón.

![invitado a invitado: chats con sin buzón de correo](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a>eDiscovery de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. El formato de los títulos de los registros indica el canal privado desde el que se enviaron.

Como cada canal privado tiene su propia colección de sitios de SharePoint que es independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo principal.

Teams no admite eDiscovery de un solo canal, de modo que se debe buscar en todo el equipo. Para realizar una búsqueda en eDiscovery de contenido en un canal privado, busque en el equipo, la colección de sitios asociada al canal privado (para incluir archivos) y buzones de miembros de canales privados (para incluir mensajes).

Siga estos pasos para identificar los archivos y mensajes de un canal privado para incluirlos en la búsqueda de eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir archivos de canal privado en una búsqueda de eDiscovery

Antes de realizar estos pasos, instale el [Shell de administración de SharePoint Online y conéctese a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas a los canales privados en el equipo.

    ```
    Get-SPOSite
    ```
2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas a los canales privados en el equipo y el identificador del grupo de equipos primario.

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Para cada uno de los IDENTIFICADOres de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado pertinentes, donde $groupID es el identificador de grupo del equipo.

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensajes de canal privado en una búsqueda de eDiscovery

Antes de realizar estos pasos, asegúrese de que tiene instalada la [última versión del módulo de PowerShell de Teams](teams-powershell-overview.md) .

1. Ejecute lo siguiente para obtener una lista de canales privados en el equipo.

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Ejecute lo siguiente para obtener una lista de miembros del canal privado.

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Incluya los buzones de todos los miembros de cada canal privado del equipo como parte de la consulta de búsqueda de eDiscovery.

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)