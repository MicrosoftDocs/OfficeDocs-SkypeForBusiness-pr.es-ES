---
title: Administrar Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Obtenga más información sobre cómo desarrollar y ejecutar tareas y mantenimientos continuos para asegurarse de que los sistemas de salas de Microsoft Teams estén disponibles para sus usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2339967d6d7705266c13dbc65fb689c49c8e8279
ms.sourcegitcommit: a5276a713697e089d0eb0d80bba83a7af8d48251
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "45202926"
---
# <a name="manage-microsoft-teams-rooms"></a>Administrar Salas de Microsoft Teams

Si tiene dispositivos certificados de salas de Microsoft Teams en su organización, puede administrarlos desde una ubicación central con el centro de administración de Microsoft Teams. Puede:

- Administración de dispositivos, como reinicio o bloqueo de dispositivos, y descarga de registros de dispositivos
- Aplicar la configuración específica de Teams
- Comprobar el estado de los dispositivos de la sala de Microsoft Teams y sus periféricos, incluidas las cámaras, las pantallas, los micrófonos, etc.
- Revisar la actividad de las reuniones actuales y pasadas (como detalles sobre la calidad de las llamadas, el estado de la red y la conectividad, así como el número de participantes)
- Ver periféricos (como cámaras y proyectores) conectados a un dispositivo de la sala de Microsoft Teams

Para administrar los dispositivos de salas de equipos, abra el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com) y vaya a **dispositivos**  >  **salas de equipos**.

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Páginas de Resumen de salas de equipos en el centro de administración de Teams":::

> [!IMPORTANT]
> Para administrar dispositivos con el centro de administración de Teams, debe tener asignados a los roles de administrador global o administrador de servicios de Teams.

## <a name="make-changes-to-teams-rooms-devices"></a>Realizar cambios en los dispositivos de salas de equipos

Si tiene más de un dispositivo de salas de equipos, puede realizar la mayoría de las acciones en varios dispositivos al mismo tiempo. Por ejemplo, puede establecer la configuración de la aplicación Teams en todos los dispositivos al mismo tiempo.

### <a name="device-settings"></a>Configuración del dispositivo

Puede cambiar la configuración en uno o más dispositivos de su organización. Para cambiar la configuración, seleccione el dispositivo o los dispositivos que quiera administrar y, después, seleccione **Editar configuración**. Se abrirá un panel nuevo con todas las opciones de configuración que puede cambiar en sus dispositivos. En la siguiente tabla se enumeran las opciones de configuración que puede cambiar con el centro de administración de Teams. Algunas opciones de configuración solo están disponibles cuando selecciona un único dispositivo.

Si selecciona más de un dispositivo, las configuraciones que admiten la edición en masa muestran las dos opciones siguientes.

- **Conservar valor existente** Si elige esta opción, no se realizarán cambios en la configuración de los dispositivos que ha seleccionado.
- **Reemplazar valor existente por** Si elige esta opción, puede actualizar la configuración en los dispositivos seleccionados con el valor que proporciona.
    > [!CAUTION]
    > Los valores existentes en la configuración que elija para actualizar se reemplazarán por el valor que proporcione. Si desea agregar a una lista de valores existentes, debe incluir los valores existentes con el valor que desea agregar. Por ejemplo, si una configuración tiene una lista de dominios existente de `contoso.com, fabrikam.com` y quiere agregar `northwindtraders.com` , el valor que debe proporcionar sería `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Si selecciona varios dispositivos, la configuración de todos los dispositivos que seleccione se cambiará al valor que proporciona. Si los dispositivos tienen valores diferentes para una configuración, se actualizarán en el mismo valor.

| Setting                                                      | Valores aceptados                                        | Compatible con la edición en masa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Cuenta*                                                    |                                                        |                    |
| **Email**                                                    | Dirección de correo electrónico                                          | No                 |
| **Modo de reunión admitido**                                   | Skype empresarial (predeterminado) y Microsoft Teams<br>Skype empresarial y Microsoft Teams (predeterminado)<br>Solo para Skype empresarial|Sí|
| **Autenticación moderna**                                    | Activado<br>Desactivado                                              | Sí                |
| **Dirección de Exchange**                                         | Dirección de correo electrónico                                          | No                 |
| **Dominio\nombredeusuario (opcional)**                               | Dominio de la cuenta y nombre de usuario                           | No                 |
| **Configurar dominio**                                         | Lista separada por comas                                   | Sí                |
| *Reuniones*                                                   |                                                        |                    |
| **Pantalla compartida automática**                                 | Activado<br>Desactivado                                              | Sí                |
| **Mostrar nombres de reunión**                                       | Activado<br>Desactivado                                              | Sí                |
| **Salir automáticamente si todos los demás han salido de la reunión**                 | Activado<br>Desactivado                                              | Sí                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modo de monitor doble**                                        | Activado<br>Desactivado                                              | Sí                |
| **Señalización Bluetooth**                                      | Activado<br>Desactivado                                              | Sí                |
| **Aceptar automáticamente las invitaciones a reuniones basadas en proximidad** | Seleccionado<br>Desactivada                                 | Sí                |
| **Enviar registros con comentarios**                                  | Activado<br>Desactivado                                              | Sí                |
| **Dirección de correo electrónico para registros y comentarios**                      | Dirección de correo electrónico                                          | Sí                |
| *Periféricos*                                                |                                                        |                    |
| **Micrófono de conferencia**                                  | Lista de micrófonos disponibles                          | No                 |
| **Altavoz de conferencia**                                     | Lista de altavoces disponibles                             | No                 |
| **Volumen predeterminado**                                           | 0-100                                                  | No                 |
| **Altavoz predeterminado**                                          | Lista de altavoces disponibles                             | No                 |
| **Volumen predeterminado**                                           | 0-100                                                  | No                 |
| **Cámara de contenido**                                           | Lista de cámaras disponibles                              | No                 |
| **Mejoras en las cámaras de contenido**                              | Activado<br>Desactivado                                              | No                 |
| **Rotar la cámara de contenido 180 grados**                        | Activado<br>Desactivado                                              | No                 |
| *Temas*                                                    |                                                        |                    |
|                                                              | Valor predeterminado<br>Sin tema<br>Custom<br>Lista de temas integrados   | Sí                |

### <a name="device-restart-options"></a>Opciones de reinicio de dispositivo

Los cambios en la configuración del dispositivo solo surtirán efecto después de que se hayan reiniciado los dispositivos. Cuando realice cambios que necesiten reiniciar, puede elegir si desea reiniciar los dispositivos inmediatamente o programar un reinicio. Estas son las opciones de reinicio disponibles:

- **Reinicio inmediato** Si elige esta opción, todos los dispositivos en los que está haciendo cambios se reiniciarán en cuanto Seleccione esta opción.
- **Reinicio programado** Si elige esta opción, puede reiniciar los dispositivos en los que está realizando cambios en un momento menos molesto para la organización.
  - **Seleccionar fecha y hora** : seleccione la fecha y la hora específicas para reiniciar el dispositivo. La fecha y la hora que elijas son locales para el dispositivo que se reiniciará. 
  - **Salir de la actualización para el reinicio nocturno** Los dispositivos se reinician por la noche para realizar el mantenimiento. Durante este reinicio, se aplicarán los cambios que realice en los dispositivos.

> [!CAUTION]
> Los dispositivos que se estén usando en el momento de reiniciar no estarán disponibles durante el proceso de reinicio. Se desconectarán de las reuniones en curso y no estarán disponibles para unirse a reuniones nuevas.

### <a name="remove-or-block-a-device"></a>Quitar o bloquear un dispositivo

Al **quitar** un dispositivo, el dispositivo se quita de la organización y ya no aparece en la lista de dispositivos de salas de equipos en el centro de administración de Teams. 

Cuando **bloquea** un dispositivo, Teams ya no se comunica con él. Los dispositivos bloqueados no se enviarán a los comandos incluso si están incluidos en un grupo de dispositivos que se están editando de forma masiva. Seguirá apareciendo en la lista de dispositivos de salas de equipos con el estado **bloqueado**.

Independientemente de si un dispositivo está bloqueado o quitado, si aún está configurado con un nombre de usuario y contraseña válidos, se volverá a agregar automáticamente a la lista de dispositivos de los salones de equipo si se conecta a Microsoft 365.

Para quitar uno o varios dispositivos, haga lo siguiente:

1. Vaya a **dispositivos**  >  **salas de equipos** y seleccione los dispositivos que quiere quitar.
1. Seleccione **Quitar**.

Para bloquear un dispositivo, haga lo siguiente:

1. Vaya a **dispositivos**  >  **salas de equipos** y seleccione el nombre del dispositivo que desea bloquear.
1. En la página Detalles del dispositivo, seleccione **acciones** en la esquina superior derecha de la página.
1. Seleccione **bloquear**.

Para desbloquear un dispositivo, haga lo siguiente:

1. Vaya a **dispositivos**  >  **salas de equipos** y seleccione el nombre del dispositivo que desea bloquear.
1. En la página Detalles del dispositivo, seleccione **acciones** en la esquina superior derecha de la página.
1. Seleccione **desbloquear**.

## <a name="download-device-logs"></a>Descargar registros del dispositivo

Puede descargar una copia de los archivos de registro de diagnóstico de un dispositivo si así se lo solicita el soporte técnico de Microsoft. Los archivos de registro se comprimen en un archivo zip que puede descargarse desde el centro de administración de Teams.

Para descargar los registros de un dispositivo de salas de equipos en el equipo, haga lo siguiente:

1. Vaya a **dispositivos**  >  **salas de equipos** y seleccione el nombre del dispositivo del que desea descargar registros.
1. Seleccione **Descargar registros del dispositivo**. Los registros del dispositivo pueden tardar varios minutos en estar disponibles.
1. Seleccione la ficha **historial** y, a continuación, seleccione el vínculo de archivo de registro en **archivo de diagnóstico**. Un archivo zip que contenga los archivos de registro de diagnóstico de su dispositivo se descargará en la carpeta descargas predeterminada del explorador.

## <a name="view-device-information"></a>Ver información del dispositivo

Desde el centro de administración de equipos, verá el estado general de todos los dispositivos de su organización y verá los detalles de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Panel de sistema de salas de equipos

El panel de sistema de salas de equipos muestra el estado y el estado de todos los dispositivos de un vistazo.

### <a name="device-details-view"></a>Vista detalles del dispositivo

Para ver información detallada sobre un dispositivo, seleccione su nombre en la lista de dispositivos. En la vista detalles, puede ver la siguiente información sobre el dispositivo:

- **Estado de mantenimiento** Muestra el estado general del dispositivo de la sala de equipos. El estado de mantenimiento puede **Healthy** ser correcto **o incorrecto.**
- **Sin conexión desde** Muestra la última vez que Microsoft 365 pudo comunicarse con el dispositivo.
- **Estado del dispositivo** Muestra el estado actual del dispositivo: **inactivo**, **reunión de Teams**, **reunión de Skype**o **ingesta**.
- **Periféricos** Muestra los periféricos conectados a su dispositivo de sala de equipos y su estado de mantenimiento. El estado de mantenimiento puede estar **conectado** o **desconectado**.
- **Estado** Muestra información detallada sobre los periféricos conectados a su dispositivo de sala de equipos, la conectividad de red, el estado de inicio de sesión a los servicios necesarios y la información de versión del software.
- **Detalles** Muestra información del fabricante, la dirección IP de red y la dirección de serie o MAC del dispositivo Room de Teams.
- **Actividad** Muestra detalles de la reunión pasada, como la fecha y la hora de la reunión, el número de participantes, la duración y la calidad del audio. Para obtener más información sobre los detalles de la reunión, consulte la sección detalles de la actividad de la [reunión](#meeting-activity-details) , más adelante en este artículo.
- **Historial** Muestra un historial de la actividad de administración en el dispositivo de la sala de equipos, incluidas las actualizaciones de configuración, los reinicios del dispositivo y los vínculos de descarga del registro del dispositivo.

#### <a name="meeting-activity-details"></a>Detalles de actividad de la reunión

En la pestaña **actividad** de detalles del dispositivo de sala de equipos se muestra información de alto nivel y detallada sobre todas las reuniones que el dispositivo ha participado en a lo largo del tiempo. En la pestaña **actividad** , puede ver cuándo se mantuvo una reunión, cuántos participantes asistieron a la reunión y la calidad de audio durante la reunión.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Lista de Resumen de actividad del dispositivo sala de equipos":::

Para ver la información detallada sobre una reunión específica, seleccione la fecha y la hora de la reunión de la que desea obtener más información. Si una reunión solo tiene dos participantes, verá la página Detalles del participante, de lo contrario, verá la página de Resumen de un participante.

##### <a name="participant-summary"></a>Resumen de participantes

La página Resumen de participantes muestra todos los participantes que han asistido a la reunión. Puede ver cuándo se unió cada participante a la reunión, su nombre, la calidad de audio y las características que se usaron durante la sesión. Para ver los detalles de la sesión de un participante, seleccione la hora de inicio de la sesión de ese participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Detalles de la Conferencia del dispositivo sala de equipos":::

##### <a name="participant-details"></a>Detalles del participante

En la página Detalles del participante se muestra información de diagnóstico de un extremo a otro para la sesión de ese participante. Como se muestra en el siguiente gráfico, se proporciona información sobre el **dispositivo**, el **sistema**y la **Conectividad** para el participante y para el dispositivo salas de equipos. También se proporciona información de diagnóstico de **red** entre el participante y el dispositivo de salas de equipos. Seleccione el icono del contexto sobre el que desea obtener más información. Para obtener información de diagnóstico adicional, seleccione la pestaña **avanzadas** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Detalles de la llamada de dispositivo de sala de equipos":::
