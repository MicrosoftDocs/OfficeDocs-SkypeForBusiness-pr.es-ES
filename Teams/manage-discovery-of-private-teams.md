---
title: Administrar la detección de equipos privados en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/20/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo controlar si los usuarios de Microsoft Teams pueden descubrir los equipos privados mediante sugerencias de la galería de equipos y resultados de la búsqueda.
ms.openlocfilehash: c938830f4f59345863d3f84570b387f07f4b08fc
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221235"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Administrar la detección de equipos privados en Microsoft Teams

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

Los administradores y los propietarios del equipo pueden controlar si los usuarios de Microsoft Teams pueden descubrir equipos privados de su organización. Cuando se detecta un equipo privado, se muestra en los resultados de la búsqueda y se incluye en las sugerencias de la galería de equipo junto con los equipos públicos de Teams. Esto facilita que los usuarios busquen y encuentren a los equipos privados a los que desean unirse. Los usuarios pueden solicitar unirse a un equipo privado y un propietario del equipo puede aprobar o denegar la solicitud.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Información general sobre los equipos públicos, los equipos privados y el descubrimiento en Teams

La mayoría de las organizaciones tienen los siguientes tipos de equipos: equipos públicos, equipos privados que se pueden descubrir y equipos privados que no se pueden descubrir.

![Captura de pantalla de la galería de equipos](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Equipos públicos

Los equipos públicos están disponibles para que todos los usuarios de su organización se unan. Los equipos públicos están visibles para todos los usuarios de la galería de equipos y los usuarios pueden unirse a un equipo público sin tener que obtener la aprobación del propietario del equipo. Entre los ejemplos de equipos públicos se incluye un equipo para debatir noticias sobre tecnología, un equipo para obtener comentarios sobre sus productos y un equipo para que los usuarios carpooling trabajar.

### <a name="discoverable-private-teams"></a>Equipos privados que se pueden descubrir

Los equipos privados que se pueden descubrir solo se pueden unir cuando el propietario del equipo les agregue usuarios. Cuando hace que un equipo privado sea reconocible, el equipo está incluido en la lista de equipos sugeridos y resultados de la búsqueda de la galería de equipos. Use equipos privados detectables para los proyectos y grupos de su organización que conozcan todos los usuarios y donde sea necesario controlar el acceso a las conversaciones y los archivos del equipo. Los ejemplos incluyen un equipo para el Departamento de recursos humanos, un equipo para todos los administradores de su organización y un equipo para un administrador y sus subordinados directos.

### <a name="non-discoverable-private-teams"></a>Equipos privados no exportadas

Los equipos privados no detectables solo se pueden unir cuando el propietario del equipo les agregue usuarios. Cuando hace que un equipo privado no sea reconocible, se oculta de la lista de equipos sugeridos y se ha eliminado de los resultados de la búsqueda en la galería de equipos. Use equipos no exportadas para colaborar en temas confidenciales y muy confidenciales. Algunos ejemplos incluyen un equipo para discutir una próxima adquisición y un equipo para discutir un cambio en la dirección estratégica de su organización.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Establecer si los nuevos equipos privados se pueden descubrir

Cuando un propietario de equipo crea un equipo privado, puede elegir que sea reconocible configurando la configuración de detección del equipo. De forma predeterminada, los nuevos equipos privados se pueden buscar y descubrir. Si el propietario del equipo no desea que el equipo privado se muestre en los resultados de búsqueda y las sugerencias, el propietario puede desactivar la configuración seleccionando **Cambiar configuración** junto a **este equipo es buscable y reconocible**.

![Captura de pantalla de la configuración de detección para nuevos equipos privados](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Establecer si los equipos privados existentes se pueden descubrir

Los propietarios de equipo pueden establecer la configuración de detección de un equipo privado existente directamente en la configuración del equipo y los administradores pueden hacerlo con PowerShell.

### <a name="in-team-settings"></a>En la configuración del equipo

En Teams, vaya al equipo privado, haga clic en **más opciones** > **administrar equipo**. En la pestaña **configuración** , expanda descubrimiento de equipo y, a continuación, Active o desactive la casilla **de verificación Activar** el **descubrimiento**.

![Captura de pantalla de la configuración de detección para equipos privados existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a>Usar PowerShell (próximamente)

Use el cmdlet **[set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** para desactivar o activar la configuración de detección de un equipo privado existente. Este es un ejemplo de cómo hacer que un equipo sea reconocible:
```
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
```
Puede usar este cmdlet en un script para establecer la configuración de detección de equipos privados existentes en masa.

## <a name="set-whether-users-can-discover-private-teams"></a>Establecer si los usuarios pueden descubrir equipos privados

Como administrador, también puede controlar los usuarios de su organización que pueden detectar equipos privados en los resultados de búsqueda y sugerencias de Teams. Cree una directiva con el cmdlet **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** y, a continuación, asigne la Directiva a los usuarios.
 
Establezca el parámetro **AllowPrivateTeamDiscovery** en **true** para permitir que los usuarios a los que se les asigne la Directiva vean equipos privados que se pueden descubrir en resultados y sugerencias de búsqueda. Al establecer el parámetro **AllowPrivateTeamDiscovery** en **false** , se quitan todos los equipos privados detectables de los resultados de búsqueda y sugerencias para los usuarios que tienen asignada la Directiva.

De forma predeterminada, **AllowPrivateTeamDiscovery** se establece en **true** para todos los usuarios de una organización.

En este ejemplo, creamos una directiva denominada VendorPolicy que impide que los usuarios descubran equipos privados que se hacen detectables y, a continuación, asignamos la Directiva a un usuario denominado vendoruser1. 
```
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> Los equipos privados que no se pueden detectar nunca se muestran en los resultados de la búsqueda ni en las sugerencias, independientemente de la configuración de la Directiva. Por ejemplo, si desactiva la configuración de descubrimiento para un equipo privado, los usuarios no podrán descubrir el equipo, aunque el parámetro **AllowPrivateTeamDiscovery** se establezca en **verdadero** en la configuración de directiva para esos usuarios.

## <a name="related-topics"></a>Temas relacionados
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)