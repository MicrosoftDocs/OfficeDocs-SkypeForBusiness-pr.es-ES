---
title: Actualizar Microsoft Teams dispositivos de forma remota
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
description: Actualizar Microsoft Teams teléfonos, paneles Teams y barras de colaboración de forma remota con el centro Teams administración
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347891"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Actualizar Microsoft Teams dispositivos de forma remota

Con el centro de administración de Microsoft Teams, puede actualizar sus dispositivos Teams, como teléfonos Teams, paneles Teams y barras de colaboración, de forma remota, y puede elegir el comportamiento de actualización automática del firmware del dispositivo. Puede actualizar lo siguiente en sus dispositivos con el centro Teams administración:

- Teams de administración de aplicaciones y equipos
- Aplicación portal de empresa
- Aplicación de agente OEM
- Firmware del dispositivo

Las actualizaciones de firmware del dispositivo se pueden aplicar automáticamente o programar para una fecha y hora futuras. Otras actualizaciones de dispositivo disponibles no se aplican automáticamente, pero se pueden aplicar manualmente o programar para una fecha y hora futuras.

> [!NOTE]
> Aunque las actualizaciones de firmware del dispositivo se pueden programar, si la fecha y la hora programadas se encuentran después del retraso máximo configurado de 30 o 90 días, la actualización del firmware se aplica cuando se alcanza el retraso máximo. La fecha y hora programadas se pasan por alto. Además, la actualización Microsoft Teams dispositivos de forma remota es una característica que aún no está disponible en los inquilinos de la nube del gobierno de Estados Unidos (GCC-High).

Para administrar dispositivos, debe ser administrador global, administrador Teams servicio o Teams de dispositivos. Para obtener más información sobre los roles de administrador, [vea Usar Microsoft Teams de administrador para administrar Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Elegir el comportamiento de actualización automática del firmware del dispositivo

Las actualizaciones de firmware del dispositivo se aplican automáticamente. Puede decidir si desea aplicar actualizaciones tan pronto como se haya publicado una (si elige esta opción, las actualizaciones se aplican el primer fin de semana después de publicar una actualización) o 30 o 90 días después de que se haya publicado una actualización. De forma predeterminada, las actualizaciones de firmware del dispositivo se aplican 30 días una publicada.

> [!IMPORTANT]
> La última versión de actualización de firmware no se aplica en el Teams dispositivo. En su lugar, la actualización que se aplica automáticamente en el dispositivo se retrasa con una versión. Por ejemplo, supongamos que el dispositivo tiene la versión "10" aplicada y se publicó la versión "11". La versión "11" aún no se aplicará. En su lugar, el dispositivo solo se actualizará a la versión "11" después de que se publicó la versión "12".

> [!NOTE]
> Algunos dispositivos aún no admiten la actualización automática del firmware. Aplicar la configuración automática de actualización de firmware en dispositivos que no admiten actualizaciones automáticas no tendrá ningún efecto en esos dispositivos. Para obtener preguntas sobre si el dispositivo admitirá actualizaciones automáticas de firmware, póngase en contacto con el fabricante del dispositivo.

Para elegir el comportamiento de actualización automática de los dispositivos, haga lo siguiente:

1. Inicie sesión en Microsoft Teams de administración visitando https://admin.teams.microsoft.com .
2. Navegue **por**  >  **teléfonos IP de dispositivos,** **barras de colaboración** o Teams **paneles.**
3. Seleccione uno o varios dispositivos y, a continuación, **seleccione Actualizar**.
4. En **Actualización automática del firmware,** seleccione una de las siguientes opciones:
    - **Tan pronto como esté disponible** La segunda actualización de firmware del dispositivo más reciente se aplica el primer fin de semana después de que se publicó la última actualización.
    - **Aplazar 30 días** La segunda actualización de firmware del dispositivo más reciente se aplica 30 días después de que se publicó la última actualización.
    - **Aplazar 90 días** La segunda actualización de firmware del dispositivo más reciente se aplica 90 días después de que se publicó la última actualización.
5. Seleccione **Actualizar**.

Si, por cualquier motivo, necesita revertir una actualización del firmware del dispositivo, debe restablecer el dispositivo a su configuración de fábrica. Restablezca el dispositivo con las instrucciones de su fabricante.  

## <a name="manually-update-remote-devices"></a>Actualizar manualmente dispositivos remotos

Al actualizar uno o varios dispositivos con el Centro de administración, puede decidir si desea actualizar los dispositivos inmediatamente o programar una actualización para una fecha y hora futuras.

Para actualizar manualmente los dispositivos remotos, haga lo siguiente:

1. Inicie sesión en Microsoft Teams de administración visitando https://admin.teams.microsoft.com .
2. Navegue **por**  >  **teléfonos IP de dispositivos,** **barras de colaboración** o Teams **paneles.**
3. Seleccione uno o varios dispositivos y, a continuación, **seleccione Actualizar**.
4. En **Actualizaciones manuales,** seleccione **Programar** si desea programar la actualización para una fecha y hora futuras. Las actualizaciones se aplican en la fecha y hora en la zona horaria seleccionada en **zona horaria.**

Lo que verá dependerá de si tiene uno o varios dispositivos seleccionados. La imagen izquierda siguiente muestra varios dispositivos seleccionados mientras que la imagen de la derecha muestra un único dispositivo seleccionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Vistas de dispositivo único y múltiple en el panel de estado de actualización de dispositivos":::

Al seleccionar varios dispositivos, puede elegir qué tipos de actualización se aplicarán a cada dispositivo seleccionado. Seleccione los tipos de actualización que desea aplicar y seleccione **Actualizar.**

Al seleccionar un único dispositivo, se muestran las actualizaciones disponibles para el dispositivo. Si hay varios tipos de actualización disponibles para el dispositivo, seleccione cada tipo de actualización que desea aplicar. Puede ver la **versión actual** aplicada en el dispositivo y la **nueva versión** que se aplicará. Seleccione las actualizaciones que desea aplicar y seleccione **Actualizar.**

Después de seleccionar **Actualizar,** las actualizaciones se aplican a los dispositivos en la fecha y hora que seleccionó si programó una actualización. Si no seleccionó una fecha y hora futuras, las actualizaciones se aplicarán a sus dispositivos en unos minutos.
