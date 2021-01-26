---
title: Usar la búsqueda de contenido en Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Obtenga información sobre el uso de la búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 para buscar contenido de Microsoft Teams almacenado en Exchange Online, SharePoint Online, OneDrive para la Empresa y OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980444"
---
<a name="use-content-search-in-microsoft-teams"></a>Usar la búsqueda de contenido en Microsoft Teams
=====================================

> [!NOTE]
> La búsqueda de contenido de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, vea [Búsqueda de contenido de canales privados.](#content-search-of-private-channels)

La búsqueda de contenido proporciona una forma de consultar información de Microsoft Teams que abarca Exchange, SharePoint Online y OneDrive para la Empresa.

Para obtener más información, [vea Búsqueda de contenido en Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search)

Por ejemplo,  si usa la búsqueda de contenido en su buzón de Especificaciones de fabricación y en el sitio de SharePoint Especificaciones de fabricación, puede buscar en las conversaciones del canal estándar de Teams desde Exchange, las cargas y modificaciones de archivos de SharePoint Online y los cambios de OneNote.

También puede agregar criterios de consulta a la búsqueda **de contenido para** restringir los resultados devueltos. En el ejemplo anterior, puede buscar contenido donde se usaron las palabras clave **"Nuevas** especificaciones de fábrica".

> [!TIP]
> Después de agregar condiciones de búsqueda, puede exportar un informe o el contenido real a su equipo para analizarlos.

## <a name="content-search-of-private-channels"></a>Búsqueda de contenido de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Como cada canal privado tiene su propia colección de sitios de SharePoint independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo primario.

Teams no admite la búsqueda de contenido de un solo canal, por lo que es necesario buscar en todo el equipo. Para realizar una búsqueda de contenido de un canal privado, busque en todo el equipo, en la colección de sitios asociada al canal privado (para incluir archivos) y en los buzones de los miembros del canal privado (para incluir mensajes).

Siga estos pasos para identificar los archivos y mensajes de un canal privado que se incluirán en la búsqueda de contenido.

### <a name="include-private-channel-files-in-a-content-search"></a>Incluir archivos de canal privado en una búsqueda de contenido

Antes de realizar estos pasos, instale el Shell de administración de [SharePoint Online y conéctese a SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas con canales privados en el equipo.

    ```PowerShell
    Get-SPOSite
    ```
2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas con canales privados en el equipo y el id. de grupo de grupo primario.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Para cada id. de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privados relevantes.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Incluir mensajes de canal privado en una búsqueda de contenido

Antes de realizar estos pasos, asegúrese de que tiene instalada la última versión del módulo [de PowerShell de Teams.](teams-powershell-overview.md)

1. Ejecute lo siguiente para obtener una lista de canales privados en el equipo.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Ejecute lo siguiente para obtener una lista de los miembros del canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Incluya los buzones de todos los miembros de cada canal privado en el equipo como parte de la consulta de búsqueda de contenido.

## <a name="related-topics"></a>Temas relacionados

- [Casos de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 