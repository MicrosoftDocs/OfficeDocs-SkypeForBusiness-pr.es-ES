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
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Obtenga información sobre cómo desarrollar y ejecutar operaciones y mantenimiento continuos para garantizar que los sistemas de Salas de Microsoft Teams están disponibles para los usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36145202e12cd9b987b50efd6de3efe636c86ac2
ms.sourcegitcommit: 1934c4803b5b6ae9b9ccd49e695944446d5d5810
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2023
ms.locfileid: "69806375"
---
# <a name="manage-microsoft-teams-rooms-and-surface-hubs"></a>Administrar Salas de Microsoft Teams y Surface Hub

Si tienes Salas de Microsoft Teams dispositivo o Un Surface Hub en tu organización, tienes opciones de administración flexibles.  Puede administrar los dispositivos usted mismo en la misma ubicación central donde administra todas las soluciones de Teams, el Centro de administración de Microsoft Teams.

Con el Centro de administración de Microsoft Teams, puede:

- Realizar la administración de dispositivos, como reiniciar dispositivos y descargar registros de dispositivos
- Aplicar la configuración específica de Teams
- Comprobar el estado de Salas de Microsoft Teams y sus periféricos, incluyendo cámaras, pantallas, micrófonos, etc.
- Revisar la actividad actual y pasada de la reunión (como los detalles sobre la calidad de la llamada, el estado y la conectividad de la red y el número de participantes)
- Ver periféricos (como cámaras y proyectores) conectados a Salas de Microsoft Teams (solo para Salas de Teams en Windows)

Para administrar Salas de Teams dispositivos, abra el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com) y vaya a **Dispositivos** >  de Teams **Salas de Teams en Windows** o **Surface Hub**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Salas de Teams página de resumen en el Centro de administración de Teams.":::


> [!IMPORTANT]
> Para administrar dispositivos mediante el Centro de administración de Teams, debe tener asignados los roles de administrador global, administrador de Teams o administrador de dispositivos de Teams.

## <a name="make-changes-to-teams-rooms-devices-or-surface-hubs"></a>Realizar cambios en dispositivos Salas de Teams o Surface Hub

Si tienes más de una Salas de Teams o un dispositivo Surface Hub, puedes realizar la mayoría de las acciones en varios dispositivos al mismo tiempo. Por ejemplo, puede establecer la configuración de la aplicación de Teams en todos los Salas de Teams al mismo tiempo.

### <a name="device-settings"></a>Configuración del dispositivo

Puedes cambiar la configuración en uno o más Salas de Teams o Surface Hub de tu organización. Para cambiar la configuración, selecciona el dispositivo o dispositivos que quieras administrar y, a continuación, selecciona **Editar configuración**. Se abrirá un nuevo panel con todas las opciones de configuración que puede cambiar. En la tabla siguiente se enumeran las opciones de configuración que puede cambiar con el Centro de administración de Teams. Algunas opciones de configuración solo están disponibles al seleccionar un solo Salas de Teams.

Si selecciona más de una, las opciones de configuración compatibles con la edición en masa mostrarán las dos opciones siguientes.

- **Mantener el valor existente** Si elige esta opción, no se realizará ningún cambio en la configuración de la Salas de Teams ha seleccionado.
- **Reemplazar el valor existente por** Si elige esta opción, puede actualizar la configuración en el Salas de Teams ha seleccionado con el valor que proporcione.
    > [!CAUTION]
    > Los valores existentes en la configuración que elija actualizar se reemplazarán por el valor que proporcione. Si desea agregar a una lista de valores existentes, debe incluir los valores existentes con el valor que desea sumar. Por ejemplo, si una configuración tiene una lista de dominios existente de `contoso.com, fabrikam.com`, y quieres agregar `northwindtraders.com`, el valor que debes proporcionar sería `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Si seleccionas varias Salas de Teams, la configuración de todos los dispositivos que selecciones cambiará al valor que proporciones. Si Salas de Teams tienen valores diferentes para una configuración, todos se actualizarán al mismo valor.

| Setting                                                      | Valores aceptados                                        | Admite la edición en masa | Tipos de dispositivos compatibles |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|------------------------|
| *Cuenta*                                                    |                                                        |                    | Salas de Teams en Windows |
| **Email**                                                    | Email dirección                                          | No                 | Salas de Teams en Windows |
| **Modo de reunión compatible**                                   | Solo Microsoft Teams<br>Skype Empresarial (predeterminado) y Microsoft Teams<br>Skype Empresarial y Microsoft Teams (predeterminado)<br>Solo Skype Empresarial|Sí| Salas de Teams en Windows |
| **Autenticación moderna**                                    | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows |
| **Dirección de Exchange**                                         | Email dirección                                          | No                 | Salas de Teams en Windows |
| **Dominio\nombre de usuario (opcional)**                               | Nombre de usuario y dominio de la cuenta                           | No                 | Salas de Teams en Windows |
| **Configurar dominio**                                         | Lista separada por comas                                   | Sí                | Salas de Teams en Windows |
| *Reuniones*                                                   |                                                        |                    | Salas de Teams en Windows, Surface Hubs |
| **Uso compartido automático de la pantalla**                                 | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows |
| **Uso compartido de audio para ingerir HDMI**                                 | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows |
| **Mostrar los nombres de las reuniones**                                       | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows |
| **Auto-leave if everyone else left meeting**                 | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows |
| **Unirse a reuniones de terceros**                 | Cisco Webex<br>Zoom                                              | Sí                | Salas de Teams en Windows, Surface Hubs |
| **Unirse con la información de la sala**                 | Seleccionado<br>No seleccionado                                              | Sí                | Salas de Teams en Windows, Surface Hubs |
| **Unirse con información personalizada**                 | Seleccionado<br>No seleccionado                                              | Sí                | Salas de Teams en Windows |
| **Nombre (obligatorio)**                 | Nombre de la sala o el espacio                                              | Sí                | Salas de Teams en Windows |
| **Email (obligatorio)**                 | Email dirección                                              | Sí                | Salas de Teams en Windows |
| *Dispositivo*                                                     |                                                        |                    | Salas de Teams en Windows |
| **Modo de monitor dual**                                        | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows |
| **Permitir la duplicación de contenido** | Seleccionado<br>No seleccionado                                 | Sí                | Salas de Teams en Windows |
| **Balizas Bluetooth**                                      | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows, Surface Hubs |
| **Aceptar automáticamente invitaciones a reuniones basadas en proximidad** | Seleccionado<br>No seleccionado                                 | Sí                | Salas de Teams en Windows, Surface Hubs |
| **Enviar registros con comentarios**                                  | Activado<br>Desactivado                                              | Sí                | Salas de Teams en Windows |
| **Email dirección para registros y comentarios**                      | Email dirección                                          | Sí                | Salas de Teams en Windows |
| *Coordinar reuniones*                                                     |                                                        |                    | Salas de Teams en Windows |
| **Reuniones coordinadas** | Activado<br>Desactivado                                 | No                | Salas de Teams en Windows, Surface Hubs |
| **Activar el micrófono de este dispositivo** | Activado<br>Desactivado                                 | No                | Salas de Teams en Windows, Surface Hubs |
| **Permitir que los usuarios lo habiliten al unirse a una reunión** | Seleccionado<br>No seleccionado                                 | No                | Salas de Teams en Windows, Surface Hubs |
| **Activar la cámara de este dispositivo** | Activado<br>Desactivado                                 | No                | Salas de Teams en Windows, Surface Hubs |
| **Permitir que los usuarios lo habiliten al unirse a una reunión** | Seleccionado<br>No seleccionado                                 | No                | Salas de Teams en Windows, Surface Hubs |
| **Activar la pizarra para este dispositivo** | Activado<br>Desactivado                                 | No                | Salas de Teams en Windows, Surface Hubs |
| **Cuentas de dispositivo de confianza (separadas con comas)** | Lista de dispositivos                              | No                | Salas de Teams en Windows, Surface Hubs |
| *Periféricos*                                                |                                                        |                    | Salas de Teams en Windows |
| **Micrófono de conferencia**                                  | Lista de micrófonos disponibles                          | No                 | Salas de Teams en Windows |
| **Orador de conferencias**                                     | Lista de altavoces disponibles                             | No                 | Salas de Teams en Windows |
| **Volumen predeterminado**                                           | 0-100                                                  | No                 | Salas de Teams en Windows |
| **Altavoz predeterminado**                                          | Lista de altavoces disponibles                             | No                 | Salas de Teams en Windows |
| **Volumen predeterminado**                                           | 0-100                                                  | No                 | Salas de Teams en Windows |
| **Cámara de contenido**                                           | Lista de cámaras disponibles                              | No                 | Salas de Teams en Windows |
| **Mejoras de la cámara de contenido**                              | Activado<br>Desactivado                                              | No                 | Salas de Teams en Windows |
| **Girar la cámara de contenido 180 grados**                        | Activado<br>Desactivado                                              | No                 | Salas de Teams en Windows |
| *Tematización*                                                    |                                                        |                    | Salas de Teams en Windows |
|                                                              | Valor predeterminado<br>Sin tema<br>Personalizado<br>Lista de temas integrados   | Sí                | Salas de Teams en Windows |

Consulta [Administrar la configuración de Microsoft Teams en Surface Hubs](surface-hub-manage-config.md) para obtener más opciones para configurar Surface Hubs.

### <a name="cortana-settings"></a>Configuración de Cortana

Puede habilitar Cortana para _la activación por voz_ o _Pulsar para hablar_ con PowerShell para todos los dispositivos de su organización, o para cada dispositivo por separado.

Consulte [Salas de Microsoft Teams en Windows](../cortana-in-teams.md) en el artículo "Asistencia de voz de Cortana en Teams".

### <a name="front-row-layout-settings"></a>Configuración de diseño de fila frontal

La fila frontal es la opción de diseño de vista de reunión para Salas de Teams en Windows.

| Dispositivo de Teams | Versión de la aplicación | Pantalla frontal de la sala |
|--------------|-------------|-----------------------|
|Salas de Microsoft Teams en Windows | 4.11.12.0 o posterior (se recomienda la versión más reciente) | Soporta pantallas únicas y duales; Tamaño mínimo: 46 pulgadas; Relación de aspecto 16:9 con resolución 1920x1080 o 21:9 con resolución 2560x1080; Todas las pantallas deben establecerse con un ajuste de escala del 100 % en la configuración de Windows |

Consulte [Salas de Microsoft Teams mantenimiento y operaciones](rooms-operations.md#scale-and-resolution), para ajustar la configuración de la pantalla y cumplir los requisitos de la fila frontal.

Para obtener información sobre cómo establecer la fila frontal como diseño predeterminado de un salón o cómo desactivarla, vea [Administrar una configuración de consola de Salas de Microsoft Teams de forma remota con un archivo de configuración XML](xml-config-file.md#set-front-row-as-the-default-layout).

Vea [Problemas conocidos](known-issues.md#Limits) para obtener más información sobre la administración de la fila frontal.

## <a name="device-restart-options"></a>Opciones de reinicio del dispositivo

Los cambios en la configuración del dispositivo solo se aplicarán después de reiniciar el dispositivo. Cuando realices cambios que necesiten un reinicio, puedes elegir si deseas reiniciar inmediatamente o programar un reinicio. Estas son las opciones de reinicio disponibles:

- **Reinicio inmediato** Si eliges esta opción, todos los dispositivos en los que realices cambios se reiniciarán en cuanto selecciones esta opción.
- **Reinicio programado** Si elige esta opción, puede reiniciar los dispositivos en los que está realizando cambios en un momento que sea menos perjudicial para su organización.
  - **Selecciona fecha y hora** : elige la fecha y hora específicas para reiniciar el dispositivo. La fecha y hora que elijas será local en el dispositivo que se reiniciará. 
  - **Dejar la actualización para reiniciar por la noche** Los dispositivos se reinician por la noche para realizar mantenimiento. Los cambios que realices en los dispositivos se aplicarán durante este reinicio.

> [!CAUTION]
> Salas de Teams y Surface Hub que se usan en el momento del reinicio no estarán disponibles durante el proceso de reinicio. Se desconectarán de las reuniones en curso y no estarán disponibles para unirse a nuevas reuniones mientras se reinicia el dispositivo.

## <a name="remove-device"></a>Quitar dispositivo

Al quitar un dispositivo, este se quita de la organización y ya no aparece en la lista de Salas de Teams en Windows o Surface Hub en el Centro de administración de Teams.

Si quitas un dispositivo y sigue configurado con un nombre de usuario y contraseña válidos, se volverá a agregar automáticamente a la lista de Salas de Teams o Surface Hub si se conecta de nuevo a Microsoft 365.

Para quitar uno o más dispositivos, haz lo siguiente:

1. Ve a **Dispositivos** >  teams **Salas de Teams en Windows** o **Surface Hub y** selecciona los dispositivos que quieras quitar.
2. Seleccione **Quitar**.

## <a name="download-device-logs"></a>Descargar registros de dispositivos

Puedes descargar una copia de los archivos de registro de diagnóstico de un dispositivo si el soporte técnico de Microsoft lo solicita. Los archivos de registro se comprimen en un archivo zip que se puede descargar desde el Centro de administración de Teams.

Para descargar registros desde un dispositivo Salas de Teams al equipo, haga lo siguiente:

1. Vaya a **Dispositivos** >  de Teams **Salas de Teams en Windows** o **Surface Hubs** y seleccione el nombre del dispositivo desde el que desea descargar los registros.
1. Selecciona **Descargar registros de dispositivos**. Los registros del dispositivo pueden tardar varios minutos en estar disponibles.
1. Selecciona la pestaña **Historial** y, a continuación, selecciona el vínculo archivo de registro en **Archivo de diagnósticos**. Se descargará un archivo zip que contenga los archivos de registro de diagnóstico del dispositivo en la carpeta de descargas predeterminada del explorador.

## <a name="view-device-information"></a>Ver información del dispositivo

Desde el Centro de administración de Teams, puede ver el estado general de todos los dispositivos de su organización y ver los detalles de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Salas de Teams panel del sistema

El Salas de Teams panel del sistema muestra el estado y el estado de todos los dispositivos de un vistazo.

### <a name="device-details-view"></a>Vista de detalles del dispositivo

Para ver información detallada sobre un dispositivo, selecciona su nombre en la lista de dispositivos. Cuando esté en la vista de detalles, puede ver la siguiente información sobre el dispositivo:

- **Estado** Muestra el estado general del dispositivo Salas de Teams o Surface Hub. El estado de salud puede ser **Correcto**, **No urgente**, **Crítico** o **Sin conexión**.
- **Sin conexión desde** Muestra la última vez que Microsoft 365 pudo comunicarse con el dispositivo.
- **Estado de uso** Muestra el estado actual del dispositivo: **Inactivo**, **Ocupado** o **No disponible**. Solo para Salas de Teams en Windows.
- **Periféricos** Muestra los periféricos conectados al dispositivo Salas de Teams y su estado de salud. El estado de mantenimiento puede ser **Conectado** o **Desconectado**. Solo para Salas de Teams en Windows.
- **Salud** Muestra información detallada sobre los periféricos conectados a tu dispositivo Salas de Teams, la conectividad de red, el estado de inicio de sesión en los servicios necesarios e información de la versión de software.
- **Detalles** Muestra la información del fabricante, la dirección IP de red y la dirección SALAS DE TEAMS dispositivo serie/MAC.
- **Actividad** Muestra los detalles de la reunión pasada, incluida la fecha y la hora de la reunión, el número de participantes, la duración y la calidad del audio. Para obtener más información sobre los detalles de la reunión, consulte la sección [Detalles](#meeting-activity-details) de la actividad de la reunión más adelante en este artículo.
- **Historia** Muestra un historial de actividad de administración en el Salas de Teams o dispositivo Surface Hub, incluidas las actualizaciones de configuración, reinicios de dispositivos y vínculos de descarga de registros de dispositivos.

#### <a name="meeting-activity-details"></a>Detalles de la actividad de la reunión

La pestaña **Actividad** de los detalles del dispositivo muestra información detallada y de alto nivel sobre todas las reuniones en las que ha participado el dispositivo a lo largo del tiempo. En la pestaña **Actividad** , puede ver cuándo se celebró una reunión, cuántos participantes asistieron a la reunión y la calidad del audio durante la reunión.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Salas de Teams lista de resumen de actividad del dispositivo.":::

Para ver la información detallada sobre una reunión específica, seleccione la fecha y la hora de la reunión sobre la que desea obtener más información. Si una reunión solo tiene dos participantes, verá la página de detalles del participante; de lo contrario, verá una página de resumen del participante.

##### <a name="participant-summary"></a>Resumen del participante

La página de resumen del participante muestra todos los participantes que asistieron a la reunión. Puede ver cuándo se unió cada participante a la reunión, su nombre, su calidad de audio y qué características se usaron durante la sesión. Para ver los detalles de la sesión de un participante, seleccione la hora de inicio de la sesión para ese participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Salas de Teams detalles de conferencia del dispositivo.":::

##### <a name="participant-details"></a>Detalles del participante

La página de detalles del participante muestra información de diagnóstico de un extremo a otro para la sesión de ese participante. Como se muestra en el siguiente gráfico, se proporciona información de **dispositivo**, **sistema** y **conectividad** para el participante y para el dispositivo Salas de Teams. También se proporciona información de diagnóstico de **red** entre el participante y el dispositivo Salas de Teams. Seleccione el icono del contexto sobre el que desea obtener más información. Para obtener información de diagnóstico adicional, selecciona la pestaña **Avanzadas** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Salas de Teams detalles de la llamada del dispositivo.":::
