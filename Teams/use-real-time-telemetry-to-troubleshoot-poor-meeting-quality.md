---
title: Usar telemetría en tiempo real para solucionar problemas de mala calidad de la reunión
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use telemetría en tiempo real con detalles sobre dispositivos, redes y conectividad para solucionar problemas de usuario con las reuniones programadas de Microsoft Teams.
ms.openlocfilehash: c7bc5ee0415a289782cad1dd7daa5c13bdaf7364
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494727"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usar telemetría en tiempo real para solucionar problemas de mala calidad de la reunión

En este artículo se explica cómo usar Real-Time Analytics (ATR) para solucionar problemas de mala calidad en las reuniones de Microsoft Teams para usuarios individuales. Puede acceder a Real-Time Analytics si tiene uno de los siguientes roles:

- Administrador de Teams
- Especialista en soporte técnico de comunicaciones de Teams
- Ingeniero de soporte en comunicaciones de Teams

Para obtener más información sobre los roles de administrador de Teams, consulte [Usar los roles de administrador de Microsoft Teams para administrar Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics permite a los administradores de TI ver las reuniones programadas de sus usuarios importantes y ver el audio, el vídeo, el uso compartido de contenido y los problemas relacionados con la red. Como administrador, puede usar esta telemetría para investigar estos problemas durante las reuniones y solucionarlos en tiempo real.

## <a name="what-is-real-time-analytics"></a>¿Qué es Real-Time Analytics?

En la actualidad, la solución de problemas de reuniones individuales está disponible para los administradores de Teams a través de [Análisis de llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) una vez finalizada la reunión. Real-Time Analytics permite a los administradores solucionar problemas de reuniones programadas mientras están en curso.

Real-Time Analytics muestra información detallada sobre las reuniones de Teams para cada usuario de su cuenta de Office 365, actualizada en tiempo real. Incluye información sobre los dispositivos, la red, la conectividad, el audio, el vídeo y los problemas de uso compartido de contenido, lo que ayudará a los administradores a solucionar los problemas de calidad de las llamadas de forma más eficaz.

Como administrador de Teams, obtiene acceso completo a todos los datos de telemetría en tiempo real para cada usuario. Además, puede asignar roles de Azure Active Directory para dar soporte al personal. Para obtener más información sobre estos roles, consulte [Conceder permiso al personal de soporte técnico y de asistencia](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Dónde encontrar telemetría de solución de problemas en tiempo real por usuario

Para ver toda la información y los datos de la reunión de un usuario, vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com). En **Usuarios** > **administrar usuarios**, seleccione un usuario y abra la pestaña **Reuniones & llamadas** en la página de perfil del usuario. En **Reuniones recientes**, verá una lista de las reuniones a las que ha asistido el usuario en las últimas 24 horas *para las que está disponible la telemetría en tiempo real*, incluidas las reuniones en curso. Si la reunión no está en curso o no tiene datos de telemetría en tiempo real, se mostrará en **Reuniones pasadas**.

:::image type="content" alt-text="Captura de pantalla de la tabla de reuniones recientes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Para obtener información adicional sobre los participantes de una reunión que está en curso, incluyendo su dispositivo, red y estadísticas de audio, busque la reunión en **Reuniones recientes** y seleccione el vínculo en la columna **Participantes** .

:::image type="content" alt-text="Captura de pantalla de la tabla de detalles del participante." source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

Para ver la telemetría de un usuario determinado para una reunión en curso, incluida la información sobre el dispositivo, la red, el audio, el vídeo y los detalles del uso compartido de contenido, seleccione el **Id. de reunión**.

:::image type="content" alt-text="Captura de pantalla de datos de sesión de usuario de análisis de llamadas." source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Detalles y medidas disponibles en Real-Time Analytics

### <a name="device-information"></a>Información del dispositivo
| Nombre | Descripción | Posibles razones para valores en blanco|
|:---|:---|:---|
| Dispositivo de captura de audio | Nombre del dispositivo de captura de audio (por ejemplo: micrófono) en uso | Es posible que el sistema no tenga un nombre asociado con el dispositivo (por ejemplo: Dispositivo de escritorio remoto o de máquina virtual 'Audio remoto')  |
| Dispositivo de representación de audio | Nombre del dispositivo de representación de audio (por ejemplo: altavoces o auriculares) en uso | Es posible que el sistema no tenga un nombre asociado con el dispositivo (por ejemplo: Dispositivo de escritorio remoto o de máquina virtual 'Audio remoto')  |
| Dispositivo de captura de vídeo | Nombre del dispositivo de captura de vídeo en uso | El usuario no está enviando vídeo desde el punto de conexión que se está supervisando |

### <a name="connectivity-information"></a>Información de conectividad
| Métrica | Unidades/Posibles valores | Descripción | Posibles razones para valores en blanco|
|:---|:---|:---|:---|
| Tipo de red | &bull; Ethernet <br/> &bull; Wi-Fi | Tipo de conexión de red en uso | |
| Wi-Fi fuerza | &bull; Excelente : -50 dBm o superior <br/> &bull; Good : -51 dBm a -64 dBm<br/> &bull; Mala : -65 dBm o inferior | Intensidad de la conexión Wi-Fi actual del usuario | El usuario no está conectado a Wi-Fi |
| canal Wi-Fi | Entero | Canal sobre el que se difunde el punto de acceso de la red de Wi-Fi | El usuario no está conectado a Wi-Fi |
| Tipo físico | String <br/> &bull; Ejemplo: 802.11ac | Tipo de infraestructura inalámbrica en uso | El usuario no está conectado a Wi-Fi |
| banda de Wi-Fi | 2,4 GHz o 5 GHz | Wi-Fi banda a la que está conectado el usuario | El usuario no está conectado a Wi-Fi |
| Ubicación | String | País en el que se encuentra el usuario | La información de ubicación del usuario está bloqueada o no está disponible |
| Dirección IP local | Cadena (IP:Puerto) | Dirección IP local del punto de conexión del usuario y el puerto multimedia | |
| Dirección IP reflexiva del servidor | Cadena (IP:Puerto) | Dirección IP pública del punto de conexión del usuario y el puerto multimedia | |
| Tipo de conectividad | UDP o TCP | Protocolo de capa de transporte en uso; UDP es el preferido para medios en tiempo real | |

### <a name="user-signals"></a>Señales de usuario
Las señales de usuario identifican cuándo un usuario participa activamente en la llamada, no está hablando, pero está activado o silenciado. Actualmente, las señales de usuario solo están disponibles para el audio.

| Modalidad | Valores posibles | Descripción |
|:---|:---|:---|
| Audio | &bull; Unmuted, participante hablando <br/> &bull; Sin audio, sin hablar <br/> &bull; Silenciado | Indica el comportamiento del usuario para la parte de audio de la llamada.  |


### <a name="audio"></a>Audio
|Nombre de la medida |Unidades |Umbral bueno |Descripción |
|:---|:---|:---|:---|
|Vibración |Milisegundos |Menos de 30 ms |La vibración es una medida de la variación en el retraso de paquetes para una transmisión de datos. Cuando esto es demasiado alto, el audio puede ser entrecortado. | 
|Pérdida de paquetes |Porcentaje |Menos del 5 % |La pérdida de paquetes se produce cuando los paquetes de datos no llegan a su destino. El porcentaje de paquetes perdidos se basa en el número total de paquetes enviados. |
|Tiempo de ida y vuelta |Milisegundos |Menos de 500 ms |El tiempo de ida y vuelta es el tiempo que tarda un único paquete en viajar desde el cliente al punto de conexión remoto y volver al cliente. Un tiempo de ida y vuelta elevado puede causar retrasos en la reproducción de la transmisión. Un ejemplo de esto es cuando dos personas en una reunión están hablando involuntariamente entre sí debido al retraso. Se muestra solo para el audio saliente. |
|Bitrate |Kilobits por segundo (Kbps) |Mayor de 24 Kbps |Rendimiento de la transmisión de audio expresada en kilobits por segundo. |
| Códec | String <br/> &bull; Ejemplo: SATINADO | Solo información | Muestra el códec de audio que se envía y recibe. Se puede recibir un códec diferente al que se envía. |


### <a name="video"></a>Vídeo
|Nombre de la medida |Unidades |Umbral bueno |Descripción |
|:---|:---|:---|:---|
|Tiempo de ida y vuelta |Milisegundos |Menos de 500 ms |El tiempo de ida y vuelta es el tiempo que tarda un único paquete en viajar desde el cliente al punto de conexión remoto y volver al cliente. Un tiempo de ida y vuelta elevado puede causar retrasos en la reproducción de la transmisión. Un ejemplo de esto es cuando dos personas en una reunión están hablando involuntariamente entre sí debido al retraso. |
|Bitrate |Megabits por segundo (Mbps) | Solo información |Rendimiento de la transmisión de vídeo expresada en megabits por segundo. |
|Velocidad de fotogramas (vídeo) |Fotogramas por segundo |360p o superior: 25-30 FPS <br/> 270p o inferior: 7-15 FPS |Para las transmisiones de vídeo salientes, la velocidad de fotogramas (FPS) es el número de fotogramas por segundo de vídeo que envía el cliente. Los valores inferiores a lo esperado pueden sugerir restricciones de recursos del sistema, ancho de banda de red insuficiente o dispositivos de captura de vídeo mal comportando. Las distintas resoluciones tienen intervalos de FPS diferentes aceptables. |
|Códec |String | Solo información |Muestra el códec de vídeo y el modo de representación de la secuencia de vídeo saliente. (Ejemplo: H264 SW HW indica una transmisión de vídeo H264 con representación de hardware y software).|
|Resolución |Píxeles | Solo información |La resolución del vídeo que se envía. La resolución de vídeo saliente es dinámica, en función del requisito más alto de un punto de conexión en la reunión. Un cliente capaz de vídeo de 1920 x 1080 solo enviará vídeo de 640 x 360 si no hay clientes que muestren el vídeo de ese usuario en un marco superior a 640 x 360 |


### <a name="application-sharing-vbss"></a>Uso compartido de aplicaciones (VBSS)
|Nombre de la medida |Unidades |Umbral bueno |Descripción |
|:---|:---|:---|:---|
|Pérdida de paquetes |Porcentaje |Menos del 5 % |La pérdida de paquetes se produce cuando los paquetes de datos no llegan a su destino. El porcentaje de paquetes perdidos se basa en el número total de paquetes enviados. |
|Tiempo de ida y vuelta |Milisegundos |Menos de 500 ms |El tiempo de ida y vuelta es el tiempo que tarda un único paquete en viajar desde el cliente al punto de conexión remoto y volver al cliente. Un tiempo de ida y vuelta elevado puede causar retrasos en la reproducción de la transmisión. Un ejemplo de esto es cuando dos personas en una reunión están hablando involuntariamente entre sí debido al retraso. |
|Bitrate |Megabits por segundo (Mbps) | Solo información |Rendimiento de la transmisión de VBSS expresada en megabits por segundo. |
|Velocidad de fotogramas |Fotogramas por segundo (FPS) | Solo información |Para VBSS, la velocidad de fotogramas es consciente del contenido para asegurarse de que se envían todos los fotogramas necesarios para garantizar una buena experiencia y evitar el envío de tramas si no son necesarias. Por ejemplo, compartir un documento de texto en pantalla solo requiere 1 fotograma por segundo para producir una buena experiencia, mientras que compartir un vídeo o contenido con más actividad aumentará los fotogramas por segundo a un máximo de 30 FPS para producir una experiencia más fluida. |
|Códec |String | Solo información |Muestra el códec y el modo de representación de la secuencia de VBSS. (Ejemplo: H264 SW HW indica una transmisión de H264 VBSS que usa tanto software como representación de hardware).|
|Resolución |Píxeles | Solo información |La resolución de la secuencia de VBSS que se envía y recibe. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Plataformas cliente compatibles con telemetría en tiempo real

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> El cliente web de Teams (incluido VDI) no admite la entrega de telemetría en tiempo real.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Dispositivos de Teams compatibles con telemetría en tiempo real

- MTR: Surface Hub
- MTR: Pantalla de Teams
- MTR: barra de colaboración
- Dispositivos IP Phone

> [!NOTE]
> Los dispositivos que se unieron a la reunión con soluciones de interoperabilidad de vídeo en la nube (CVI) no son compatibles con Real-Time Analytics.


## <a name="limitations"></a>Limitaciones

- La telemetría en tiempo real solo está disponible para las reuniones programadas y Reunirse ahora. En las llamadas RTC, individuales y grupales, la telemetría en tiempo real no está disponible.
- La telemetría en tiempo real solo está disponible para los moderadores de eventos en directo programados. Actualmente no está disponible para los asistentes al evento en directo.
- Los datos de telemetría en tiempo real están disponibles para una reunión en **Reuniones recientes** durante 24 horas después de que finalice la reunión. Después de 24 horas, no puede acceder a los datos y la reunión se mueve a **Reuniones pasadas**. Si una reunión dura más de 3 horas, la telemetría en tiempo real solo estará disponible durante las *últimas 3 horas*.
- La telemetría no está disponible en tiempo real al usar versiones anteriores de Teams. Si no hay telemetría disponible, intenta actualizar el cliente.
- Si participantes externos o usuarios anónimos se unen a una reunión, su nombre para mostrar se mostrará como **no disponible** para conservar la privacidad entre espacios empresariales.

## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas por usuario](set-up-call-analytics.md)

[Use los roles de administrador de Microsoft Teams para administrar Teams](/MicrosoftTeams/using-admin-roles).
