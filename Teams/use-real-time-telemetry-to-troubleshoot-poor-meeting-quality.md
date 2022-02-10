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
description: Use telemetría en tiempo real con detalles sobre dispositivos, redes y conectividad para solucionar problemas de usuario con Microsoft Teams reuniones programadas.
ms.openlocfilehash: 09c31b7734a849740cf1b0ff5749e4d82c667faf
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518732"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usar telemetría en tiempo real para solucionar problemas de mala calidad de la reunión

En este artículo se explica cómo usar Real-Time Analytics (RTA) para solucionar problemas de Microsoft Teams calidad de reunión para usuarios individuales. Puede acceder a Real-Time Analytics si tiene uno de los siguientes roles:

- Administrador de Teams
- Teams de soporte técnico de comunicaciones
- Ingeniero de soporte en comunicaciones de Teams

Para obtener más información sobre Teams de administrador, vea Usar Microsoft Teams [de administrador para administrar Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics permite a los administradores de TI ver las reuniones programadas de sus usuarios importantes y ver audio, vídeo, uso compartido de contenido y problemas relacionados con la red. Como administrador, puede usar esta telemetría para investigar estos problemas durante las reuniones y solucionar problemas en tiempo real.

## <a name="what-is-real-time-analytics"></a>¿Qué Real-Time Analytics?

Hoy en día, la solución de problemas de reunión individual está disponible para Teams administradores a través de [Call Analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) una vez que finalice la reunión. Real-Time Analytics permite a los administradores solucionar problemas de reuniones programadas mientras están en curso.

Real-Time Analytics muestra información detallada sobre Teams reuniones de cada usuario de su cuenta de Office 365, actualizada en tiempo real. Incluye información sobre dispositivos, red, conectividad, audio, vídeo y problemas de uso compartido de contenido, lo que ayudará a los administradores a solucionar problemas de calidad de llamadas de forma más eficaz.

Como administrador Teams, obtiene acceso completo a todos los datos de telemetría en tiempo real para cada usuario. Además, puede asignar roles Azure Active Directory al personal de soporte técnico. Para obtener más información sobre estos roles, vea [Conceder permiso al personal de soporte técnico y de soporte técnico](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Dónde buscar telemetría de solución de problemas en tiempo real por usuario

Para ver toda la información de la reunión y los datos de un usuario, vaya al [centro de Teams de administración](https://admin.teams.microsoft.com). En **UsuariosAge** >  **usuarios**, seleccione un usuario y abra la pestaña Reuniones **& llamadas** en la página de perfil del usuario. En **Reuniones recientes**, verá una lista de reuniones a las que ha asistido el usuario en las últimas 24 horas para las que la telemetría en tiempo *real* está disponible, incluidas las reuniones en curso. Si la reunión no está en curso o no tiene datos de telemetría en tiempo real, se mostrará en **Reuniones anteriores**.

:::image type="content" alt-text="Captura de pantalla de la tabla reuniones recientes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Para obtener información adicional sobre los participantes de una reunión que está en curso, incluidas sus estadísticas de dispositivo, red y audio, busque la reunión en  Reuniones recientes y seleccione el vínculo debajo de la columna **Participantes**.

:::image type="content" alt-text="Captura de pantalla de la tabla de detalles del participante." source="media/participant-details.png" lightbox="media/participant-details.png":::

Para ver la telemetría de un usuario determinado para una reunión en curso, incluida la información sobre los detalles del dispositivo, la red, el audio, el vídeo y el uso compartido de contenido, seleccione el Id. de **reunión**.

:::image type="content" alt-text="Captura de pantalla de los datos de sesión de usuario de análisis de llamadas." source="media/real-time-telemetry.png" lightbox="media/real-time-telemetry.png":::

## <a name="measures-available-in-real-time-analytics"></a>Medidas disponibles en Real-Time Analytics

### <a name="audio"></a>Audio
|Nombre de la medida |Unidades |Umbral bueno |Descripción |
|:---|:---|:---|:---|
|Vibración |Milisegundos |Menos de 30 ms |Vibración es una medida de la variación en el retraso de paquetes para una transmisión de datos. Cuando esto es demasiado alto, el audio puede ser entrecortado. | 
|Pérdida de paquetes |Porcentaje |Menos del 5 % |La pérdida de paquetes se produce cuando los paquetes de datos no llegan a su destino. El porcentaje de paquetes perdidos se basa en el número total de paquetes enviados. |
|Hora de ida y vuelta |Milisegundos |Menos de 500 ms |El tiempo de ida y vuelta es el tiempo que tarda un único paquete en desplazarse desde el cliente hasta el punto de conexión remoto y volver al cliente. El tiempo alto de ida y vuelta puede causar retrasos en la reproducción en streaming. Un ejemplo de esto es cuando dos personas de una reunión hablan involuntarlamente entre sí debido al retraso. |
|Velocidad de bits |Kilobits por segundo (Kbps) |Mayor que 24 Kbps |Rendimiento de la transmisión de audio expresada en kilobits por segundo. |


### <a name="video"></a>Vídeo
|Nombre de la medida |Unidades |Umbral bueno |Descripción |
|:---|:---|:---|:---|
|Hora de ida y vuelta |Milisegundos |Menos de 500 ms |El tiempo de ida y vuelta es el tiempo que tarda un único paquete en desplazarse desde el cliente hasta el punto de conexión remoto y volver al cliente. El tiempo alto de ida y vuelta puede causar retrasos en la reproducción en streaming. Un ejemplo de esto es cuando dos personas de una reunión hablan involuntarlamente entre sí debido al retraso. |
|Velocidad de bits |Megabits por segundo (Mbps) | Solo información |Rendimiento de la transmisión de vídeo expresada en megabits por segundo. |
|Velocidad de fotogramas (vídeo) |Fotogramas por segundo |360p o mejor: 25-30 FPS <br/> 270p o inferior: 7-15 FPS |Para las transmisiones de vídeo salientes, la velocidad de fotogramas (FPS) es el número de fotogramas por segundo de vídeo que envía el cliente. Los valores inferiores a los esperados aquí pueden sugerir restricciones de recursos del sistema, ancho de banda de red insuficiente o mal comportamiento de los dispositivos de captura de vídeo. Las diferentes resoluciones tienen diferentes rangos de FPS aceptables. |
|Códec |String | Solo información |Muestra el códec de vídeo y el modo de representación de la transmisión de vídeo saliente. (Ejemplo: H264 SW HW indica una transmisión de vídeo H264 con representación de software y hardware).|
|Resolución |Píxeles | Solo información |La resolución del vídeo que se envía. La resolución de vídeo saliente es dinámica, en función del requisito más alto de un punto de conexión de la reunión. Un cliente capaz de vídeo de 1920 x 1080 solo enviará vídeo de 640 x 360 si ningún cliente muestra el vídeo de ese usuario en un marco superior a 640 x 360 |


### <a name="application-sharing-vbss"></a>Uso compartido de aplicaciones (VBSS)
|Nombre de la medida |Unidades |Umbral bueno |Descripción |
|:---|:---|:---|:---|
|Pérdida de paquetes |Porcentaje |Menos del 5 % |La pérdida de paquetes se produce cuando los paquetes de datos no llegan a su destino. El porcentaje de paquetes perdidos se basa en el número total de paquetes enviados. |
|Hora de ida y vuelta |Milisegundos |Menos de 500 ms |El tiempo de ida y vuelta es el tiempo que tarda un único paquete en desplazarse desde el cliente hasta el punto de conexión remoto y volver al cliente. El tiempo alto de ida y vuelta puede causar retrasos en la reproducción en streaming. Un ejemplo de esto es cuando dos personas de una reunión hablan involuntarlamente entre sí debido al retraso. |
|Velocidad de bits |Megabits por segundo (Mbps) | Solo información |Rendimiento de la transmisión VBSS expresada en megabits por segundo. |
|Velocidad de fotogramas |Fotogramas por segundo (FPS) | Solo información |Para VBSS, la velocidad de fotogramas es consciente del contenido para asegurarse de que se envían tantas tramas como sea necesario para garantizar una buena experiencia y evitar el envío de tramas si no son necesarias. Por ejemplo, compartir un documento de texto en pantalla solo requiere 1 fotograma por segundo para producir una buena experiencia, mientras que compartir un vídeo o contenido con más actividad aumentará fotogramas por segundo a un máximo de 30 FPS para producir una experiencia más fluida. |
|Códec |String | Solo información |Muestra el códec y el modo de representación de la transmisión VBSS. (Ejemplo: H264 SW HW indica una transmisión H264 VBSS con representación de software y hardware).|
|Resolución |Píxeles | Solo información |La resolución de la transmisión VBSS que se envía y recibe. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Plataformas cliente compatibles con telemetría en tiempo real

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams cliente web (incluido VDI) no admite la entrega de telemetría en tiempo real.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams dispositivos compatibles con telemetría en tiempo real

- MTR: Surface Hub
- MTR: Teams pantalla
- MTR: barra de colaboración
- Dispositivos Teléfono IP

> [!NOTE]
> Los dispositivos que se unieron a la reunión con soluciones de interoperabilidad de vídeo en la nube (CVI) no son compatibles con Real-Time Analytics.


## <a name="limitations"></a>Limitaciones

- La telemetría en tiempo real solo está disponible para las reuniones programadas. Para reuniones ad hoc como Reunirse ahora, RTC, llamadas 1:1 y llamadas grupales, la telemetría en tiempo real no está disponible.
- La telemetría en tiempo real solo está disponible para los presentadores de eventos en directo programados. Actualmente no está disponible para los asistentes al evento en directo.
- Los datos de telemetría en tiempo real están disponibles para una reunión en Reuniones **recientes** durante 24 horas después de que haya finalizado la reunión. Después de 24 horas, no podrá acceder a los datos y la reunión se moverá a **Reuniones anteriores**. Si una reunión dura más de 3 horas, la telemetría en tiempo real solo estará disponible durante las *últimas 3 horas*.
- La telemetría no está disponible en tiempo real al usar versiones anteriores de Teams. Si no hay telemetría disponible, intente actualizar el cliente.
- Si participantes externos o usuarios anónimos se unen a una reunión, su nombre para mostrar se mostrará como no **disponible para conservar** la privacidad entre inquilinos.

## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas por usuario](set-up-call-analytics.md)

[Use Microsoft Teams de administrador para administrar Teams](/MicrosoftTeams/using-admin-roles).
