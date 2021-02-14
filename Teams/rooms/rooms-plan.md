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
description: En este artículo se explican las consideraciones de planificación relevantes para implementar Salas de Microsoft Teams, la próxima generación de Sistemas de salas de Skype.
ms.openlocfilehash: ccc24aea1a45d2aa75c3b1a5de668b520483c2bd
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662475"
---
# <a name="plan-microsoft-teams-rooms"></a>Planear salas de Microsoft Teams

Este artículo presenta un enfoque integral para planear, ofrecer y operar salas de Microsoft Teams como parte de la estrategia general de las salas de reuniones y de conferencias.

A continuación encontrará información de planificación que cubre el enfoque recomendado y las decisiones clave que debe tomar, con vínculos a información técnica de soporte técnico. Le recomendamos que revise las secciones Planear, Implementar y Administrar, incluso si ya está totalmente implementado.

## <a name="overview-of-microsoft-teams-rooms"></a>Información general de salas de Microsoft Teams

Las salas de Microsoft Teams proporcionan una experiencia de reunión completa que ofrece vídeo HD, audio y uso compartido de contenido a reuniones de todos los tamaños, desde pequeñas áreas de reunión hasta salas de conferencias grandes.

![Una consola, un micrófono y una pantalla grande instalada en la pared de una sala de conferencias ilustran los elementos de un ejemplo de configuración de salas de Microsoft Teams.](../media/room-systems-image1.png "Una consola, un micrófono y una pantalla grande instalada en la pared de una sala de conferencias ilustran los elementos de un ejemplo de configuración de salas de Microsoft Teams.")

[La ayuda de salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) es un gran recurso para obtener más información sobre salas de Microsoft Teams y cómo puede agregar valor como parte de la implementación. Además, le recomendamos que consulte este vídeo [de información general.](https://youtu.be/tNey5KZVCl0) 

## <a name="microsoft-teams-rooms-components"></a>Componentes de Salas de Microsoft Teams

Salas de Microsoft Teams incluye los siguientes componentes clave para ofrecer una excelente experiencia de usuario:

- Panel de control de pantalla táctil
- Calcular
- Aplicación Salas de Microsoft Teams
- Base/extender
- Dispositivos periféricos (cámara, micrófono, altavoz)
- Pantallas externas (máximo de dos)
- Entrada HDMI

Puede adquirir estos componentes como paquetes preinstalados de varios proveedores o puede comprar los componentes compatibles individualmente siguiendo los requisitos documentados en [este artículo.](requirements.md)

Además de la combinación de Surface Pro y base, también puede comprar salas de Microsoft Teams con el panel de control de pantalla táctil, el proceso, la base y los dispositivos periféricos clave integrados. 

Normalmente, los paquetes y las unidades integradas incluyen software preinstalado, mientras que si compras los componentes compatibles individualmente para los sistemas Surface Pro, tendrás que instalar el software. Para obtener instrucciones, consulte [este artículo sobre la instalación de software en dispositivos.](rooms-scale.md) 

Puede implementar salas de Microsoft Teams con Microsoft Teams, Skype Empresarial Online o con implementaciones híbridas o locales de Skype Empresarial.  Consulte la actualización [de licencias de salas de reuniones de Teams](rooms-licensing.md) para obtener información sobre las licencias necesarias.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Implementará Salas de Microsoft Teams en su organización? </li><li>¿Cómo adquirirá sus sistemas de salas de Microsoft Teams, agrupados, como componentes independientes o como una unidad integrada?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes | <ul><li>Identifique quién realizará las actividades clave durante la implementación.</li><li>Revise las salas de reuniones que tiene (y planee configurarlas) para comprender dónde quiere implementar salas de Microsoft Teams y los dispositivos periféricos que serían adecuados para el tamaño de la sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quién realizará las actividades clave durante la implementación

Use el método que se muestra a continuación para guiarlo a través de la implementación y personalizar los resultados de ejemplo proporcionados a lo largo de estos artículos según sea necesario para su organización.

Comience por comprender qué salas de conferencias tiene y ver cuál sería mejor para usted en el futuro, luego pase por seleccionar y adquirir el equipo que necesita, preparar los sitios, configurar e implementar el servicio, administrar la adopción del cambio y el usuario, y desarrollar operaciones y procedimientos de mantenimiento.

![Comience con la comprensión de lo que tiene y con la visión de lo que le funcionaría mejor, después pase por seleccionar y adquirir el equipo que necesita, preparar los sitios, configurar e implementar el servicio, administrar la adopción del cambio y el usuario, y desarrollar procedimientos de mantenimiento y operaciones.](../media/room-systems-image2.png "Comience con la comprensión de lo que tiene y con la visión de lo que le funcionaría mejor, después pase por seleccionar y adquirir el equipo que necesita, preparar los sitios, configurar e implementar el servicio, administrar la adopción del cambio y el usuario, y desarrollar procedimientos de mantenimiento y operaciones.")

Es posible que necesite coordinar estas actividades en varios equipos. Proporcionamos una vista de alto nivel de las actividades principales que debe cubrir, así como sugerencias para los equipos que suelen participar en la implementación y la administración de sistemas de salas de conferencias, para ayudarle a decidir con quién tiene que trabajar.

| Tarea                       | Quién podría realizar la tarea           | Asignado a | Vínculos a este contenido |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salas de inventario            | Instalaciones / equipo de AV / equipo de proyecto de IT |             | [Inventario de sala y planificación de funciones](#room-inventory-and-capability-planning)        |
| Capacidades del plan          | Equipo de proyecto de IT                        |             | [Inventario de sala y planificación de funciones](#room-inventory-and-capability-planning)                       |
| Selección de dispositivos           | Equipo de proyecto de IT /equipo de AV              |             | [Selección de dispositivos](#device-selection)                      |
| Compra                | Equipo de proyecto de IT /equipo de AV              |             | [Compra](#procurement)                      |
| Disponibilidad del sitio             | Instalaciones / equipo de AV / equipo de proyecto de IT |             | [Disponibilidad del sitio](rooms-deploy.md#site-readiness)                      |
| Preparación del servicio          | Equipo de proyecto de IT                        |             | [Preparación del servicio](rooms-deploy.md#service-readiness)                      |
| Configuración              | Equipo de proyecto de IT                        |             | [Configuración e implementación](rooms-deploy.md#configuration-and-deployment)                      |
| Deployment                 | Instalaciones / equipo de AV / equipo de proyecto de IT |             | [Lista de comprobación de implementación](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adopción                   | Instalaciones / equipo de AV / equipo de proyecto de IT |             | [Adopción](#plan-for-adoption-and-change-management)                      |
| Mantenimiento y funcionamiento | Equipo de AV/ equipo de proyecto de IT              |             | [Introducción a la administración](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventario de sala y planificación de funciones

El primer paso es realizar un inventario de las salas de reuniones y conferencias existentes de su organización para comprender su entorno, tamaño de sala, diseño y finalidad, y para identificar las capacidades que desea que cada sala dentro del ámbito tenga en el futuro, por ejemplo, qué capacidades de colaboración más completas se habilitarán en la sala. 

Después de crear un inventario del equipamiento y las capacidades de cada sala existente, los requisitos para esa fuente de sala dentro de la planificación de la selección de dispositivos para crear una solución de conferencias enriquez. Las modalidades (audio, vídeo) necesarias para cada sala, además del tamaño de la sala y la finalidad, desempeñan un papel importante a la hora de decidir qué solución es la más adecuada para cada sala. 

Como parte de la detección, es esencial tener en cuenta la acústico y el diseño de las sala. Por ejemplo, compruebe que las sillas de la sala no bloqueen la vista de cámara. Compruebe que la sala no tenga eco excesivo o aire ruidoso y que tiene suficiente energía para las pantallas y salas de Microsoft Teams. Hay muchos factores a tener en cuenta que su equipo de audio visual (AV) o su socio podrán avisar. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Qué salas están dentro del ámbito de esta implementación?</li><li>¿Qué sitios están dentro del ámbito de la implementación?</li><li>¿Quién realizará el inventario de las salas de reuniones?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Revise los salas en el ámbito y defina las configuraciones de salas de Microsoft Teams para ellos.</li></ul>|

_Ejemplo de inventario de salas de reuniones o conferencias_

| Sitio  | Nombre del salón | Tipo de sala | Número de personas  | ¿Dentro del ámbito? | Funcionalidades de sala actuales       | Capacidades futuras de las sala     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| London HQ | Curie         | Medio        | 6 &ndash; 12                  | Sí          | Manos libres                        | 1 pantalla, audio y vídeo más presentación<br>Acceso RTC |
| Sydney HQ | Hill          | Grande         | 12 &ndash; 16                 | Sí          | Unidad AV heredada, 1 pantalla y cámara | 2 pantallas, audio y vídeo más presentación<br>Acceso RTC |

## <a name="device-selection"></a>Selección de dispositivos 

Evalúe qué solución de Salas de Microsoft Teams es la más adecuada para cada sala en función de las capacidades futuras que quiera para la sala. Decida qué dispositivos periféricos AV son los más adecuados, según el tamaño de la sala y el diseño. 

Para obtener instrucciones sobre el tipo de sistema y los dispositivos periféricos, según el tipo de sala y el tamaño, consulte el artículo sobre requisitos de salas [de Microsoft Teams.](requirements.md) 

Según el proveedor que prefiera, use la información que se proporciona en el artículo de requisitos para definir sus salas de Microsoft Teams y la configuración admitida del dispositivo periférico por tipo de sala, y use esta como plantilla para su implementación. 

**Sugerencia:** es posible que algunos tipos de salón no sean aplicables a la implementación.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Del inventario, ¿qué tipos de salas están dentro del ámbito de la implementación?</li><li>¿Qué sistemas implementará para cada tipo de salón?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a recopilar el material operativo clave para los sistemas elegidos e interactúe con el equipo de compra.</li></ul>|

_Ejemplo de plantilla de implementación de Salas de Microsoft Teams para su organización_

| **Tamaño o tipo de sala** | **Número de personas**  | **Sistema de salas de Microsoft Teams** | **Dispositivos periféricos**  | **Pantallas** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Foco 10' por 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| 16' pequeño por 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| Medio 18' por 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| 15' grande por 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Sugerencia profesional :** Ahora es un buen momento para empezar a recopilar información sobre la solución de Salas de Microsoft Teams que ha elegido.

## <a name="procurement"></a>Compra 

Puedes adquirir tu sistema elegido como un paquete o una solución integrada a través de partners de dispositivos. También puede adquirir una base de dispositivos asociada y preparar su propia solución de Salas de Microsoft Teams mediante un dispositivo Surface Pro y dispositivos periféricos _AV_ compatibles existentes. 

Puede adquirir salas de Microsoft Teams de varios partners que aparecen en el artículo [de requisitos.](requirements.md) Visite los sitios web de los partners para obtener más información sobre estas soluciones y opciones de compra. 

Según la escala y el enfoque de implementación, es posible que decida tener salas de Microsoft Teams y dispositivos periféricos admitidos enviados a una ubicación central para la configuración inicial y la asignación. Este podría ser un buen enfoque para una implementación por fases en muchos sitios. O bien, puedes enviar los paquetes directamente a tus sitios. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Enviará los componentes directamente a un sitio o a una instalación de ensayo?</li><li>¿Quién administrará las instalaciones de ensayo (si decide usar una)?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Planifique para operaciones.</li><li>Planee la adopción y la administración de cambios.</li></ul>|

## <a name="plan-for-operations"></a>Plan para operaciones 

Su organización debe ejecutar las tareas de supervisión, administración y administración de forma continua y es clave acordar quién realizará estas tareas al principio de la implementación. 

Muchas organizaciones tienen un equipo de AV o un partner que administra sus salas de conferencias y dispositivos. Este equipo debe participar en la aceptación de quién administrará los dispositivos de Salas de Microsoft Teams en el futuro para supervisar el rendimiento e implementar las actualizaciones y revisiones de software. 

Tenga en cuenta a qué cola del departamento de soporte técnico dirigirá las llamadas relacionadas con Microsoft Teams Rooms֪ y proporcionará una pregunta frecuente al equipo del departamento de soporte técnico para que puedan comprender mejor cómo usar salas de Microsoft Teams y los pasos clave de solución de problemas que pueden realizar. Un buen punto de partida para estas preguntas más frecuentes es la [ayuda del usuario](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) y los problemas [conocidos.](known-issues.md)

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará salas de Microsoft Teams.</li><li>Decida a qué cola del departamento de soporte técnico quiere dirigir las llamadas relacionadas con salas de Microsoft Teams.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepárese para hospedar cuentas. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planear la adopción y la administración de cambios

Los sistemas de salas de Microsoft Teams presentan nuevas capacidades a los usuarios. Es importante que reconozca que va a ser un cambio para los usuarios y debe asegurarse de que su campaña identifica los beneficios que tendrá el nuevo sistema para sus usuarios y los puntos de conversación clave que pueden usar los responsables de la conversación para hablar con sus equipos. 

Considere la posibilidad de programar eventos de presentación y entrega y pósteres en cada sitio para informar a los usuarios de las nuevas capacidades. También puede crear "guías de inicio rápido" en la sala. Considere la posibilidad de encontrar a un campeón de reuniones en cada sitio que pueda ayudar a otros usuarios a estar al día y empezar a usar los dispositivos.
