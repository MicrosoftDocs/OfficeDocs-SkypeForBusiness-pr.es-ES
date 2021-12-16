---
title: Cerrar sesión en Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: Obtenga información sobre cómo cerrar sesión en Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5789dac9d54de153c6d4c712a2d68367ad79c0
ms.sourcegitcommit: 8d728ca42dc917a28b94e2de84ce4f5b2515d485
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61513601"
---
# <a name="sign-out-of-microsoft-teams"></a>Cerrar sesión en Microsoft Teams

Se recomienda que los usuarios mantengan la sesión iniciada en la aplicación de Microsoft Teams para seguir recibiendo chats, llamadas entrantes y otras actividades. Somos conscientes de que, en ocasiones, es posible que los usuarios quieran cerrar sesión en la aplicación de Teams por varias razones:

- Porque han terminado de usar Teams por el resto del día
- Quieren usar una cuenta diferente
- Porque están en un dispositivo que comparten con otra persona

Por estos motivos y otros, Teams le permite cerrar sesión en la aplicación y finalizar la sesión.

## <a name="account-sharing-between-apps"></a>Uso compartido de cuentas entre aplicaciones

Los sistemas operativos modernos permiten compartir cuentas entre diferentes aplicaciones en un dispositivo. Este diseño de inicio de sesión único (SSO) permite a los usuarios usar varias aplicaciones en su dispositivo sin necesidad de iniciar sesión en cada aplicación. Teams no controla este comportamiento, pero aprovecha la comodidad que este diseño proporciona para la experiencia del usuario final.

El inicio de sesión único tiene un impacto importante en el cierre de sesión. Cuando los usuarios cierran sesión en Teams, los datos asociados a su cuenta se quitan de la aplicación Teams, pero otras aplicaciones del dispositivo podrían seguir teniendo acceso a su cuenta. También significa que es posible que no se pida a los usuarios que vuelvan a escribir sus credenciales si deciden volver a iniciar sesión en Teams con la misma cuenta.

## <a name="sign-out-of-teams-on-desktop"></a>Cerrar sesión de Teams en el escritorio

Para cerrar sesión en el cliente de escritorio de Teams o en el explorador, seleccione su imagen de perfil en la parte superior de la aplicación y seleccione **Cerrar sesión**.

Para la aplicación de escritorio, también puede hacer clic con el botón derecho en el icono de la aplicación en la barra de tareas y seleccionar **Cerrar sesión**.

Si tiene varias cuentas agregadas, deberá cerrar la sesión de cada cuenta individual. Una vez que haya cerrado la sesión de las cuentas en Teams, es posible que tenga que escribir sus credenciales de nuevo en el siguiente inicio de la aplicación para acceder a su cuenta.

## <a name="sign-out-of-teams-on-mobile-devices"></a>Cerrar sesión de Teams en dispositivos móviles

En dispositivos móviles, puede cerrar sesión en Teams dirigiéndose al menú y eligiendo el menú **Más**, para luego elegir **Cerrar sesión**. Una vez que se haya cerrado la sesión, deberá volver a introducir sus credenciales la próxima vez que inicie la aplicación.

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>Inicio y cierre de sesión globales para trabajadores de primera línea

La aplicación de Android de Teams ahora es compatible con el inicio y cierre de sesión globales para que los trabajadores de primera línea pueden iniciar y cerrar sesión sin problemas. Los empleados pueden elegir un dispositivo del grupo de dispositivos compartidos y realizar un inicio de sesión único para "hacerlo suyo" por la duración del turno. Una vez finalizado su turno, deberían ser capaces de realizar la sesión de forma global en el dispositivo. Este proceso quitará toda su información personal y de la compañía del dispositivo para que pueda devolverlo al grupo de dispositivos. Para obtener esta funcionalidad, el dispositivo debe estar en modo compartido. Para obtener información sobre cómo configurar un dispositivo compartido, consulte [Cómo usar un modo de dispositivo compartido en Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

## <a name="manual-cleanup"></a>Limpieza manual

Aunque es poco frecuente, es posible que Teams no pueda limpiarse después de cerrar sesión por completo. En base a los informes de usuario, las causas comunes incluyen archivos bloqueados por un servicio que se ejecuta en el sistema, pero podría haber otras razones que dependan de las configuraciones o directivas de un dispositivo individual y de los permisos de usuario aplicados al dispositivo.

Una manifestación común de este problema es que Teams intentará seleccionar automáticamente una cuenta existente para iniciar la sesión del usuario. En situaciones como esta, es posible que el usuario quiera limpiar manualmente la caché local de Teams. Obtenga más información en [Iniciar sesión o quitar una cuenta de Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US).

## <a name="related-topics"></a>Temas relacionados

[Iniciar sesión o quitar una cuenta de Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)
