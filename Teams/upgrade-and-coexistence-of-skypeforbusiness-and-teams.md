---
title: Actualización de Microsoft Teams desde Skype empresarial | Modos, coexistencia
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Detalles de Skype empresarial y Microsoft Teams opciones y modos de coexistencia, y actualización de los viajes a los equipos de Skype empresarial con escenarios de ejemplo.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 362e973bee33b8e556a84c0f03fd54d649d9ab14
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "35535879"
---
![Actualizar diagrama de viaje, enfatizar implementación e implementación] (media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e") implementación

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Inventar a los participantes del proyecto](upgrade-enlist-stakeholders.md)
- [Definió el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [La coexistencia y la interoperabilidad de Skype para empresas y equipos](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Elegir el viaje de actualización de Skype empresarial a teams

De esta manera, Microsoft Teams reemplazará a Skype empresarial online, por lo que deberá planear Teams ahora para que esté listo.

Como cliente existente de Skype empresarial, la transición completa a teams puede llevar algún tiempo. Sin embargo, puede empezar a obtener el valor de Teams hoy, lo que permite a los usuarios usar Teams junto con Skype empresarial. Dado que hay alguna funcionalidad superpuesta entre las dos aplicaciones, le recomendamos que revise los modos disponibles de coexistencia y actualización para determinar qué ruta de acceso es adecuada para su organización. Por ejemplo, puede optar por habilitar todas las cargas de trabajo en ambas soluciones sin interoperabilidad. O bien, puede decidir administrar la experiencia del usuario, ya sea mediante la presentación gradual de las capacidades de Teams o la segmentación de grupos de usuarios para capacidades de selección, hasta que su organización esté lista para actualizar a todos los equipos. Use el resultado de su prueba piloto para evaluar el camino adecuado para la actualización de su organización.

> [!IMPORTANT]
> En este artículo se describen los distintos modos que le permiten administrar las modalidades de Skype empresarial y de los equipos disponibles para los usuarios. Al igual que con cualquier implementación, le recomendamos encarecidamente que [planee su plan previsto](pilot-essentials.md) con un grupo de usuarios seleccionado antes de actualizar su organización a teams. Recuerde que la presentación de nuevas tecnologías puede ser perjudicial para los usuarios. Tomarse el tiempo para evaluar la preparación de los usuarios e implementar un plan de comunicación y formación antes de implementar cualquiera de los modos descritos en el presente documento.

## <a name="upgrade-journey-building-blocks"></a>Actualizar los bloques de creación del viaje

Para preparar formalmente su organización para su viaje a Teams, debe comenzar a planear los escenarios de actualización que le permitirán a su organización adoptar completamente equipos como una única solución de comunicaciones y colaboración.

Para ayudarle en el proceso de toma de decisiones, familiarícese con los distintos modos, conceptos y terminología relacionados con la actualización de Skype empresarial a teams. Para obtener más información, consulte [Microsoft Teams y la coexistencia e interoperabilidad de Skype empresarial](https://aka.ms/SkypeToTeams-Coexist)

Cuando algunos de los usuarios están listos para usar solo equipos para las comunicaciones diarias y las necesidades de colaboración, puede empezar a actualizar estos usuarios a teams habilitando el modo **solo para equipos** .

Si no es factible que toda la organización se traslade a Teams, puede empezar por equipos de prueba piloto junto con Skype empresarial en modo de coexistencia de **islas** . Como los modos de coexistencia adicionales, (es decir, **Skype empresarial con la colaboración entre equipos** y **Skype empresarial con la colaboración y las reuniones**de Teams) están completamente disponibles en los próximos meses, también puede empezar a hacerlo por completo adoptar Teams como una solución de colaboración de grupo antes de mantener Skype empresarial como la solución de comunicaciones unificadas de su organización. Esta es la ruta recomendada por Microsoft para clientes que usan Skype empresarial Server (local o híbrida) y clientes con una gran complejidad cuya trayectoria a teams incluirá un período de coexistencia largo.

![Captura de pantalla de actualización de bloques de creación de Skype empresarial a teams] (media/upgrade_journeys_building_block.png "Captura de pantalla de la actualización de bloques de creación de Skype empresarial a equipos, que consta de Skype empresarial con&ndash;el modo solo de colaboración de Teams, Skype empresarial con el modo de colaboración y reuniones de Teams, modo islas, solo para equipos y Skype para Modo&ndash;de solo empresa.")

En la siguiente tabla se comparan los modos de coexistencia y actualización.

|Multimodo |Problema |Uso recomendado |Ofrece |ADVERTENCIAS |
|---|---|---|---|---|
|Logra |Implementación de Skype para empresas más pequeña o más sencilla<br><br>Capacidad y voluntad de administrar una complejidad a corto plazo para desplazarse a teams más rápidamente |Vaya a la experiencia completa de Teams lo antes posible<br><br>Realizar una prueba de concepto (PoC) de Teams<br><br>Ruta de actualización recomendada para las organizaciones que han adoptado Skype empresarial online |Funcionamiento sencillo<br><br>La experiencia de los equipos más rica en la parte delantera de todas las funciones |Requiere una buena comunicación de usuario para evitar confusiones y para impulsar el uso de equipos<br><br>La estrategia de salida requiere que los usuarios hayan adoptado los equipos por completo antes de iniciar la actualización a la fase solo de Teams.<br><br>No hay interoperabilidad para usuarios en modo islas; Además, no hay Federación de equipos cuando la cuenta de Skype empresarial del usuario está hospedada en local|
|Skype empresarial con colaboración de Teams |Implementación de Skype empresarial con requisitos que aún no se cumplen con Teams (por ejemplo, cumplimiento avanzado)<br><br>Necesidad o compromiso de Skype empresarial a largo plazo|Comienza la adopción de Teams rápidamente, centrándose primero en la colaboración de grupos<br><br>¿Desea mantener todas las cargas de trabajo de comunicaciones unificadas en Skype empresarial por ahora?<br><br>Uso recomendado como punto de partida para que la organización empiece su viaje desde las instalaciones locales (o híbridas) de Skype empresarial|No hay funcionalidades superpuestas entre Teams y Skype empresarial<br><br>La conversación de mensajería instantánea y la programación de reuniones residirán en Skype empresarial (ligadas a las llamadas).<br><br>Interoperabilidad con usuarios solo en Teams|
|Skype empresarial con colaboración y reuniones de Teams |Implementación de Skype empresarial con un uso significativo de telefonía y llamadas empresariales que aún no cumplen los equipos<br><br>Necesidad o compromiso de Skype empresarial a largo plazo<br><br>Podría estar usando un servicio de reuniones de terceros|Comenzar la adopción de Teams rápidamente, que va más allá de la colaboración de grupos<br><br>Mejorar la experiencia de las reuniones de los usuarios<br><br>Se recomienda usar para organizaciones locales que deseen aprovechar las reuniones de Teams antes de prepararse para la actualización completa (generalmente debido a la versión local de Enterprise Voice). |No hay funcionalidades superpuestas<br><br>Reuniones superiores en Teams. Guía básica de características, experiencia de usuario y plataforma cruzada, calidad y fiabilidad<br><br>Experiencias "mejores" entre Skype empresarial y Teams<br><br>Usuarios de interoperabilidad solo en Teams.|La mensajería instantánea y el chat residirán en Skype empresarial (vinculado a las llamadas).|
|Solo equipos |Teams solo es el destino final para todos los usuarios.<br><br>Algunos usuarios necesitan permanecer en Skype empresarial<br><br>Está actualizando sus usuarios de Skype empresarial online a teams a la vez que mantiene usuarios locales de Skype empresarial en Skype empresarial Server<br><br>Es posible que ya haya implementado usuarios en modo islas y esté listo para retirar Skype empresarial para grupos de usuarios |Reducir los costos variables en Skype empresarial (operaciones de servidor locales, contrato de outsourcing, etc.)<br><br>Vaya a la experiencia de Teams completa lo antes posible, al menos para algunos usuarios|Limita la confusión de usuarios al proporcionar a un solo cliente el trabajo con la interoperabilidad con usuarios de Skype empresarial solamente, Skype empresarial con la colaboración entre equipos, Skype empresarial con colaboración y reuniones de Teams|La interoperabilidad solo admite conversaciones y llamadas básicas entre Skype empresarial y Teams, y escenarios de escalado para el uso compartido de escritorio y llamadas y videollamadas de varios participantes|
|Solo para Skype empresarial |Algunos usuarios necesitan permanecer en Skype empresarial<br><br>|Limita la confusión del usuario proporcionando solo un cliente para trabajar con<br><br>El usuario puede seguir participando en las reuniones de Team a las que se les invita|Seguir cumpliendo con los requisitos empresariales que actualmente solo Skype empresarial puede cumplir<br><br>Interoperabilidad con usuarios solo en Teams|La interoperabilidad solo admite conversaciones y llamadas básicas entre Skype empresarial y Teams, y escenarios de escalado para el uso compartido de escritorio y llamadas y videollamadas de varios participantes|

## <a name="upgrade-journeys"></a>Actualizar viajes

Puede tomar varias estrategias para actualizar de Skype empresarial, ya sea en línea o local, a teams:

- En un viaje de actualización directa, implemente primero Teams junto con Skype empresarial en modo **islas** como parte de la evaluación y a la adopción temprana, y luego actualice los usuarios al modo **solo para equipos** con el objetivo de retirar rápidamente Skype empresarial de la entorno para todos los usuarios de la organización. Este es el camino recomendado para los clientes de Skype para empresas online, a menos que se preocupe de que sus usuarios tengan dos herramientas para realizar la misma acción (conversación, llamadas, programación de reuniones).
- Un viaje de actualización gradual proporciona un modo específico de coexistencia y actualización a un grupo específico de usuarios (también denominado *COHORT*), en función de sus requisitos de comunicación y colaboración. A lo largo del tiempo, toda la organización puede converger con Teams solamente y, eventualmente, reemplazar Skype empresarial. Sin embargo, si su organización tiene razones empresariales atractivas para mantener Skype empresarial, como una dependencia en una solución basada en la API administrada de comunicaciones (UCMA) unificada que se integra con aplicaciones de línea de negocio o con una solución de pared ética actualmente disponible solo para Skype empresarial, o una compleja implementación de voz de empresa que tardará más tiempo en actualizarse a teams: **solo**puede actualizar una parte de los usuarios al modo **solo** de Teams, a la vez que conserva los usuarios de Skype empresarial en una de las modos de coexistencia para una parte de la población de usuarios. El viaje de actualización gradual es el enfoque recomendado para clientes locales (y híbridos) a partir de Skype empresarial con el modo de coexistencia de colaboración de Teams y pasar de allí al modo de solo equipos cuando se cumplen los requisitos para los usuarios (posiblemente a través del Skype empresarial con el modo de coexistencia de reuniones y reuniones de Teams).

> [!IMPORTANT]
> Para ambos tipos de viajes de actualización, si su organización es actualmente una implementación local de Skype empresarial, necesita empezar a planificar la implementación de Skype empresarial híbrido antes de actualizar los usuarios al modo solo para **equipos** . Esto también ayudará a facilitar la interoperabilidad con Teams.

> [!NOTE]
> El modo **solo** de Teams requiere que los usuarios que forman parte de cohorts se basen en Skype empresarial online y se necesite una relación híbrida entre la implementación local de Skype empresarial y el inquilino de Skype empresarial online para facilitar el interoperabilidad entre Skype empresarial y Teams. El cambio a Skype empresarial online debe completarse para los usuarios que forman parte de la cohorts antes de que se actualicen al modo **solo para equipos** . Skype empresarial Server 2019 y la actualización de Skype empresarial 2015 con CU8 simplifican la mecánica de la actualización de usuarios locales a equipos mediante la administración de la migración a Skype empresarial online y la actualización de los usuarios al modo **solo para equipos** en un solo paso .

### <a name="direct-upgrade-journey"></a>Viaje de actualización directa

El viaje de actualización directa se muestra en el siguiente diagrama.

![Captura de pantalla del viaje de actualización directa] (media/upgrade_journey_direct_upgrade.png "Captura de pantalla del viaje de actualización directa. Inicialmente, todos los usuarios usan Teams en modo islas, después, pasan a modo de solo Teams, con el estado final de toda la organización actualizado a teams.")

Teams se implementa en todos los usuarios de la organización y se configura en el modo **islas** . Cuando su organización determine que Teams está listo para satisfacer todas sus necesidades de comunicación y colaboración, notifíqueselo a los usuarios y actualícelo a modo de **solo equipos** . En ese momento, Skype empresarial puede ser retirado del entorno.

### <a name="gradual-upgrade-journey"></a>Viaje de actualización gradual

En el siguiente diagrama se muestra un ejemplo de un viaje de actualización gradual.

![Ejemplo ilustrado del viaje de actualización gradual] (media/upgrade_journey_gradual_upgrade.png "En el viaje de actualización gradual, la cohorts de los usuarios inicialmente usa Teams en modo islas para la evaluación y luego, en una variedad de modos de actualización para una adopción temprana, en paralelo con Skype empresarial. Algunas cohortsn la transición al modo de solo equipos, mientras que un grupo de usuarios se mantiene con Skype empresarial y el modo de colaboración y reuniones de Teams.")

Teams se implementa en la organización en el modo **islas** para la evaluación y, a continuación, pasa a diferentes modos de coexistencia y actualización para los distintos grupos de usuarios. Por ejemplo, un grupo de usuarios puede estar habilitado para el modo **islas** , otro habilitado para **Skype empresarial con el modo de colaboración y reuniones** de Teams, mientras que un tercer grupo de usuarios podría estar inicialmente habilitado para **Skype empresarial con Teams modo de solo colaboración** .

Con el tiempo, los grupos de usuarios se pueden actualizar al modo **solo para equipos** , seguido del resto de la organización. Finalmente, toda la organización estará lista para retirar Skype empresarial y utilizar solo equipos para las comunicaciones y la colaboración, o bien, si los requisitos empresariales exigen que Skype empresarial se conserve para un grupo específico, la mayoría de los usuarios de la la organización puede usar solo Teams. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Puntos de decisión</td><td><ul> ¿Qué viaje de actualización es adecuado para los requisitos empresariales de su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Siguiente paso</td><td><ul> Identificar el modelo de implementación actual, los escenarios de casos de uso y las consideraciones clave para su organización informarán al viaje a los equipos que mejor se adapten a su organización.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Puntos de decisión</td><td><ul> ¿Qué escenario de actualización es aplicable a su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul> Decidir la escala de tiempo del viaje de actualización de su organización en función de la mensajería, las reuniones y los requisitos empresariales de llamadas.<br><br> Decida el trabajo adicional necesario para completar el viaje de actualización.<br><br></ul></td></tr>
</table>

Una vez que haya elegido el mejor viaje de actualización para su organización, [realice la actualización a teams](https://aka.ms/SkypeToTeams-Upgrade).
