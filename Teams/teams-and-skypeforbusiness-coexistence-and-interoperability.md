---
title: Microsoft Teams | Actualizar, modo islas, Directiva de interoperabilidad, solamente
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Detalles de Skype empresarial y las opciones de coexistencia de Microsoft Teams y la interoperabilidad entre Skype empresarial y Teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c10a5fd2a1a172410a69362687146ba50cd69529
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344573"
---
![Etapas del viaje de actualización, con énfasis en la fase de definición del proyecto] (media/upgrade-banner-project-definition.png "Etapas del viaje de actualización, con énfasis en la fase de definición del proyecto")

Este artículo forma parte de la fase de definición de proyecto de su viaje de actualización, una actividad que ha completado después de crear un Coalition de patrocinio y un equipo de proyecto y definir el ámbito, los objetivos y la visión de su proyecto. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Inventar a los participantes del proyecto](upgrade-enlist-stakeholders.md)
- [Definió el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprender Microsoft Teams y la coexistencia e interoperabilidad de Skype empresarial

Si su organización usa Skype empresarial hoy y usted desea comenzar a usar Teams con Skype empresarial, o desea comenzar la actualización a Teams, es importante que comprenda cómo coexisten las dos aplicaciones, Cuándo y cómo interoperan, y cómo administre la migración de los usuarios hasta su actualización eventual desde Skype empresarial a teams.

> [!Tip]
> Vea la siguiente sesión para obtener información sobre la coexistencia [y](https://aka.ms/teams-upgrade-coexistence-interop) la interoperabilidad

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistencia de Teams y Skype empresarial

Además de las capacidades de colaboración, Teams ofrece funciones de chat, llamadas y reuniones. En función de cómo elija implementar Teams, estas capacidades se superpondrán con las capacidades que ofrece Skype empresarial para un usuario determinado. El modo predeterminado es ejecutar Teams junto con Skype empresarial; sin embargo, a un usuario se le puede asignar uno de los diversos modos de coexistencia diseñados para garantizar que estas funcionalidades no se solapen para ese usuario.

Le recomendamos que revise los modos de coexistencia que se describen a continuación para determinar qué ruta de acceso es adecuada para su organización.

> [!Important]
> La presentación de nuevas tecnologías o la realización de cambios en el entorno existente de Skype para empresas, a la vez que ofrece excelentes beneficios comerciales nuevos, puede ser perjudicial para los usuarios. Tome el tiempo de evaluar la preparación del usuario e implementar un plan de comunicación y aprendizaje antes de implementar cualquiera de los cambios descritos en este artículo. Además, le recomendamos encarecidamente que planee su plan con un grupo de usuarios seleccionado antes de implementarlo en toda la organización.

### <a name="islands-mode"></a>Modo islas

De forma predeterminada, los usuarios pueden ejecutar equipos junto con Skype empresarial como dos soluciones independientes que ofrecen capacidades similares y superpuestas, como chat, llamadas y reuniones. Los usuarios de Teams también pueden aprovechar las capacidades de colaboración, como los equipos y los canales, el acceso a los archivos de Office 365 y las aplicaciones.

En este modo de coexistencia, denominado **islas**, cada una de las aplicaciones cliente funciona como una isla independiente. Skype empresarial habla con Skype empresarial y Teams se comunica con Teams. Los usuarios ejecutan ambos clientes y pueden comunicarse de forma nativa en el cliente desde el que se inició la comunicación. Por lo tanto, no hay necesidad de interoperabilidad en el modo **islas** .

> [!Tip]
> La ruta recomendada para los clientes de Skype empresarial online es empezar con el modo **islas** predeterminadas, la saturación de adopción de unidades en la organización y, a continuación, ir rápidamente al modo **solo equipos** . Los clientes híbridos y locales pueden beneficiarse de implementar el próximo **Skype empresarial con** el modo de colaboración de Teams como punto de partida en lugar de islas, y de pasar de allí al modo de **solo equipos** cuando la organización está lista para su adopción Podrán.

### <a name="skype-for-business-only"></a>Solo para Skype empresarial

En este modo de coexistencia, los usuarios permanecen en Skype para empresas, no en los equipos, para las capacidades de chat, reuniones y llamadas, y no usan Teams para equipos y canales. Este modo está disponible hoy; sin embargo, en la implementación actual las modalidades de los equipos no se desactivan automáticamente para el usuario. Esta capacidad es la próxima. Mientras tanto, los administradores pueden quitar la licencia de Teams de todos los usuarios que necesiten permanecer en Skype empresarial como la única aplicación de comunicaciones.

### <a name="teams-only"></a>Solo equipos

Un **solo** usuario de Skype puede usar el cliente de Skype empresarial para unirse a reuniones de Skype empresarial existentes o a reuniones de Skype empresarial organizadas por usuarios que no se han actualizado o por parte de terceros. Un usuario actualizado puede seguir comunicándose con otros usuarios de la organización que siguen usando Skype empresarial con las funciones de interoperabilidad entre Teams y Skype empresarial; sin embargo, un usuario actualizado no puede iniciar una conversación, una llamada o una reunión de Skype empresarial.

Tan pronto como su organización esté lista para que algunos o todos los usuarios usen Teams como la única herramienta de comunicación y colaboración, puede actualizar esos usuarios al modo de **solo equipos** .

Para obtener más información sobre cómo cambiar al modo solo de Teams, vea [consideraciones del modo solo](teams-only-mode-considerations.md)de Teams.

![Cliente de Skype empresarial que se ejecuta en un modo especial después de que el usuario se actualice como un usuario de solo equipo] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente de Skype empresarial que se ejecuta en un modo especial después de que el usuario se actualice como un usuario de solo equipo")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype empresarial con colaboración en equipo (este modo es el próximo)

Use este modo para presentar equipos en su entorno mientras continúa aprovechando la inversión existente en Skype empresarial. En este modo, no se cambia Skype empresarial con las funciones de chat, llamadas y reuniones, y usted agrega capacidades de colaboración de Teams: equipos y canales, acceso a los archivos de Office 365 y aplicaciones. Las organizaciones con un punto de partida de Skype empresarial Server local o híbrido deben usar este modo en lugar del modo islas.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype empresarial con la colaboración y las reuniones de Teams (este modo es el próximo)

Use este modo de coexistencia para acelerar la disponibilidad de las capacidades de reunión de los equipos de su organización, además de sus capacidades de colaboración, lo que permite a los usuarios aprovechar la excelente calidad, las nuevas capacidades, como la transcripción y traducción y soporte técnico para las reuniones en exploradores.

Junto con el uso de Teams para las conversaciones basadas en equipos y canales en este modo, los usuarios empiezan a usar Teams para programar y realizar sus reuniones. Los chats privados, las llamadas y las videollamadas, permanecen en Skype empresarial. Este modo de coexistencia es especialmente útil para los usuarios de las implementaciones locales de Skype empresarial que tienen una telefonía IP empresarial, que es probable que tarden un poco en actualizarse a Teams, pero desean beneficiarse de las reuniones superiores de los equipos.

> [!Note]
> Cuando se implementan en modos de coexistencia específicos, los equipos [](#interoperability-of-teams-and-skype-for-business)y Skype empresarial pueden interoperar, lo que permite a los usuarios conversar con ellos y llamarse a ellos y garantizar que las comunicaciones permanezcan fluidas en toda la organización durante el viaje de actualización a teams. Los modos de coexistencia rigen la interoperabilidad. El modo de coexistencia del receptor determina si estará disponible la interoperabilidad. Por ejemplo, si el receptor está en un modo en el que la conversación solo está disponible en un cliente (por ejemplo, Teams), la interoperabilidad de chat estará disponible generalmente en caso de que el iniciador use el otro cliente (en este caso, Skype empresarial) para iniciar la conversación. Por otro lado, si el receptor está en un modo en el que la conversación está disponible en ambos clientes, la interoperabilidad no estará disponible para la conversación, y el destinatario recibirá el mensaje en el mismo cliente en el que el iniciador inició la conversación.

Para obtener más información sobre los modos de coexistencia, los requisitos previos y la administración, consulte [Guía de migración e interoperabilidad para las organizaciones que usan Teams junto con Skype empresarial](https://aka.ms/SkypeToTeams-Interop) y [establecer la coexistencia y la actualización de la configuración](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Puntos de decisión|<ul><li>¿Qué modo o modos de coexistencia se adaptan mejor a las necesidades de los usuarios y de su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Siguiente paso|<ul><li>Elige el mejor enfoque para tu viaje de actualización.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidad de Teams y Skype empresarial

La interoperabilidad es la capacidad de que los equipos y los usuarios de Skype empresarial de la misma organización se comuniquen entre equipos y Skype empresarial.

### <a name="native-interop-and-interop-escalation"></a>Interoperabilidad nativa y escalabilidad de interoperabilidad

Existen dos tipos de experiencias de interoperabilidad: nativas y de interoperabilidad.

- La experiencia de interoperabilidad _nativa_ se produce en el cliente que el usuario está usando actualmente. Un usuario estará en el cliente de Skype empresarial, el otro en Teams. Una experiencia de interoperabilidad nativa no las llevará a otro cliente para comunicarse, los usuarios podrán realizar su conversación en el cliente que actualmente están usando. Las experiencias de interoperabilidad nativas son chats uno a uno y llamadas.
- Una __ experiencia de escalado de interoperabilidad significa que, como parte de ayudar a los usuarios a realizar una acción avanzada (como compartir su escritorio), el servicio puede facilitar la creación de una reunión y continuar con la experiencia de esa reunión. La reunión se crea en la plataforma del iniciador de la acción. El usuario o los usuarios que no se encuentren en la plataforma recibirán coordenadas de la reunión y se unirán a la reunión (después de cambiar los clientes).

### <a name="native-interop-experiences"></a>Experiencias de interoperabilidad nativas

Según los modos de coexistencia asignados a los usuarios (como se ha descrito anteriormente), están disponibles las siguientes experiencias de interoperabilidad nativas:

- Los usuarios de Skype empresarial pueden chatear uno a uno con los usuarios de Teams, y viceversa. Un chat de interoperabilidad debe atravesar un Gateway de interoperabilidad que forma parte de los servicios en la nube de Teams (y, por lo tanto, solo está conectado). Los chats interoperativos son texto sin formato: el texto enriquecido y los emoticonos no se admiten. Se notifica a los usuarios de teams que la conversación es una conversación de interoperabilidad; pronto se proporcionará una notificación similar para los usuarios de Skype empresarial.

![Experiencia de chat de interoperabilidad de Teams] (media/Interop_chat_experience_from_Teams.png "Experiencia de chat de interoperabilidad de Teams")

- Los usuarios de Skype empresarial pueden hacer llamadas y videollamadas individuales a los usuarios de Teams, y viceversa.

![Experiencia de llamadas de interoperabilidad de equipos] (media/Interop_calling_experience_from_Teams.png "Experiencia de llamadas de interoperabilidad de equipos")

> [!Important]
> Las experiencias de interoperabilidad con una implementación local de Skype empresarial requieren que el entorno local esté en modo híbrido con Office 365 Skype empresarial. Para obtener más información, consulte [Guía de migración e](https://aka.ms/SkypeToTeams-Interop)interoperabilidad.

Estas experiencias de interoperabilidad están disponibles para los usuarios que tienen uno de los siguientes modos de coexistencia asignado: **Skype empresarial con colaboración**de Teams, **Skype empresarial con colaboración y reuniones**de Teams, **Skype para Solo para empresas**o **Teams**. No hay ninguna interoperabilidad para los usuarios en el modo islas.

### <a name="native-interop-experience-limitations"></a>Limitaciones de la experiencia de interoperabilidad nativa

Algunas características no están disponibles para la conversación interoperativa y la experiencia de interoperabilidad entre equipos y Skype empresarial:

- No se admite el descuento, el texto enriquecido ni el conjunto de emoticonos completo de equipos o de Skype empresarial. No se admiten otras características nativas del cuadro de redacción en los chats de Teams.
- No se admite la pantalla compartida (uso compartido de escritorio o aplicaciones) entre equipos y Skype empresarial.
- Los chats grupales (conversaciones de varios participantes) en Teams solo pueden incluir participantes que usen Teams.
- Las conversaciones de mensajería instantánea de varios participantes (chats grupales) en Skype empresarial solo pueden incluir participantes que usen Skype empresarial.
- No se admite la escala de una llamada de voz o videollamada de punto a punto continuado a una llamada de varios participantes que implique a equipos y usuarios de Skype empresarial.
- No se admite la transferencia de archivos para chats de dos participantes o datos adjuntos en chats grupales, de equipos a Skype para empresas, y viceversa.
- No existe una interoperabilidad con el chat persistente de Skype empresarial.

Para todas estas limitaciones (excepto para conversaciones persistentes), una posible solución es que un usuario inicie una reunión e invite a otro usuario a unirse a ella. Esta solución alternativa constituye la base para el escalamiento de interoperabilidad.

> [!Important]
> Lo que comienza como una conversación simple (mi) puede escalarse rápidamente a una llamada o a una reunión ad-hoc. Somos conscientes de que estos escenarios son esenciales para el uso y la experiencia del usuario, y estamos continuamente evolucionando experiencias de interoperabilidad entre Skype empresarial y los usuarios de Teams. Vuelva a consultar la información más actualizada.

Después de revisar este artículo, vea [elegir la actualización del viaje, la](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) [migración y](https://aka.ms/SkypeToTeams-Interop)la interoperabilidad de la actualización, coexistencia [con Skype empresarial](coexistence-chat-calls-presence.md)y [configurar la coexistencia y la configuración de actualización para la](https://aka.ms/SkypeToTeams-SetCoexistence) implementación. sobre.

## <a name="related-links"></a>Vínculos relacionados

[Vídeo: administrar la coexistencia y la interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
