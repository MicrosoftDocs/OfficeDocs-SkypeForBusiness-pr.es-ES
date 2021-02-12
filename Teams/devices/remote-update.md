---
title: Actualizar los dispositivos de Microsoft Teams de forma remota
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Actualizar los teléfonos y las barras de colaboración de Microsoft Teams de forma remota mediante el Centro de administración de Teams
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962891"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Actualizar los dispositivos de Microsoft Teams de forma remota

Con el Centro de administración de Microsoft Teams, puede actualizar sus dispositivos de Teams, como teléfonos y barras de colaboración, de forma remota, y puede elegir el comportamiento de la actualización automática del firmware del dispositivo. Puede actualizar lo siguiente en sus dispositivos mediante el Centro de administración de Teams:

- Agente de administración de la aplicación Teams y de los equipos
- Aplicación del portal de la empresa
- Aplicación de agente OEM
- Firmware del dispositivo

Las actualizaciones de firmware de los dispositivos se pueden aplicar de forma automática o programada para una fecha y hora futuras. Otras actualizaciones de dispositivo disponibles no se aplican automáticamente, pero se pueden aplicar de forma manual o programada para una fecha y hora futuras.

> [!NOTE]
> Aunque las actualizaciones de firmware del dispositivo se pueden programar, si la fecha y hora programadas son 30 o 90 días después del retraso máximo configurado, la actualización del firmware se aplica cuando se alcanza el retraso máximo. La fecha y hora programadas se pasan por alto. Además, la actualización remota de dispositivos de Microsoft Teams es una característica que aún no está disponible en los inquilinos de la nube del gobierno de Estados Unidos (GCC-High).

Para administrar dispositivos, debe ser administrador global, administrador del servicio de Teams o administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, [consulte Usar roles de administrador de Microsoft Teams para administrar Teams.](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>Elegir el comportamiento de actualización automática del firmware del dispositivo

Las actualizaciones de firmware del dispositivo se aplican automáticamente. Puede decidir si desea aplicar actualizaciones tan pronto como se haya publicado (si elige esta opción, las actualizaciones se aplicarán el primer fin de semana después de publicar una actualización), o 30 o 90 días después de que se haya publicado una actualización. De forma predeterminada, las actualizaciones de firmware del dispositivo se aplican 30 días uno de ellos.

> [!IMPORTANT]
> La última versión de actualización de firmware no se aplica en el dispositivo de Teams. En su lugar, la actualización que se aplica automáticamente en el dispositivo se retrasa en una versión. Por ejemplo, supongamos que el dispositivo tiene aplicada la versión "10" y que se publicó la versión "11". La versión "11" no se aplicará todavía. En su lugar, el dispositivo solo se actualizará a la versión "11" después de que se publicó la versión "12".

> [!NOTE]
> Algunos dispositivos todavía no admiten la actualización automática de firmware. Aplicar la configuración de actualización automática de firmware en dispositivos que no admiten actualizaciones automáticas no tendrá ningún efecto en esos dispositivos. Para preguntas sobre si el dispositivo admitirá actualizaciones automáticas de firmware, póngase en contacto con el fabricante del dispositivo.

Para elegir el comportamiento de la actualización automática de sus dispositivos, haga lo siguiente:

1. Inicia sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com
2. Navegar por  >  **teléfonos o barras** de **colaboración**
3. Selecciona uno o más dispositivos y, a continuación, selecciona **Actualizar**
4. En **Actualización automática de firmware,** seleccione una de las siguientes opciones:
    - **Tan pronto como esté disponible** La actualización de firmware del segundo dispositivo más reciente se aplica el primer fin de semana después de la última actualización.
    - **Aplazar 30 días** La actualización de firmware del segundo dispositivo más reciente se aplica 30 días después de la última actualización.
    - **Aplazar 90 días** La actualización de firmware del segundo dispositivo más reciente se aplica 90 días después de la última actualización.
5. Seleccione **Actualizar**

Si, por cualquier motivo, necesita revertir una actualización de firmware del dispositivo, debe restablecer la configuración de fábrica del dispositivo. Restablece el dispositivo con las instrucciones del fabricante.  

## <a name="manually-update-remote-devices"></a>Actualizar manualmente dispositivos remotos

Al actualizar uno o más dispositivos con el Centro de administración, puede decidir si desea actualizar los dispositivos inmediatamente o programar una actualización para una fecha y hora futura.

Para actualizar manualmente los dispositivos remotos, haga lo siguiente:

1. Inicia sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com
2. Navegar por  >  **teléfonos o barras** de **colaboración**
3. Selecciona uno o más dispositivos y, a continuación, selecciona **Actualizar**
4. En **Actualizaciones manuales,** **seleccione Programación** si desea programar la actualización para una fecha y hora futuras. Las actualizaciones se aplican en la fecha y hora de la zona horaria seleccionada en **la zona horaria.**

Lo que verá dependerá de si tiene uno o varios dispositivos seleccionados. La siguiente imagen de la izquierda muestra varios dispositivos seleccionados, mientras que la imagen de la derecha muestra un único dispositivo seleccionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Una sola vista de varios dispositivos en el panel de estado de actualización del dispositivo":::

Al seleccionar varios dispositivos, puede elegir qué tipos de actualización se aplicarán a cada dispositivo seleccionado. Seleccione los tipos de actualización que quiera aplicar y seleccione **Actualizar.**

Cuando selecciona un único dispositivo, se muestran las actualizaciones disponibles para el dispositivo. Si hay varios tipos de actualización disponibles para el dispositivo, seleccione los tipos de actualización que quiere aplicar. Puede ver la **versión actual** aplicada en el dispositivo y la **nueva** versión que se aplicará. Seleccione las actualizaciones que quiera aplicar y, después, haga clic en **Actualizar.**

Después de seleccionar **Actualizar,** las actualizaciones se aplicarán a los dispositivos en la fecha y hora que haya seleccionado si programó una actualización. Si no seleccionaste una fecha y hora futuras, las actualizaciones se aplicarán en los dispositivos en unos minutos.
