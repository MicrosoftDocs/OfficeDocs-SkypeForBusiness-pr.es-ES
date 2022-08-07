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
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Actualizar los teléfonos, los paneles de Teams y las barras de colaboración de Microsoft Teams de forma remota mediante el Centro de administración de Teams
ms.openlocfilehash: 36f84025feec5b88b2cbf28a52fcb89cb76aeaa5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269465"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Actualizar los dispositivos de Microsoft Teams de forma remota

Con el Centro de administración de Microsoft Teams, puede actualizar sus dispositivos de Teams, como teléfonos, paneles de Teams y barras de colaboración, de forma remota, y puede elegir el comportamiento de actualización automática del firmware del dispositivo. Puede actualizar lo siguiente en sus dispositivos con el Centro de administración de Teams:

- Agente de administración de equipos y aplicaciones de Teams
- Aplicación del portal de empresa
- Aplicación de agente OEM
- Firmware del dispositivo

Las actualizaciones de firmware del dispositivo se pueden aplicar automáticamente o programar para una fecha y hora futuras. Otras actualizaciones de dispositivos disponibles no se aplican automáticamente, pero se pueden aplicar manualmente o programadas para una fecha y hora futuras.

> [!NOTE]
> Aunque se pueden programar actualizaciones de firmware del dispositivo, si la fecha y hora programadas se producen después de un retraso máximo de 30 o 90 días, la actualización de firmware se aplica cuando se alcanza el retraso máximo. La fecha y hora programadas se pasan por alto. Además, actualizar los dispositivos de Microsoft Teams de forma remota es una característica que aún no está disponible en los inquilinos de US Government Cloud (GCC-High).

Para administrar dispositivos, debe ser administrador global, administrador de servicios de Teams o administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Elegir el comportamiento de actualización automática de firmware del dispositivo

Las actualizaciones de firmware del dispositivo se aplican automáticamente. Puede decidir si quiere aplicar las actualizaciones tan pronto como se publique una (si elige esta opción, las actualizaciones se aplican el primer fin de semana después de que se publique una actualización) o 30 o 90 días después de la actualización. De manera predeterminada, las actualizaciones de firmware del dispositivo se aplican 30 días después del lanzamiento.

> [!IMPORTANT]
> La última versión de actualización de firmware no se aplica en su dispositivo de Teams. En su lugar, la actualización que se aplica automáticamente en el dispositivo se retrasa en una versión. Por ejemplo, supongamos que el dispositivo tiene aplicada la versión "10" y se publica la versión "11". La versión "11" aún no se aplicará. En su lugar, el dispositivo solo se actualizará a la versión "11" después de que se publique la versión "12".

> [!NOTE]
> Algunos dispositivos aún no admiten la actualización automática de firmware. Aplicar la configuración de actualización automática de firmware en dispositivos que no admiten actualizaciones automáticas no tendrá ningún efecto en esos dispositivos. Para preguntas sobre si el dispositivo admitirá actualizaciones automáticas de firmware, ponte en contacto con el fabricante del dispositivo.

Para elegir el comportamiento de actualización automática para los dispositivos, haga lo siguiente:

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue por **los teléfonos IP** de **los dispositivos** >  de Teams, las **barras de colaboración** o **los paneles de Teams**.
3. Selecciona uno o más dispositivos y, a continuación **, actualizar.**
4. En **Actualización automática de firmware**, selecciona una de las siguientes opciones:
    - **Tan pronto como esté disponible** La segunda actualización de firmware del dispositivo más reciente se aplica el primer fin de semana después de que se publique la actualización más reciente.
    - **Aplazar 30 días** La segunda actualización de firmware del dispositivo más reciente se aplica 30 días después del lanzamiento de la última actualización.
    - **Aplazar 90 días** La segunda actualización de firmware del dispositivo más reciente se aplica 90 días después del lanzamiento de la última actualización.
5. Selecciona **Actualizar**.

Si, por cualquier motivo, necesitas revertir una actualización de firmware del dispositivo, debes restablecer el dispositivo a su configuración de fábrica. Restablece el dispositivo siguiendo las instrucciones del fabricante.  

## <a name="manually-update-remote-devices"></a>Actualizar manualmente los dispositivos remotos

Cuando actualizas uno o más dispositivos mediante el centro de administración, puedes decidir si quieres actualizar los dispositivos inmediatamente o programar una actualización para una fecha y hora futuras.

Para actualizar manualmente los dispositivos remotos, haz lo siguiente:

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue por **los teléfonos IP** de **los dispositivos** >  de Teams, las **barras de colaboración** o **los paneles de Teams**.
3. Selecciona uno o más dispositivos y, a continuación **, actualizar.**
4. En **Actualizaciones manuales**, selecciona **Programar** si quieres programar la actualización para una fecha y hora futuras. Las actualizaciones se aplican en la fecha y hora en la zona horaria seleccionada en **la zona horaria**.

Lo que verás dependerá de si tienes uno o varios dispositivos seleccionados. La siguiente imagen izquierda muestra varios dispositivos seleccionados, mientras que la imagen de la derecha muestra un único dispositivo seleccionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Vistas de un solo dispositivo y de varios dispositivos en el panel de estado de actualización de dispositivos.":::

Al seleccionar varios dispositivos, puedes elegir qué tipos de actualización se aplicarán a cada dispositivo seleccionado. Selecciona los tipos de actualización que quieras aplicar y selecciona **Actualizar**.

Al seleccionar un único dispositivo, se muestran las actualizaciones disponibles para el dispositivo. Si hay varios tipos de actualizaciones disponibles para el dispositivo, selecciona cada tipo de actualización que quieras aplicar. Puede ver la **versión actual** aplicada en el dispositivo y la **nueva versión** que se aplicará. Selecciona las actualizaciones que quieras aplicar y selecciona **Actualizar**.

Después de seleccionar **Actualizar**, las actualizaciones se aplican a los dispositivos en la fecha y hora que seleccionaste si programaste una actualización. Si no seleccionaste una fecha y hora futuras, las actualizaciones se aplican a los dispositivos en unos minutos.
