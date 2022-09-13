---
title: Solicitudes de usuario para administradores
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
ms.openlocfilehash: 62d34aae25ef1ebff585ea430aeb3db20856669a
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657330"
---
# <a name="manage-user-requests"></a>Administrar solicitudes de usuario

Las aplicaciones que están bloqueadas en su organización pueden afectar a la productividad y la colaboración del usuario final. Los usuarios finales no pueden usar aplicaciones bloqueadas, pero pueden ver dichas aplicaciones y su información en la tienda de Teams, así como solicitar la aprobación de los administradores. Después de evaluar la solicitud, puede optar por permitir una aplicación o descartarla.

Esta funcionalidad le proporciona una señal sobre la demanda de una aplicación dentro de su organización. Puede ver fácilmente el número agregado de solicitudes para cada aplicación solicitada. Te ayuda a tomar una decisión informada sobre qué aplicaciones debes evaluar para permitirlas.

Conservas el control completo de las aplicaciones que se permiten o bloquean para los usuarios. Si elige permitir una aplicación, los controles y la interfaz de usuario para administrar aplicaciones seguirán siendo los mismos.

* La opción predeterminada envía las solicitudes de usuario al Centro de administración de Teams, donde puede [ver las solicitudes de usuario y permitir las aplicaciones solicitadas](#view-user-requests-in-teams-admin-center).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Captura de pantalla que muestra la opción de solicitar a un administrador que apruebe una aplicación bloqueada.":::

* Una personalización le permite [configurar la experiencia del usuario final](#modify-the-default-setting-to-receive-end-user-requests) más adecuada para su organización. Puede proporcionar una instrucción o un mensaje personalizado que se muestra en la tienda de aplicaciones de Teams y la opción de aprobación de la solicitud dirige a los usuarios a una dirección URL específica de la organización para recopilar sus solicitudes.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Captura de pantalla que muestra la experiencia del usuario final de las aplicaciones en store cuando un administrador redirige la dirección URL de solicitud de aplicación permitida a una dirección URL específica de la organización.":::

## <a name="view-user-requests-in-teams-admin-center"></a>Ver solicitudes de usuario en el Centro de administración de Teams

Las solicitudes de usuario final recibidas con el método predeterminado se muestran en el Centro de administración de Teams. Puede ver y administrar fácilmente las solicitudes. Se recomienda una clasificación regular para comprobar las solicitudes de los usuarios finales. Para ver y permitir las aplicaciones, sigue estos pasos:

1. Inicie sesión en el Centro de administración de Teams y vaya a Aplicaciones  > **de Teams**[**Administrar aplicaciones**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Elija si desea mostrar la columna **Solicitudes por usuarios** . También puede ordenar la columna.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Captura de pantalla que muestra la columna de solicitudes de usuario en el Centro de administración de Teams y que se puede ordenar." lightbox="media/user-requests-tac-expanded.png":::

1. Para abrir la página de detalles de la aplicación que quieras permitir, selecciona el nombre de la aplicación.

1. Seleccione **Administrar solicitudes**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Captura de pantalla que muestra la opción administrar solicitudes en la página de detalles de la aplicación." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Siga uno o varios de los siguientes pasos, tal y como se muestra en el cuadro de diálogo emergente. Los pasos para aprobar una aplicación varían en función del método utilizado para bloquearla.

   * Si la aplicación se bloquea mediante directivas de permisos, [modifique las directivas de permisos](teams-app-permission-policies.md).
   * Si la aplicación está bloqueada para todos los usuarios, [permita la aplicación](manage-apps.md#allow-and-block-apps).
   * Si todas las aplicaciones están bloqueadas para todos los usuarios, [modifique la configuración de toda la organización](manage-apps.md#manage-org-wide-app-settings).

Los usuarios finales pueden ver la opción **Agregar** de una aplicación en la tienda de Teams para comprobar si se permite la aplicación. Cuando permite una aplicación después de recibir solicitudes en el Centro de administración de Teams, Teams no informa a los usuarios finales de que se debe a su solicitud. Al permitir una aplicación, el contador de solicitudes no se restablece a cero.

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Modificar la configuración predeterminada para recibir solicitudes del usuario final

Teams proporciona un mensaje predeterminado para que los usuarios soliciten la aprobación de una aplicación. Puede modificar la configuración predeterminada para agregar un mensaje personalizado con instrucciones, una dirección URL específica de la organización o ambas. Las modificaciones se muestran para cada aplicación en la tienda de Teams.

Para configurar un mensaje personalizado y redirigir a los usuarios a una dirección URL específica de la organización, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y vaya a Aplicaciones  > **de Teams**[**Administrar aplicaciones**](https://admin.teams.microsoft.com/policies/manage-apps).

1. En la esquina superior derecha, seleccione **Configuración de aplicaciones para toda la organización**.

1. Para mostrar un mensaje personalizado o instrucciones en el almacén de Teams, escriba un mensaje de texto en el campo de texto en **Configuración de solicitudes de usuario**.

1. Para proporcionar una dirección URL específica de la organización para recopilar solicitudes de usuario, siga estos pasos:

   1. Activa el botón de alternancia **Redirigir solicitudes a vínculo externo** .
   1. Proporcione la dirección URL específica de su organización.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Captura de pantalla para cambiar la personalización de la dirección URL de la solicitud del usuario para desbloquear la aplicación en la interfaz de usuario de configuración de toda la organización.":::

1. Seleccione **Guardar**.

Los métodos para evaluar y permitir las aplicaciones solicitadas siguen siendo los mismos.

## <a name="dismiss-user-requests"></a>Descartar solicitudes de usuario

Para descartar las solicitudes a una aplicación permitida, siga estos pasos:

1. Seleccione el nombre de la aplicación para la que desea descartar las solicitudes de usuario.
1. Seleccione **Administrar solicitudes**.
1. En el cuadro de diálogo Administrar solicitudes de usuario, seleccione **Descartar todas las solicitudes**.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Los administradores puede aprobar una solicitud de usuario al permitir una aplicación o descartar la solicitud y no realizar ninguna acción.":::

Si descartas una solicitud, no se informará al usuario final de que se debe a su acción. Al descartar una solicitud para permitir una aplicación, el número de solicitudes en el centro de administración se restablece a cero. Además, después de pocas horas de descartar una solicitud, los usuarios finales pueden volver a solicitar que se permita la misma aplicación.

## <a name="related-article"></a>Artículo relacionado

* [Información general sobre cómo administrar aplicaciones de terceros](manage-apps.md).
