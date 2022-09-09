---
title: Solicitudes de usuario para administradores para permitir aplicaciones
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Obtenga información sobre cómo administrar y configurar la solicitud del usuario final para permitir las aplicaciones que están bloqueadas en una organización.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: c47578184aa97f9c6cc366e186c1590ef1e3fba4
ms.sourcegitcommit: ebffec34c050421dc8d09a16907644657ce323f4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "67637320"
---
# <a name="manage-user-requests-to-allow-apps-that-are-blocked-by-admins"></a>Administrar solicitudes de usuario para permitir aplicaciones que los administradores bloquean

Las aplicaciones que bloquee en su organización pueden reducir la productividad y la colaboración del usuario final. Los usuarios finales no pueden usar las aplicaciones que están disponibles en la tienda de Teams, pero que están bloqueadas en su organización. Sin embargo, para mantenerse informados, los usuarios finales pueden ver las aplicaciones bloqueadas, la información de la aplicación y los casos de uso que los servidores. Los usuarios pueden solicitar la aprobación del administrador para que puedan usar estas aplicaciones en Teams, después de elegir permitir la aplicación.

Esta funcionalidad le proporciona una señal sobre la demanda de una aplicación dentro de su organización. Puede ver fácilmente el número agregado de solicitudes de aplicaciones y tomar decisiones informadas sobre qué aplicaciones considerar permitir en su organización.

Conservas el control completo de las aplicaciones que se permiten o bloquean para los usuarios. Si elige permitir una aplicación, los controles y la interfaz de usuario para administrar aplicaciones seguirán siendo los mismos.

* La opción predeterminada envía las solicitudes de usuario en el Centro de administración de Teams, donde puede [ver las solicitudes de usuario y permitir las aplicaciones solicitadas](#view-user-requests-and-allow-the-requested-apps).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Captura de pantalla que muestra la opción de solicitar a un administrador que apruebe una aplicación bloqueada.":::

* Una personalización le permite [configurar la experiencia del usuario final](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app) redirigiendo al usuario a un método de solicitud de aplicación personalizado. Puede proporcionar un mensaje de texto personalizado para informar a los usuarios y dirigir a los usuarios a la dirección URL interna de su organización para que recopile solicitudes para permitir las aplicaciones.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Captura de pantalla que muestra la experiencia del usuario final de las aplicaciones en store cuando un administrador redirige la dirección URL de solicitud de aplicación permitida a una dirección URL personalizada.":::

## <a name="modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app"></a>Modificar la configuración predeterminada para recibir solicitudes del usuario final para permitir una aplicación

Para configurar un mensaje personalizado y redirigir a los usuarios a una dirección URL específica de la organización para solicitar la aprobación de la aplicación, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a la página **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)** >  de **Teams**.

1. Seleccione Configuración de aplicaciones para toda la organización.

1. Para mostrar un mensaje personalizado o instrucciones en el almacén de clientes de Teams, proporcione un mensaje de texto en Configuración de solicitudes de usuario.

1. Para proporcionar una dirección URL específica de la organización para recopilar solicitudes de usuario, haga lo siguiente:

   1. Cambie la opción Solicitudes de redirección a herramienta externa a Activado.
   1. Proporcione su dirección URL personalizada específica de la organización.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Captura de pantalla para cambiar la personalización de la dirección URL de la solicitud del usuario para desbloquear la aplicación en la interfaz de usuario de configuración de toda la organización.":::

1. Seleccione **Guardar**.

## <a name="view-user-requests-and-allow-the-requested-apps"></a>Ver solicitudes de usuario y permitir las aplicaciones solicitadas

Las solicitudes de usuario final recibidas con el método predeterminado se muestran en el Centro de administración de Teams. Puede ver y administrar fácilmente las solicitudes. Se recomienda encarecidamente tener una evaluación periódica de prioridades para comprobar las solicitudes del usuario final. Para ver y permitir las aplicaciones, sigue estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a la página **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)** >  de **Teams**.

1. Elija si desea mostrar la columna **Solicitudes por usuarios** . También puede ordenar la columna.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Captura de pantalla que muestra la columna de solicitudes de usuario en el Centro de administración de Teams y que se puede ordenar." lightbox="media/user-requests-tac-expanded.png":::

1. Para abrir la página de detalles de la aplicación que quieras permitir, selecciona el nombre de la aplicación.

1. Seleccione **Administrar solicitudes**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Captura de pantalla que muestra la opción administrar solicitudes en la página de detalles de la aplicación." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Siga uno o varios de los siguientes pasos, tal y como se muestra en el cuadro de diálogo emergente. Los pasos para aprobar una aplicación varían en función del método utilizado para bloquearla.

   * Si la aplicación se bloquea mediante directivas de permisos, [modifique las directivas de permisos](teams-app-permission-policies.md).
   * Si la aplicación está bloqueada para todos los usuarios, [permita la aplicación](manage-apps.md#allow-and-block-apps).
   * Si todas las aplicaciones están bloqueadas para todos los usuarios, [modifique la configuración de toda la organización](manage-apps.md#manage-org-wide-app-settings).

1. Opcionalmente, para cambiar a una configuración personalizada a la dirección URL específica de su organización, seleccione el vínculo Configurar solicitudes de usuario en el cuadro de diálogo Administrar solicitudes de usuario. Se abrirá el panel de configuración de aplicaciones para toda la organización, en el que puede [configurar la experiencia de solicitud del usuario final](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app).

Si permite una aplicación después de recibir solicitudes en el Centro de administración de Teams, Teams no informa al usuario final de que se trata de una solicitud. El usuario puede comprobar la aplicación en la Tienda Teams para comprobar si se permite la aplicación. La opción Agregar la aplicación está disponible para el usuario después de permitirla. Si permite una aplicación después de recibir solicitudes a través de su método específico de la organización, se aplicarán los mecanismos internos para proporcionar una actualización de estado al usuario final.

Para restablecer el número de solicitudes de aplicación a cero, descarte las solicitudes. Solo permitir una aplicación no restablece su contador de solicitudes a cero.

## <a name="dismiss-user-requests"></a>Descartar solicitudes de usuario

Para descartar las solicitudes para permitir la aplicación, sigue estos pasos:

1. Seleccione el nombre de la aplicación para la que desea descartar las solicitudes de usuario.
1. Seleccione **Administrar solicitudes** y seleccione **Descartar todas las solicitudes** en el cuadro de diálogo.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Los administradores puede aprobar una solicitud de usuario al permitir una aplicación o descartar la solicitud y no realizar ninguna acción.":::

Si descartas una solicitud, no se informará al usuario final de que se debe a su acción. Al descartar una solicitud para permitir una aplicación, el número de solicitudes en el centro de administración se restablece a cero. Además, después de pocas horas de descartar una solicitud, los usuarios finales pueden volver a solicitar que se permita la misma aplicación.

## <a name="related-article"></a>Artículo relacionado

* [Información general sobre cómo administrar aplicaciones de terceros](manage-apps.md).
