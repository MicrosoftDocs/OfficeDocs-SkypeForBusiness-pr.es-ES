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
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: En este artículo se explican las consideraciones de planeación pertinentes para implementar salas de Microsoft Teams, la nueva generación de sistemas de salas de Skype.
ms.openlocfilehash: ccc24aea1a45d2aa75c3b1a5de668b520483c2bd
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662475"
---
# <a name="plan-microsoft-teams-rooms"></a>Planear salas de Microsoft Teams

Este artículo presenta un enfoque end-to-end para planear, entregar y trabajar con salas de Microsoft Teams como parte de su estrategia general de reuniones y salas de conferencias.

Encontrará información de planeación a continuación sobre el método recomendado y las decisiones clave que necesita tomar, con vínculos a información técnica de soporte. Le recomendamos que revise las secciones planificar, implementar y administrar, incluso si ya se ha implementado por completo.

## <a name="overview-of-microsoft-teams-rooms"></a>Información general sobre salas de Microsoft Teams

Salas de Microsoft Teams proporciona una experiencia de reunión completa que aporta video, audio y uso compartido de contenido de alta definición a reuniones de todos los tamaños, desde pequeñas áreas de Huddle hasta grandes salas de conferencias.

![Una consola, un micrófono y una pantalla grande montada en una pared de sala de conferencias ilustrar los elementos de un ejemplo de configuración de salas de Microsoft Teams.](../media/room-systems-image1.png "Una consola, un micrófono y una pantalla grande montada en una pared de sala de conferencias ilustrar los elementos de un ejemplo de configuración de salas de Microsoft Teams.")

La [ayuda de Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) es un excelente recurso para obtener más información sobre las salas de Microsoft Teams y cómo puede agregar valor como parte de la implementación. Además, te recomendamos ver este [vídeo de información general](https://youtu.be/tNey5KZVCl0). 

## <a name="microsoft-teams-rooms-components"></a>Componentes de salas de Microsoft Teams

Salas de Microsoft Teams incluye los siguientes componentes clave para ofrecer una experiencia de usuario excelente:

- Panel de control de pantalla táctil
- Calcular
- Aplicación salas de Microsoft Teams
- Dock/extensor
- Dispositivos periféricos (cámara, micrófono, altavoz)
- Pantallas externas (máximo de dos)
- Entrada HDMI

Puede adquirir estos componentes como paquetes preinstalados de varios proveedores, o bien puede comprar los componentes compatibles de forma individual siguiendo los [requisitos documentados en este artículo](requirements.md).

Además de la combinación Surface Pro/Dock, también puede comprar salas de Microsoft Teams con el panel de control de pantalla táctil, compute, Dock y dispositivos periféricos clave integrados. 

Por lo general, los paquetes y las unidades integradas incluyen software preinstalado, mientras que si usted compra componentes admitidos por separado para los sistemas Surface Pro, tendrá que instalar el software. Para obtener instrucciones, consulte [este artículo sobre la instalación de software en dispositivos](rooms-scale.md). 

Puede implementar salas de Microsoft Teams con Microsoft Teams, Skype empresarial online o implementaciones híbridas o locales de Skype empresarial.  Consulte la [actualización de licencias de sala de reuniones de Teams](rooms-licensing.md) para obtener información sobre las licencias necesarias.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Implementará salas de Microsoft Teams en su organización? </li><li>¿Cómo va a adquirir sus sistemas de salas de Microsoft Teams: paquetes como componentes separados o como una unidad integrada?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes | <ul><li>Identifique quién llevará a cabo las actividades clave en toda su implementación.</li><li>Revise las salas de reuniones que tiene (y planee la configuración) para comprender dónde quiere implementar las salas de Microsoft Teams y los dispositivos periféricos que serían adecuados para el tamaño de la habitación.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quién llevará a cabo las actividades clave en toda la implementación

Use el método que se muestra a continuación para guiarse a través de la implementación y personalizar los resultados de ejemplo proporcionados en estos artículos según sea necesario para su organización.

Empiece por comprender qué salas de conferencias tiene y cómo le resultará más adecuado para usted en el futuro, luego desplácese por la selección y la provisión del equipo que necesita, prepare sus sitios, configure e implemente su servicio, administre el cambio y la adopción de usuarios, y desarrolle procedimientos operativos y de mantenimiento.

![Comience por comprender lo que tiene y en previsión, lo que le resultará más adecuado para usted, a continuación, desplácese seleccionando y deteniendo el equipo que necesita, preparando sus sitios, configurando e implementando su servicio, administrando el cambio y la adopción por el usuario, y desarrollando procedimientos de operaciones y mantenimiento.](../media/room-systems-image2.png "Comience por comprender lo que tiene y en previsión, lo que le resultará más adecuado para usted, a continuación, desplácese seleccionando y deteniendo el equipo que necesita, preparando sus sitios, configurando e implementando su servicio, administrando el cambio y la adopción por el usuario, y desarrollando procedimientos de operaciones y mantenimiento.")

Es posible que tenga que coordinar estas actividades en varios equipos. Proporcionamos una vista de alto nivel de las principales actividades que debe cubrir, así como sugerencias para los equipos que normalmente participan en la implementación y administración de sistemas de salas de conferencias, para ayudarle a decidir con quién necesita trabajar.

| Tarea                       | ¿Quién puede llevar a cabo la tarea?           | Asignada a | Vínculos a este contenido |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salas de inventario            | Equipo de instalaciones/equipos AV/IT del proyecto de ti |             | [Inventario de salas y planificación de capacidades](#room-inventory-and-capability-planning)        |
| Capacidades del plan          | Equipo del proyecto de ti                        |             | [Inventario de salas y planificación de capacidades](#room-inventory-and-capability-planning)                       |
| Selección de dispositivos           | Equipo de proyecto de ti/equipo de AV              |             | [Selección de dispositivos](#device-selection)                      |
| Obtención                | Equipo de proyecto de ti/equipo de AV              |             | [Obtención](#procurement)                      |
| Disponibilidad del sitio             | Equipo de instalaciones/equipos AV/IT del proyecto de ti |             | [Disponibilidad del sitio](rooms-deploy.md#site-readiness)                      |
| Preparación del servicio          | Equipo del proyecto de ti                        |             | [Preparación del servicio](rooms-deploy.md#service-readiness)                      |
| Configuración              | Equipo del proyecto de ti                        |             | [Configuración e implementación](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | Equipo de instalaciones/equipos AV/IT del proyecto de ti |             | [Lista de comprobación de implementación](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Aprobación                   | Equipo de instalaciones/equipos AV/IT del proyecto de ti |             | [Aprobación](#plan-for-adoption-and-change-management)                      |
| Mantenimiento y funcionamiento | Equipo AV/equipo de proyecto de ti              |             | [Introducción a la administración](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventario de salas y planificación de capacidades

El primer paso es hacer un inventario de las reuniones y las salas de reuniones de su organización para comprender su entorno, su tamaño, su diseño y propósito, y para identificar las capacidades que desea que tenga cada sala en el ámbito en el futuro, como qué capacidades de colaboración enriquecidas estarán habilitadas en el salón. 

Después de crear un inventario del equipo y de las capacidades de cada habitación existente, sus requisitos para la alimentación de la habitación en la planificación de selección de dispositivos para crear una solución de conferencia enriquecida. Las modalidades (audio y vídeo) necesarias para cada habitación, además del tamaño y la finalidad de la habitación, juegan un importante papel en la decisión de la solución más adecuada para cada sala. 

Como parte de tu descubrimiento, es esencial que consideres el formato acústico de la sala. Por ejemplo, verifica que las sillas del salón no bloqueen la vista de la cámara. Verifique que el salón no tenga demasiado eco o aire acondicionado con ruido y que tenga suficiente potencia para las pantallas y las salas de Microsoft Teams. Hay muchos factores que deben tenerse en cuenta para que tu equipo audiovisual (AV) o tu partner pueda avisarle. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Qué salas están en el ámbito de esta implementación?</li><li>¿Qué sitios están en el ámbito de la implementación?</li><li>¿Quién llevará a cabo el inventario de las salas de reuniones?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Revise las salas en el ámbito y defina las configuraciones de las salas de Microsoft Teams para ellas.</li></ul>|

_Ejemplo de inventario de reunión/sala de conferencias_

| Sitio  | Nombre del salón | Tipo de habitación | Número de personas  | En el ámbito? | Capacidades actuales de la sala       | Capacidades de la sala en el futuro     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| HQ de Londres | Curie         | Medio        | 6 &ndash; 12                  | Sí          | Emitiendo                        | 1 Presentación de pantalla, audio y vídeo<br>Acceso a través de RTC |
| HQ de Sydney | Arrancar          | Grande         | 12 &ndash; 16                 | Sí          | Unidad AV heredada, 1 pantalla y cámara | 2 pantallas, presentación de audio y vídeo Plus<br>Acceso a través de RTC |

## <a name="device-selection"></a>Selección de dispositivos 

Evalúe qué solución Rooms de Microsoft Teams es la más adecuada para cada habitación en función de las capacidades futuras que desee para el salón. Decidir qué dispositivos periféricos de AV son los mejores de acuerdo con el tamaño y el diseño del salón. 

Para obtener información sobre el tipo de dispositivos periféricos y de sistema según el tipo de habitación y tamaño, consulte el artículo sobre los requisitos de las [salas de Microsoft Teams](requirements.md) . 

Según el proveedor que prefiera, use la información proporcionada en el artículo requisitos para definir las salas de Microsoft Teams y la configuración de dispositivos periféricos admitidos por tipo de habitación y use esta como una plantilla para su implementación. 

**Sugerencia Pro** : es posible que algunos tipos de salas no sean aplicables a su implementación.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Desde el inventario, ¿qué tipos de salas están en el ámbito de la implementación?</li><li>¿Qué sistemas se implementarán para cada tipo de sala?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comience a recopilar material operativo clave para los sistemas elegidos y póngase en colaboración con su equipo de compras.</li></ul>|

_Plantilla de implementación de salas de Microsoft Teams para su organización_

| **Tipo/tamaño de la sala** | **Número de personas**  | **Sistema de salas de Microsoft Teams** | **Dispositivos periféricos**  | **Mostrar (s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Foco 10 ' por 9 '      | 2 &ndash; 4                   |                                  |                         |                 |
| 16 ' por 16 ' de tamaño pequeño     | 4 &ndash; 6                   |                                  |                         |                 |
| Medio de 18 ' por 20 '    | 6 &ndash; 12                  |                                  |                         |                 |
| 15 de gran tamaño ' por 32 '     | 12 &ndash; 16                 |                                  |                         |                 |

**Sugerencia Pro:** Ahora es un buen momento para empezar a recopilar información sobre la solución salas de Microsoft teams que ha elegido.

## <a name="procurement"></a>Obtención 

Puedes adquirir tu sistema elegido como un paquete o una solución integrada a través de los socios de dispositivos. También puede adquirir un dispositivo asociado acoplar y preparar su propia solución de salas de Microsoft Teams con un dispositivo Surface Pro y dispositivos periféricos AV existentes _admitidos_ . 

Puede adquirir salas de Microsoft Teams a partir de varios socios que aparecen en el [artículo requisitos](requirements.md). Visite los sitios web de los socios para obtener más información sobre estas soluciones y opciones de compras. 

Según el nivel de implementación y el método, es posible que se envíen las salas de Microsoft Teams y los dispositivos periféricos compatibles a una ubicación central para la configuración inicial y la asignación. Puede ser un buen enfoque para una implementación preconfigurada en muchos sitios. También puedes optar por enviar los paquetes directamente a tus sitios. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Enviará los componentes directamente a un sitio o a un servicio de ensayo?</li><li>¿Quién administrará el servicio de ensayo (si decides usar uno)?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Planear las operaciones.</li><li>Planear la adopción y la administración de cambios.</li></ul>|

## <a name="plan-for-operations"></a>Planear las operaciones 

Su organización debe ejecutar tareas de supervisión, administración y administración de manera continua, y es clave para acordar quién realizará estas tareas al principio de la implementación. 

Muchas organizaciones tienen un equipo AV o asociado que administra sus salas de conferencias y dispositivos. Este equipo debe participar en la aceptación de quién administrará los dispositivos de salas de Microsoft teams que avanzarán para supervisar el rendimiento e implementar revisiones y actualizaciones de software. 

Considere la cola de ayuda de la que va a enrutar las llamadas relacionadas con Microsoft Teams Rooms֪ y envíe una pregunta frecuente al equipo de ayuda técnica para que puedan comprender mejor cómo usar las salas de Microsoft Teams y los pasos clave para la solución de problemas que pueden llevar a cabo. Un buen punto de partida para esta pregunta frecuente es la [ayuda del usuario](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) y los [problemas conocidos](known-issues.md).

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir quién administrará las salas de Microsoft Teams.</li><li>Decidir qué cola de ayuda para enrutar las llamadas relacionadas con Microsoft Team Rooms.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepararse para hospedar cuentas. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planear la adopción y la administración de cambios

Los sistemas de salas de Microsoft Teams introducen nuevas capacidades a los usuarios. Es importante que reconozca que se trata de un cambio para los usuarios y que debe asegurarse de que su campaña identifique las ventajas que tendrá el nuevo sistema para que los usuarios y los puntos de habla clave puedan usar para hablar con sus equipos. 

Considere la posibilidad de programar eventos de presentación y de pósters en cada sitio para informar a los usuarios de las nuevas capacidades. También puede crear guías de inicio rápido. Considere buscar un experto en reuniones en cada sitio que pueda ayudar a otros a ponerse al día y empezar a usar los dispositivos.
