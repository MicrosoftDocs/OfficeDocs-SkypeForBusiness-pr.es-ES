---
title: Plan para Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: En este artículo se explican las consideraciones de planeación relevantes para implementar Salas de Microsoft Teams, la próxima generación de sistemas de salas de Skype.
ms.openlocfilehash: 392a14e3a72d60903db88b34d9b72152e1a8ec81
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761372"
---
# <a name="plan-microsoft-teams-rooms"></a>Planear Salas de Microsoft Teams

En este artículo se presenta un enfoque de principio a fin en la planificación, la entrega y el funcionamiento de Salas de Microsoft Teams como parte de la estrategia general de reuniones y salas de conferencias.

Encontrará información de planeación a continuación sobre el enfoque recomendado y las decisiones clave que debe tomar, con vínculos a información técnica de soporte. Le recomendamos que revise las secciones Planear, Implementar y Administrar incluso si ya está completamente implementado.

## <a name="overview-of-microsoft-teams-rooms"></a>Información general sobre Salas de Microsoft Teams

Salas de Microsoft Teams proporciona una experiencia de reunión completa que ofrece vídeo hd, audio y uso compartido de contenido para reuniones de todos los tamaños, desde pequeñas áreas de reunión hasta salas de conferencias grandes.

![Un usuario pulsa una Salas de Teams consola, con una pantalla en segundo plano.](../media/room-systems-image1.jpg "Un usuario pulsa una Salas de Teams consola, con una pantalla en segundo plano")
 [Salas de Microsoft Teams ayuda](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) es un gran recurso para obtener más información sobre Salas de Microsoft Teams y cómo puede agregar valor como parte de la implementación.

## <a name="microsoft-teams-rooms-components"></a>Salas de Microsoft Teams componentes

Salas de Microsoft Teams incluye los siguientes componentes clave para ofrecer una excelente experiencia de usuario:

- Consola de pantalla táctil
- Módulo de cálculo
- aplicación Salas de Microsoft Teams
- Dispositivos periféricos (cámara, micrófono, altavoz)
- Pantallas externas (máximo de dos)
- Entrada HDMI

Puedes adquirir estos componentes como paquetes preinstalados de varios proveedores o puedes comprar los componentes admitidos individualmente siguiendo [los requisitos documentados en este artículo](requirements.md).

Puede implementar Salas de Microsoft Teams con implementaciones locales de Microsoft Teams o Skype Empresarial.  Consulte la [actualización de licencias de Teams Sala de reuniones](rooms-licensing.md) para obtener información sobre las licencias necesarias.

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![decidir la implementación.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Implementará Salas de Microsoft Teams en su organización? </li><li>¿Cómo adquirirás tus sistemas de Salas de Microsoft Teams?</li></ul> |
| ![identificar actividades.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes | <ul><li>Identifique quién llevará a cabo las actividades clave durante toda la implementación.</li><li>Revise las salas de reuniones que tiene (y tiene previsto configurar) para comprender dónde quiere implementar Salas de Microsoft Teams y los dispositivos periféricos que serían adecuados para el tamaño de la sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quién llevará a cabo las actividades clave durante la implementación

Use el enfoque que se muestra a continuación para guiarle por la implementación y personalizar los resultados de ejemplo proporcionados según sea necesario para su organización.

Comience por comprender qué salas de conferencias tiene y concise qué le funcionaría mejor en el futuro y, a continuación, desplácese por la selección y la procuración del equipo que necesita, preparando sus sitios, configurando e implementando su servicio, administrando el cambio y la adopción del usuario, y desarrollando operaciones y procedimientos de mantenimiento.

![Comience con la comprensión de lo que tiene y la visualización de lo que funcionaría mejor para usted, a continuación, desplazarse a través de la selección y la procuración del equipo que necesita, la configuración de los sitios, la configuración e implementación de su servicio, la administración de cambios y la adopción del usuario, y el desarrollo de operaciones y procedimientos de mantenimiento.](../media/room-systems-image2.png "Comience con la comprensión de lo que tiene y la visualización de lo que funcionaría mejor para usted, a continuación, desplazarse a través de la selección y la procuración del equipo que necesita, la configuración de los sitios, la configuración e implementación de su servicio, la administración de cambios y la adopción del usuario, y el desarrollo de operaciones y procedimientos de mantenimiento.")

Es posible que necesite coordinar estas actividades en varios equipos. Proporcionamos una vista de alto nivel de las actividades principales que debe cubrir, así como sugerencias para los equipos que suelen participar en la implementación y administración de sistemas de salas de conferencias, para ayudarle a decidir con quién necesita trabajar.

| Tarea                       | Quién realizar la tarea           | Asignado a | Vínculos a este contenido |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Inventario de salas            | Servicios / AV team / IT Project Team |             | [Inventario de salas y planeamiento de capacidades](#room-inventory-and-capability-planning) |
| Funcionalidades del plan          | Equipo de Project de TI                        |             | [Inventario de salas y planeamiento de capacidades](#room-inventory-and-capability-planning) |
| Selección de dispositivos           | Equipo de Project DE TI/AV              |             | [Selección de dispositivos](#device-selection) |
| Adquisiciones                | Equipo de Project DE TI/AV              |             | [Adquisiciones](#procurement) |
| Disponibilidad del sitio             | Servicios / AV team / IT Project Team |             | [Disponibilidad del sitio](rooms-deploy.md#site-readiness) |
| Preparación del servicio          | Equipo de Project de TI                        |             | [Preparación del servicio](rooms-deploy.md#service-readiness) |
| Configuración              | Equipo de Project de TI                        |             | [Configuración e implementación](rooms-deploy.md#configuration-and-deployment) |
| Deployment                 | Servicios / AV team / IT Project Team |             | [Lista de comprobación de implementación](console.md#microsoft-teams-rooms-deployment-checklist) |
| Adopción                   | Servicios / AV team / IT Project Team |             | [Adopción](#plan-for-adoption-and-change-management) |
| Mantenimiento y funcionamiento | Equipo de AV/equipo de Project de TI              |             | [Introducción a la administración](rooms-manage.md) |

## <a name="room-inventory-and-capability-planning"></a>Inventario de salas y planeamiento de capacidades

El primer paso es hacer un inventario de los espacios de reunión y salas de conferencias existentes de su organización para comprender su entorno, tamaño, diseño y finalidad. A continuación, puedes identificar las capacidades que quieres que tenga cada sala, como cámaras inteligentes, pizarra, cámara de contenido, etc.

Después de crear un inventario del equipo y las capacidades de cada sala existente, los requisitos de esa fuente de sala se incluyen en el planeamiento de selección de dispositivos para crear una solución de conferencia enriquecida. Las modalidades (audio y vídeo) necesarias para cada sala, además del tamaño y el propósito de la sala, desempeñan un papel importante a la hora de decidir qué solución es la más adecuada para cada sala.

Como parte de su descubrimiento, es clave tener en cuenta la acústica y la distribución de las salas. Por ejemplo, compruebe que las sillas de la sala no bloquee la vista de la cámara. Compruebe que la habitación no tiene eco excesivo o aire acondicionado ruidoso y que tiene suficiente energía para las pantallas y Salas de Microsoft Teams. Hay muchos factores que debe tener en cuenta que su equipo o socio audiovisual (AV) podrá asesorar.

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![habitaciones deplyment.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Revise las salas en el ámbito y defina configuraciones de Salas de Microsoft Teams para ellas.</li></ul>|

_Inventario de reuniones o salas de conferencias de ejemplo_

| Sitio      | Nombre de la sala | Tipo de sala | Número de personas | ¿En el ámbito? | Capacidades de la sala actual           | Capacidades futuras de la sala |
|-----------|-----------|-----------|------------------|-----------|-------------------------------------|--------------------------|
| SEDE de Londres | Curie     | Medio    | 6&ndash;12       | Sí       | Altavoz                        | 1 pantalla, audio y vídeo y presentación<br>Acceso RTC |
| Sede de Sydney | Colina      | Grande     | 12&ndash;16      | Sí       | Unidad AV heredada, 1 pantalla y cámara | 2 pantallas, audio y vídeo más presentación<br>Acceso RTC |

## <a name="device-selection"></a>Selección de dispositivos

Evalúe qué solución Salas de Microsoft Teams es la más adecuada para cada sala en función de las capacidades futuras que desee para la sala. Decide qué dispositivos periféricos AV son el mejor ajuste, en función del tamaño y la distribución de la sala.

Para obtener instrucciones sobre el tipo de sistema y dispositivos periféricos por tipo y tamaño de sala, consulte el artículo [requisitos de Salas de Microsoft Teams](requirements.md).

Según el proveedor que prefiera, use la información proporcionada en el artículo de requisitos para definir su Salas de Microsoft Teams y la configuración de dispositivos periféricos admitidos por tipo de salón, y úsela como plantilla para la implementación.

**Sugerencia de Pro**: es posible que algunos tipos de salas no sean aplicables a la implementación.

| &nbsp; | &nbsp; |
|---|---|
| ![habitaciones en el ámbito.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión | <ul><li>En el inventario, ¿qué tipos de salas están dentro del ámbito de la implementación?</li><li>¿Qué sistemas implementará para cada tipo de salón?</li></ul> |
| ![recopilar material.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes | <ul><li>Empiece a recopilar material operativo clave para los sistemas elegidos y a involucrar a su equipo de compras.</li></ul> |

_Plantilla de implementación de Salas de Microsoft Teams de ejemplo para su organización_

| Tamaño y tipo de habitación     | Número de personas | sistema Salas de Microsoft Teams | Dispositivos periféricos | Pantallas      |
|--------------------|------------------|------------------------------|--------------------|-----------------|
| Focus 10' por 9'    | 2&ndash;4        |                              |                    |                 |
| Pequeño de 16' por 16'   | 4&ndash;6        |                              |                    |                 |
| Mediana de 18' por 20'  | 6&ndash;12       |                              |                    |                 |
| Grande 15' por 32'   | 12&ndash;16      |                              |                    |                 |

**sugerencia Pro:** ahora es un buen momento para empezar a recopilar información sobre la solución Salas de Microsoft Teams que ha elegido.

## <a name="procurement"></a>Adquisiciones

Puedes adquirir el sistema elegido como un paquete o una solución integrada a través de partners de dispositivos.

Puede adquirir Salas de Microsoft Teams a varios partners que se enumeran en el [artículo de requisitos](requirements.md). Visite los sitios web de los asociados para obtener más información sobre estas soluciones y opciones de adquisición.

Según la escala de implementación y el enfoque, es posible que decida que los dispositivos periféricos compatibles y de Salas de Microsoft Teams se envíen a una ubicación central para la asignación y configuración iniciales. Este podría ser un buen enfoque para una implementación preconfigurada en muchos sitios. O bien, puedes enviar los paquetes directamente a tus sitios.

| &nbsp; | &nbsp; |
|---|---|
| ![componentes de envío.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Enviará los componentes directamente a un sitio o a una instalación de ensayo?</li><li>Quién administrará la instalación provisional (si decides usar una)?</li></ul> |
| ![planificar operaciones.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Planear las operaciones.</li><li>Planear la adopción y la administración de cambios.</li></ul> |

## <a name="plan-for-operations"></a>Plan de operaciones

Su organización debe ejecutar las tareas de supervisión, administración y administración de forma continua, y es clave acordar quién llevará a cabo estas tareas al principio de la implementación.

Muchas organizaciones tienen un equipo de AV o un socio que administra sus salas de conferencias y dispositivos. O puedes hacer que Microsoft te ayude a administrar Salas de Teams aprovechando Salas de Microsoft Teams Premium. Decida quién administrará los dispositivos Salas de Microsoft Teams en el futuro para supervisar el rendimiento e implementar actualizaciones de software y revisiones.

Tenga en cuenta a qué cola del departamento de soporte técnico redirigirá las llamadas relacionadas con Salas de Microsoft Teams y proporcione unas preguntas más frecuentes al equipo del departamento de soporte técnico para que puedan comprender mejor cómo usar Salas de Microsoft Teams y los pasos clave de solución de problemas que pueden seguir. Un buen punto de partida para estas preguntas frecuentes es la [ayuda del usuario](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) y [los problemas conocidos](known-issues.md).

| &nbsp; | &nbsp; |
|---|---|
| ![elige administrador.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará Salas de Microsoft Teams.</li><li>Decida a qué cola del departamento de soporte técnico redirigir las llamadas relacionadas con Salas de Microsoft Teams.</li></ul> |
| ![preparar cuentas de host.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes |<ul><li>Prepárese para hospedar cuentas.</li></ul> |

## <a name="plan-for-adoption-and-change-management"></a>Planear la adopción y la administración de cambios

Salas de Microsoft Teams sistemas presentan nuevas capacidades a los usuarios. Es importante que reconozca que este será un cambio para los usuarios y que debe asegurarse de que su campaña de marketing interno identifica los beneficios que el nuevo sistema tendrá para sus usuarios y los principales puntos de conversación que los clientes potenciales pueden usar para debatir con sus equipos.

Considere la posibilidad de programar eventos de presentación y entregas de pósteres en cada sitio para informar a los usuarios de las nuevas capacidades. También puede crear "guías de inicio rápido" en la sala. Considere la posibilidad de buscar un experto en reuniones en cada sitio que pueda ayudar a otros a ponerse al día y empezar a usar los dispositivos.
