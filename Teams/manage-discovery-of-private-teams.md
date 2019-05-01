---
title: Administrar la detección de los equipos privados en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo controlar si los equipos privados se pueden detectar los usuarios de Microsoft Teams a través de sugerencias en el equipo galería y resultados de búsqueda.
ms.openlocfilehash: 3609a592c3c940e9f7cbec6ca5c58fd072322c46
ms.sourcegitcommit: 0bb55cad74b15fc821ae916799aa8c0cb13dd31d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2019
ms.locfileid: "33497956"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Administrar la detección de los equipos privados en Microsoft Teams

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

Los propietarios de los administradores y del equipo pueden controlar si se pueden detectar los equipos privados por los usuarios de Microsoft Teams en su organización. Una vez que se pueda detectar un equipo privado, se muestra en los resultados de búsqueda y se incluye en sugerencias en la Galería de equipo junto con los equipos públicos en los equipos. Esto facilita a los usuarios a buscar y encontrar los equipos privados que deseen unirse a. Los usuarios pueden solicitar para unirse a un equipo privado que el propietario de un equipo, a continuación, puede aprobar o denegar.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Información general de los equipos públicos, los equipos privados y detección en los equipos

La mayoría de las organizaciones tienen los siguientes tipos de equipos - equipos públicos, que se pueda detectar equipos privados y equipos privados no detectable.

![Galería de equipo](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Equipos públicos

Están disponibles para todos los usuarios de la organización para unirse a los equipos públicos. Los equipos públicos están visibles para todos los usuarios en la Galería de los equipos y los usuarios pueden unirse a un equipo público sin necesidad de obtener la aprobación del propietario del equipo. Algunos ejemplos de los equipos públicos son un equipo para discutir noticias en tecnología, un equipo para obtener comentarios dogfood para sus productos y un equipo para molesta de personas para que funcione.

### <a name="discoverable-private-teams"></a>Equipos privados que se pueda detectar

Sólo se pueden unir los equipos privados que se pueda detectar cuando el propietario del equipo agrega a los usuarios a ellos. Cuando realiza un equipo privado que se pueda detectar, el equipo se incluye en la lista de los equipos sugeridos y los resultados de búsqueda en la Galería de los equipos. Use que se pueda detectar equipos privados para proyectos y grupos de la organización que todos los usuarios es consciente de y donde el acceso a las conversaciones y los archivos en el equipo deben controlarse. Algunos ejemplos son un equipo para el departamento de recursos humanos, un equipo para todos los administradores de la organización y un equipo de un administrador y sus subordinados directos.

### <a name="non-discoverable-private-teams"></a>Equipos privados que no se pueda detectar

Sólo se pueden unir los equipos privados que no se pueda detectar cuando el propietario del equipo agrega a los usuarios a ellos. Cuando realiza no puede detectar un equipo privado, tiene oculto de la lista de los equipos sugeridas y se quitan los resultados de búsqueda en la Galería de los equipos. Uso de los equipos que no sean reconocibles para colaborar en los temas importantes y altamente confidenciales. Algunos ejemplos son un equipo para discutir una adquisición próxima y un equipo para discutir un cambio en la dirección estratégica de su organización.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Establecer si se puede detectar nuevos equipos privados

Cuando el propietario de un equipo, crea un equipo privado, pueden elegir para que se pueda detectar mediante la configuración de detección del grupo. De forma predeterminada, los equipos privados nuevo son que admite búsquedas y que se pueda detectar. Si el propietario del equipo no desea que el equipo privado aparezca en los resultados de búsqueda y sugerencias, puede activar desactiva la opción seleccionando **Cambiar configuración** junto a **este equipo es que admite búsquedas y que se pueda detectar**.

![configuración de detección para nuevos equipos privados](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Establecer si se puede detectar los equipos privados existentes

Los propietarios de equipo pueden establecer la configuración de detección de un equipo privado existente directamente en la configuración del equipo y los administradores pueden hacerlo mediante el uso de PowerShell.

### <a name="in-team-settings"></a>En configuración del equipo

En los equipos, vaya al equipo privado, haga clic en **más ˙˙˙ opciones** > **Administrar equipo**. En la ficha **configuración** , expanda la **detección de equipo**y, a continuación, desactive o Active la casilla de verificación **activar la detectabilidad** .

![configuración de detección de equipos privados existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a>Uso de PowerShell (próximamente)

Use el cmdlet **Set-equipo** para activar o desactivar la opción de detección de un equipo privado existente. Este es un ejemplo de cómo hacer que un equipo que se pueda detectar:

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
Puede usar este cmdlet en una secuencia de comandos para establecer la configuración de detección de equipos privados existentes de forma masiva.

## <a name="set-whether-users-can-discover-private-teams"></a>Establecer si los usuarios pueden detectar los equipos privados

Como administrador, también puede controlar qué usuarios de la organización se permiten detectar equipos privados en los resultados de búsqueda y sugerencias en los equipos. Crear una directiva con el cmdlet **New-CsTeamsChannelsPolicy** y, a continuación, asigne la directiva a los usuarios.
 
Establezca el parámetro **AllowPrivateTeamDiscovery** en **true** para permitir que a los usuarios que tienen asignados la directiva para ver que se pueda detectar equipos privados en los resultados de búsqueda y sugerencias. Si el parámetro **AllowPrivateTeamDiscovery** se establece en **false** , quita todos los equipos privados detectable de los resultados de búsqueda y sugerencias para los usuarios que tienen asignadas la directiva.

De forma predeterminada, **AllowPrivateTeamDiscovery** se establece en **true** para todos los usuarios de una organización.

En este ejemplo, se crea una directiva denominada VendorPolicy que impide que los usuarios descubrir cualquier equipos privados que se realizan puede detectar y, a continuación, se asigne la directiva a un usuario denominado vendoruser1. 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> Los equipos privados que no se pueden descubrir nunca se muestran en los resultados de búsqueda y sugerencias, independientemente de la configuración de directiva. Por ejemplo, si desactiva la configuración de detección de un equipo privado, los usuarios son no se puede detectar el equipo, aunque el parámetro **AllowPrivateTeamDiscovery** se establece en **true** en la configuración de directiva para esos usuarios.

## <a name="related-topics"></a>Temas relacionados
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)