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
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138382"
---
# <a name="sharing-files-in-microsoft-teams"></a>Compartir archivos en Microsoft Teams

En Microsoft Teams, los usuarios pueden compartir contenido con otros usuarios de Teams dentro y fuera de su organización. El uso compartido en Teams se basa en la configuración de SharePoint y OneDrive, por lo que todo lo que configure para SharePoint y OneDrive también controlará el uso compartido en Teams.

## <a name="overview"></a>Descripción general

Los usuarios pueden compartir archivos desde los equipos y sitios a los que tengan acceso en OneDrive, así como también desde su equipo personal. Para compartir un archivo, los usuarios pueden hacer lo siguiente:

- En el canal, haga clic en **Adjuntar** (icono de clip), seleccione **Recientes**, **Buscar equipos y canales**, **OneDrive** o bien, **Cargar desde mi PC** y, a continuación, elija el archivo que desea compartir. <br> 
    ![Recorte de pantalla que muestra cómo compartir un archivo desde un canal](media/share-files-channel.png)
- En el chat, haga clic en **Adjuntar** (icono de clip) y seleccione **OneDrive** o bien, **Cargar desde mi PC** y, a continuación, elija el archivo que desea compartir. <br>
    ![Recorte de pantalla que muestra cómo compartir un archivo desde un chat](media/share-files-chat.png)
- Copie y pegue el vínculo para compartir en el cuadro para redactar.<br>
    ![Recorte de pantalla que muestra la vista previa del archivo en el cuadro para redactar](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>Lo que debe saber sobre la experiencia de uso compartido de archivos

### <a name="permissions-of-shared-files-and-sharing-links"></a>Permisos de los archivos compartidos y vínculos de uso compartido

Cuando los usuarios comparten un archivo buscándolo en OneDrive o en los equipos y canales, se concede acceso a todos los destinatarios además del [permiso predeterminado que se establece a nivel de la organización](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Cuando un usuario copia y pega un vínculo para compartir, los permisos definidos en el vínculo para compartir se respetan y la dirección URL de SharePoint se acorta al nombre de archivo. Es decir, Teams solo usa el nombre de archivo como vínculo para el archivo.

Cuando los usuarios comparten un archivo desde Teams, pueden configurar quién puede acceder al archivo de la misma forma en que lo harían en Microsoft 365. Pueden permitir el acceso a cualquier usuario, a los usuarios de su organización, a los usuarios con acceso previo o a personas específicas (entre las que se incluyen las personas en un chat individual, un chat de grupo o un canal).  Al compartir un archivo, la vista previa del archivo estará disponible en el mensaje, junto con todas sus acciones respectivas como **Abrir en línea**, **Descargar** y **Copiar vínculo**. De forma predeterminada, el archivo se abrirá en Teams. En ocasiones, puede que el vínculo para compartir no se haya convertido a la vista previa del archivo para el momento en que el usuario envía el mensaje. El sistema generará la vista previa del archivo, pero, en este caso particular, el vínculo para compartir no se reducirá únicamente al nombre de archivo.

Cuando un usuario comparte un archivo en un canal o chat, se le notifica cuáles son los destinatarios que no cuentan con el permiso para ver el archivo. El usuario podrá cambiar los permisos del archivo antes de compartirlo haciendo clic en la flecha situada junto a la vista previa del archivo que ahora aparece en el mensaje.

![Recorte de pantalla de la notificación si los destinatarios no tienen los permisos](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Copiar un vínculo para compartir en Teams

Los usuarios pueden copiar un vínculo para compartir de SharePoint y cambiar los permisos de uso compartido de la misma forma en que lo harían en Microsoft 365. Pueden permitir el acceso a cualquier persona, a los usuarios de la organización, a personas con acceso previo o a personas específicas. El permiso predeterminado del vínculo es el mismo que el conjunto predeterminado de permisos a nivel de la organización, a menos que los permisos a nivel del sitio de SharePoint los anulen.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Configurar el uso compartido en OneDrive y SharePoint

Para más información sobre el uso compartido de archivos en OneDrive y SharePoint, incluido cómo configurar el uso compartido y cómo activarlo o desactivarlo, consulte:

- [Información general sobre el uso compartido externo](https://docs.microsoft.com/sharepoint/external-sharing-overview): Describe lo que ocurre cuando los usuarios comparten de acuerdo con lo que compartan y con quién.

- [Administrar configuración de uso compartido](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off): Describe cómo los administradores globales y de SharePoint pueden cambiar su configuración de uso compartido a nivel de la organización para SharePoint y OneDrive.

- [Activar o desactivar el uso compartido externo de un sitio](https://docs.microsoft.com/sharepoint/change-external-sharing-site): Describe la forma en que los administradores de SharePoint y globales pueden activar o desactivar el uso compartido externo de un sitio.

- [Cambiar el tipo de vínculo predeterminado para un sitio](https://docs.microsoft.com/sharepoint/change-default-sharing-link): Describe cómo establecer el tipo de vínculo predeterminado para que sea más restrictivo.

## <a name="more-information"></a>Más información

- [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint y Teams: mejor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Compartir archivos y carpetas de OneDrive](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Compartir archivos o carpetas de SharePoint](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
