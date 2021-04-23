---
title: Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & interacción de OneDrive para la Empresa con Teams; Almacenamiento privado de archivos de chat & interacción entre equipo, canal estándar, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948633"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), Grupos de Microsoft 365, Exchange, SharePoint y OneDrive para la Empresa: [Conceptos básicos de Microsoft Teams](https://aka.ms/teams-foundations)

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal estándar de un equipo obtiene una carpeta dentro de la biblioteca de documentos predeterminada del sitio de grupo. Los archivos compartidos en una conversación se agregan automáticamente a la biblioteca de documentos y los permisos y las opciones de seguridad de archivos establecidas en SharePoint se reflejan automáticamente en Teams. Para ver el impacto de cambiar una dirección de sitio en SharePoint, lea [Cambiar una dirección de sitio.](/sharepoint/change-site-address)

> [!NOTE]
> Este artículo solo se aplica a los canales estándar. La arquitectura de los canales privados es diferente de los canales estándar. Cada canal privado tiene su propia colección de sitios de SharePoint independiente del sitio de grupo principal. Para obtener más información, vea [Canales privados en Microsoft Teams.](private-channels.md)

Los archivos de chat privados se almacenan en la carpeta de OneDrive para la Empresa del remitente y los permisos se conceden automáticamente a todos los participantes como parte del proceso de uso compartido de archivos.

Si a los usuarios no se les asigna ni se les habilita licencias de SharePoint Online, no tendrán almacenamiento de OneDrive para la Empresa en Office 365 o en Microsoft 365. El uso compartido de archivos seguirá funcionando en canales estándar, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la Empresa en Microsoft 365 u Office 365.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. 

> [!NOTE]
> La integración con SharePoint local no es compatible con Microsoft Teams en este momento.

A continuación se muestra el ejemplo de relaciones entre el equipo, el canal estándar y la biblioteca de documentos.

Para cada equipo, se crea un sitio de SharePoint y la carpeta **Documentos** compartidos es la carpeta predeterminada creada para el equipo. Cada canal estándar, incluido el **canal General** (el canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos.**

![Diagrama de carpetas documentos compartidos en SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro. Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad. Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> Para agregar una pestaña a su equipo que se vincula a una página de sitio de SharePoint existente o a la biblioteca de documentos de SharePoint existente:
> 1. Seleccione el signo más junto a las pestañas.
> 2. Seleccione **SharePoint para una** página de sitio de SharePoint existente o **Biblioteca de documentos** para una biblioteca de documentos existente.
> 3. Seleccione la página o biblioteca de documentos adecuada.

Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.

![Diagrama de la carpeta de OneDrive denominada Archivos de chat de Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Tenga en cuenta que, en el caso de los equipos públicos, el sitio de grupo de SharePoint está aprovisionado con el acceso "Todos excepto los usuarios externos". El equipo público no se muestra en Teams para personas que no son miembros de ese equipo. Sin embargo, pueden obtener acceso al contenido del sitio de grupo de SharePoint con la dirección URL del sitio de grupo de SharePoint. 

## <a name="channel-files-tab"></a>Pestaña Archivos de canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

La **pestaña** Archivos de Teams se parece mucho a la vista documentos de SharePoint. En la **pestaña** Archivos, los usuarios pueden:

- Vea opciones adicionales en el **menú Nuevo** archivo.
- Sincronice archivos con su unidad local.
- En el **menú Todos los documentos,** cambie de la **vista** Lista a la **lista compacta** a la **vista Mosaicos.**
- Identifique archivos que necesiten atención o que tengan malware.
- Vea inmediatamente si un archivo es de solo lectura o está desprotegiendo.
- Des check-out and check in files.
- Anclar, desanclar y cambiar el criterio de ordenación de los archivos.
- Identificar qué archivos necesitan metadatos
- Elija entre muchas más opciones de filtro.
- Agrupar archivos basados en encabezados de columna.
- Modifique la configuración de columna (mover a la izquierda o a la derecha, ocultar) y el ancho de columna.

## <a name="default-link-type-setting"></a>Configuración predeterminada del tipo de vínculo

SharePoint y OneDrive tienen una configuración de administrador para especificar el tipo de vínculo predeterminado para los vínculos que se crean para un archivo. Teams está adoptando ese mismo enfoque al volver a la configuración que el administrador establece para SharePoint y OneDrive. Más detalles sobre este enfoque se describen en [Cambiar el tipo de vínculo predeterminado cuando los usuarios obtienen vínculos para compartir.](/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>Más información

Para obtener más información sobre cómo funciona SharePoint con Teams, vea [SharePoint y Teams: mejor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Para obtener más información sobre la experiencia de invitado en Teams, lea [¿Cómo es la experiencia de invitado?](guest-experience.md)