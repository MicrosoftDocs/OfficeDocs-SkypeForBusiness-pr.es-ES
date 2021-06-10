---
title: Cómo SharePoint y OneDrive interactúan con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive interacción con Teams; Almacenamiento privado de archivos de chat & interacción entre equipo, canal estándar, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855959"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>Cómo SharePoint y OneDrive interactúan con Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre Teams interactúa con Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint y OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint y cada canal estándar de un equipo obtiene una carpeta dentro de la biblioteca de documentos de sitio de grupo predeterminada. Cada [canal privado](private-channels.md) obtiene su propio sitio de SharePoint independiente.

Los archivos compartidos dentro de una conversación se agregan automáticamente a la biblioteca de documentos y los permisos y las opciones de seguridad de archivos establecidas en SharePoint se reflejan automáticamente en Teams. Para ver el impacto de cambiar una dirección de sitio en SharePoint, lea [Cambiar una dirección de sitio](/sharepoint/change-site-address).

Los archivos de chat privados se almacenan en la carpeta OneDrive del remitente y los permisos se conceden automáticamente a todos los participantes como parte del proceso de uso compartido de archivos.

Si a los usuarios no se les SharePoint licencias, no tienen OneDrive almacenamiento en Microsoft 365. El uso compartido de archivos funciona en canales estándar, pero los usuarios no podrán compartir archivos en chats sin OneDrive almacenamiento en Microsoft 365.

Al almacenar los archivos en la SharePoint de documentos y OneDrive, se seguirán todas las reglas de cumplimiento configuradas en el nivel de la organización. 

> [!NOTE]
> La integración con SharePoint Server no es compatible con Teams.

A continuación se muestra el ejemplo de relaciones entre el equipo, el canal estándar y la biblioteca de documentos.

Para cada equipo, se crea SharePoint sitio  y la carpeta Documentos compartidos es la carpeta predeterminada creada para el equipo. Cada canal estándar, incluido el **canal General** (el canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos.**

![Diagrama de carpetas documentos compartidos en SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

El sitio SharePoint y la biblioteca de documentos predeterminadas no se pueden reemplazar por uno diferente.

Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.

![Diagrama de la carpeta OneDrive llamada Microsoft Teams archivos de chat](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Tenga en cuenta que, en el caso de los equipos públicos, SharePoint sitio de grupo está aprovisionado con el acceso "Todos excepto los usuarios externos". El equipo público no se muestra en Teams personas que no son miembros de ese equipo. Sin embargo, pueden obtener acceso al contenido del SharePoint de grupo mediante la dirección URL del SharePoint de grupo. 

## <a name="channel-files-tab"></a>Pestaña Archivos de canal

La **pestaña** Archivos de Teams similar a la vista SharePoint documentos. En la **pestaña** Archivos, los usuarios pueden:

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

El tipo de vínculo de uso compartido que se muestra de forma predeterminada cuando un usuario ha compartido un archivo se establece en el centro SharePoint administración. Vea [Cambiar el tipo de vínculo predeterminado cuando los usuarios obtienen vínculos para compartir](/sharepoint/change-default-sharing-link) para obtener información.

## <a name="related-topics"></a>Temas relacionados

[SharePoint y Teams: mejor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

[Cómo es la experiencia de invitado](guest-experience.md)