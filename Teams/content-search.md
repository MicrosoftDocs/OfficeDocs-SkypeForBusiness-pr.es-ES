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
description: Obtenga información sobre cómo usar la búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 para buscar contenido Microsoft Teams almacenado en Exchange Online, SharePoint Online, OneDrive para la Empresa y OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6810355304371564a2a305c82290df7667f5efd41889e598021636cc9ccd11d4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278218"
---
# <a name="use-content-search-in-microsoft-teams"></a>Usar la búsqueda de contenido en Microsoft Teams

> [!NOTE]
> La búsqueda de contenido de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, vea [Búsqueda de contenido de canales privados.](#content-search-of-private-channels)

La búsqueda de contenido proporciona una forma de consultar Microsoft Teams información que abarca Exchange, SharePoint en línea y OneDrive para la Empresa.

Para obtener más información, vea [Búsqueda de contenido en Microsoft 365](/microsoft-365/compliance/content-search).

Por ejemplo,  con la búsqueda de contenido en su buzón de especificaciones de fabricación y en el sitio de Especificaciones de fabricación SharePoint Teams, puede buscar en conversaciones de canal estándar de Exchange, cargas de archivos y modificaciones de SharePoint Online y OneNote cambios.

También puede agregar criterios de consulta a la búsqueda **de contenido** para restringir los resultados devueltos. En el ejemplo anterior, puede buscar contenido donde se usaron las palabras clave **"Nuevas** especificaciones de fábrica".

> [!TIP]
> Después de agregar condiciones de búsqueda, puede exportar un informe o el contenido real al equipo para su análisis.

## <a name="content-search-of-private-channels"></a>Búsqueda de contenido de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Dado que cada canal privado tiene su propia colección de sitios SharePoint independiente del sitio de grupo principal, los archivos de un canal privado se administran independientemente del equipo principal.

Teams no admite la búsqueda de contenido de un solo canal, por lo que se debe buscar a todo el equipo. Para realizar una búsqueda de contenido de un canal privado, busque en todo el equipo, la colección de sitios asociada con el canal privado (para incluir archivos) y los buzones de los miembros del canal privado (para incluir mensajes).

Siga estos pasos para identificar archivos y mensajes en un canal privado para incluirlos en la búsqueda de contenido.

### <a name="include-private-channel-files-in-a-content-search"></a>Incluir archivos de canal privado en una búsqueda de contenido

Antes de realizar estos pasos, instale SharePoint Shell de administración en línea [y conéctese a SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Ejecute lo siguiente para obtener una lista de todas SharePoint colecciones de sitios asociadas con canales privados en el equipo.

    ```PowerShell
    Get-SPOSite
    ```
2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios SharePoint asociadas con canales privados en el equipo y el id. de grupo de grupo principal.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Para cada id. de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado relevantes.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Incluir mensajes de canal privado en una búsqueda de contenido

Antes de realizar estos pasos, asegúrese de que tiene instalada la versión más reciente [Teams módulo de PowerShell.](teams-powershell-overview.md)

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

- [Casos de exhibición de documentos electrónicos en el Centro Microsoft 365 cumplimiento](/Office365/SecurityCompliance/ediscovery-cases)