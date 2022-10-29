---
title: Administrar la aplicación Elogiar en el Centro de administración de Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: how-to
ms.service: msteams
ms.localizationpriority: medium
description: Obtenga información sobre cómo administrar la aplicación Elogiar en el Centro de administración de Microsoft Teams.
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.openlocfilehash: a14b35811158d253aa3a211521c568f23869b043
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784345"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Administrar la aplicación Elogiar en el Centro de administración de Microsoft Teams

La aplicación Elogiar de Microsoft Teams ayuda a los usuarios a mostrar su agradecimiento a los miembros de su organización o clase. Los distintivos de Elogiar están diseñados para ayudar a reconocer el esfuerzo que se realiza en la amplia gama de trabajo que realizan los usuarios de Teams, desde educadores hasta trabajadores de primera línea. Para obtener más información, consulte [Enviar elogios a los usuarios](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Los administradores deben tener una licencia de Teams para acceder a esta característica. Si intenta acceder a esta característica sin una licencia de Teams, recibirá un mensaje de error.

> [!NOTE]
> La aplicación Elogiar está disponible para el entorno de nube GCC, pero no para GCC High o DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Habilitar o deshabilitar Elogio en su organización

Elogio está habilitado de forma predeterminada para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Captura de pantalla de la página de detalles de la aplicación Elogiar en el Centro de administración de Teams, que muestra el botón de alternancia Estado.":::

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la lista de aplicaciones, busca la aplicación Elogiar, selecciónala y cambia el botón de alternancia **Estado** a **Bloqueada** o **Permitida**.

Tenga en cuenta que esta configuración afecta tanto a la aplicación Elogiar como a la característica Elogiar de la aplicación Viva Insights en Teams.

Si establece el Estado en Bloqueado, la aplicación Elogiar se bloqueará en unos minutos para Teams. Sin embargo, elogios en Viva Insights pueden tardar entre 7 y 9 días en bloquearse.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Elogio para usuarios específicos de su organización

Para permitir o impedir que usuarios específicos de su organización usen Elogiar, asegúrese de que Elogiar está activado para su organización en la página [Administrar aplicaciones](manage-apps.md) . A continuación, cree una directiva personalizada para los permisos de la aplicación y asígnela a esos usuarios. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-app-permission-policies.md).

## <a name="badges"></a>Insignias

Este es el conjunto predeterminado de distintivos en Elogiar. Los usuarios de Teams de su organización pueden usar estos distintivos para reconocer a sus compañeros por ir más allá con su trabajo.

:::image type="content" source="media/default-set-praise.png" alt-text="Imagen de distintivos en el conjunto de distintivos predeterminado.":::

> [!NOTE]
> A partir de febrero de 2022, los usuarios solo pueden enviar y recibir distintivos predeterminados. Los distintivos personalizados ya no están disponibles y las opciones para los distintivos personalizados se han quitado del Centro de administración de Teams.

## <a name="related-articles"></a>Artículos relacionados

[Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
