---
title: Microsoft Teams actualizar de Skype para la empresa | Modos de coexistencia
author: lsomi
ms.author: lsomi
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Detalles de Skype para profesionales y Microsoft Teams opciones de coexistencia y modos y viajes de actualización a los equipos de Skype para la empresa con los escenarios de ejemplo.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bf81e18970366fee397504642b181f6e8c40add
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461615"
---
![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")

En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización. Antes de continuar, confirme que ha realizado las siguientes actividades:

- [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
- [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Elija su viaje por la actualización de Skype para la empresa a los equipos

Como un Skype existente para cliente comercial, la transición completa a los equipos puede tardar algún tiempo. Sin embargo, puede empezar a darse cuenta el valor de los equipos en la actualidad, permitiendo que los usuarios usen los equipos junto con Skype para la empresa. Dado que hay algunas de las funciones superpuestas entre las dos aplicaciones, se recomienda que revise la coexistencia disponible y actualizar los modos para ayudar a determinar qué ruta de acceso es la adecuada para su organización. Por ejemplo, puede optar por habilitar todas las cargas de trabajo en ambas soluciones sin interoperabilidad. O bien, es posible que decida administrar la experiencia del usuario, introduciendo gradualmente capacidades de los equipos o mediante la identificación de grupos de usuarios para las capacidades de select, hasta que esté lista para actualizar todos los usuarios a los equipos de la organización. Use el resultado de la prueba piloto para ayudar a evaluar el viaje por la actualización a la derecha para su organización.

> [!IMPORTANT]
> En este artículo se describe los distintos modos que permiten administrar qué modalidades de Skype para la empresa y los equipos están disponibles para los usuarios. Al igual que con cualquier implementación, recomendamos encarecidamente realizar una [prueba piloto del plan previsto](pilot-essentials.md) con un grupo seleccionado de usuarios antes de actualizar la organización a los equipos. Recuerde, introducción a la nueva tecnología puede ser perjudiciales para los usuarios. Tardar en evaluar la preparación del usuario e implementar un plan de aprendizaje antes de implementar cualquiera de los modos en que se describen en este documento y la comunicación.

## <a name="upgrade-journey-building-blocks"></a>Actualización de bloques de creación de viaje

Para preparar formalmente la organización para su viaje a los equipos, es necesario para empezar a planear para los escenarios de actualización que finalmente permitirá a su organización Aceptar completamente los equipos como las comunicaciones única y la solución de colaboración.

Para ayudar a guiar el proceso de toma de decisiones, debe familiarizarse con los distintos modos, conceptos y terminología relevante para la actualización de Skype para la empresa a los equipos. Para obtener más información, vea [equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](https://aka.ms/SkypeToTeams-Coexist)

Cuando algunos de los usuarios están listos para usar sólo los equipos para sus comunicaciones diarias y colaboración las necesidades, puede empezar a actualizar estos usuarios a los equipos mediante la habilitación de modo de **Equipos sólo** para ellos.

Si no es factible para toda la organización mover a los equipos, puede iniciar mediante la implementación piloto equipos junto con Skype para la empresa en modo de coexistencia de **Islas** . A medida que los modos de coexistencia adicionales, (es decir, **Skype para la empresa con la colaboración de equipos** y **Skype para la empresa con la colaboración de los equipos y las reuniones**), se progresivamente completamente disponibles en los próximos meses, también puede iniciar de forma totalmente adoptando los equipos como una solución de colaboración de grupo, en primer lugar, manteniendo Skype para la empresa como solución de comunicaciones unificadas de su organización. Que es la ruta de acceso recomendado de Microsoft para los clientes que usen Skype para clientes y servidores de negocio (local o híbrida) con complejidad significativo cuya trayectoria a los equipos incluirá un período de coexistencia de tipo long.

![Captura de pantalla de actualización bloques de creación de Skype para la empresa a los equipos, que se compone de Skype para la empresa con la colaboración de equipos&ndash;modo exclusivo, Skype para la empresa con la colaboración de equipos y modo de reuniones, modo de islas, modo de solo los equipos y Skype para Business&ndash;sólo modo.](media/upgrade_journeys_building_block.png)

En la siguiente tabla se compara los modos de actualización y coexistencia.

|Modo |Situación |Uso recomendado |Ventajas |Advertencias |
|---|---|---|---|---|
|Islas |Skype más pequeño o más sencilla para la implementación empresarial<br><br>Capacidad y su deseo de que administrar cierta complejidad a corto plazo para mover a los equipos con mayor rapidez |Vaya a la experiencia completa de los equipos tan pronto como sea posible<br><br>Realizar una prueba de concepto (PoC) de los equipos<br><br>Ruta de actualización recomendada para las organizaciones que adoptadas Skype para profesionales en línea |Simple operar<br><br>Mejor experiencia de los equipos por adelantado para todas las capacidades de |Requiere la comunicación del usuario buena para evitar confusiones y al uso de unidad hacia los equipos<br><br>Estrategia de salida requiere que los usuarios han adoptado totalmente los equipos antes de iniciar la actualización a los equipos sólo fase<br><br>No hay interoperabilidad para los usuarios en el modo de islas; También ningún federación desde los equipos cuando Skype del usuario para la cuenta de empresa está hospedado local|
|Skype para la empresa con la colaboración de equipos |Skype para la implementación de negocio con los requisitos que aún no se cumple por parte de equipos (por ejemplo, cumplimiento de normas avanzada)<br><br>Necesidad a largo plazo de o compromiso de Skype para la empresa|Iniciar la adopción de los equipos rápidamente, centrándose en primer lugar en colaboración en grupo<br><br>Desea mantener todas las cargas de trabajo de comunicaciones unificadas en Skype para la empresa por ahora<br><br>Se recomienda usar como punto de partida para iniciar su viaje desde en local (o híbrida) de organización Skype para la empresa|No hay capacidades superpuestas entre los equipos y Skype para la empresa<br><br>Mensajería instantánea chat y programación de reuniones residirán en Skype para la empresa (vinculada a llamar a)<br><br>Interoperabilidad con los usuarios de los equipos sólo|
|Skype para la empresa con la colaboración de los equipos y las reuniones |Skype para la implementación de negocio con un uso importante de enterprise voice y los requisitos que aún no se cumplen por parte de equipos de llamada<br><br>Necesidad a largo plazo de o compromiso de Skype para la empresa<br><br>Es posible que esté usando un servicio de reunión de terceros|Iniciar rápidamente, adopción de los equipos va más allá de colaboración en grupo<br><br>Mejorar la experiencia de las reuniones de los usuarios<br><br>Uso recomendado para en organizaciones locales que desean sacar partido de las reuniones de los equipos antes de que se está listo para actualizar totalmente (generalmente debido a Enterprise Voice local). |No hay capacidades superpuestas<br><br>Reuniones superior en los equipos. Plataforma de esta guía, experiencia de usuario y entre las características, la calidad y la confiabilidad<br><br>Experiencias de "Mejor juntos" entre los equipos y de Skype para la empresa<br><br>Usuarios de interoperabilidad en los equipos sólo.|Mensajería instantánea y charla residirán en Skype para la empresa (vinculada a llamar a)|
|Sólo los equipos |Algunos usuarios necesitan permanecer en Skype para la empresa<br><br>Está actualizando su Skype para usuarios profesionales en línea para los equipos mientras mantiene Skype para la empresa local a los usuarios en Skype para Business Server<br><br>Es posible que ya ha implementado los usuarios en el modo de islas y está listo para retirar Skype para la empresa para grupos de usuarios |Reducir los costos de la variable en Skype para la empresa (las operaciones del servidor local, el contrato de subcontratación etc.)<br><br>Vaya a la experiencia completa de los equipos tan pronto como sea posible, para al menos algunos usuarios|Limita la confusión del usuario al proporcionar un solo cliente para trabajar con la interoperabilidad con los usuarios de Skype para sólo empresarial, Skype para empresarial con colaboración de equipos, Skype para la empresa con la colaboración de los equipos y las reuniones|Interoperabilidad sólo es compatible con chat básica y realizar llamadas entre Skype para profesionales y los equipos y escalación interoperabilidad escenarios de uso compartido de escritorio y chat de varios participantes y llamar al método|
|Skype para la empresa solo |Algunos usuarios necesitan permanecer en Skype para la empresa<br><br>|Limita la confusión de los usuarios proporcionando a trabajar con un único cliente<br><br>Usuario todavía puede participar en las reuniones de los equipos que lo invita a|Continuar cumplir los requisitos de negocio que actualmente sólo pueden cumplir por Skype para la empresa<br><br>Interoperabilidad con los usuarios de los equipos sólo|Interoperabilidad sólo es compatible con chat básica y realizar llamadas entre Skype para profesionales y los equipos y escalación interoperabilidad escenarios de uso compartido de escritorio y chat de varios participantes y llamar al método|

## <a name="upgrade-journeys"></a>Actualización de viajes

Puede tardar varios enfoques para la actualización de Skype para la empresa, ya sea en línea o local, para los equipos:

- En un viaje de actualización directo, en primer lugar implementar los equipos junto con Skype para la empresa en el modo de **Islas** como parte de evaluación y adopción temprana y, a continuación, actualice los usuarios al modo de **Sólo los equipos** con el objetivo de retirada rápidamente de Skype para la empresa desde el entorno para todos los usuarios de la organización. Este es el viaje recomendado para los clientes en línea de negocio de Skype, a menos que sean que se trate de que sus usuarios se confundirse con tener dos herramientas para realizar la misma acción (chat, llamada, la programación de la reunión).
- Un viaje de actualización gradual ofrece una coexistencia específico y el modo de actualización a un grupo específico de usuarios (también denominado un *grupo de edad*), según sus requisitos de colaboración y comunicaciones. Con el tiempo, toda la organización puede convergen en los equipos sólo se utiliza y finalmente reemplace Skype para la empresa. Sin embargo, si su organización tiene razones empresariales convincentes para mantener Skype para la empresa, como una dependencia en una solución basada en Unified Communications API administrada de UCMA que se integra con aplicaciones de línea de negocio, o de una solución de datos confidenciales actualmente disponibles para Skype para la empresa sólo, o una implementación de Enterprise Voice compleja que tardará tiempo para actualizar a **Sólo los equipos**, puede actualizar una parte de los usuarios al modo de **Sólo los equipos** conservando Skype para los usuarios de negocio en uno de los modos de coexistencia para una parte de la población de usuarios. Viaje de actualización gradual es el enfoque recomendado para local (y híbrido) a los clientes empezando por Skype para la empresa con el modo de coexistencia de colaboración de equipos y mover desde allí a modo de equipos sólo cuando se cumplen los requisitos para los usuarios (posiblemente a través del Skype para la empresa con el modo de coexistencia de colaboración de equipos y las reuniones).

> [!IMPORTANT]
> Para ambos tipos de viaje de actualización, si la organización está actualmente una Skype para implementación sólo, la empresa local necesita para empezar a planear implementar Skype para entornos híbridos de negocio antes de actualizar a los usuarios al modo de **Sólo los equipos** . Esto también ayudará a facilitar la interoperabilidad con los equipos.
>
> Use [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para guiar su Skype para implementación híbrida de negocio.

> [!NOTE]
> Modo de **Equipos sólo** requiere que los usuarios que forman parte de las cohortes estar alojado en Skype para profesionales en línea y se requiere para facilitar una relación híbrida entre su Skype para la implementación local de empresa y su Skype para inquilino empresarial en línea la interoperabilidad entre Skype para la empresa y los equipos. Debe completarse el movimiento a Skype para empresarial en línea para los usuarios que forman parte de la cohortes antes de que se está actualizado al modo de **Sólo los equipos** . Skype para Business Server 2019 y Skype para Business Server 2015 con la actualización de CU8 pueden simplificar la mecánica de actualización de usuarios locales a los equipos mediante la administración de la migración de Skype para profesionales en línea y actualización de los usuarios a modo de **Sólo los equipos** en un solo paso .

### <a name="direct-upgrade-journey"></a>Viaje actualización directa

El viaje de actualización directo se ilustra en el siguiente diagrama.

![Una captura de pantalla del viaje actualización directo. Todos los usuarios inicialmente usa los equipos en modo de islas, a continuación, realizar la transición al modo de sólo los equipos, con el estado final de toda la organización actualizado a los equipos.](media/upgrade_journey_direct_upgrade.png)

Los equipos se implementan en todos los usuarios de la organización y configurado en modo de **Islas** . Cuando la organización determina que los equipos está listo para cumplir con todas las comunicaciones y colaboración necesita, notificar a los usuarios y actualizarlas a modo de **Sólo los equipos** . En ese momento, puede ser retirado Skype para la empresa desde el entorno.

### <a name="gradual-upgrade-journey"></a>Viaje de actualización gradual

En el siguiente diagrama se muestra un ejemplo de un viaje de actualización gradual.

![En el viaje de actualización gradual, las cohortes de usuarios usa inicialmente los equipos en el modo de islas para la evaluación y, a continuación, en una gran variedad de modos de actualización para la adopción temprana, codo con codo con Skype para la empresa. Algunos transición las cohortes al modo de sólo los equipos, mientras se mantiene un grupo de usuarios con Skype para la empresa con la colaboración de equipos y el modo de las reuniones.](media/upgrade_journey_gradual_upgrade.png)

Los equipos se implementa en la organización en el modo de **Islas** para la evaluación y, a continuación, mover a diferente coexistencia y actualizar los modos para distintos grupos de usuarios. Por ejemplo, un grupo de usuarios puede habilitarse para el modo de **Islas** , otro habilitado para el modo de **Skype para la empresa con la colaboración de los equipos y las reuniones** , mientras un tercer grupo de usuarios podría estar habilitado inicialmente en **Skype para la empresa con los equipos colaboración sólo** modo.

Con el tiempo, se pueden actualizar grupos de usuarios a **Los equipos sólo** modo, seguido por el resto de la organización. Finalmente, estará lista para retirar Skype para la empresa y usar sólo los equipos de comunicaciones y colaboración, toda la organización o, si los requisitos empresariales exigen que se conserven Skype para la empresa para un grupo específico: la mayoría de los usuarios en el organización puede usar únicamente los equipos. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul> ¿Qué viaje por la actualización es adecuado para los requisitos empresariales de su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Siguiente paso</td><td><ul> Identificación de su modelo de implementación actual, escenarios de casos de uso y consideraciones clave para su organización le informará el viaje a los equipos que es más adecuado para su organización.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul> ¿Qué escenario de actualización es aplicable a su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul> Decidir la escala de tiempo de viaje de actualización de la organización en función de mensajería, las reuniones y llamar a los requisitos empresariales.<br><br> Decidir el trabajo adicional necesario para completar su viaje por la actualización.<br><br></ul></td></tr>
</table>

Una vez que se ha elegido el viaje de actualización mejor para su organización, [realizar la actualización a los equipos](https://aka.ms/SkypeToTeams-Upgrade).
