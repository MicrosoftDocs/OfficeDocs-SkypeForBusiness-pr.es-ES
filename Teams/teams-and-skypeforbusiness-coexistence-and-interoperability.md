---
title: Comprender la coexistencia e interoperabilidad de Skype para empresas y Microsoft Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 09/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Detalles de Skype para profesionales y Microsoft Teams opciones de coexistencia y la interoperabilidad entre Skype para la empresa y los equipos.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 158e563151fe426f6abbbeb7519ba9e793f2d202
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296421"
---
![Fases de la actualización viaje, con especial hincapié en la fase de definición del proyecto] (media/upgrade-banner-project-definition.png "Fases de la actualización viaje, con especial hincapié en la fase de definición del proyecto")

En este artículo forma parte de la fase de proyecto definición de su viaje por la actualización, una actividad completar después de crear un equipo de proyecto y coalition patrocinadores y definir el ámbito, objetivos y visión para el proyecto. Antes de continuar, confirme que ha realizado las siguientes actividades:

-   [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
-   [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Descripción de Microsoft Teams y Skype para la interoperabilidad y coexistencia de negocio

Si la organización usa Skype para la empresa hoy mismo y desea empezar a usar los equipos junto con Skype para la empresa — o que va a iniciar la actualización a los equipos, es importante comprender cómo coexistan las dos aplicaciones, cuándo y cómo interoperan y cómo a administrar la migración de los usuarios hasta su eventual actualización desde Skype para la empresa a los equipos.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistencia de los equipos y Skype para la empresa

Además de las capacidades de colaboración, los equipos ofrece capacidades de reunión, llamada y chat. Dependiendo de cómo elija implementar los equipos, estas capacidades es posible que se solapan con las funciones de entrega por Skype para la empresa para un usuario determinado. El modo predeterminado es ejecutar los equipos junto con Skype para la empresa; Sin embargo, un usuario puede asignarse uno de varios modos de coexistencia que se diseñaron para asegurarse de que no se superpongan estas capacidades para ese usuario.

Le recomendamos que revise los modos de coexistencia que se describen a continuación para ayudarle a determinar qué ruta de acceso es la adecuada para su organización.

> [!Important]
> Introducción a la nueva tecnología o realizar cambios en su Skype existente y familiar para el entorno empresarial, al tiempo que ofrece grandes ventajas empresariales nuevo, puede ser perjudiciales para los usuarios. Tardar en evaluar la preparación del usuario e implementar un plan de aprendizaje y comunicación antes de implementar cualquiera de los cambios que se describen en este artículo. Además, recomendamos encarecidamente a su plan de la prueba piloto con un grupo seleccionado de usuarios antes de implementarlo en toda la organización. 

### <a name="islands-mode"></a>Modo de islas

De forma predeterminada, los usuarios pueden ejecutar los equipos junto con Skype para la empresa como dos soluciones independientes que ofrecen capacidades similares y superpuestas como chat, llamadas y reuniones. Los usuarios de los equipos también pueden aprovechar las capacidades de colaboración, como los equipos y canales, acceso a los archivos en Office 365 y aplicaciones.

En este modo de coexistencia, denominado **Islas**, cada una de las aplicaciones cliente funciona como una isla separada. Skype para se comunica empresarial con Skype para la empresa y los equipos se comunica con los equipos. Los usuarios ejecutan a ambos clientes y pueden comunicarse de forma nativa en el cliente desde el que se inició la comunicación. Por lo tanto, no es necesario para la interoperabilidad en modo de **Islas** .

> [!Tip]
> Cuando están disponibles los modos próximos modos de **Los equipos sólo** y **Skype para la empresa con la colaboración de equipos** , el modo predeterminado para nuevos usuarios en línea debe ser **Skype para la empresa con la colaboración de equipos**, hasta que esté lista para su organización Mover a **Sólo los equipos**.Tan pronto como su organización está preparada, deben mover los usuarios existentes en el modo de **Islas** directamente al modo de **Sólo los equipos** . 

### <a name="skype-for-business-only"></a>Skype para la empresa solo

En este modo de coexistencia, los usuarios permanecen en Skype para la empresa: los equipos no — para chat, convocatorias de reunión y llamar a funciones y no usan los equipos para los equipos y los canales. Este modo está disponible en la actualidad; Sin embargo, en la implementación actual modalidades de los equipos no se desactivan para el usuario automáticamente. Esta capacidad es próxima. Mientras tanto, los administradores pueden quitar la licencia de los equipos de los usuarios que necesiten permanecer en Skype para la empresa como su única aplicación de comunicaciones.

### <a name="teams-only-this-mode-started-rolling-out-summer-2018-and-will-be-completed-to-all-tenants-by-fall-2018"></a>Sólo los equipos (este modo iniciado sucesivas desproteger verano 2018 y se completará para todos los inquilinos otoño 2018)

Tan pronto como su organización está preparada para algunos o todos los usuarios usar los equipos como su herramienta de comunicaciones y colaboración sólo, puede actualizar los usuarios al modo de **sólo los equipos** .

Un usuario de **los equipos sólo** solo puede usar la Skype para cliente empresarial para unirse a Skype existente para reuniones de negocios o reuniones en Skype para la empresa que se han organizado por los usuarios que no sean actualizado o partes externas. Un usuario actualizado puede continuar para comunicarse con otros usuarios de la organización que todavía se están utilizando la Skype para la empresa mediante el uso de las capacidades de la interoperabilidad entre los equipos y Skype para la empresa; Sin embargo, un usuario actualizado no puede iniciar un Skype para chat empresarial, la llamada o reunión.

![Skype para cliente empresarial que se ejecuta en un modo especial después de actualiza el usuario como un usuario solo los equipos] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype para cliente empresarial que se ejecuta en un modo especial después de actualiza el usuario como un usuario solo los equipos")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype para la empresa con la colaboración de los equipos (este modo es próxima)

Utilice este modo para presentar los equipos en el entorno mientras se siguen sacar provecho de su inversión existente en Skype para la empresa. En este modo, se deja Skype para la empresa sin cambios con conversaciones, llamadas y las capacidades de la reunión, y agregar las capacidades de colaboración de equipos, los equipos y los canales de acceso a archivos en Office 365 y las aplicaciones.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype para la empresa con la colaboración de los equipos y las reuniones (este modo es próxima)

Utilice este modo de coexistencia para acelerar la disponibilidad de los equipos de las capacidades de la organización, además de sus capacidades de colaboración de la reunión, lo que permite a los usuarios para aprovechar la gran calidad, nuevas capacidades de como transcripción y conversión y compatibilidad para reuniones en exploradores.

Junto con el uso de los equipos de los equipos y basado en canales de conversaciones en este modo, los usuarios empiezan a usar los equipos para programar y llevar a cabo sus reuniones. Chats privados y de voz y llamadas de vídeo, permanecen en Skype para la empresa. Es especialmente útil para los usuarios de Skype para profesionales las implementaciones locales que tienen la telefonía IP empresarial, que están probables que se necesite algún tiempo para actualizarse a los equipos de este modo de coexistencia

> [!Note]
> Cuando se implementan en los modos de coexistencia específico, los equipos y Skype para la empresa pueden [interoperar](#interoperability-of-teams-and-skype-for-business), habilitar a los usuarios para conversaciones con y llamar a otro y asegurarse de que communications siga siendo fluida en toda la organización durante su viaje por la actualización a los equipos. Modos de coexistencia rigen interoperabilidad. El modo de coexistencia del receptor determina si interoperabilidad estará disponible. Por ejemplo, si el receptor está en un modo en el que chat sólo está disponible en un cliente (por ejemplo, equipos), interoperabilidad de chat por lo general estará disponible en caso de que el iniciador utiliza al otro cliente (en este caso, Skype para la empresa) para iniciar la conversación. Por otro lado, si el receptor está en un modo en el que está disponible en ambos clientes chat, interoperabilidad no estará disponible para el chat, y se recibirá el mensaje por el receptor en el mismo cliente en el que el iniciador iniciado el chat.

Para obtener más detalles sobre los modos de coexistencia, los requisitos previos y administración, vea [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://aka.ms/SkypeToTeams-Interop) y [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>¿Qué modos de coexistencia mejor ajustarse a las necesidades de su organización y los usuarios?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguiente paso|<ul><li>Elija el mejor enfoque para su viaje por la actualización.</li></ul>|


## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidad de los equipos y Skype para la empresa

La interoperabilidad es la capacidad de los equipos y Skype para los usuarios de negocio en la misma organización comunicarse a través de los equipos y Skype para la empresa.


### <a name="native-interop-and-interop-escalation"></a>Escalado de interoperabilidad e interoperabilidad nativa

Hay dos tipos de experiencias de interoperabilidad: escalación nativa e interoperabilidad.

-   Se produce una experiencia de _interoperabilidad nativa_ en el cliente que usa actualmente el usuario. Un usuario estará en el Skype para cliente empresarial, la otra en los equipos. Una experiencia de interoperabilidad nativa no lleve a otro cliente para la comunicación, los usuarios podrán llevar a cabo su conversación en el cliente que utiliza actualmente. Las experiencias de interoperabilidad nativas son chat uno a uno y con la llamada.
-   Una experiencia de _escalación interoperabilidad_ significa que, como parte de ayudar a los usuarios realizar una acción avanzada (por ejemplo, para compartir su escritorio), el servicio puede facilitar la creación de una reunión y continuar la experiencia en esa reunión. La reunión se crea en la plataforma del iniciador de la acción. El usuario o usuarios que no están en esa plataforma reciben la reunión unirse a las coordenadas y unirse a la reunión (después de cambiar los clientes).

### <a name="native-interop-experiences"></a>Experiencias de interoperabilidad nativa

Función de los modos de coexistencia que se asigna a los usuarios (como se describió anteriormente), las experiencias de interoperabilidad nativa siguientes están disponibles:

-   Skype para los usuarios de negocio puede iniciar una charla privada con los usuarios de los equipos y viceversa. Necesita una charla de interoperabilidad ir a través de una puerta de enlace de interoperabilidad que forma parte de los equipos en la nube de servicios (y, por tanto, sólo existe en línea). Interoperabilidad chats son de texto sin formato: texto enriquecido y los iconos gestuales no son compatibles. Se notificación a los usuarios en los equipos que la conversación es una conversación de interoperabilidad; pronto se proporcionará una notificación similar de Skype para los usuarios empresariales.
![Experiencia de los equipos de chat de interoperabilidad] (media/Interop_chat_experience_from_Teams.png "Experiencia de los equipos de chat de interoperabilidad")
-   Puede realizar Skype para usuarios profesionales proporcionó llamadas de voz y vídeo a los usuarios de los equipos y viceversa.
![Interoperabilidad al llamar a la experiencia de los equipos] (media/Interop_calling_experience_from_Teams.png "Interoperabilidad al llamar a la experiencia de los equipos")

> [!Important]
> Experiencias de interoperabilidad con una implementación local de Skype para la empresa requieren que el entorno local está en modo de híbrida con Office 365 Skype para la empresa. Para obtener información detallada, vea la [Guía de interoperabilidad y migración](https://aka.ms/SkypeToTeams-Interop).

Estas evaluaciones interoperabilidad están disponibles para los usuarios que tienen uno de los siguientes modos de coexistencia asignado: **Skype para la empresa con la colaboración de equipos**, **Skype para la empresa con la colaboración de los equipos y las reuniones**, **Skype para la empresa **, o **solo los equipos**.


### <a name="native-interop-experience-limitations"></a>Limitaciones de la experiencia de interoperabilidad nativa

Algunas características no están disponibles para la interoperabilidad conversaciones y la experiencia de llamada interoperabilidad entre los equipos y Skype para la empresa:

-   No se admiten descuento, texto enriquecido y el conjunto completo de icono gestual de Skype para la empresa o de los equipos. No se admiten otras características nativos del cuadro de redacción en chats de los equipos.
-   No se admite la pantalla de uso compartido (uso compartido de aplicaciones o escritorio) entre los equipos y Skype para la empresa.
-   Grupos chats (conversaciones entre varios participantes) en los equipos sólo pueden incluir a los participantes que usan los equipos.
-   Conversaciones de mensajería instantánea entre varios participantes (charlas de grupo) en Skype para la empresa pueden incluir sólo los participantes que usan Skype para la empresa.
-   No se admite el cambio espontáneo un curso voz de punto a punto o llamada de vídeo a una llamada entre varios participantes que implican los equipos y Skype para los usuarios empresariales.
-   Transferencia de chats de dos partes de archivos o datos adjuntos del archivo en charlas de grupo, desde los equipos de Skype para la empresa y viceversa: no se admiten.
-   No hay ninguna interoperabilidad con Skype para Chat persistente de negocio.

Para todas estas limitaciones (excepto para Chat persistente), una posible solución es para que un usuario para iniciar una reunión e invitar a otro usuario a unirse a ella. Esta solución alternativa es la base para la interoperabilidad escalación.

> [!Important]
> ¿Qué se inicia como un simple chat (IM) es posible que pasar rápidamente a una llamada o una reunión ad-hoc. Sabemos que estos escenarios son esenciales para la experiencia del usuario y la facilidad de uso, y nos estamos evolucionando experiencias de interoperabilidad entre Skype para los usuarios profesionales y los equipos. Vuelva a consultar para obtener la información más reciente.

Después de revisar este artículo, vea [elegir su viaje por la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [migración y la Guía de interoperabilidad](https://aka.ms/SkypeToTeams-Interop)y [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) para detalles de implementación.
