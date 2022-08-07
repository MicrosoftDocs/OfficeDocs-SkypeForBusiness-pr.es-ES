---
title: Usar la búsqueda de contenido en Microsoft Teams
author: v-tophillips
ms.author: v-tophillips
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Obtenga información sobre cómo usar búsqueda de contenido en el portal de cumplimiento Microsoft Purview para buscar contenido de Microsoft Teams almacenado en Exchange Online, SharePoint Online, OneDrive Entreprise y OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a069478dc65fcafb5e1354796360c994aa2f0d36
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267445"
---
# <a name="use-content-search-in-microsoft-teams"></a>Usar la búsqueda de contenido en Microsoft Teams

> [!NOTE]
> La búsqueda de contenido de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, consulte [Búsqueda de contenido de canales privados](#content-search-of-private-channels).

La búsqueda de contenido proporciona una forma de consultar la información de Microsoft Teams que abarca Exchange, SharePoint Online y OneDrive Entreprise.

Para obtener más información, consulte [Búsqueda de contenido en Microsoft 365](/microsoft-365/compliance/content-search).

Por ejemplo, si usa la **búsqueda de contenido** en el buzón Especificaciones de fabricación y en el sitio de SharePoint Especificaciones de fabricación, puede buscar en conversaciones de canal estándar de Teams desde Exchange, cargas y modificaciones de archivos desde SharePoint Online y cambios en OneNote.

También puede agregar criterios de consulta a la **búsqueda de contenido** para restringir los resultados devueltos. En el ejemplo anterior, puede buscar contenido donde se usaron las palabras clave "**Nuevas especificaciones de fábrica"** .

> [!TIP]
> Después de agregar condiciones de búsqueda, puede exportar un informe o el contenido real al equipo para analizarlo.

## <a name="content-search-of-private-channels"></a>Búsqueda de contenido de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Como cada canal privado tiene su propia colección de sitios de SharePoint independiente del sitio de grupo primario, los archivos de un canal privado se administran de forma independiente del equipo primario.

Teams no admite la búsqueda de contenido de un solo canal, por lo que es necesario buscar a todo el equipo. Para realizar una búsqueda de contenido de un canal privado, busque en el equipo, en la colección de sitios asociada al canal privado (para incluir archivos) y en los buzones de los miembros del canal privado (para incluir mensajes).

Siga estos pasos para identificar los archivos y mensajes de un canal privado que se incluirán en la búsqueda de contenido.

### <a name="include-private-channel-files-in-a-content-search"></a>Incluir archivos de canal privados en una búsqueda de contenido

Antes de realizar estos pasos, instale el [Shell de administración de SharePoint Online y conéctese a SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas a canales privados del equipo.

    ```PowerShell
    Get-SPOSite
    ```
2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas a los canales privados del equipo y el id. del grupo del equipo primario.

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

### <a name="include-private-channel-messages-in-a-content-search"></a>Incluir mensajes del canal privado en una búsqueda de contenido

Antes de realizar estos pasos, asegúrese de que tiene instalada la [versión más reciente del módulo PowerShell de Teams](teams-powershell-overview.md) .

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

- [Casos de exhibición de documentos electrónicos en la portal de cumplimiento Microsoft Purview](/Office365/SecurityCompliance/ediscovery-cases)