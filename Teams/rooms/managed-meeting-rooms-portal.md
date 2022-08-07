---
title: Portal de Salas de Microsoft Teams
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Proporciona una vista del estado de las salas de reuniones.
f1keywords: ''
ms.openlocfilehash: d76f1f68e0cc73d2abd554ec5c2fc115139a6a0f
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269215"
---
# <a name="microsoft-managed-meeting-rooms-portal"></a>Portal de salas de reuniones administrado por Microsoft

## <a name="overview"></a>Información general

El Portal administrado de salas de reuniones ("Portal de salas") proporciona una vista del estado de las salas de reuniones. Una vista del cliente de este portal es para su visibilidad y comentarios, y para facilitar sus prácticas y herramientas de supervisión existentes.

El ámbito de la supervisión es

- Vista de incidentes
  - Principales problemas que afectan a las salas
  - Acciones necesarias para restaurar las salas al estado correcto
  - Problemas que Microsoft está investigando
- Vista de dispositivos de salas de Microsoft Teams
  - Instantánea del estado en el nivel del dispositivo Salas de Microsoft Teams (MTR)
  - Historial básico y detalles para cada dispositivo

**Vista de dispositivos de salas de Microsoft Teams**

- Instantánea del estado en el nivel del dispositivo Salas de Microsoft Teams (MTR)
- Historial básico y detalles para cada dispositivo

> [!Important]
> Revise [**Asignar usuarios al rol Administrador de servicios administrados**](enrolling-mtrp-managed-service.md#assign-users-to-the-managed-service-administrator-role) y asegúrese de que el acceso al portal está limitado en función de sus necesidades empresariales.

## <a name="terminology"></a>Terminología

Estos son los términos más usados en el portal.

|Término |Significado |
| :- | :- |
|**Software de supervisión** |Agente de supervisión que se implementa en cada uno de los dispositivos de salas de Microsoft Teams. |
|**Aplicación** |Aplicación de sistema de salas de Microsoft Teams (independientemente de si usa Skype for Business o Microsoft Teams como servicio de colaboración. |
|**Sala o dispositivo** |El dispositivo certificado del sistema de salas de Microsoft Teams. |
|**No supervisada** | El software de supervisión de Microsoft implementado como parte de los servicios administrados no puede conectarse a los servicios en la nube. No recibimos telemetría sobre el dispositivo. |
|<p>**En buen estado /** </p><p>**Insalubre** </p>|Anomalías en dispositivos o periféricos. |
|**Suprimido** |Si se sabe que un dispositivo está en mantenimiento y se deben ignorar sus alertas, el dispositivo se puede suprimir deliberadamente. |
|**Incorporación** |Se agrega el estado de un dispositivo de sala mientras se configura, pero no está listo como una sala admitida con regularidad. |
|**Incidente** |Un problema que afecta a las experiencias de reunión de los usuarios finales que necesitan una acción. |
|**Desconfigurado** |La configuración detectada no es correcta o se usa habitualmente. |
|**Vale de soporte técnico** |Identificador de seguimiento interno de Microsoft que realiza un seguimiento de todas las comunicaciones y acciones relacionadas con un incidente. |

## <a name="incidents-view"></a>Vista incidentes

Esta vista es una descripción general de la pestaña Incidentes en el Portal de salas administradas. Esta página es la página principal predeterminada del portal.

### <a name="top-level-summary"></a>Resumen de nivel superior 
El resumen de nivel superior muestra de un vistazo los problemas que afectan a las salas, lo que necesita hacer y lo que Microsoft está haciendo al respecto:

![Captura de pantalla que muestra un resumen de nivel superior de problemas](../media/rooms-monitor-001new.png)

|# |Explicación |
| :- | :- |
|1 |Tipos de incidentes que afectan a las salas |
|2 |**ACCIÓN NECESARIA**: Elementos que requieren su intervención para resolver. |
|3 |**ASIGNADOS A MICROSOFT**: Elementos investigados actualmente por el personal de Microsoft. |
|4 |**INVESTIGACIÓN PENDIENTE**: Los elementos de la cola que investigará el personal de Microsoft. |

Se espera que los incidentes estén en uno de los tres estados siguientes:

- **Acción necesaria**: asignada a usted para realizar una acción
- **Asignado a Microsoft**: Asignado a Microsoft para la siguiente acción
- **Investigación pendiente**: en investigación para conocer los pasos siguientes

### <a name="reviewing-incidents"></a>Revisión de incidentes

En la imagen siguiente se enumeran todos los incidentes que están activos actualmente en las salas. Las que se le asignaron *están en la parte superior* : esto es lo que debe consultar para ver los pasos siguientes. Además, las asignadas a Microsoft o la investigación pendiente tienen detalles que puede utilizar para intervenir.

Al hacer clic en cualquiera de los elementos que tienen el estado "**Necesita acción**" se muestran detalles adicionales sobre el incidente.

## <a name="types-of-incidents"></a>Tipos de incidentes

Los incidentes se clasifican en dos tipos de gravedad generales:

- **Importante**: Los incidentes que probablemente estén causando problemas en las reuniones deben priorizarse.
- **Advertencia** : incidentes que son notificaciones para planear acciones de mantenimiento. Si estos no se cuidan, a lo largo del tiempo, es más probable que las salas se encuentren en un problema. Las advertencias están pensadas para darle tiempo para planear y orquestar el apoyo.

Es posible que una advertencia pase a "**Importante**" si no se atendió durante un tiempo.

## <a name="health-status-of-device-and-incidents"></a>Estado del dispositivo e incidentes

Los incidentes clasificados como **"Importante"** en gravedad afectarán al estado de un dispositivo. Si hay al menos un incidente de **gravedad = "Importante"** asociado a un dispositivo, se clasifica como dispositivo **_con mal estado_** .

Los incidentes clasificados como de gravedad **"Advertencia"** no afectan al estado notificado en un dispositivo. Sin embargo, si un dispositivo tiene incidentes de nivel de advertencia asociados, se mostrará con el estado del dispositivo como se indica a continuación.

![Captura de pantalla que muestra el estado de salud de una sala](../media/rooms-monitor-004.jpg)

A continuación se indican algunos de los tipos de incidentes que es posible que vea y las explicaciones de cada tipo. Para cada tipo, la acción asociada al incidente será más específica en función del problema.

**Tabla 1: Incidentes con gravedad "Importante"**

|Tipo |Explicación |
| :- | :- |
|**Pantalla** |La pantalla conectada al dispositivo no parece estar en buen estado.|
|**Micrófono de conferencia, orador de conferencia** |Los dispositivos de audio (micrófono / altavoz) parecen estar mal configurados. |
|**Cámara** |La cámara conectada al dispositivo no parece estar en buen estado. |
|**Entrada de HDMI** |La ingestión de HDMI no es saludable. |
|**Inicio de sesión** (Exchange) |La aplicación de salas de Microsoft Teams accede a la información del calendario desde Exchange y cualquier problema relacionado con el inicio de sesión correcto se notificará con un incidente de inicio de sesión. |
|**Inicio de sesión** (Teams) |La aplicación De salas de Microsoft Teams inicia sesión en el dispositivo y se notificará el error al iniciar sesión con este incidente (si el cliente está usando Teams). |
|**Inicio de sesión** (Skype for Business) |La aplicación Sala de Microsoft Teams inicia sesión en el dispositivo y se notificará que no se ha iniciado sesión con este incidente (si el cliente está usando Skype for Business) |
|**Sensor de proximidad** |La aplicación Sala de Microsoft Teams invita a los asistentes a unirse a una reunión si se encuentran cerca. Los errores de esta característica se notificarán en este incidente. |

**Tabla 2: Incidentes con gravedad "Advertencia"**

|Tipo |Explicación |
| :- | :- |
|**Versión de la aplicación** |La versión de la aplicación de salas de Microsoft Teams que se ejecuta en el dispositivo no es la actual. Las versiones obsoletas son causas conocidas de problemas experimentados por los usuarios. |
|**Versión del sistema operativo** |Ya no se recomienda la versión del sistema operativo Windows que se ejecuta en la sala de reuniones. |
|**Red** |Esto se quitará como un tipo de advertencia a corto plazo debido al trabajo adicional necesario después de la evaluación. |

## <a name="responding-to-incidents"></a>Responder a incidentes

Los incidentes se dividen en tres categorías: Acción de necesidades, Investigación pendiente o Asignada a Microsoft.

### <a name="needs-action-incidents"></a>Incidentes "Necesita acción"

Los incidentes que tengan el estado establecido **en "Necesita acción"** se le asignarán para que realice una acción correctiva.

Cada incidente tendrá un campo de acción con una acción recomendada de Microsoft de la siguiente manera:

![Captura de pantalla que muestra la acción de incidente recomendada](../media/rooms-monitor-005.jpg)

- Si ha realizado la acción, puede responder al incidente con sus notas en el cuadro Responder y, a continuación, elegir "Asignar a Microsoft" antes de publicar.
- También es posible que la notificación sea incorrecta en función de su revisión. En ese caso, facilita esos comentarios y vuelve a asignarlos a Microsoft.
- Por último, si desea agregar un comentario para proporcionar contexto adicional para su propio equipo o para el equipo de Microsoft, publique el mensaje sin activar "Asignar a Microsoft".

>[!NOTE]
>La acción correctiva puede solucionar el problema y que la supervisión de salones administrados borre ese incidente de la lista. En la situación anterior, es posible que no puedas resolver el problema y volver a asignarlo a Microsoft. Este problema se abordará en una versión futura.

### <a name="pending-investigation-incidents"></a>Incidentes de "Investigación pendiente"

Para los incidentes investigados, el campo de descripción contiene información sobre el incidente, las causas típicas y las resoluciones que pueden ser útiles para resolver determinados problemas de forma que pueda actuar sin demora.

### <a name="assigned-to-microsoft-incidents"></a>Incidentes "Asignados a Microsoft"

Para los incidentes asignados a Microsoft, el campo "Acción" contendrá breves detalles sobre los pasos correctivos planeados o progresados. Estos pasos podrían necesitar colaboración con su equipo y la colaboración ampliada se realizará a través de correo electrónico o llamadas según sea necesario. Una vez resueltos estos problemas, desaparecerán del portal y, en el futuro, habrá historial para realizar un seguimiento de estos incidentes y su resolución.

![Captura de pantalla que muestra los pasos correctivos de MS](../media/rooms-monitor-006.jpg)

## <a name="rooms-view"></a>Vista de habitaciones

Cada dispositivo es un proxy para una sala y sus periféricos conectados. Un dispositivo saludable representa una sala sana y un dispositivo con mal estado representa una sala que probablemente causa problemas durante las reuniones. Además de la vista Incidentes, el Portal de salas administradas también proporciona información general sobre el estado de las salas y le ayuda a solucionar los detalles del dispositivo, así como a comprender los errores repetidos con el historial de incidentes.

![Captura de pantalla que muestra la información general del estado de una sala](../media/rooms-monitor-007.jpg)

**En buen estado, No saludable, Desconectado** El panel superior de la vista Salas proporciona una instantánea rápida de cuántos dispositivos están en buen estado ("En buen estado"), cuántos se ven afectados por problemas ("Incorrecto"), cuántos no proporcionan telemetría ("Desconectado") y cuántos dispositivos se suprimen para recibir alertas (como invalidación). Los salones están supervisados por motivos de salud utilizando criterios en evolución y heurística. El objetivo es reflejar la realidad de la experiencia del usuario en la sala con la mayor precisión posible y que sea útil.

**Habitaciones sanas o malsanas**:

Los dispositivos o periféricos que no tengan incidentes de gravedad "Importante" cumplen los criterios actuales de mantenimiento se marcan como correctos. Sin embargo, no implica que haya una interrupción de espacio para cada dispositivo en mal estado en el portal. La descripción y la parte de acción del incidente contiene detalles más específicos sobre el problema y el posible impacto en la experiencia del usuario.

**Dispositivo desconectado:**

El agente de supervisión de Microsoft implementado como parte del programa piloto De salas administradas se desconecta de los servicios en la nube de salas administradas. No recibimos telemetría sobre la sala y no tenemos el estado de salud más reciente. Esto puede ocurrir debido a problemas de red, cambios en la directiva de firewall o si se realizan cambios en la imagen del dispositivo.

## <a name="room-detail-status-and-changes"></a>Detalle de la sala: Estado y cambios

**Detalles de la sala: Estado** La pestaña *Estado* del dispositivo proporciona una vista consolidada del estado de un dispositivo, todos los problemas activos del dispositivo, las acciones necesarias para resolverlos o los que están en curso. La pestaña Estado también contiene el desglose de los diferentes componentes del estado del dispositivo en la *pestaña Incidentes*. Si un dispositivo está desconectado, los detalles de estado no estarán disponibles.

![Captura de pantalla que muestra la vista de estado consolidado](../media/rooms-monitor-008.png)

**Mostrar todas las señales:** Para ver todas las señales contenidas dentro de una categoría de señal, habilita el botón de alternancia Mostrar todas las señales. Las flechas de expansión aparecerán junto a los encabezados de categoría en los que se puede hacer clic para expandir la vista de acordeón.

![Captura de pantalla que muestra señales dentro de una categoría](../media/rooms-monitor-009.png)

**Suprimir/Desuppress Ticket** Cuando se inscribe un salón, indica que desea recibir notificaciones de cambios en la telemetría del salón. Hay ocasiones en las que un dispositivo o periférico determinado se encuentra en un estado conocido en el que no quieres que se generen entradas o notificaciones. Al usar la funcionalidad Suprimir incidencia, se silenciará cualquier notificación sobre esa señal en particular. Cuando estés listo para que el servicio te supervise y te avise sobre esa señal, simplemente desanclar la señal individual.

![Captura de pantalla que muestra las entradas suprimidas de la sala](../media/rooms-monitor-010.png)

**Expansión de categoría de vale activa** En cada categoría de vale, se mostrará cualquier vale resuelto o activo junto con la gravedad y la última actualización del vale. Al hacer clic en la flecha de expansión, todas las entradas aparecerán con un vínculo activo a la información de la incidencia.

Expansión de la categoría de vale activa: en cada categoría de vale, se mostrará cualquier vale resuelto o activo junto con la gravedad y la última vez que se actualizó el ticket. Al hacer clic en la flecha de expansión, todas las entradas aparecerán con un vínculo activo a la información de la incidencia.

![Captura de pantalla que muestra la categoría de vales resuelta](../media/rooms-monitor-011.png)

## <a name="active-ticket-overview"></a>Vale activo: Información general

Cada incidente que se crea identifica el problema que se ha detectado y la acción correctiva que se debe realizar para restaurar la sala a un estado correcto. El vale generado transmitirá información general sobre incidentes con los mensajes generados por la IA de los servicios administrados, así como con el equipo de ingeniería de servicios de Microsoft que investiga el problema. Se mostrarán todos los datos adjuntos recopilados para la solución de problemas de incidentes. La pestaña Historial proporciona las fechas en las que se han identificado los problemas.

![Captura de pantalla que muestra información general del vale activo](../media/rooms-monitor-012.png)

Vale activo: Mensajes La interfaz de usuario de mensajes es la herramienta de comunicación principal para interactuar con los ingenieros de servicio de Microsoft que trabajan para corregir el problema identificado. Es importante reconocer las comunicaciones de Microsoft para garantizar que le proporcionamos el mejor servicio posible. Si ha realizado las acciones recomendadas, responda a este incidente con sus notas en el cuadro Responder y asígnelas de nuevo a Microsoft haciendo clic en "Asignar a Microsoft" antes de publicar.
También es posible que la notificación sea incorrecta en función de su revisión. En ese caso, facilita esos comentarios y vuelve a asignarlos a Microsoft.
Por último, si desea agregar un comentario para proporcionar contexto adicional para su propio equipo o para el equipo de Microsoft, simplemente publique el mensaje sin activar "Asignar a Microsoft

![Captura de pantalla que muestra los mensajes de vale activos](../media/rooms-monitor-013.png)


Vale activo: datos adjuntos Hay ocasiones en las que los ingenieros de servicio de Microsoft necesitan información adicional para ampliar su investigación del problema. La pestaña de datos adjuntos le ofrece la posibilidad de cargar imágenes, vídeos o registros que se soliciten.

![Captura de pantalla que muestra adjunciones de vales activas](../media/rooms-monitor-014.png)

Vale activo: Historial Cada señal de la sala solo tiene un número de billete asignado a propósito. Un dispositivo de sala o periférico se mantiene en una sala y puede tener problemas con el tiempo. Al mantener esta información bajo un id. de vale único específico, toda la información histórica se mantiene y se puede analizar para encontrar patrones de comportamiento. La interfaz de usuario de Historial proporciona una vista de todas las acciones de tickets creadas y resueltas para esta señal.

![Captura de pantalla que muestra el historial de vales activos](../media/rooms-monitor-015.png)

Preguntas frecuentes ¿Cómo me afectan las entradas dinámicas a mí y a las operaciones de mis salas?  
Los clientes verán la creación de tickets y correcciones más inteligentes que se expanden más allá de un vale de señal binaria. Por ejemplo, puede haber hasta tres pantallas en una sala de reuniones (Pantalla 1, Pantalla 2 & la pantalla del panel táctil MTR). Sin embargo, solo hay 1 (una) señal de pantalla que está saludable o no saludable. Con las nuevas entradas dinámicas, ahora podemos generar tickets únicos para cada señal de visualización.
