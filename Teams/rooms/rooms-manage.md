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
description: Obtenga información sobre cómo desarrollar y ejecutar operaciones y mantenimiento continuos para asegurarse de que sus Salas de Microsoft Teams están disponibles para los usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4f326f58bea724dbf1d728955ee1d63b018ba628
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306295"
---
# <a name="manage-microsoft-teams-rooms"></a>Administrar Salas de Microsoft Teams

Si tiene dispositivos Salas de Microsoft Teams certificados en su organización, tiene opciones de administración flexibles.  Puede administrar los dispositivos usted mismo en la misma ubicación central donde administra todas Teams soluciones, Microsoft Teams Centro de administración. Como alternativa, puede transferir la responsabilidad de administración a expertos dedicados con [Salas de Microsoft Teams Servicios administrados.](https://portal.rooms.microsoft.com)  También puede delegar el acceso de administración a un partner de su elección para cualquiera de las opciones.

Con Microsoft Teams de administración, puede:

- Realizar la administración de dispositivos como reiniciar dispositivos y descargar registros de dispositivos
- Aplicar Teams configuración específica
- Comprobar el estado de Microsoft Teams dispositivos de sala y sus periféricos, incluidas las cámaras, las pantallas, los micrófonos, entre otros
- Revisar la actividad de reunión actual y pasada (por ejemplo, detalles sobre la calidad de las llamadas, el estado de la red y la conectividad, y el número de participantes)
- Ver periféricos (como cámaras y proyectores) conectados a un dispositivo Microsoft Teams room

Para administrar Salas de Teams dispositivos, abra el Microsoft Teams de [administración](https://admin.teams.microsoft.com) y vaya a Teams **dispositivos** Salas de Teams  >  **en Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Salas de Teams de resumen en Teams de administración.":::


> [!IMPORTANT]
> Para administrar dispositivos con el Teams de administración, debe tener asignado el administrador global, Teams administrador o Teams administrador de dispositivos.

## <a name="make-changes-to-teams-rooms-devices"></a>Realizar cambios en Salas de Teams dispositivos

Si tiene más de un Salas de Teams, puede realizar la mayoría de las acciones en varios dispositivos al mismo tiempo. Por ejemplo, puede establecer la Teams de la aplicación en todos los dispositivos al mismo tiempo.

### <a name="device-settings"></a>Configuración del dispositivo

Puede cambiar la configuración en uno o varios dispositivos de su organización. Para cambiar la configuración, seleccione el dispositivo o dispositivos que desea administrar y, a continuación, **seleccione Editar Configuración**. Se abrirá un nuevo panel con todas las opciones de configuración que puede cambiar en sus dispositivos. En la tabla siguiente se enumeran las opciones de configuración que puede cambiar con el Teams de administración. Algunas opciones de configuración solo están disponibles al seleccionar un único dispositivo.

Si selecciona más de un dispositivo, las opciones que admiten la edición en masa muestran las dos opciones siguientes.

- **Mantener el valor existente** Si elige esta opción, no se realizarán cambios en la configuración de los dispositivos seleccionados.
- **Reemplazar el valor existente con** Si elige esta opción, puede actualizar la configuración en los dispositivos seleccionados con el valor que proporcione.
    > [!CAUTION]
    > Los valores existentes en la configuración que elija actualizar se reemplazarán por el valor que proporcione. Si desea agregar a una lista de valores existentes, debe incluir los valores existentes con el valor que desea agregar. Por ejemplo, si una configuración tiene una lista de dominios existente de y desea `contoso.com, fabrikam.com` agregarla, el valor que debe `northwindtraders.com` proporcionar sería `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Si selecciona varios dispositivos, la configuración de todos los dispositivos que seleccione cambiará al valor que proporcione. Si los dispositivos tienen valores diferentes para una configuración, todos se actualizarán al mismo valor.

| Setting                                                      | Valores aceptados                                        | Admite la edición en masa |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Cuenta*                                                    |                                                        |                    |
| **Email**                                                    | Dirección de correo electrónico                                          | No                 |
| **Modo de reunión compatible**                                   | Skype Empresarial (predeterminado) y Microsoft Teams<br>Skype Empresarial y Microsoft Teams (predeterminado)<br>Skype Empresarial solo para Skype Empresarial|Sí|
| **Autenticación moderna**                                    | Activado<br>Desactivado                                              | Sí                |
| **Exchange dirección**                                         | Dirección de correo electrónico                                          | No                 |
| **Dominio\nombre de usuario (opcional)**                               | Nombre de usuario y dominio de la cuenta                           | No                 |
| **Configurar dominio**                                         | Lista separada por comas                                   | Sí                |
| *Reuniones*                                                   |                                                        |                    |
| **Uso compartido automático de pantalla**                                 | Activado<br>Desactivado                                              | Sí                |
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

## <a name="cortana-settings"></a>Cortana configuración 
Puede habilitar Cortana activación  por voz o _Push_ para hablar con PowerShell para todos los dispositivos de su organización o para cada dispositivo por separado. 
-   En el nivel de organización y grupo, debe usar PowerShell.
-   En el nivel de dispositivo, tiene algunas opciones. Puede usar PowerShell, editar el archivo de configuración XML o cambiar la configuración en Teams de administración. 

Para obtener más información sobre el uso de PowerShell para configurar Cortana, vea Control de administración y limitaciones para Cortana [en Teams](/microsoftteams/cortana-in-teams#admin-control-and-limitations).

Para obtener más información sobre cómo configurar el dispositivo con el archivo de configuración XML, vea Administrar una configuración de Salas de Microsoft Teams consola de forma remota [con un archivo de configuración XML.](/microsoftteams/rooms/xml-config-file#manage-console-settings-with-an-xml-configuration-file)

En el nivel de dispositivo, puede configurar Cortana que se active para:
- _Pulsar para hablar_ con PowerShell  
  - Cómo activarlo: Cortana Push _to talk_ está habilitado de forma predeterminada para todos los dispositivos configurados con configuración regional independientemente de la región geográfica
  - Cómo desactivarlo: use Powershell. 
- _Activación por voz_ con archivo de configuración XML o Teams de administración.
  - Cómo activarlo: establecerlo en el archivo de configuración XML o usar la configuración correspondiente en Teams `<CortanaWakeWord>true</>` centro de administración
  - Cómo desactivarla: Cortana activación de voz está desactivada de forma predeterminada 
  
  Tenga en cuenta que deben cumplirse tres condiciones para tener Cortana _activación de voz_ en el dispositivo:
    1. Su organización debe tener Cortana habilitado
    2. El dispositivo debe configurarse con una de las siguientes configuraciones regionales: en-au, en-ca, en-gb, en-in, en-us
    3. Debe tener un dispositivo Cortana certificado conectado a su sala Teams más [información](/microsoftteams/cortana-in-teams)   

### <a name="device-restart-options"></a>Opciones de reinicio del dispositivo

Los cambios en la configuración del dispositivo solo tendrán efecto después de reiniciar los dispositivos. Cuando realice cambios que necesiten reiniciarse, puede elegir si desea reiniciar los dispositivos inmediatamente o programar un reinicio. Estas son las opciones de reinicio disponibles:

- **Reinicio inmediato** Si elige esta opción, todos los dispositivos a los que está realizando cambios se reiniciarán tan pronto como seleccione esta opción.
- **Reinicio programado** Si elige esta opción, puede reiniciar los dispositivos a los que está realizando cambios en un momento que sea menos perjudicial para su organización.
  - **Seleccionar fecha y hora:** elija la fecha y hora específicas para reiniciar el dispositivo. La fecha y hora que elija es local para el dispositivo que se está reiniciando. 
  - **Dejar la actualización para reiniciar por la noche** Los dispositivos se reinician por la noche para realizar tareas de mantenimiento. Los cambios que realice en los dispositivos se aplicarán durante este reinicio.

> [!CAUTION]
> Los dispositivos en uso en el momento de reiniciar no estarán disponibles durante el proceso de reinicio. Se desconectarán de las reuniones en curso y no estarán disponibles para unirse a nuevas reuniones.

### <a name="remove-device"></a>Quitar dispositivo

Al quitar un dispositivo, el dispositivo se quita de la organización y ya no aparece en la lista de Salas de Teams dispositivos en el centro de administración Teams usuario.

Si quita un dispositivo y sigue configurado con un nombre de usuario y una contraseña válidos, se volverá a agregar automáticamente a la lista de dispositivos de Salas de Teams si se conecta a Microsoft 365 nuevo.

Para quitar uno o varios dispositivos, haga lo siguiente:

1. Ve a **Teams**  >  **dispositivos Salas de Teams** y selecciona los dispositivos que quieras quitar.
1. Seleccione **Quitar**.

## <a name="download-device-logs"></a>Descargar registros de dispositivos

Puede descargar una copia de los archivos de registro de diagnóstico de un dispositivo si el soporte técnico de Microsoft lo solicita. Los archivos de registro se comprimen en un archivo zip que se puede descargar desde el Teams de administración.

Para descargar registros desde un Salas de Teams en el equipo, haga lo siguiente:

1. Vaya a **Teams dispositivos** Salas de Teams y seleccione el nombre del dispositivo desde el  >   que desea descargar registros.
1. Seleccione **Descargar registros de dispositivos**. Los registros de dispositivos pueden tardar varios minutos en estar disponible.
1. Seleccione la **pestaña** Historial y, a continuación, seleccione el vínculo archivo de registro en **Archivo de diagnóstico.** Un archivo zip que contiene los archivos de registro de diagnóstico del dispositivo se descargará en la carpeta descargas predeterminada del explorador.

## <a name="view-device-information"></a>Ver información del dispositivo

Desde el Teams de administración, puede ver el estado general de todos los dispositivos de su organización y ver los detalles de cada dispositivo individualmente.

### <a name="teams-rooms-system-dashboard"></a>Salas de Teams panel del sistema

El Salas de Teams del sistema le muestra el estado y el estado de todos los dispositivos de un vistazo.

### <a name="device-details-view"></a>Vista detalles del dispositivo

Para ver información detallada sobre un dispositivo, seleccione su nombre en la lista de dispositivos. Cuando esté en la vista de detalles, puede ver la siguiente información sobre el dispositivo:

- **Estado de estado** Muestra el estado general del dispositivo Teams room. El estado de estado puede ser **Correcto** o **Incorrecto.**
- **Sin conexión desde** Muestra la última vez Microsoft 365 se pudo comunicar con el dispositivo.
- **Estado del dispositivo** Muestra el estado actual del dispositivo: **Inactivo**, **Teams ,** **Skype reunión** o **Ingerir**.
- **Periféricos** Muestra los periféricos conectados a su dispositivo Teams room y su estado de estado. El estado de estado puede estar **conectado** o **desconectado.**
- **Estado** Muestra información detallada sobre los periféricos conectados a su dispositivo Teams Room, conectividad de red, estado de inicio de sesión a los servicios necesarios e información de versión de software.
- **Detalles** Muestra la información del fabricante, la dirección IP de red y Teams de serie o MAC del dispositivo de la sala.
- **Actividad** Muestra detalles de la reunión pasadas, como la fecha y la hora de la reunión, el número de participantes, la duración y la calidad del audio. Para obtener más información sobre los detalles de la reunión, vea la [sección Detalles de la actividad de](#meeting-activity-details) la reunión más adelante en este artículo.
- **Historial** Muestra un historial de actividades de administración en el dispositivo Teams room, incluidas las actualizaciones de configuración, los reinicios del dispositivo y los vínculos de descarga del registro de dispositivos.

#### <a name="meeting-activity-details"></a>Detalles de la actividad de la reunión

La **pestaña** Actividad de Teams detalles del dispositivo de sala muestra información detallada y de alto nivel sobre todas las reuniones en las que ha participado el dispositivo a lo largo del tiempo. En la **pestaña** Actividad, puede ver cuándo se celebró una reunión, cuántos participantes asistieron a la reunión y la calidad del audio durante la reunión.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams de resumen de actividad de dispositivos de sala.":::

Para ver la información detallada sobre una reunión específica, seleccione la fecha y hora de la reunión sobre la que desea obtener más información. Si una reunión solo tiene dos participantes, verá la página de detalles del participante, de lo contrario verá una página de resumen del participante.

##### <a name="participant-summary"></a>Resumen del participante

La página de resumen del participante muestra todos los participantes que asistieron a la reunión. Puede ver cuándo se unió cada participante a la reunión, su nombre, calidad de audio y qué características se usaron durante la sesión. Para ver los detalles de la sesión de un participante, seleccione la hora de inicio de la sesión para ese participante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams detalles de la conferencia del dispositivo de la sala.":::

##### <a name="participant-details"></a>Detalles del participante

La página de detalles del participante muestra información de diagnóstico de un extremo a otro para la sesión de ese participante. Como se muestra en el siguiente  **gráfico,** se proporciona información de **dispositivo,** sistema y conectividad para el participante y para el Salas de Teams dispositivo. **También** se proporciona información de diagnóstico de red entre el participante y Salas de Teams dispositivo. Seleccione el icono del contexto sobre el que desea obtener más información. Para obtener información de diagnóstico adicional, seleccione la **pestaña** Avanzadas.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams detalles de la llamada del dispositivo de la sala.":::
