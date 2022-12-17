---
title: Actualizar Microsoft dispositivos de Teams de forma remota
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
description: Actualice Microsoft teléfonos, paneles de Teams y Salas de Teams en dispositivos Android de forma remota mediante el Centro de administración de Teams.
ms.openlocfilehash: c69a4deb43df5d40bf158a3c5bc467d431b041d5
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438268"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Actualizar Microsoft dispositivos de Teams de forma remota

Con el centro de administración de Microsoft Teams, puede actualizar sus dispositivos de Teams, como teléfonos, paneles de Teams y Salas de Teams en Android, de forma remota. Los siguientes componentes de software en el dispositivo se pueden actualizar desde el Centro de administración de Teams:

- Aplicación Teams
- Firmware del dispositivo

Las actualizaciones de firmware del dispositivo se realizan automáticamente de manera predeterminada. Sin embargo, puedes actualizar manualmente el firmware y otros componentes de software. Al aplicar actualizaciones manualmente, se pueden aplicar inmediatamente o programar para una fecha y hora futuras.

Solo las versiones de firmware que ha probado Microsoft están disponibles para la actualización automática o manual a través del Centro de administración de Teams. Las versiones de firmware probadas por Microsoft están etiquetadas **como Verificadas por Microsoft**. Las versiones de firmware que no han probado Microsoft tienen la etiqueta **Versión desconocida**. Los dispositivos que ejecutan una versión de firmware desconocida no se pueden actualizar automáticamente; estos dispositivos solo se pueden actualizar manualmente.

Para administrar dispositivos, debe ser administrador global, administrador de servicios de Teams o administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, vea [Usar Microsoft roles de administrador de Teams para administrar Teams](../using-admin-roles.md).

## <a name="assign-devices-to-an-automatic-update-phase"></a>Asignar dispositivos a una fase de actualización automática

Asignar dispositivos a una fase de actualización automática es una función Salas de Teams Pro para Salas de Teams en dispositivos Android. Los dispositivos con una licencia Salas de Teams Basic se asignarán a la fase General. Se mantendrá cualquier fase preconfigurada y no se permitirá ningún cambio adicional. Para obtener más información, vea [Salas de Microsoft Teams licencias](../rooms/rooms-licensing.md).  

Las actualizaciones automáticas de dispositivos de Teams que usan el Centro de administración de Teams no están disponibles en GCC High. Sin embargo, las organizaciones de GCC High pueden [actualizar manualmente los dispositivos de Teams](#manually-update-remote-devices) mediante el Centro de administración de Teams.

> [!IMPORTANT]
> La característica de actualización automática se encuentra actualmente en la versión anticipada. Novedades se pueden implementar más lentamente que la fase seleccionada. Durante los próximos meses, la velocidad a la que se implementan automáticamente las actualizaciones aumentará hasta llegar a la fase seleccionada.

> [!NOTE]
> Algunos dispositivos aún no admiten actualizaciones automáticas de firmware. Aplicar la configuración de actualización automática de firmware en dispositivos que no admiten actualizaciones automáticas no tendrá ningún efecto en esos dispositivos. Para preguntas sobre si el dispositivo admitirá actualizaciones automáticas de firmware, ponte en contacto con el fabricante del dispositivo.
>
> Novedades se aplican los fines de semana y fuera del horario laboral típico para evitar interrupciones. Los dispositivos dentro de una fase se actualizarán gradualmente durante unas pocas semanas, en lugar de hacerlo todos a la vez.

Para elegir la fase de actualización automática para tus dispositivos, haz lo siguiente:

1. Inicie sesión en Microsoft centro de administración de Teams visitando https://admin.teams.microsoft.com.
2. Vaya a **dispositivos de Teams** y, después, seleccione **Teléfonos**, **Pantallas**, **Paneles** o **Salas de Teams en Android**.  
3. Selecciona uno o más dispositivos y, a continuación **, actualizar.**
4. En **Actualización automática de firmware**, selecciona una de las siguientes opciones:
    - **Prueba** Esta opción es la mejor para dispositivos de laboratorio o de prueba en los que puede realizar cualquier validación que necesite realizar. Novedades iniciar la implementación tan pronto como se publique la versión de firmware más reciente. Anteriormente se llamaba **Lo antes posible**.
    - **General** Esta es la opción predeterminada y es la mejor para la mayoría de los dispositivos de uso general. Novedades iniciar la implementación solo transcurridos 30 días desde el lanzamiento de la nueva versión de firmware. Anteriormente se llamaba **Aplazar 30 días**.
    - **Final** Esta opción es la mejor para dispositivos que usan las VIP y en configuraciones grandes después de completar la validación a gran escala. Novedades iniciar la implementación solo transcurridos 90 días desde el lanzamiento de la nueva versión de firmware. Anteriormente se llamaba **Aplazar 90 días**.
5. Selecciona **Actualizar**.

Para ver en qué fase se encuentran los dispositivos, consulte la columna **Actualización automática de firmware** en el Centro de administración de Teams. Para ver qué dispositivos forman parte de una fase específica, usa la opción **Filtro** con el parámetro **Fase de actualización automática** .

Para revertir una actualización de firmware del dispositivo, debes restablecer el dispositivo a su configuración de fábrica. Restablece el dispositivo siguiendo las instrucciones del fabricante.  

## <a name="manually-update-remote-devices"></a>Actualizar manualmente los dispositivos remotos

Si desea actualizar manualmente los dispositivos mediante el Centro de administración de Teams, puede decidir si desea actualizar los dispositivos inmediatamente o programar una actualización para una fecha y hora futuras.

Para actualizar manualmente los dispositivos remotos, haz lo siguiente:

1. Inicie sesión en Microsoft centro de administración de Teams visitando https://admin.teams.microsoft.com.
2. Vaya a **Dispositivos de Teams** y, después, seleccione **Teléfonos**, **Pantallas**, **Paneles** o **Salas de Teams en Android**.
3. Selecciona uno o más dispositivos y, a continuación **, actualizar.**
4. En **Actualizaciones manuales**, selecciona **Programar** si quieres programar la actualización para una fecha y hora futuras. Las actualizaciones se aplican en la fecha y hora en la zona horaria seleccionada en **la zona horaria**.

Lo que verás dependerá de si tienes uno o varios dispositivos seleccionados. La siguiente imagen izquierda muestra varios dispositivos seleccionados, mientras que la imagen de la derecha muestra un único dispositivo seleccionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Vistas de un solo dispositivo y de varios dispositivos en el panel de estado de actualización de dispositivos.":::

Al seleccionar varios dispositivos, puedes elegir qué tipos de actualización se aplicarán a cada dispositivo seleccionado. Selecciona los tipos de actualización que quieras aplicar y selecciona **Actualizar**.

Al seleccionar un único dispositivo, se muestran las actualizaciones disponibles para el dispositivo. Si hay varios tipos de actualizaciones disponibles para el dispositivo, selecciona cada tipo de actualización que quieras aplicar. Puede ver la **versión actual** aplicada en el dispositivo y la **nueva versión** que se aplicará. Selecciona las actualizaciones que quieras aplicar y selecciona **Actualizar**.

Después de seleccionar **Actualizar**, las actualizaciones se aplican a los dispositivos en la fecha y hora que seleccionaste si programaste una actualización. Si no seleccionaste una fecha y hora futuras, las actualizaciones se aplican a los dispositivos en unos minutos.
