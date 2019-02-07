---
title: ¿Cuáles son las directivas de mensajería de Teams?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Descubra más cosas sobre las directivas de mensajería y cómo se pueden usar para controlar los mensajes de chats en Teams.
ms.openlocfilehash: d4d2a4f424de1750c70ea851d1d1d35a2aaf9e44
ms.sourcegitcommit: dfd075d092db9826c792cf947c83c33cfcd8ef4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "29763719"
---
# <a name="what-are-messaging-policies-in-teams"></a>¿Cuáles son las directivas de mensajería de Teams?
::: zone target="docs"
Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams. You can use the default policy that is created or create one or more custom messaging policies for people in your organization. After you create a policy, you will assign it a user or groups of users in your organization.

Policies can be easily managed in the Teams Admin Center (http://admin.teams.microsoft.com) by logging in with administrator credentials and clicking **Messaging Policies** in the left navigation. To edit the existing default policy for your organization, select the **Global (Org-wide default)** row and click **Edit**. To create a new messaging policy, click **New policy**.

![Directivas de mensajería en Teams](media/messaging-policies.png)
::: zone-end

A continuación se describe la configuración disponible para la directiva: 

- **Los propietarios pueden eliminar los mensajes enviados** Use esta opción para permitir que los propietarios eliminen los mensajes que envían los usuarios en un chat.
- **Los usuarios pueden eliminar los mensajes enviados** Use esta opción para permitir que los usuarios eliminen los mensajes que envían en un chat.
- **Los usuarios pueden editar los mensajes enviados** Use esta opción para permitir que los usuarios editen los mensajes que envían en un chat.
- **Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.
<a name="bkchat"> </a>

- **Chat** Active esta opción si desea que los usuarios de su organización puedan chatear con otras personas con la aplicación de Teams.
- **Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people. Giphy is an online database and search engine that allows users to search for and share animated GIF files. Each Giphy is assigned a content rating.
- **Clasificación de contenido de Giphy** 
    - **Sin restricción** Indica que los usuarios pueden insertar todas las imágenes Giphy en los chats, independientemente de la clasificación de contenido que tengan.
    - **Moderado** Indica que los usuarios pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.
    - **Estricto** Indica que los usuarios pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma estricta.
- **Usar Memes en las conversaciones** Si activa esta opción, los usuarios podrán incluir Memes en las conversaciones de chat que mantengan con otras personas. 
- **Usar adhesivos en las conversaciones** Si activa esta opción, los usuarios podrán incluir adhesivos en las conversaciones de chat que mantengan con otras personas.
- **Permitir vistas previas de URL** Use esta opción si desea activar o desactivar la visualización previa automática de direcciones URL en los mensajes.
- **Permitir a los usuarios traducir mensajes** Active esta opción para que los usuarios pueden traducir automáticamente los mensajes de Teams en el idioma que se especifique en su configuración de idioma personal de Office 365.

::: zone target="docs"
If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.  To assign a custom policy to a user in the Teams Admin Center, click **Users** in the left navigation, select the user you want to assign the policy to, and then choose **Edit** under **Assigned Policies**.
::: zone-end

### <a name="related-topics"></a>Temas relacionados
[Directivas de reuniones en Microsoft Teams](meeting-policies-in-teams.md)
