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
description: Obtenga información sobre cómo usar la búsqueda de contenido en Microsoft Teams para consultar información de Microsoft Teams desde Exchange, SharePoint Online, OneDrive para la empresa y OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d05d815a74fc395c06763920014b7de453847bec
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121530"
---
<a name="use-content-search-in-microsoft-teams"></a>Usar la búsqueda de contenido en Microsoft Teams
=====================================

> [!NOTE]
> La búsqueda de contenido de mensajes y archivos de [canales privados](private-channels.md) funciona de manera diferente que en los canales estándar. Para obtener más información, consulta [búsqueda de contenido de canales privados](#content-search-of-private-channels).

Búsqueda de contenido proporciona una manera de consultar información de Microsoft Teams en Exchange, SharePoint Online y OneDrive para la empresa.

Para obtener más información, lea [búsqueda de contenido en Microsoft 365 u Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

Por ejemplo, mediante la **búsqueda de contenido** en el sitio de SharePoint especificaciones de fabricación, buzón y especificaciones de fabricación, puede buscar entre las conversaciones de canal estándar de Teams de Exchange, las cargas de archivos y las modificaciones de SharePoint Online y los cambios de OneNote.

También puede Agregar criterios de consulta a la **búsqueda de contenido** para restringir los resultados devueltos. En el ejemplo anterior, puede buscar contenido en el que se hayan usado las palabras clave "**nuevas especificaciones de fábrica"** .

> [!TIP]
> Después de agregar condiciones de búsqueda, puede exportar un informe o los datos a su equipo para analizarlos.

## <a name="content-search-of-private-channels"></a>Búsqueda de contenido de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Como cada canal privado tiene su propia colección de sitios de SharePoint que es independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo principal.

Teams no admite la búsqueda de contenido de un único canal, por lo que se debe buscar en todo el equipo. Para realizar una búsqueda de contenido de un canal privado, busque en el equipo, la colección de sitios asociada al canal privado (para incluir archivos) y buzones de miembros de canales privados (para incluir mensajes).

Siga estos pasos para identificar los archivos y mensajes de un canal privado para incluirlos en la búsqueda de contenido.

### <a name="include-private-channel-files-in-a-content-search"></a>Incluir archivos de canal privado en una búsqueda de contenido

Antes de realizar estos pasos, instale el [Shell de administración de SharePoint Online y conéctese a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas a los canales privados en el equipo.

    ```PowerShell
    Get-SPOSite
    ```
2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas a los canales privados en el equipo y el identificador del grupo de equipos primario.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Para cada uno de los IDENTIFICADOres de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado pertinentes.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Incluir mensajes de canal privado en una búsqueda de contenido

Antes de realizar estos pasos, asegúrese de que tiene instalada la [última versión del módulo de PowerShell de Teams](teams-powershell-overview.md) .

1. Ejecute lo siguiente para obtener una lista de canales privados en el equipo.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Ejecute lo siguiente para obtener una lista de miembros del canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Incluya los buzones de todos los miembros de cada canal privado del equipo como parte de la consulta de búsqueda de contenido.

## <a name="related-topics"></a>Temas relacionados

- [casos de eDiscovery en el centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 