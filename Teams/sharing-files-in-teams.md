---
title: Compartir archivos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Obtenga más información sobre la experiencia de uso compartido de archivos en Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138382"
---
# <a name="sharing-files-in-microsoft-teams"></a>Compartir archivos en Microsoft Teams

En Microsoft Teams, los usuarios pueden compartir contenido con otros usuarios de Teams dentro y fuera de su organización. El uso compartido en Teams se basa en la configuración establecida en SharePoint y OneDrive, por lo que todo lo que configure para SharePoint y OneDrive controlará también el uso compartido en Teams.

## <a name="overview"></a>Información general

Los usuarios pueden compartir archivos de OneDrive, desde los equipos y los sitios a los que tienen acceso y desde su equipo. Para compartir un archivo, los usuarios pueden hacer lo siguiente:

- En un canal, haga clic en **adjuntar** (el icono de clip), seleccione **recientes**, **examinar equipos y canales**, **OneDrive**o **cargar desde mi equipo**y, a continuación, elija el archivo que desea compartir. <br> 
    ![Captura de pantalla que muestra el uso compartido de un archivo desde un canal](media/share-files-channel.png)
- En un chat, haga clic en **adjuntar** (el icono de clip), seleccione o **OneDrive** o **cargar desde mi equipo**y, a continuación, elija el archivo que desea compartir. <br>
    ![Captura de pantalla que muestra compartir un archivo desde un chat](media/share-files-chat.png)
- Copie y pegue el vínculo para compartir en el cuadro de redacción.<br>
    ![Captura de pantalla que muestra la vista previa del archivo en el cuadro de redacción](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>Lo que debe saber sobre la experiencia de uso compartido de archivos

### <a name="permissions-of-shared-files-and-sharing-links"></a>Permisos de archivos compartidos y vínculos de uso compartido

Cuando los usuarios comparten un archivo desplazándose hasta él en OneDrive o en equipos y canales, a todos los destinatarios se les concede acceso junto con los [permisos predeterminados que se establecen en el nivel de la organización](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Cuando un usuario copia y pega un vínculo de uso compartido, se consiguen los permisos establecidos en ese vínculo para compartir y la dirección URL de SharePoint se acorta al nombre de archivo. En otras palabras, Teams usa solo el nombre de archivo para vincular a un archivo.

Cuando los usuarios comparten un archivo desde Teams, pueden establecer quién puede acceder al archivo de la misma manera que en Microsoft 365. Pueden dar acceso a cualquier persona, a las personas de su organización, a personas con acceso existente o a personas específicas (que pueden incluir a las personas en un chat de 1:1, una conversación grupal o un canal).  Cuando un archivo está compartido, la vista previa del archivo está disponible en el mensaje, junto con todas las acciones de archivo, como **abrir en línea**, **Descargar**y **Copiar vínculo**. De forma predeterminada, el archivo se abre en Teams. En ocasiones, es posible que el vínculo para compartir no se haya convertido a una vista previa de archivo en el momento en que un usuario envía el mensaje. El sistema generará la vista previa del archivo, pero en este escenario, el vínculo para compartir no se acortará al único nombre de archivo.

Cuando los usuarios comparten un archivo en un canal o una conversación, se les notifica si algunos o todos los destinatarios no tienen permiso para ver el archivo. Pueden cambiar los permisos del archivo antes de compartirlo haciendo clic en la flecha situada junto a la vista previa del archivo que aparece en el mensaje.

![Captura de pantalla de la notificación si los destinatarios no tienen permisos](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Copiar un vínculo para compartir en Teams

Los usuarios pueden copiar un vínculo para compartir de SharePoint y cambiar los permisos de uso compartido del mismo modo que en Microsoft 365. Pueden conceder acceso a cualquier persona, a personas de su organización, a personas con acceso existente o a personas específicas. El permiso predeterminado del vínculo es el mismo que el conjunto de permisos predeterminado en el nivel de la organización, a menos que los permisos del nivel del sitio de SharePoint lo reemplacen.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Configurar el uso compartido en OneDrive y SharePoint

Para obtener más información sobre cómo compartir archivos en OneDrive y SharePoint, incluido cómo configurar el uso compartido y cómo activar y desactivar el uso compartido, vea:

- [Información general sobre el uso compartido externo](https://docs.microsoft.com/sharepoint/external-sharing-overview) : describe lo que ocurre cuando los usuarios comparten, en función de lo que estén compartiendo y con quién.

- [Administrar la configuración de uso compartido](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : describe cómo los administradores globales y de SharePoint pueden cambiar la configuración de uso compartido en el nivel de organización para SharePoint y OneDrive.

- [Activar o desactivar el uso compartido externo en un sitio](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : describe cómo los administradores globales y de SharePoint pueden activar o desactivar el uso compartido externo en un sitio.

- [Cambiar el tipo de vínculo predeterminado para un sitio](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : describe cómo establecer el tipo de vínculo predeterminado para que sea más restrictivo.

## <a name="more-information"></a>Más información

- [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint y Teams: mejor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Compartir archivos y carpetas de OneDrive](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Compartir archivos o carpetas de SharePoint](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
