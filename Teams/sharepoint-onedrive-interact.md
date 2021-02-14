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
description: SharePoint Online & interacción de OneDrive para la Empresa con Teams; almacenamiento de archivos de chat & interacción entre el equipo, el canal estándar & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ff18a0645f81d1892e246ee7432d58a1c728f3ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757785"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), Grupos de Microsoft 365, Exchange, SharePoint y OneDrive para la Empresa: [Conceptos básicos de Microsoft Teams](https://aka.ms/teams-foundations)

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online, y cada canal estándar de un equipo recibe una carpeta dentro de la biblioteca de documentos predeterminada del sitio de grupo. Los archivos compartidos en una conversación se agregan automáticamente a la biblioteca de documentos, y los permisos y opciones de seguridad de archivos establecidos en SharePoint se reflejan automáticamente en Teams. Para ver las consecuencias de cambiar la dirección de un sitio en SharePoint, lea [Cambiar una dirección del sitio.](https://docs.microsoft.com/sharepoint/change-site-address)

> [!NOTE]
> Este artículo se aplica solo a los canales estándar. La arquitectura de los canales privados es diferente de los canales estándar. Cada canal privado tiene su propia colección de sitios de SharePoint independiente del sitio de grupo primario. Para obtener más información, [vea Canales privados en Microsoft Teams.](private-channels.md)

Los archivos de chat privado se almacenan en la carpeta de OneDrive para la Empresa del remitente y los permisos se conceden automáticamente a todos los participantes como parte del proceso de uso compartido de archivos.

Si a los usuarios no se les asigna ni se les habilita licencias de SharePoint Online, no tendrán almacenamiento de OneDrive para la Empresa en Office 365 o en Microsoft 365. El uso compartido de archivos seguirá funcionando en canales estándar, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la Empresa en Microsoft 365 u Office 365.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. 

> [!NOTE]
> La integración con SharePoint local no es compatible con Microsoft Teams en este momento.

El siguiente es el ejemplo de relaciones entre el equipo, el canal estándar y la biblioteca de documentos.

Para cada grupo, se crea un  sitio de SharePoint y la carpeta Documentos compartidos es la carpeta predeterminada creada para el equipo. Cada canal estándar, incluido **el canal General** (el canal predeterminado para cada equipo) tiene una carpeta en Documentos **compartidos.**

![Diagrama de las carpetas Documentos compartidos en SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro. Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad. Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.

> [!TIP]
> Para agregar una pestaña al equipo que vincula a una página de sitio de SharePoint existente o a su biblioteca de documentos de SharePoint existente:
> 1. Seleccione el signo más situado junto a las pestañas.
> 2. Seleccione **SharePoint para una** página de sitio de SharePoint existente o **biblioteca de documentos** para una biblioteca de documentos existente.
> 3. Seleccione la página o biblioteca de documentos apropiada.

Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.

![Diagrama de la carpeta de OneDrive denominada Archivos de chat de Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Tenga en cuenta que para los equipos públicos, el sitio de grupo de SharePoint está aprovisionado con acceso "Todos excepto los usuarios externos". El equipo público no se muestra en Teams para las personas que no son miembros de ese equipo. Sin embargo, pueden acceder al contenido del sitio de grupo de SharePoint mediante la dirección URL del sitio de grupo de SharePoint. 

## <a name="channel-files-tab"></a>Pestaña Archivos de canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

La **pestaña** Archivos de Teams se asemeja mucho a la vista de documentos de SharePoint. En la **pestaña** Archivos, los usuarios pueden:

- Vea las opciones adicionales en **el menú** Nuevo archivo.
- Sincronizar archivos en su unidad local.
- En el **menú Todos los** documentos, cambie de la **vista** Lista a la **lista compacta** a la **vista Mosaicos.**
- Identifique archivos que necesiten atención o que tengan malware.
- Vea inmediatamente si un archivo es de solo lectura o está desprotegdo.
- Des check out and check in files.
- Anclar, desanclar y cambiar el criterio de ordenación de los archivos.
- Identificar qué archivos necesitan metadatos
- Elija entre muchas más opciones de filtro.
- Agrupar archivos en función de los encabezados de columna.
- Modifique la configuración de las columnas (mover a la izquierda o la derecha, ocultar) y el ancho de columna.

## <a name="default-link-type-setting"></a>Configuración predeterminada del tipo de vínculo

SharePoint y OneDrive tienen una configuración de administrador para especificar el tipo de vínculo predeterminado para los vínculos que se crean para un archivo. Teams está adoptando el mismo enfoque, reusando la configuración que el administrador establece para SharePoint y OneDrive. Más detalles sobre este método se describen en Cambiar el tipo de [vínculo predeterminado cuando los usuarios obtienen vínculos para compartir.](https://docs.microsoft.com/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>Más información

Para obtener más información sobre cómo funciona SharePoint con Teams, [vea SharePoint y Teams: mejor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Para obtener más información sobre la experiencia de invitado en Teams, lea [cómo es la experiencia de invitado.](guest-experience.md)

