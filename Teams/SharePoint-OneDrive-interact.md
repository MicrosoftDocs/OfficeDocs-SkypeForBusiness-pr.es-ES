---
title: Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Conozca cómo SharePoint Online y OneDrive para la Empresa interaccionan con Microsoft Teams (por ejemplo, cómo se almacenan los chats privados) y la relación entre el equipo, el canal y la biblioteca de documentos.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827743"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams

> [!Tip]
> Vea la sesión siguiente para obtener información sobre cómo los equipos interactúa con Azure Active Directory (AAD), grupos de Office 365, Exchange, SharePoint y OneDrive para la empresa: [Fundamentos de los equipos de Microsoft](https://aka.ms/teams-foundations)

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Los archivos de chats privados se almacenan en la carpeta de OneDrive para la Empresa del remitente y se conceden permisos automáticamente a todos los participantes como parte del proceso de compartir archivos.

Si los usuarios no están asignados y habilitados con licencias de SharePoint Online, no tienen OneDrive para el almacenamiento de negocio en Office 365. Uso compartido de archivos seguirán funcionando en canales, pero los usuarios no podrán compartir archivos en chats sin OneDrive para el almacenamiento de negocio en Office 365.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. 

> [!NOTE]
> No se admite la integración con SharePoint local para Microsoft Teams en este momento.

Este es un ejemplo de las relaciones entre el equipo, el canal y la biblioteca de documentos.

Se crea un sitio de SharePoint para cada equipo y la carpeta **Documentos compartidos** es la carpeta predeterminada que se crea para el equipo. Cada canal, incluido el canal **General** (que es un canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos**.

![Diagrama de las carpetas Documentos compartidos de SharePoint Online para un equipo y sus canales de Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro. Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad. Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.

> [!TIP]
> Para agregar una ficha a su equipo que vincula a una página del sitio de SharePoint existente o a la biblioteca de documentos de SharePoint existente:
> 1. Seleccione el signo más junto a las fichas.
> 2. Seleccione **Biblioteca de documentos** para una biblioteca de documentos existente o **SharePoint** para una página del sitio de SharePoint existente.
> 3. Seleccione la biblioteca de documentos o página adecuada.

Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.

![Diagrama de la carpeta de OneDrive denominada Archivos de chat de Microsoft Teams de los chats de cada usuario.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Ficha archivos de canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

La ficha **archivos** en los equipos se parezca a la vista de documentos de SharePoint. En la pestaña **archivos** , los usuarios pueden:

- Ver opciones adicionales en el menú archivo de **nuevo** .
- Sincronizar los archivos en su unidad local.
- En el menú de **Todos los documentos** , cambiar de vista de **lista** a **Compact list** a la vista de **mosaicos** .
- Identificar los archivos que necesitan atención o malware.
- Ver inmediatamente si un archivo es de sólo lectura o checked out.
- Desproteger y proteger archivos.
- Anclar, Desanclar y cambiar el criterio de ordenación de los archivos.
- Identificar qué archivos necesitan metadatos
- Elegir entre muchos más opciones de filtro.
- Archivos de grupo en función de los encabezados de columna.
- Modificar configuración de columna (mover a la izquierda o derecha, ocultar) y el ancho de columna.

## <a name="default-link-type-setting"></a>Configuración predeterminada del tipo de vínculo

SharePoint y OneDrive tienen una configuración de administración para especificar el tipo de vínculo predeterminado para los vínculos que se crean para un archivo. Los equipos se adoptando ese mismo enfoque mediante la reutilización de la configuración que establece el Administrador de SharePoint y OneDrive. Para obtener más detalles acerca de este enfoque se describen en [cambiar el tipo de vínculo predeterminado cuando los usuarios obtener vínculos para compartir](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Más información

Para obtener más información acerca del funcionamiento de SharePoint con los equipos, vea [SharePoint y equipos: mejor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Para obtener más información acerca de la experiencia de invitado en los equipos, lea [¿Qué es la experiencia de invitado como](guest-experience.md).

