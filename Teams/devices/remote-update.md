---
title: Actualizar dispositivos de Microsoft Teams de forma remota
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
description: Actualizar teléfonos y barras de colaboración de Microsoft Teams de forma remota con el centro de administración de Teams
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962891"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Actualizar dispositivos de Microsoft Teams de forma remota

Con el centro de administración de Microsoft Teams, puede actualizar los dispositivos de su equipo, como teléfonos y barras de colaboración de forma remota, y puede elegir el comportamiento de actualización automática del firmware del dispositivo. Puede actualizar los siguientes elementos en los dispositivos con el centro de administración de Teams:

- Aplicación de Teams y agente de administración de Teams
- Aplicación portal de empresa
- Aplicación de agente OEM
- Firmware del dispositivo

Las actualizaciones del firmware del dispositivo se pueden aplicar automáticamente o programar para una fecha y hora futuras. Otras actualizaciones de dispositivos disponibles no se aplican automáticamente, pero se pueden aplicar de forma manual o programada para una fecha y hora futuras.

> [!NOTE]
> Si bien las actualizaciones del firmware del dispositivo se pueden programar, si la fecha y la hora programadas caen después del retraso máximo configurado de 30 o 90, la actualización del firmware se aplicará cuando se alcance el retraso máximo. La fecha y la hora programadas se pasan por alto. Además, la actualización remota de dispositivos de Microsoft Teams es una característica que aún no está disponible en los inquilinos de la nube del gobierno de Estados Unidos (GCC-High).

Para administrar dispositivos, debe ser un administrador global, un administrador de servicios de equipo o un administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, consulte [usar los roles de administrador de Microsoft Teams para administrar equipos](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Elegir comportamiento de actualización automática del firmware del dispositivo

Las actualizaciones del firmware del dispositivo se aplican automáticamente. Puede decidir si desea aplicar las actualizaciones tan pronto como se publique una (si elige esta opción, las actualizaciones se aplicarán el primer fin de semana después de que se publique una actualización) o 30 o 90 días después de que se publique una actualización. De forma predeterminada, las actualizaciones del firmware del dispositivo se aplican 30 días de la publicación.

> [!IMPORTANT]
> La versión más reciente de la actualización de firmware no se aplica en el dispositivo de Teams. En su lugar, la actualización que se aplica automáticamente en el dispositivo se retrasa en una versión. Por ejemplo, supongamos que el dispositivo tiene la versión "10" aplicada y que la versión "11" está publicada. La versión "11" aún no se aplicará. En su lugar, el dispositivo solo se actualizará a la versión "11" después de que se publique la versión "12".

> [!NOTE]
> Algunos dispositivos aún no admiten la actualización automática del firmware. La aplicación de la configuración de actualización de firmware automática en dispositivos que no admiten actualizaciones automáticas no afectará a esos dispositivos. Para obtener más información sobre si el dispositivo admite actualizaciones automáticas de firmware, póngase en contacto con el fabricante del dispositivo.

Para elegir el comportamiento de actualizaciones automáticas para sus dispositivos, haga lo siguiente:

1. Inicie sesión en el centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com
2. Navegar por los **dispositivos**  >  **Phones** o las **barras de colaboración**
3. Seleccione uno o más dispositivos y, después, seleccione **Actualizar** .
4. En **actualización automática del firmware**, seleccione una de las opciones siguientes:
    - **Tan pronto como esté disponible** Second-la actualización del firmware del dispositivo más reciente se aplica el primer fin de semana después de que se publique la última actualización.
    - **Aplazar 30 días** Second-la actualización del firmware del dispositivo más reciente se aplica 30 días después de que se publique la actualización más reciente.
    - **Diferir 90 días** Segunda: se aplica la actualización del firmware del dispositivo más reciente 90 días después de que se publique la actualización más reciente.
5. Seleccione **Actualizar**

Si, por cualquier motivo, necesita revertir una actualización del firmware del dispositivo, debe restablecer el dispositivo a la configuración de fábrica. Restablece tu dispositivo con las instrucciones del fabricante.  

## <a name="manually-update-remote-devices"></a>Actualizar manualmente los dispositivos remotos

Al actualizar uno o más dispositivos con el centro de administración, puede decidir si desea actualizar los dispositivos inmediatamente o programar una actualización para una fecha y hora futuras.

Para actualizar los dispositivos remotos de forma manual, haga lo siguiente:

1. Inicie sesión en el centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com
2. Navegar por los **dispositivos**  >  **Phones** o las **barras de colaboración**
3. Seleccione uno o más dispositivos y, después, seleccione **Actualizar** .
4. En **actualizaciones manuales**, seleccione **programación** si desea programar la actualización para una fecha y hora futuras. Las actualizaciones se aplican en la fecha y hora de la zona horaria seleccionada en la zona **horaria**.

Lo que verás depende de si tienes uno o varios dispositivos seleccionados. La imagen de la izquierda muestra varios dispositivos seleccionados mientras que la imagen de la derecha muestra un solo dispositivo seleccionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Vistas de dispositivo único y múltiple en el panel estado de actualización de dispositivo":::

Al seleccionar varios dispositivos, puede elegir qué tipos de actualización aplicar a cada dispositivo seleccionado. Seleccione los tipos de actualización que desea aplicar y seleccione **Actualizar**.

Cuando selecciona un solo dispositivo, se muestran las actualizaciones que están disponibles para el dispositivo. Si hay varios tipos de actualización disponibles para el dispositivo, seleccione cada tipo de actualización que quiera aplicar. Puede ver la **versión actual** aplicada en el dispositivo y la **nueva versión** que se aplicará. Seleccione las actualizaciones que desea aplicar y seleccione **Actualizar**.

Después de seleccionar **Actualizar**, las actualizaciones se aplican a los dispositivos en la fecha y la hora que seleccionó Si programó una actualización. Si no ha seleccionado una fecha y hora futuras, las actualizaciones se aplicarán a sus dispositivos en unos minutos.
