---
title: Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Conozca cómo SharePoint Online y OneDrive para la Empresa interaccionan con Microsoft Teams (por ejemplo, cómo se almacenan los chats privados) y la relación entre el equipo, el canal y la biblioteca de documentos.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28a4a968fc9e478c3a13fb38acd1019221b5dcb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232281"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), grupos de Office 365, Exchange, SharePoint y OneDrive para la empresa: [bases de Microsoft Teams](https://aka.ms/teams-foundations)

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Los archivos de chats privados se almacenan en la carpeta de OneDrive para la Empresa del remitente y se conceden permisos automáticamente a todos los participantes como parte del proceso de compartir archivos.

Si los usuarios no tienen asignada ni habilitada licencias de SharePoint Online, no tienen almacenamiento de OneDrive para la empresa en Office 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la empresa en Office 365.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. 

> [!NOTE]
> En este momento, la integración con SharePoint local no es compatible con Microsoft Teams.

Este es un ejemplo de las relaciones entre el equipo, el canal y la biblioteca de documentos.

Se crea un sitio de SharePoint para cada equipo y la carpeta **Documentos compartidos** es la carpeta predeterminada que se crea para el equipo. Cada canal, incluido el canal **General** (que es un canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos**.

![Diagrama de carpetas de documentos compartidos en SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro. Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad. Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.

> [!TIP]
> Para agregar una pestaña a su equipo que tenga un vínculo a una página de un sitio de SharePoint existente o a la biblioteca de documentos de SharePoint existente:
> 1. Seleccione el signo más situado junto a las pestañas.
> 2. Seleccione **SharePoint** para una página de sitio de SharePoint existente o **biblioteca de documentos** para una biblioteca de documentos existente.
> 3. Seleccione la página o biblioteca de documentos adecuada.

Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.

![Diagrama de la carpeta de OneDrive denominada archivos de chat de Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Ficha archivos de canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

La pestaña **archivos** de Teams es muy similar a la vista documentos de SharePoint. En la pestaña **archivos** , los usuarios pueden:

- Consulte Opciones adicionales en el menú **nuevo** archivo.
- Sincronizar archivos con su unidad local.
- En el menú **todos los documentos** , cambie de la vista de **lista** a la de **lista compacta** a vista de **mosaicos** .
- Identifique los archivos que necesitan atención o tienen malware.
- Ver inmediatamente si un archivo es de solo lectura o desprotegido.
- Desproteger y proteger archivos.
- Anclar, desanclar y cambiar el orden de los archivos.
- Identificar qué archivos necesitan metadatos
- Elija entre más opciones de filtro.
- Agrupar archivos en función de los encabezados de columna.
- Modificar la configuración de las columnas (desplazarse a la izquierda o a la derecha, ocultar) y ancho de columna.

## <a name="default-link-type-setting"></a>Configuración de tipo de vínculo predeterminado

SharePoint y OneDrive tienen una configuración de administrador para especificar el tipo de vínculo predeterminado para los vínculos que se crean para un archivo. Teams adopta ese mismo enfoque al reutilizar la configuración que los conjuntos de administradores para SharePoint y OneDrive. Se describen más detalles sobre este enfoque en [cambiar el tipo de vínculo predeterminado cuando los usuarios obtienen vínculos para compartir](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Más información

Para obtener más información acerca de cómo funciona SharePoint con Teams, vea [SharePoint y Teams: mejor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Para obtener más información sobre la experiencia de invitado en Teams, lea [el aspecto de la experiencia de invitado](guest-experience.md).

