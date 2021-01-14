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
description: Obtenga información sobre cómo desarrollar y ejecutar operaciones y mantenimiento continuos para garantizar que los sistemas de Salas de Microsoft Teams estén disponibles para los usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 830caffbbb0256e64198e84876a4067337e90266
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848842"
---
# <a name="manage-microsoft-teams-rooms"></a>Administrar Salas de Microsoft Teams

Si tiene dispositivos certificados para salas de Microsoft Teams en su organización, tiene opciones de administración flexibles.  Puede administrar los dispositivos usted mismo en la misma ubicación central donde administra todas las soluciones de Teams, el Centro de administración de Microsoft Teams o puede transferir la responsabilidad de administración a expertos dedicados con servicios administrados de Salas de [Microsoft Teams.](https://portal.rooms.microsoft.com)  También puede delegar el acceso de administración a un partner de su elección para cualquiera de las opciones.

Con el Centro de administración de Microsoft Teams, puede:

- Realizar la administración de dispositivos, como reiniciar o bloquear dispositivos, y descargar registros de dispositivos
- Aplicar la configuración específica de Teams
- Comprobar el estado de mantenimiento de los dispositivos de Sala de Microsoft Teams y sus periféricos, incluidas cámaras, pantallas, micrófonos, entre otros
- Revisar la actividad actual y pasada de una reunión (como detalles sobre la calidad de la llamada, el estado y la conectividad de la red y el número de participantes)
- Ver periféricos (como cámaras y proyectores) conectados a un dispositivo de Microsoft Teams Room

Para administrar dispositivos de Salas de Teams, abra el Centro [de administración](https://admin.teams.microsoft.com) de Microsoft Teams y vaya a Salas de Teams para   >  **dispositivos.**

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Páginas de resumen de salas de Teams en el Centro de administración de Teams":::

> [!IMPORTANT]
> Para administrar dispositivos mediante el Centro de administración de Teams, debe tener asignados los roles de Administrador global, Administrador de servicios de Teams o Administrador de dispositivos de Teams.

## <a name="make-changes-to-teams-rooms-devices"></a>Realizar cambios en los dispositivos de Salas de Teams

Si tiene más de un dispositivo de Salas de Teams, puede realizar la mayoría de las acciones en varios dispositivos al mismo tiempo. Por ejemplo, puede establecer la configuración de la aplicación Teams en todos los dispositivos al mismo tiempo.

### <a name="device-settings"></a>Configuración del dispositivo

Puede cambiar la configuración en uno o más dispositivos de su organización. Para cambiar la configuración, seleccione el dispositivo o dispositivos que desea administrar y, a continuación, **seleccione Editar configuración.** Se abrirá un nuevo panel con todas las opciones de configuración que puede cambiar en sus dispositivos. En la tabla siguiente se enumeran los ajustes que puede cambiar con el Centro de administración de Teams. Algunas configuraciones solo están disponibles cuando se selecciona un único dispositivo.

Si selecciona más de un dispositivo, las opciones que admiten la edición en masa muestran las dos opciones siguientes.

- **Mantener el valor existente** Si elige esta opción, no se realizará ningún cambio en la configuración de los dispositivos que ha seleccionado.
- **Reemplazar valor existente con** Si elige esta opción, puede actualizar la configuración en los dispositivos que ha seleccionado con el valor que proporciona.
    > [!CAUTION]
    > Los valores existentes en la configuración que elija actualizar se reemplazarán por el valor que proporcione. Si desea agregar a una lista de valores existentes, debe incluir los valores existentes con el valor que desea agregar. Por ejemplo, si una configuración tiene una lista de dominios existente y desea agregarla, el valor `contoso.com, fabrikam.com` `northwindtraders.com` que debe proporcionar `contoso.com, fabrikam.com, northwindtraders.com` sería.
    >
    > Si selecciona varios dispositivos, la configuración en todos los dispositivos que seleccione cambiará al valor que proporcione. Si los dispositivos tienen valores diferentes para una configuración, todos se actualizarán al mismo valor.

| Setting                                                      | Valores aceptados                                        | Es compatible con la edición en masa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Cuenta*                                                    |                                                        |                    |
| **Email**                                                    | Dirección de correo electrónico                                          | No                 |
| **Modo de reunión admitido**                                   | Skype Empresarial (predeterminado) y Microsoft Teams<br>Skype Empresarial y Microsoft Teams (predeterminado)<br>Solo Skype Empresarial|Sí|
| **Autenticación moderna**                                    | Activado<br>Desactivado                                              | Sí                |
| **Dirección de Exchange**                                         | Dirección de correo electrónico                                          | No                 |
| **Dominio #A0 (opcional)**                               | Nombre de usuario y dominio de la cuenta                           | No                 |
| **Configurar dominio**                                         | Lista separada por comas                                   | Sí                |
| *Reuniones*                                                   |                                                        |                    |
| **Pantalla compartida automática**                                 | Activado<br>Desactivado                                              | Sí                |
| **Mostrar nombres de reunión**                                       | Activado<br>Desactivado                                              | Sí                |
| **Auto-leave if everyone else left meeting**                 | Activado<br>Desactivado                                              | Sí                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modo de monitor dual**                                        | Activado<br>Desactivado                                              | Sí                |
| **Bluetooth balizas**                                      | Activado<br>Desactivado                                              | Sí                |
| **Aceptar automáticamente invitaciones a reuniones basadas en proximidad** | Seleccionado<br>No seleccionado                                 | Sí                |
| **Enviar registros con comentarios**                                  | Activado<br>Desactivado                                              | Sí                |
| **Dirección de correo electrónico para registros y comentarios**                      | Dirección de correo electrónico                                          | Sí                |
| *Periféricos*                                                |                                                        |                    |
| **Micrófono de conferencia**                                  | Lista de micrófonos disponibles                          | No                 |
| **Orador de conferencias**                                     | Lista de altavoces disponibles                             | No                 |
| **Volumen predeterminado**                                           | 0-100                                                  | No                 |
| **Altavoz predeterminado**                                          | Lista de altavoces disponibles                             | No                 |
| **Volumen predeterminado**                                           | 0-100                                                  | No                 |
| **Cámara de contenido**                                           | Lista de cámaras disponibles                              | No                 |
| **Mejoras de la cámara de contenido**                              | Activado<br>Desactivado                                              | No                 |
| **Girar la cámara de contenido 180 grados**                        | Activado<br>Desactivado                                              | No                 |
| *Theming*                                                    |                                                        |                    |
|                                                              | Valor predeterminado<br>Sin tema<br>Personalizado<br>Lista de temas integrados   | Sí                |

### <a name="device-restart-options"></a>Opciones de reinicio del dispositivo

Los cambios en la configuración del dispositivo solo tendrán efecto después de reiniciar los dispositivos. Cuando realice cambios que necesiten reiniciarse, puede elegir si desea reiniciar los dispositivos inmediatamente o programar uno. Estas son las opciones de reinicio disponibles:

- **Reinicio inmediato** Si eliges esta opción, todos los dispositivos en los que estás haciendo cambios se reiniciarán en cuanto selecciones esta opción.
- **Reinicio programado** Si elige esta opción, puede reiniciar los dispositivos en los que está realizando cambios a la vez que sea menos molesto para su organización.
  - **Seleccione la fecha y la hora:** elija la fecha y la hora específicas para reiniciar el dispositivo. La fecha y hora que elijas será local en el dispositivo que se reiniciará. 
  - **Salir de la actualización para el reinicio nocturno** Los dispositivos se reinician todos los noches para realizar tareas de mantenimiento. Los cambios que realices en los dispositivos se aplicarán durante este reinicio.

> [!CAUTION]
> Los dispositivos en uso en el momento de reiniciar no estarán disponibles durante el proceso de reinicio. Se desconectarán de las reuniones en curso y no estarán disponibles para unirse a nuevas reuniones.

### <a name="remove-or-block-a-device"></a>Quitar o bloquear un dispositivo

Al quitar **un dispositivo,** este se quita de la organización y ya no aparece en la lista de dispositivos de salas de Teams en el Centro de administración de Teams. 

Al bloquear **un** dispositivo, Teams ya no se comunica con el dispositivo. Los dispositivos bloqueados no se enviarán comandos aunque estén incluidos en un grupo de dispositivos que se están editando en masa. Todavía aparece en la lista de dispositivos de Salas de Teams con el estado **Bloqueado.**

Independientemente de si un dispositivo está bloqueado o quitado, si aún está configurado con un nombre de usuario y una contraseña válidos, se volverá a agregar automáticamente a la lista de dispositivos de Salas de Teams si se conecta a Microsoft 365.

Para quitar uno o más dispositivos, haga lo siguiente:

1. Vaya a **Salas**  >  **de Teams para** dispositivos y seleccione los dispositivos que desea quitar.
1. Seleccione **Quitar**.

Para bloquear un dispositivo, haga lo siguiente:

1. Vaya a **Salas**  >  **de Teams para** dispositivos y seleccione el nombre del dispositivo que quiere bloquear.
1. En la página de detalles del dispositivo, seleccione **Acciones** en la esquina superior derecha de la página.
1. Seleccione **Bloquear.**

Para desbloquear un dispositivo, haga lo siguiente:

1. Vaya a **Salas**  >  **de Teams para** dispositivos y seleccione el nombre del dispositivo que quiere bloquear.
1. En la página de detalles del dispositivo, seleccione **Acciones** en la esquina superior derecha de la página.
1. Seleccione **Desbloquear.**

## <a name="download-device-logs"></a>Descargar registros de dispositivos

Puede descargar una copia de los archivos de registro de diagnóstico de un dispositivo si así lo solicita el soporte técnico de Microsoft. Los archivos de registro se comprimen en un archivo zip que se puede descargar desde el Centro de administración de Teams.

Para descargar registros desde un dispositivo de Salas de Teams a su equipo, haga lo siguiente:

1. Vaya a **Salas** de Teams para dispositivos y seleccione el nombre del dispositivo del  >   que quiere descargar registros.
1. Seleccione **Descargar registros de dispositivos.** Los registros del dispositivo pueden tardar varios minutos en estar disponibles.
1. Seleccione la pestaña **Historial** y, a continuación, seleccione el vínculo del archivo de registro en **archivo de diagnóstico.** Se descargará un archivo zip que contiene los archivos de registro de diagnóstico del dispositivo en la carpeta de descargas predeterminada del explorador.

## <a name="view-device-information"></a>Ver información del dispositivo

Desde el Centro de administración de Teams, puede ver el estado general de todos los dispositivos de su organización y ver los detalles de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Panel del sistema salas de Teams

El panel del sistema Salas de Teams le muestra de un vistazo el estado y el estado de todos sus dispositivos.

### <a name="device-details-view"></a>Vista de detalles del dispositivo

Para ver información detallada sobre un dispositivo, seleccione su nombre de la lista de dispositivos. Cuando esté en la vista de detalles, puede ver la siguiente información sobre el dispositivo:

- **Estado de estado** Muestra el estado general del dispositivo de Teams Room. El estado de mantenimiento puede **ser Correcto** o **Incorrecto.**
- **Sin conexión desde** Muestra la última vez que Microsoft 365 pudo comunicarse con el dispositivo.
- **Estado del dispositivo** Muestra el estado actual del dispositivo: **Inactivo,** **Reunión de Teams,** **Reunión de Skype** o **Ingerir.**
- **Periféricos** Muestra los periféricos conectados al dispositivo de la sala de Teams y su estado. El estado de mantenimiento puede **ser Conectado** **o Desconectado.**
- **Estado** Muestra información detallada sobre los periféricos conectados al dispositivo de la sala de Teams, la conectividad de red, el estado de inicio de sesión de los servicios necesarios e información sobre la versión del software.
- **Detalles** Muestra la información del fabricante, la dirección IP de la red y la dirección de serie o MAC del dispositivo teams room.
- **Actividad** Muestra los detalles de reuniones pasadas, incluida la fecha y la hora de la reunión, el número de participantes, la duración y la calidad del audio. Para obtener más información sobre los detalles de la reunión, vea la sección Detalles de la [actividad de la](#meeting-activity-details) reunión más adelante en este artículo.
- **Historial** Muestra un historial de la actividad de administración en el dispositivo de la sala de Teams, incluidas las actualizaciones de configuración, los reinicios de dispositivos y los vínculos de descarga de registros de dispositivos.

#### <a name="meeting-activity-details"></a>Detalles de la actividad de la reunión

La **pestaña** Actividad de los detalles del dispositivo de la sala de Teams muestra información de alto nivel e detallada sobre todas las reuniones en las que ha participado el dispositivo a lo largo del tiempo. En la **pestaña** Actividad, puede ver cuándo se realizó una reunión, cuántos participantes participaron en la reunión y la calidad del audio durante la reunión.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Lista de resumen de actividad de dispositivos de sala de Teams":::

Para ver la información detallada sobre una reunión específica, seleccione la fecha y la hora de la reunión sobre la que quiere obtener más información. Si una reunión solo tiene dos participantes, verá la página de detalles del participante; de lo contrario, verá una página de resumen de participantes.

##### <a name="participant-summary"></a>Resumen del participante

La página de resumen del participante muestra todos los participantes que han participado en la reunión. Puede ver cuándo se unió cada participante a la reunión, su nombre, calidad de audio y qué características se usaron durante su sesión. Para ver los detalles de la sesión de un participante, seleccione la hora de inicio de la sesión para ese participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Detalles de conferencias del dispositivo de la sala de Teams":::

##### <a name="participant-details"></a>Detalles del participante

La página de detalles del participante muestra información de diagnóstico de un extremo a otro de la sesión del participante. Como se muestra en el siguiente  **gráfico,** se proporciona información de **dispositivo,** sistema y conectividad para el participante y para el dispositivo de Salas de Teams. **También se** proporciona información de diagnóstico de red entre el participante y el dispositivo salas de Teams. Seleccione el icono del contexto sobre el que quiere obtener más información. Para obtener más información de diagnóstico, seleccione la **pestaña** Avanzadas.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Detalles de llamada del dispositivo de la sala de Teams":::
