---
title: Portal de administración de Salas de Microsoft Teams Pro
author: altsou
ms.author: altsou
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
ms.openlocfilehash: 2439b4edb59845515ccef6997d542ee0a2855fa0
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243951"
---
# <a name="microsoft-teams-rooms-pro-management-portal"></a>Portal de administración de Salas de Microsoft Teams Pro

## <a name="overview"></a>Información general

El portal de administración de MTR Pro proporciona una vista del estado de sus salas de reuniones y ayuda a facilitar sus prácticas y herramientas de supervisión existentes.

El ámbito de la supervisión es

- Vista de incidentes
  - Principales problemas que afectan a las salas
  - Acciones necesarias para restaurar las salas al estado correcto
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
|**Aplicación** |Aplicación de sistema de salas de Microsoft Teams (independientemente de si usa Skype Empresarial o Microsoft Teams como servicio de colaboración. |
|**Sala o dispositivo** |El dispositivo certificado del sistema de salas de Microsoft Teams. |
|**No supervisada** | El software de supervisión de Microsoft implementado como parte de los servicios de administración no puede conectarse a los servicios en la nube. No recibimos telemetría sobre el dispositivo. |
|<p>**Sano/** </p><p>**Insalubre** </p>|Anomalías en dispositivos o periféricos. |
|**Suprimido** |Si se sabe que un dispositivo está en mantenimiento y se deben ignorar sus alertas, el dispositivo se puede suprimir deliberadamente. |
|**Incorporación** |Se agrega el estado de un dispositivo de sala mientras se configura, pero no está listo como una sala admitida con regularidad. |
|**Incidente** |Un problema que afecta a las experiencias de reunión de los usuarios finales que necesitan una acción. |
|**Desconfigurado** |La configuración detectada no es correcta o se usa habitualmente. |

## <a name="incidents-view"></a>Vista incidentes

Esta vista es una descripción general de la pestaña Incidentes del Portal de administración de Pro. Esta página es la página principal predeterminada del portal.

### <a name="top-level-summary"></a>Resumen de nivel superior 
El resumen de nivel superior muestra de un vistazo los problemas que afectan a las salas y lo que necesita hacer.

Se espera que los incidentes estén en uno de estos dos estados:

- **Need Action**: acción requerida por usted para resolver el incidente.
- **Sistema investigando**: Bajo investigación automática por la plataforma de monitoreo. Si no se puede resolver automáticamente, se proporcionarán los pasos siguientes.

### <a name="reviewing-incidents"></a>Revisión de incidentes

Al hacer clic en cualquiera de los elementos que tienen el estado "**Necesita acción**" se muestran detalles adicionales sobre el incidente.

## <a name="types-of-incidents"></a>Tipos de incidentes

Los incidentes se clasifican en dos tipos de gravedad generales:

- **Importante**: Incidentes que probablemente causan problemas en las reuniones y que deben priorizarse.
- **Advertencia** : incidentes que son notificaciones para planear acciones de mantenimiento. Si estos no se cuidan, a lo largo del tiempo, es más probable que las salas se encuentren con un problema. Las advertencias están pensadas para darle tiempo para planear y orquestar el apoyo.

Es posible que una advertencia pase a "**Importante**" si no se atendió durante un tiempo.

## <a name="health-status-of-device-and-incidents"></a>Estado del dispositivo e incidentes

Los incidentes clasificados como **"Importante"** en gravedad afectarán al estado de un dispositivo. Si hay al menos un incidente de **gravedad = "Importante"** asociado a un dispositivo, se clasifica como dispositivo **_en mal estado_** .

Los incidentes clasificados como de gravedad **"Advertencia"** no afectan al estado notificado en un dispositivo. Sin embargo, si un dispositivo tiene incidentes de nivel de advertencia asociados, se mostrará con el estado del dispositivo.


A continuación se indican algunos de los tipos de incidentes que es posible que vea y las explicaciones de cada tipo. Para cada tipo, la acción asociada al incidente será más específica en función del problema.

**Tabla 1: Incidentes con gravedad "Importante"**

|Tipo |Explicación |
| :- | :- |
|**Pantalla** |La pantalla conectada al dispositivo no parece estar en buen estado.|
|**Micrófono de conferencia, orador de conferencia** |Los dispositivos de audio (micrófono / altavoz) parecen estar mal configurados. |
|**Cámara** |La cámara conectada al dispositivo no parece estar en buen estado. |
|**Entrada de HDMI** |La ingesta de HDMI no es saludable. |
|**Inicio de sesión** (Exchange) |Salas de Microsoft Teams aplicación tiene acceso a la información del calendario de Exchange y cualquier problema relacionado con el inicio de sesión correcto se notificará con un incidente de inicio de sesión. |
|**Inicio de sesión** (Teams) |Salas de Microsoft Teams aplicación inicia sesión en el dispositivo y si no se inicia sesión se notificará con este incidente (si el cliente está usando Teams). |
|**Inicio de sesión** (Skype Empresarial) |Salas de Microsoft Teams aplicación inicia sesión en el dispositivo y se notificará que no se ha iniciado sesión con este incidente (si el cliente está usando Skype Empresarial). |
|**Sensor de proximidad** |Salas de Microsoft Teams aplicación invita a los asistentes a unirse a una reunión si se encuentran cerca. Los errores de esta característica se notificarán en este incidente. |

**Tabla 2: Incidentes con gravedad "Advertencia"**

|Tipo |Explicación |
| :- | :- |
|**Versión de la aplicación** |La versión de la aplicación de salas de Microsoft Teams que se ejecuta en el dispositivo no es la actual. Las versiones obsoletas son causas conocidas de problemas experimentados por los usuarios. |
|**Versión del sistema operativo** |Ya no se recomienda la versión del sistema operativo Windows que se ejecuta en la sala de reuniones. |
|**Red** |Esto se quitará como un tipo de advertencia a corto plazo debido al trabajo adicional necesario después de la evaluación. |

## <a name="responding-to-incidents"></a>Responder a incidentes

Los incidentes se dividen en dos categorías: Necesita acción o Investigación del sistema.

### <a name="needs-action-incidents"></a>Incidentes "Necesita acción"

Los incidentes que tengan el estado establecido **en "Necesita acción"** se le asignarán para que realice una acción correctiva.

Cada incidente tendrá un campo de acción con una acción recomendada de Microsoft de la siguiente manera:

- Si ha realizado la acción, puede responder al incidente con sus notas para proporcionar contexto adicional en el cuadro Responder.

### <a name="system-investigating-incidents"></a>Incidentes de "investigación del sistema"

Para los incidentes investigados, el campo de descripción contiene información sobre el incidente, las causas típicas y las resoluciones que pueden ser útiles para resolver determinados problemas de forma que pueda actuar sin demora. 

## <a name="rooms-view"></a>Vista de habitaciones

Cada dispositivo es un proxy para una sala y sus periféricos conectados. Un dispositivo saludable representa una sala sana y un dispositivo con mal estado representa una sala que probablemente causa problemas durante las reuniones. Además de la vista Incidentes, el Portal de administración de Pro también proporciona información general sobre el estado de la sala y le ayuda a solucionar los detalles del dispositivo y a comprender los errores repetidos con el historial de incidentes.

**En buen estado, No saludable, Desconectado** El panel superior de la vista Salas proporciona una instantánea rápida de cuántos de los dispositivos están en buen estado ("En buen estado"), cuántos se ven afectados por problemas ("Incorrecto"), cuántos no proporcionan telemetría ("Desconectado") y cuántos dispositivos se suprimen para recibir alertas (como invalidación). Los salones están supervisados por motivos de salud utilizando criterios en evolución y heurística. El objetivo es reflejar la realidad de la experiencia del usuario en la sala con la mayor precisión posible y que sea útil.

**Habitaciones sanas o malsanas**:

Los dispositivos o periféricos que no tengan incidentes de gravedad "Importante" cumplen los criterios actuales de mantenimiento se marcan como correctos. Sin embargo, no implica que haya una interrupción de espacio para cada dispositivo con mal estado en el portal. La descripción y la parte de acción del incidente contiene detalles más específicos sobre el problema y el posible impacto en la experiencia del usuario.

**Dispositivo desconectado:**

El agente de supervisión de Microsoft implementado se desconecta de los servicios en la nube de Pro Management. No recibimos telemetría sobre la sala y no tenemos el estado de mantenimiento más reciente. Esto puede ocurrir debido a problemas de red, cambios en la directiva de firewall o si se realizan cambios en la imagen del dispositivo.

## <a name="room-detail-status-and-changes"></a>Detalle de la sala: Estado y cambios

**Detalles de la sala: Estado** La pestaña *Estado* del dispositivo proporciona una vista consolidada del estado de un dispositivo, todos los problemas activos del dispositivo, las acciones necesarias para resolverlos o los que están en curso. La pestaña Estado también contiene el desglose de los diferentes componentes del estado del dispositivo en la *pestaña Incidentes*. Si un dispositivo está desconectado, los detalles de estado no estarán disponibles.

**Mostrar todas las señales:** Para ver todas las señales contenidas dentro de una categoría de señal, habilita el botón de alternancia Mostrar todas las señales. Las flechas de expansión aparecerán junto a los encabezados de categoría en los que se puede hacer clic para expandir la vista de acordeón.

**Suprimir/Desuppress Ticket** Cuando se inscribe un salón, indica que desea recibir notificaciones de cambios en la telemetría del salón. Hay ocasiones en las que un dispositivo o periférico determinado se encuentra en un estado conocido en el que no quieres que se generen entradas o notificaciones. Al usar la funcionalidad Suprimir incidencia, se silenciará cualquier notificación sobre esa señal en particular. Cuando estés listo para que el servicio te supervise y te avise sobre esa señal, simplemente desanclar la señal individual.

**Expansión de categoría de vale activa** En cada categoría de vale, se mostrará cualquier vale resuelto o activo junto con la gravedad y la última actualización del vale. Al hacer clic en la flecha de expansión, todas las entradas aparecerán con un vínculo activo a la información de la incidencia.

Expansión de la categoría de vale activa: en cada categoría de vale, se mostrará cualquier vale resuelto o activo junto con la gravedad y la última vez que se actualizó el ticket. Al hacer clic en la flecha de expansión, todas las entradas aparecerán con un vínculo activo a la información de la incidencia.

## <a name="active-ticket-overview"></a>Vale activo: Información general

Cada incidente que se crea identifica el problema que se ha detectado y la acción correctiva que se debe realizar para restaurar la sala a un estado correcto. El vale generado transmitirá información general sobre incidentes con los mensajes generados por el servicio de administración de Pro. Se mostrarán todos los datos adjuntos recopilados para la solución de problemas de incidentes. La pestaña Historial proporciona las fechas en las que se han identificado los problemas.

Vale activo: Mensajes La interfaz de usuario de mensajes es la herramienta de comunicación principal para interactuar con su propio equipo y supervisar los mensajes del bot de Pro Management.

Vale activo: Datos adjuntos Hay ocasiones en las que su equipo necesitará información adicional para ampliar la investigación del problema. La pestaña de datos adjuntos le ofrece la posibilidad de cargar imágenes, vídeos o registros que se soliciten.

Vale activo: Historial Cada señal de la sala solo tiene un número de billete asignado a propósito. Un dispositivo de sala o periférico se mantiene en una sala y puede tener problemas con el tiempo. Al mantener esta información bajo un id. de vale único específico, toda la información histórica se mantiene y se puede analizar para encontrar patrones de comportamiento. La interfaz de usuario de Historial proporciona una vista de todas las acciones de tickets creadas y resueltas para esta señal.

Preguntas frecuentes ¿Cómo me afectan las entradas dinámicas a mí y a las operaciones de mis salas?  
Los clientes verán la creación de tickets y correcciones más inteligentes que se expanden más allá de un vale de señal binaria. Por ejemplo, puede haber hasta tres pantallas en una sala de reuniones (Pantalla 1, Pantalla 2 & la pantalla del panel táctil MTR). Sin embargo, solo hay 1 (una) señal de pantalla que está saludable o no saludable. Con las nuevas entradas dinámicas, ahora podemos generar tickets únicos para cada señal de visualización.
