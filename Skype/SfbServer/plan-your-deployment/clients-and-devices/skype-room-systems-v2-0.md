---
title: Plan para salas de equipos de Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: En este artículo se explica las consideraciones de planeación relevantes para la implementación de salas de equipos de Microsoft, la próxima generación de sistemas de salón de Skype.
ms.openlocfilehash: 7de824eee31b29b4b229d7b4d1b8eb7d60f5a632
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013053"
---
# <a name="plan-microsoft-teams-rooms"></a>Planeación de salas de equipos de Microsoft

En este artículo se presenta un enfoque end-to-end para la planeación, la entrega y salones de los equipos operativos de Microsoft como parte de su estrategia de salas de conferencia y reunión general.

Encontrará información debajo que cubren el enfoque recomendado y las decisiones clave que debe tomar, con vínculos a información técnica auxiliar de planificación. Se recomienda que revise las secciones del Plan, implementar y administrar incluso si totalmente ya está implementado.

## <a name="overview-of-microsoft-teams-rooms"></a>Información general de las salas de equipos de Microsoft

Salones de los equipos de Microsoft proporciona una experiencia de reunión completa que combine el uso compartido del contenido, audio y vídeo de alta definición a las reuniones de todos los tamaños de ponerse a trabajar pequeñas áreas para salas de conferencias de gran tamaño.

![Una consola, un micrófono y una pantalla grande montado en la pared de la sala de conferencia ilustran los elementos de una configuración de ejemplo de salas de equipos de Microsoft.] (../../media/room-systems-image1.png "Una consola, un micrófono y una pantalla grande montado en la pared de la sala de conferencia ilustran los elementos de una configuración de ejemplo de salas de equipos de Microsoft.")

[Ayuda de salas de equipos de Microsoft](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) es un recurso excelente para obtener más información acerca de los salones de los equipos de Microsoft y cómo puede agregar valor como parte de su implementación. Además, se recomienda Mire este [vídeo de información general](https://youtu.be/tNey5KZVCl0). 

## <a name="microsoft-teams-rooms-components"></a>Componentes de salas de equipos de Microsoft

Salones de los equipos de Microsoft incluye los siguientes componentes clave para proporcionar una experiencia de usuario excelente:

- Panel de control de pantalla táctil
- COMPUTE
- Aplicación de salas de equipos de Microsoft
- Acoplar/extensor
- Dispositivos periféricos (cámara, micrófono, altavoz)
- Pantallas externas (máximo de dos)
- Entrada HDMI

Puede adquirir estos componentes como preinstalados paquetes desde un número de proveedores, o puede comprar individualmente los componentes admitidos siguiendo los [requisitos documentan en este artículo](requirements.md).

También, además de la combinación de acoplar / Surface Pro, puede comprar salones de los equipos de Microsoft con el panel de control de pantalla táctil, compute, acoplar y clave dispositivos periféricos integrados. 

Normalmente, los paquetes y las unidades integradas incluyen software preinstalado, mientras que si comprar componentes admitidos por separado para los sistemas Surface Pro, necesitará instalar el software. Para obtener instrucciones, vea [este artículo sobre la instalación de software en los dispositivos](../../deploy/deploy-clients/room-systems-scale.md). 

Puede implementar Microsoft salones de los equipos con los equipos, Skype para profesionales en línea o Skype para las implementaciones empresariales de híbrida o local.  Vea [Salones de licencias de los equipos de Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) para obtener información sobre las licencias necesarias.

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Va a implementar los salones de los equipos de Microsoft en su organización? </li><li>¿Cómo va a adquirir los sistemas de salas de equipos de Microsoft: agrupado, como componentes separados, o bien como una unidad integrada?</li></ul> |
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes | <ul><li>Identificar quién emprenderá las actividades clave en toda la implementación.</li><li>Revise las salas de reuniones tiene (y va a configurar) para comprender donde desea implementar Microsoft salones de los equipos y los dispositivos periféricos que serían apropiado para el tamaño de la sala.</li></ul> |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quién emprenderá las actividades clave en toda la implementación

Use el enfoque se ilustra a continuación le guiarán a través de la implementación y personalizar los resultados de ejemplo proporcionados a lo largo de estos artículos, según sea necesario para la organización.

Comience con la descripción de salones de qué conferencia tienen y qué proceso de previsión funcionaría mejor para usted en el futuro, a continuación, desplazarse por selección y obtención el equipo necesario, preparación de los sitios, configuración e implementación de su servicio, administración de cambios y adopción de usuario y el desarrollo de las operaciones y los procedimientos de mantenimiento.

![Comience con la descripción de lo que tiene y previsión qué funcionaría mejor para usted, a continuación, mover a través de la selección y obtención de los equipos que necesita, preparación de los sitios, configuración e implementación de su servicio, administración de adopción de cambio y el usuario, y desarrollo de las operaciones y los procedimientos de mantenimiento.] (../../media/room-systems-image2.png "Comience con la descripción de lo que tiene y previsión qué funcionaría mejor para usted, a continuación, mover a través de la selección y obtención de los equipos que necesita, preparación de los sitios, configuración e implementación de su servicio, administración de adopción de cambio y el usuario, y desarrollo de las operaciones y los procedimientos de mantenimiento.")

Es posible que necesite coordinar estas actividades a través de varios equipos. Se proporciona una visión general de las actividades principales que deben abarcar así como sugerencias para los equipos que son normalmente implicados en la implementación y administración de sistemas de salas de conferencia, para ayudarle a decidir que necesita para que funcione con.

| Tarea                       | Quién puede realizar la tarea           | Asignado a | Vínculos a este contenido |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salones de inventario            | Instalaciones / equipo AV / equipo de proyecto de TI |             | [Inventario de sala y planeación de capacidad](#room-inventory-and-capability-planning)        |
| Plan de capacidades          | TI equipo del proyecto                        |             | [Inventario de sala y planeación de capacidad](#room-inventory-and-capability-planning)                       |
| Selección de dispositivos           | TI equipo del proyecto o equipo AV              |             | [Selección de dispositivos](#device-selection)                      |
| Compras                | TI equipo del proyecto o equipo AV              |             | [Compras](#procurement)                      |
| Preparación del sitio             | Instalaciones / equipo AV / equipo de proyecto de TI |             | [Preparación del sitio](../../deploy/deploy-clients/room-systems-v2.md#site-readiness)                      |
| Preparación del servicio          | TI equipo del proyecto                        |             | [Preparación del servicio](../../deploy/deploy-clients/room-systems-v2.md#service-readiness)                      |
| Configuración              | TI equipo del proyecto                        |             | [Configuración e implementación](../../deploy/deploy-clients/room-systems-v2.md#configuration-and-deployment)                      |
| Deployment                 | Instalaciones / equipo AV / equipo de proyecto de TI |             | [Lista de comprobación de implementación](../../deploy/deploy-clients/console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adopción                   | Instalaciones / equipo AV / equipo de proyecto de TI |             | [Adopción](#plan-for-adoption-and-change-management)                      |
| Mantenimiento y funcionamiento | Equipo de AV / equipo de proyecto de TI              |             | [Introducción a la administración](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventario de sala y planeación de capacidad

El primer paso consiste en realizar un inventario de reunión existente y salas de conferencias para comprender su entorno, el tamaño de la sala, el diseño y el propósito y para identificar las capacidades que desee cada sala en el ámbito que se debe tener en el futuro, como qué más completos de la organización las capacidades de colaboración se habilitará en la sala. 

Después de crear un inventario de los equipos y las capacidades de cada sala existente, los requisitos para esa sala fuente en la selección de dispositivo de planeación crear una solución de conferencias de gran versatilidad. Las modalidades (audio, vídeo) necesarias para cada sala, además de tamaño de la sala y propósito — todos desempeñan un rol importante en decidir cuál es la solución más adecuada para cada sala. 

Como parte de la detección, lo s clave a tener en cuenta el diseño y acústica de la sala. Por ejemplo, compruebe que las sillas en la sala no puede bloquear la vista de la cámara. Compruebe que no tiene la sala de eco excesivo o ruido aire acondicionado, y que tiene suficiente capacidad para las pantallas y salas de equipos de Microsoft. Existen muchos factores a tener en cuenta que podrán realizar de aviso en su equipo audiovisual (AV) o socio. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Qué salones están en el ámbito de esta implementación?</li><li>¿Los sitios que están en el ámbito de la implementación?</li><li>¿Inventario de las salas que realizará la reunión?</li></ul> |
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Revise las salas de ámbito y definir configuraciones de salas de equipos de Microsoft para ellos.</li></ul>|

_Inventario de sala de reunión o conferencia de ejemplo_

| Sitio  | Nombre del salón | Tipo de salón | Número de personas  | ¿En el ámbito? | Capacidades de salón actual       | Capacidades de sala futuras     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| HQ de Londres | Curie         | Medio        | 6&ndash;12                  | Sí          | Manos libres                        | 1 pantalla, audio y vídeo plus presentación<br>Acceso de RTC |
| HQ Sidney | Hill          | Grande         | 12&ndash;16                 | Sí          | Heredado AV unidad, 1 pantalla y cámara | 2 pantallas, audio y vídeos plus presentación<br>Acceso de RTC |

**Sugerencia pro** – si tiene muchos sitios de inventario, es posible que desee descargar y usar la [implantación de sitio y planificación de la migración - cuestionario de sitio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_15).

## <a name="device-selection"></a>Selección de dispositivos 

Evaluar qué solución de salas de equipos de Microsoft es el más adecuado para cada sala en función de las capacidades futuras que desee de la sala. Decidir qué dispositivos periféricos AV son el mejor ajuste, según el tamaño de la sala y diseño. 

Para obtener instrucciones para el tipo de sistema y los dispositivos periféricos por tipo de sala y el tamaño, vea el artículo de [los requisitos de salas de equipos de Microsoft](requirements.md) . 

Según el proveedor que lo prefiere, use la información proporcionada en el artículo de los requisitos para definir la configuración de dispositivo periférico admitidos por tipo de habitación y salas de equipos de Microsoft y usar como plantilla para la implementación. 

**Sugerencia pro** – no es posible aplicables para la implementación de algunos tipos de sala.

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Desde el inventario, que son tipos de salas en el ámbito de la implementación?</li><li>¿Los sistemas que va a implementar para cada tipo de salón?</li></ul>|
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empieza a recopilar material operativa clave para los sistemas elegidos y haga participar a su equipo de compras.</li></ul>|

_Plantilla de implementación de ejemplo salones de los equipos de Microsoft para su organización_

| **Tipo y tamaño de la sala** | **Número de personas**  | **Sistema de salas de equipos de Microsoft** | **Dispositivos periféricos**  | **Display(s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Enfoque 10' por 9'      | 2&ndash;4                   |                                  |                         |                 |
| Pequeña 16' por 16'     | 4&ndash;6                   |                                  |                         |                 |
| Medio 18' por 20'    | 6&ndash;12                  |                                  |                         |                 |
| Grandes 15' por 32 º     | 12&ndash;16                 |                                  |                         |                 |

**Sugerencia Pro:** Ahora es un buen momento para iniciar la recopilación de información acerca de la solución de salas de equipos de Microsoft que haya elegido. Se recomienda que trabaje con su proveedor para explicar la finalización de la plantilla de diseño para capturar la información que va a ser relevante para la implementación; puede [descargar esta plantilla útil](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_11) desde MyAdvisor. 

## <a name="procurement"></a>Compras 

Puede adquirir el sistema elegido como un paquete o una solución integrada a través de los socios de dispositivo. También puede adquirir un muelle de dispositivo de socio y preparar su propia solución de salas de equipos de Microsoft mediante el uso de un dispositivo Surface Pro y existentes, _admite_ AV dispositivos periféricos. 

Puede adquirir salas de equipos de Microsoft desde un número de socios que se enumeran en el [artículo de los requisitos](requirements.md). Visite los sitios Web de los asociados de negocios para obtener más información acerca de estas soluciones y opciones de adquisiciones. 

Dependiendo de su escala de implementación y el enfoque, podría decidir tener las salas de los equipos de Microsoft y admite dispositivos periféricos que se van a enviar a una ubicación central para la configuración inicial y asignación. Esto puede resultar un buen método para una implementación por fases en muchos sitios. O bien, es posible que elija Enviar los paquetes directamente a los sitios. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Se incluyen los componentes directamente a un sitio o a una instalación de almacenamiento provisional?</li><li>¿Quién va a administrar las instalaciones de almacenamiento provisional (si decide utilizar uno)?</li></ul>|
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Planeación de operaciones.</li><li>Planeación de adopción y administración de cambios.</li></ul>|

## <a name="plan-for-operations"></a>Planeación de operaciones de 

La organización debe ejecutar las tareas de supervisión, administración y gestión de forma continuada y la clave de TI para que se lleven a cabo estas tareas en su implementación de acuerdo. 

Muchas organizaciones tienen un socio que administra sus dispositivos y salas de conferencias o un equipo de AV. Este equipo debe estar implicado en quién va a administrar los dispositivos de salas de equipos de Microsoft en el futuro para supervisar el rendimiento e implementar las actualizaciones de software y revisiones de acuerdo. 

Tenga en cuenta qué cola del departamento de soporte técnico que enrutar llamadas relacionados con el Rooms֪ de los equipos de Microsoft y proporcionar preguntas más frecuentes para el equipo del departamento de soporte técnico por lo que pueden mejor comprender el uso de salas de equipos de Microsoft y la clave de solución de problemas de pasos que pueden llevar a cabo. Un buen punto de partida para estas preguntas más frecuentes es la [Ayuda del usuario](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) y el [conocido lista de problemas](../../manage/skype-room-systems-v2/known-issues.md).

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir quién va a administrar salones de los equipos de Microsoft.</li><li>Decidir con qué cola del departamento de soporte técnico para enrutar llamadas relacionadas con salas de equipos de Microsoft – a.</li></ul>|
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepárese para las cuentas de host. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planeación de adopción y administración de cambios

Sistemas de salas de equipos de Microsoft presentan las nuevas capacidades a los usuarios. Es importante que reconocer que se trata de un cambio para los usuarios, y debe asegurarse de que la campaña identifica las ventajas que del nuevo sistema tendrá para los usuarios y los clientes potenciales de los puntos de conversación clave se pueden usar para explicar con sus equipos. 

Considere la posibilidad de programar póster y eventos de show-and-tell cae en cada sitio para informar a los usuarios de las nuevas capacidades. También puede crear en la sala "guías de inicio rápido." Considere la posibilidad de buscar a un experto de las reuniones en cada sitio que puede ayudar a otros a ponerse en marcha y empezar a usar los dispositivos.
