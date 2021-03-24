---
title: Comprender la coexistencia e interoperabilidad de Microsoft Teams y Skype Empresarial
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalles de las opciones de coexistencia de Skype Empresarial y Microsoft Teams, así como la interoperabilidad resultante entre Skype Empresarial y Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3332ec1a5c5bc05bc833511a3b33e0f4dff6cccc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111136"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprender la coexistencia e interoperabilidad de Microsoft Teams y Skype Empresarial

![Diagrama de itinerario de actualización, énfasis en la fase de definición del proyecto](media/upgrade-banner-project-definition.png "Fases del itinerario de la actualización, con énfasis en la fase de definición del proyecto")

Este artículo forma parte de la fase de definición de proyecto de su vía de actualización. Completado después de crear una coalición de patrocinio y un equipo de proyecto y definir el ámbito, los objetivos y el plan para el proyecto. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)

Si su organización usa Skype Empresarial hoy en día y está empezando a usar Teams junto con Skype Empresarial (o está empezando a actualizar a Teams), es importante comprender cómo coexisten las dos aplicaciones, cuándo y cómo interactúan, y cómo administrar la migración de los usuarios hasta su actualización final de Skype Empresarial a Teams.

> [!Tip]
> Vea la siguiente sesión para obtener información sobre [coexistencia e interoperabilidad.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Además, puede unirse a nosotros para realizar talleres interactivos en directo en los que compartiremos instrucciones, procedimientos recomendados y recursos diseñados para iniciar la planificación y la implementación de la actualización.
>
> Para empezar, únase en primer lugar a la sesión [Planificar la actualización](./upgrade-workshops-landing-page.yml).

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Información general sobre la coexistencia de Teams y Skype Empresarial

En las secciones siguientes se describen los modos de coexistencia que están disponibles cuando decide actualizar a Teams y las capacidades que ofrece cada modo. Además, describimos la interoperabilidad (interoperabilidad) que se produce entre los usuarios de los clientes de Skype Empresarial y los usuarios de los clientes de Teams, y cómo la interoperabilidad se ve afectada por el modo de coexistencia elegido.

 Teams ofrece capacidades de colaboración, chat, llamadas y reuniones. Dependiendo de cómo elija implementar Teams, estas capacidades pueden superponerse con las funcionalidades entregadas por Skype Empresarial para un usuario determinado. El modo predeterminado es ejecutar Teams junto con Skype Empresarial con las capacidades superpuestas. Sin embargo, a un usuario se le puede asignar uno de los varios modos de coexistencia (también conocidos como modos de actualización) diseñados para asegurarse de que estas capacidades no se superpongan para ese usuario (en cuyo caso está disponible la interoperabilidad entre Teams y Skype Empresarial). Por ejemplo, si tiene activos locales importantes de Skype Empresarial Server con una implementación Telefonía IP empresarial compleja, pero quiere que los usuarios [](meetings-first.md) disfruten de las reuniones modernas lo antes posible, es posible que desee evaluar Reuniones primero como una ruta alternativa.

Le recomendamos que revise los siguientes modos de coexistencia para ayudar a determinar qué ruta es la adecuada para su organización.

> [!Important]
> La introducción de nuevas tecnologías o la realización de cambios en su entorno existente y familiar de Skype Empresarial, al tiempo que ofrece grandes ventajas empresariales, puede ser perjudicial para los usuarios. Tómese un tiempo para evaluar la preparación del usuario e implementar un plan de comunicación y aprendizaje antes de implementar cualquiera de los cambios descritos en este artículo. Además, le recomendamos encarecidamente que pilote su plan con un grupo seleccionado de usuarios antes de implementarlo en toda la organización.

### <a name="islands-mode"></a>Modo Islas

De forma predeterminada, los usuarios pueden ejecutar Teams junto con Skype Empresarial como dos soluciones independientes que ofrecen capacidades similares y superpuestas. Las capacidades incluyen presencia, chat, llamadas y reuniones. Los usuarios de Teams también pueden aprovechar las nuevas capacidades de colaboración, como equipos y canales, acceso a archivos en Microsoft 365 u Office 365 y aplicaciones.

En este modo de coexistencia, denominado **Islas,** cada una de las aplicaciones cliente funciona como una isla independiente. Skype Empresarial habla con Skype Empresarial y Teams habla con Teams. Se espera que los usuarios ejecuten ambos clientes en todo momento y que puedan comunicarse de forma nativa en el cliente desde el que se inició la comunicación. Por lo tanto, no es necesario interoperabilidad en el **modo Islas.**

Para evitar una experiencia confusa o regresiva de Skype Empresarial, Skype Empresarial se encarga de las siguientes integraciones que no se manejan en el modo islas **de** Teams:

- Comunicaciones externas (federadas).
- Servicios de voz RTC y aplicaciones de voz, integración de Office.
- Controles HID para dispositivos USB.
- Varias otras integraciones.  

El sistema telefónico no es compatible con Teams en modo **Islas.** **El** modo Islas no es compatible Telefonía IP empresarial cliente es Skype Empresarial.

> [!Important]
> En **el modo** Islas, todos los mensajes y llamadas de usuarios federados (personas de fuera de su organización) se entregan a Skype Empresarial. Después de actualizar al **modo solo de Teams,** todos los mensajes y llamadas de fuera de su organización se entregan a Teams.

> [!Tip]
> La ruta recomendada para los clientes de  Skype Empresarial Online es empezar con el modo islas predeterminado, impulsar la saturación de adopción de Teams en la organización y, a continuación, pasar rápidamente al modo solo de **Teams.** Los clientes locales e híbridos, especialmente los complejos, pueden beneficiarse de implementar el  modo de colaboración de Skype Empresarial con **Teams** como punto de partida en lugar del  modo Islas, y avanzar desde allí a Skype Empresarial con el modo de colaboración y reuniones de **Teams** (es decir, Reuniones en primer lugar), si procede, y al modo Solo para equipos cuando la organización esté lista para adoptar Teams.

### <a name="teams-only"></a>Solo en Teams

Un **usuario solo de Teams** (también denominado usuario actualizado) tiene acceso a todas las funcionalidades de Teams.  Pueden conservar el cliente de Skype Empresarial para unirse a reuniones en Skype Empresarial que hayan sido organizadas por usuarios no actualizados o partes externas. Un usuario actualizado puede seguir comunicándose con otros usuarios de la organización que siguen usando Skype Empresarial mediante las capacidades de interoperabilidad entre Teams y Skype Empresarial (siempre que los usuarios de Skype Empresarial no estén en modo Islas).  Sin embargo, un usuario actualizado no puede iniciar un chat, llamada o reunión de Skype Empresarial.

Tan pronto como su organización esté lista para que algunos o todos los usuarios usen Teams como su única herramienta de comunicaciones y colaboración, actualice esos usuarios al modo **solo de** Teams. Si va a actualizar desde el modo **Islas,** le recomendamos que primero sature la adopción de Teams en toda su organización antes de comenzar el proceso de actualización. Esta adopción evita situaciones de comunicación rotas debido a **que el modo Islas** no proporciona interoperabilidad.

Cuando se encuentra **en modo Solo** para equipos, Teams es la aplicación predeterminada para el protocolo SIP/Tel. Teams controlará los vínculos de la tarjeta de contacto de un usuario en Outlook para llamadas o chats.

Para obtener consideraciones adicionales sobre cómo pasar al modo **Solo** para equipos, vea Consideraciones del modo [Solo equipos.](teams-only-mode-considerations.md)

![Captura de pantalla del mensaje de confirmación de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente de Skype Empresarial que se ejecuta en un modo especial después de actualizar al usuario como usuario solo de Teams")

### <a name="skype-for-business-only"></a>Solo Skype Empresarial

En este modo de coexistencia, los usuarios permanecen en Skype Empresarial, no en Teams, para las capacidades de chat, reunión y llamadas, y no usan Teams para equipos y canales. Este modo está disponible hoy; sin embargo, en la implementación actual, los equipos y los canales no se desactivarán automáticamente para el usuario. Esto se puede lograr mediante la directiva de configuración de la aplicación para ocultar equipos y archivos.

Este modo se puede usar antes de iniciar una implementación administrada de Teams para evitar que los usuarios empiecen a usar Teams antes de haber creado preparación. Este modo también es una forma de habilitar la participación autenticada en las reuniones de Teams para los usuarios de Skype Empresarial, siempre que los usuarios estén autorizados para Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Colaboración de Skype Empresarial con Teams

Use este modo para introducir Teams en su entorno mientras sigue usando su inversión existente en Skype Empresarial. Deje Skype Empresarial sin cambios para las capacidades de chat, llamadas y reuniones. Agregar capacidades de colaboración de Teams:

- Equipos y canales.
- Acceso a archivos en Microsoft 365 u Office 365.
- Aplicaciones. Capacidades de comunicaciones de Teams: chat privado, llamadas y programación de reuniones.

Las reuniones privadas de chat, llamadas y programación de Teams están desactivadas de forma predeterminada en este modo.

Las organizaciones con un punto de partida de Skype Empresarial Server  local o híbrido deben considerar este modo como una alternativa al modo Islas si quieren proporcionar a sus usuarios interoperabilidad y  predictibilidad para sus comunicaciones, así como tener una escala de tiempo predecible para su actualización a Teams (en lugar de depender de la saturación de adopción en el modo Islas).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype Empresarial con la colaboración y las reuniones de Teams, también conocidas como Reuniones en primer lugar

Use este modo de coexistencia para acelerar la disponibilidad de las capacidades de reunión y colaboración de Teams en su organización. El modo de coexistencia permite a los usuarios aprovechar la experiencia superior de reuniones de Teams:

- Excelente calidad.
- Transcripción y traducción.
- Fondo difuminado.
- Experiencia de usuario superior en todas las plataformas, incluidos dispositivos móviles y exploradores.

Además de usar Teams para las conversaciones basadas en equipos y canales en este modo, los usuarios usarán Teams para programar y dirigir sus reuniones. El chat privado y las llamadas permanecen en Skype Empresarial. Teams y Skype Empresarial se benefician de una amplia gama de funcionalidades de "mejor conjunto", como la conciliación de presencia, la retención/detención automática y la compatibilidad con dispositivos HID en ambas aplicaciones. Es posible ocultar equipos y canales, si lo desea, con la directiva de configuración de la aplicación.

Este modo de coexistencia es especialmente útil para las organizaciones con implementaciones locales de Skype Empresarial con Telefonía IP empresarial. Es probable que estas organizaciones den algún tiempo para actualizar a Teams y quieran beneficiarse de las reuniones superiores de Teams tan pronto como sea posible.

> [!TIP]
> Para ayudar a identificar el modo de actualización recomendado en función de las capacidades que quiera habilitar en Teams mientras Skype Empresarial sigue en uso, use el Asistente para la actualización de Skype a [Teams.](https://aka.ms/SkypeToTeamsWizard)

Para obtener más información sobre los modos de coexistencia, los requisitos previos y la administración, vea Instrucciones de migración e interoperabilidad para organizaciones que usan Teams junto con [Skype](./migration-interop-guidance-for-teams-with-skype.md) Empresarial y Establecer la configuración de coexistencia [y actualización.](./setting-your-coexistence-and-upgrade-settings.md)

|Icono de punto de decisión |Definición de icono |Descripción |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto de decisión|<ul><li>¿Qué modo de coexistencia se adapta mejor a las necesidades de su organización y de los usuarios?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Paso siguiente|<ul><li>Elija el mejor método para el viaje de actualización.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidad de Teams y Skype Empresarial

La interoperabilidad es la capacidad para que los usuarios de Teams y Skype Empresarial de la misma organización se comuniquen entre Teams y Skype Empresarial.

La interoperabilidad se rige por el modo de coexistencia (también conocido como modo de actualización) del receptor. No hay interoperabilidad cuando el receptor está en modo **Islas.**

> [!Note]
> Cuando se implementa en cualquier modo de coexistencia excepto **islas,** Teams y Skype Empresarial pueden [interoperar,](#interoperability-of-teams-and-skype-for-business)lo que permite a los usuarios chatear y llamar entre sí, y garantizar que las comunicaciones sigan siendo fluidas en toda la organización durante el viaje de actualización a Teams. Los modos de coexistencia rigen la interoperabilidad. El modo de coexistencia del receptor determina si la interoperabilidad estará disponible. Por ejemplo, si el receptor está en un modo en el que el chat solo está disponible en un cliente (por ejemplo, Teams), la interoperabilidad del chat estará disponible generalmente en caso de que el iniciador use el otro cliente (en este caso, Skype Empresarial) para iniciar el chat. Por otro lado, si el receptor está en el modo en que el chat está disponible en ambos clientes (modo Islas), la interoperabilidad no estará disponible para el chat. El mensaje lo recibirá el receptor en el mismo cliente en el que el iniciador inició el chat. Por lo tanto, la comunicación correcta en **el modo Islas** requiere saturación de adopción de Teams; es decir, todos los usuarios que usan y supervisan activamente ambos clientes.

> [!Note]
> **Para tener la experiencia de coexistencia más reciente, la versión del cliente debe ser el cliente disponible más reciente en el canal de implementación de Office del usuario.**

#### <a name="native-interop-and-interop-escalation"></a>Escalación nativa de interoperabilidad y interoperabilidad

Hay dos tipos de experiencias de interoperabilidad: nativa y escalación de interoperabilidad.

- Se _produce una experiencia de interoperabilidad_ nativa en el cliente que el usuario está usando actualmente. Un usuario estará en el cliente de Skype Empresarial y el otro en Teams. Una experiencia de interoperabilidad nativa no los llevará a otro cliente para comunicarse. Los usuarios podrán llevar a cabo su conversación en el cliente que están usando actualmente. Las experiencias de interoperabilidad nativas son llamadas y chats uno a uno.
- Una _experiencia de escalado_ de interoperabilidad significa que, como parte de ayudar a los usuarios a realizar una acción avanzada (como compartir su escritorio), el cliente facilita la creación de una reunión a la que los usuarios pueden unirse para continuar la experiencia en esa reunión. La reunión se crea en la plataforma del iniciador de la acción. El usuario o los usuarios que no están en esa plataforma reciben un vínculo de unirse a la reunión. Al hacer clic en este vínculo, se unen a la reunión en un cliente compatible (explorador, aplicación web o cliente completo, según la configuración). La escalación de interoperabilidad de Skype Empresarial requiere un cliente reciente. La escalación de interoperabilidad de Teams ya está disponible. Ambas son compatibles con las experiencias de interoperabilidad en el espacio empresarial y con las comunicaciones federadas entre inquilinos.

#### <a name="native-interop-experiences"></a>Experiencias de interoperabilidad nativas

Según los modos de coexistencia asignados a los usuarios (como se ha descrito anteriormente), están disponibles las siguientes experiencias de interoperabilidad nativas:

Los usuarios de Skype Empresarial pueden chatear uno a uno con los usuarios de Teams y viceversa. Un chat de interoperabilidad debe pasar por una puerta de enlace de interoperabilidad que forma parte de los servicios en la nube de Teams (y, por lo tanto, solo existe en línea). Los chats de interoperabilidad son texto sin formato: el texto enriquecido y los emoticonos no son compatibles. A los usuarios de Teams y skype empresarial se les notifica que la conversación es una conversación de interoperabilidad.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Los usuarios de Skype Empresarial pueden realizar llamadas de voz y videollamadas uno a uno a los usuarios de Teams, y los usuarios de Teams pueden hacer lo mismo.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Las experiencias de interoperabilidad con una implementación local de Skype Empresarial requieren que el entorno local esté en modo híbrido con Microsoft 365 u Office 365 Skype Empresarial. Para obtener más información, vea [Instrucciones de migración e interoperabilidad.](./migration-interop-guidance-for-teams-with-skype.md)

Estas **experiencias** de interoperabilidad están disponibles para los usuarios que tienen uno de los siguientes modos de coexistencia asignados: Skype Empresarial con colaboración de **Teams,** Skype Empresarial con colaboración y reuniones de Teams, **Solo Skype** Empresarial o **Solo** Equipos. No hay interoperabilidad para los usuarios en el **modo Islas.**

#### <a name="native-interop-experience-limitations"></a>Limitaciones de la experiencia de interoperabilidad nativa

Debido a la diferencia entre protocolos y tecnología, no es posible admitir todas las capacidades de forma nativa. En concreto, las siguientes funcionalidades no están disponibles:

- Markdown, texto enriquecido y todo el conjunto de emoticonos no son compatibles ni con Teams ni con Skype Empresarial. No se admiten otras características nativas del cuadro de redacción en los chats de Teams.
- El uso compartido de pantalla (uso compartido de aplicaciones o escritorio) entre Teams y Skype Empresarial no se admite de forma nativa. Sin embargo, es compatible con la escalación de interoperabilidad.
- Los chats grupales (conversaciones de varias partes) en Teams solo pueden incluir participantes que usan Teams.
- Las conversaciones de mensajería instantánea de varias partes (chats grupales) en Skype Empresarial solo pueden incluir participantes que usan Skype Empresarial. Sin embargo, la escalación de interoperabilidad a varias partes está disponible desde Skype Empresarial.
- No es compatible escalar una llamada de punto a punto o una videollamada continua a una llamada de varias partes que involucre a los usuarios de Teams y Skype Empresarial.
- La transferencia de archivos para chats de dos partes o datos adjuntos de archivos en chats grupales, de Teams a Skype Empresarial y viceversa, no es compatible.
- No hay interoperabilidad con el chat persistente de Skype Empresarial.

Para todas estas limitaciones (excepto chat persistente), una posible solución alternativa es que un usuario inicie una reunión e invite al otro usuario a unirse a ella.

Esta solución alternativa es la base para la escalada de interoperabilidad. En particular, el uso compartido de pantalla y la escalación a varios partes no se pueden lograr de forma nativa, pero se admiten mediante la escalación de interoperabilidad.

#### <a name="interop-escalation-experiences"></a>Experiencias de escalado de interoperabilidad

La escalación de interoperabilidad consiste en complementar las capacidades de interoperabilidad nativas con escalaciones administradas a las reuniones. Las reuniones ofrecen experiencias enriquecciones disponibles para cualquier persona, independientemente del cliente que tengan.

Cuando el usuario de Teams desencadena la escalada de interoperabilidad, se crea una reunión de Teams. Cuando se activa por el usuario de Skype Empresarial, se crea una reunión de Skype Empresarial. En ambos casos, la reunión creada es una reunión **Reunirse** ahora, que no se refleja en el calendario del usuario.

La otra parte recibe el vínculo de unirse a la reunión a través del chat de interoperabilidad y se une haciendo clic en ese vínculo. Si el usuario de Skype Empresarial tiene una cuenta de Teams y es invitado por el usuario de Teams, se unirá a la reunión autenticada. En caso contrario, se unirán como participante anónimo. Por el contrario, los usuarios de Teams casi siempre tienen una cuenta de Skype Empresarial y un cliente de Skype Empresarial que pueden usar para unirse a una reunión de Skype Empresarial como participante autenticado, pero también pueden unirse como participante anónimo, por ejemplo, con la aplicación reunión de Skype.

Una vez que las partes se han unido a la reunión, pueden realizar cualquier actividad compatible con reuniones, como el uso compartido de contenido o de escritorio, el uso compartido de archivos o la transferencia, agregar otros participantes, y así sucesivamente.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalación de interoperabilidad desde Skype Empresarial

La escalación de interoperabilidad y interoperabilidad de Skype Empresarial se actualizó en la compilación de julio de 2019 de C2R mensual. Anteriormente, Skype Empresarial no tenía conciencia previa de que el usuario remoto estaba usando Teams. Solo sucedía que a partir de la señalización recibida después de establecer una sesión.

Cuando la señalización indicaba que la respuesta provenía de (o a través) de la puerta de enlace de interoperabilidad, mostraría la barra de negocios amarilla (banner) que indicaba que la otra parte no estaba usando Skype Empresarial. Con la evolución de nuestro servicio, esto dio como resultado falsos positivos en los que los usuarios de Skype Empresarial verían la barra de negocios cuando estaban conectados al servicio de correo de voz en la nube u otros servicios de voz en la nube, en lugar de a un usuario real de **Teams Only.**

Para evitar estos falsos positivos, el servicio de presencia ahora informa al cliente de Skype Empresarial cuando la otra parte es un usuario real solo de **Teams.** Esto permite que Skype Empresarial sea consciente de que necesita crear una conversación de interoperabilidad antes de que se haya creado y que la ventana de conversación sea específica para la interoperabilidad.

![Captura de pantalla del mensaje de Teams para crear una conversación de interoperabilidad con un usuario de Skype Empresarial](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si el usuario de Skype Empresarial quiere compartir su escritorio, por ejemplo, se le informa de que iniciaremos una reunión y le guiaremos por los pasos.

![Captura de pantalla del mensaje de Teams para empezar a reunirse con un usuario de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Mientras tanto, el usuario de Teams recibe un mensaje de chat entrante con el vínculo a la reunión y se le guía para unirse.

Esta escala a una reunión de Skype Empresarial está disponible tanto para la interoperabilidad en el espacio empresarial como para las llamadas y chats federados entre inquilinos. Está en la opción predeterminada y no hay ninguna configuración que el administrador tenga que aprovisionar.

#### <a name="interop-escalation-from-teams"></a>Escalación de interoperabilidad desde Teams

La escalación de interoperabilidad de Teams a una reunión de Teams ahora está disponible cuando el usuario de Teams selecciona el botón de uso compartido de escritorio en un hilo de interoperabilidad en el espacio empresarial con un usuario de Skype Empresarial o en un hilo de federación de interoperabilidad entre inquilinos. La escalación de interoperabilidad se admite desde una conversación de chat 1:1 o desde una llamada 1:1.

La funcionalidad se admite en el cliente de escritorio de Teams para Windows, en el cliente de escritorio de Teams para Mac y en el cliente web de Teams en exploradores en los que se admite el uso compartido de contenido, mientras se comunica con cualquier versión de cliente de Skype Empresarial.

En los hilos de interoperabilidad y en los hilos de interoperabilidad de federación, el usuario de Teams ahora tiene los controles (botón) para iniciar el uso compartido de contenido. Cuando el usuario de Teams selecciona el botón, se le presenta un menú adicional que le informa de que, para compartir contenido, tendrá que iniciar una reunión de Teams.

Si los usuarios estaban en una llamada, el menú también les advierte de que la llamada actual entre Teams y Skype Empresarial se finalizará cuando se coloquen en una reunión de Teams. Si lo eligen, pueden advertir al usuario de Skype Empresarial antes de aceptarlo.

![Captura de pantalla del mensaje de Teams para compartir reunión con un usuario de Skype Empresarial](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Tras la aceptación, se colocarán en la reunión de Teams; deben empezar a compartir desde la bandeja de uso compartido de la reunión.

Mientras tanto, el usuario de Skype Empresarial recibe un mensaje de chat entrante con el vínculo a la reunión y se le guía para unirse.

Esta escala a una reunión de Teams está disponible tanto para la interoperabilidad en el espacio empresarial como para las llamadas y chats federados entre inquilinos. Está en la opción predeterminada y no hay ninguna configuración que el administrador tenga que aprovisionar. Sin embargo, se desactivará para el usuario si el administrador ``-AllowPrivateMeetNow`` establece en ``CsTeamsMeetingPolicy`` ``$false`` .

Después de revisar este artículo, vea Elegir el viaje de [actualización,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)Instrucciones [](./setting-your-coexistence-and-upgrade-settings.md) de migración e interoperabilidad, [](./migration-interop-guidance-for-teams-with-skype.md)Coexistencia con Skype [Empresarial](coexistence-chat-calls-presence.md)y Establecer la configuración de coexistencia y actualización para obtener detalles de implementación. También se recomienda el siguiente vídeo: [Vídeo: Administrar la coexistencia y la interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Detalles técnicos de teams y coexistencia de Skype Empresarial

En las secciones siguientes se resume el comportamiento que se puede experimentar al ejecutar clientes de Teams y Skype Empresarial en la misma organización, independientemente del modo y del método de actualización que se usa:

- [Reuniones](#meetings)
- [Interoperabilidad](#interoperability)
- [Interoperabilidad frente a hilos de conversación nativos](#interop-versus-native-conversation-threads)
- [Presence](#presence)
- [Federación](#federation)
- [Contactos](#contacts)

### <a name="meetings"></a>Reuniones

Independientemente de su modo, los usuarios siempre pueden unirse a cualquier tipo de reunión a la que estén invitados, ya sea Skype Empresarial o Teams.  Sin embargo, los usuarios deben unirse a la reunión con un cliente correspondiente que coincida con el tipo de reunión:

- Si la reunión es una reunión de Teams, todos los participantes (ya sean usuarios de TeamsOnly, Islas o Skype Empresarial) usan el cliente de Teams para unirse a la reunión. Si Teams no está instalado, el usuario se dirigirá a la web al intentar unirse a una reunión.

- Si la reunión es una reunión de Skype Empresarial, todos los participantes (ya sean usuarios de TeamsOnly, Islas o Skype Empresarial) usan el cliente de Skype Empresarial para unirse a la reunión. Si el cliente de Skype Empresarial no está instalado, se dirigirá al usuario a la web para que se una a través de la aplicación de reunión de Skype.

Al organizar reuniones, el tipo de reunión que se programa se basa en el modo del organizador, como se muestra en la tabla siguiente:

| Modo de organizador    |      Comportamiento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas las reuniones programadas en Teams. El complemento de Skype Empresarial no está disponible en Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas las reuniones programadas en Skype Empresarial. El complemento teams no está disponible en Outlook. | 
| Aplicaciones aisladas | De forma predeterminada, las reuniones se pueden programar en Skype Empresarial o en Teams. Ambos complementos están disponibles en Outlook. Sin embargo, opcionalmente, puede requerir que los usuarios de islas siempre programen reuniones en Teams asignándolos una instancia de TeamsMeetingPolicy con preferredMeetingProviderForIslandsMode=Teams.| 


### <a name="interoperability"></a>Interoperabilidad

Como se describe anteriormente en [Interoperabilidad de Teams y Skype Empresarial,](#interoperability-of-teams-and-skype-for-business)Teams admite la interoperabilidad con Skype Empresarial en determinados escenarios. La comunicación de interoperabilidad hace referencia a un chat o llamada entre un usuario de Skype Empresarial y un usuario de Teams.  La comunicación de interoperabilidad solo es posible entre dos usuarios; No se admiten chats o llamadas de varias partes o la adición de usuarios adicionales.

Se crea un chat de interoperabilidad o una llamada entre dos usuarios cuando cada uno de los siguientes son verdaderos:

- Un usuario usa Teams y el otro usa Skype Empresarial.

- El modo del destinatario de la comunicación inicial es ISLAS NO (de lo contrario, la comunicación llegaría al mismo cliente) si ambos usuarios están en la misma organización. En escenarios federados, el usuario remitente usa Teams y el destinatario no está en modo TeamsOnly. 

- El usuario de Teams TAMPOCO tiene una cuenta de Skype Empresarial alodada localmente.

Dentro de la comunicación de interoperabilidad, el chat solo es de texto sin formato. Además, el uso compartido de archivos y el uso compartido de pantalla no son *posibles en el chat de interoperabilidad.* Sin embargo, los usuarios de una conversación de interoperabilidad pueden lograr fácilmente el uso compartido de archivos y/o pantalla creando una reunión a petición, desde el chat de interoperabilidad, como se describe a continuación:

- Si el usuario de Teams intenta compartir su pantalla, se crea automáticamente una reunión de Teams a petición y se envía un vínculo de invitación a esa reunión al cliente del usuario de Skype Empresarial. Al hacer clic en el vínculo, el usuario de Skype Empresarial abrirá Teams y se unirá a la reunión. Ambos usuarios se encuentran ahora en una reunión de Teams y pueden compartirlos según sea necesario.

- Si el usuario de Skype Empresarial usa un cliente de 2018 o posterior e intenta compartir contenido, se crea automáticamente una reunión de Skype Empresarial a petición y se envía un vínculo de invitación a esa reunión al cliente del usuario de Teams. Al hacer clic en el vínculo, el usuario de Teams intentará unirse a la reunión de Skype Empresarial. Si el usuario de Teams tiene instalado el cliente de Skype Empresarial, se abrirá y se le pedirá que inicie sesión (si aún no ha iniciado sesión).  Si el usuario de Teams no tiene instalado el cliente de Skype Empresarial, se le pedirá que use la versión web. Una vez que ambos usuarios han iniciado sesión, se encuentran en una reunión de Skype Empresarial y pueden compartirlos según sea necesario.

### <a name="interop-versus-native-conversation-threads"></a>Interoperabilidad frente a hilos de conversación nativos

Como las comunicaciones de interoperabilidad no admiten todas las características de la conversación nativa de Teams, el cliente de Teams mantiene conversaciones independientes para la comunicación de Teams a Teams y Teams-to-Skype Empresarial. Estas conversaciones se representan de forma diferente en la interfaz de usuario: los hilos de interoperabilidad se pueden diferenciar de un hilo nativo normal de Teams:

- Falta de controles para texto enriquecido, uso compartido de archivos/pantalla, incapacidad para agregar usuarios.
- Una modificación del icono del usuario de destino, que muestra una "S" para Skype Empresarial.

Estas diferencias se muestran en las siguientes capturas de pantalla:

Una conversación nativa de Teams a Teams con prueba G3 de usuario

![Diagrama que muestra una conversación nativa de Teams a Teams](media/teams-upgrade-native-thread.png)

Una conversación de interoperabilidad con la misma prueba G3 de usuario

![Diagrama que muestra una conversación de interoperabilidad de Teams a Teams](media/teams-upgrade-interop-thread.png)

Una vez que se crea un hilo de conversación, su tipo nunca cambia. Una vez creado, un hilo de interoperabilidad en Teams siempre se dirigirá al cliente de Skype Empresarial del usuario de destino. Una conversación nativa siempre se dirigirá al cliente de Teams del usuario de destino.  Si cambia el modo de un usuario destinatario, los hilos existentes de Teams para ese usuario ya no funcionarán y se mostrará una nota en ese chat con un vínculo para iniciar una nueva conversación nativa, como se muestra en la siguiente captura de pantalla.

![Diagrama que muestra un chat con el usuario actualizado de Skype Empresarial](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presence

La presencia de un usuario determinado se basa en la actividad del usuario en el servicio a través del cliente. A continuación, se publica la presencia para que otros usuarios puedan verlo.  Skype Empresarial y Teams son servicios independientes con clientes independientes, por lo que cada servicio tiene su propio estado de presencia para un usuario.   También hay sincronización entre los servicios de presencia en Teams y en Skype Empresarial Online.  Esto permite que un servicio pueda publicar la presencia del usuario del otro servicio si es necesario. 

El comportamiento de publicación de presencia se basa en el modo del usuario. Hay tres casos básicos:

- Si un usuario está en modo TeamsOnly, todos los demás usuarios verán la presencia de Teams para ese usuario, independientemente del cliente que usen.

- Si un usuario está en cualquiera de los modos de Skype Empresarial, todos los demás usuarios verán la presencia de Skype Empresarial para ese usuario, independientemente del cliente que usen.

- Si un usuario está en modo Islas, la presencia publicada en Skype Empresarial y Teams es independiente, por lo que la presencia que se muestra a los usuarios de la misma organización dependerá del cliente del otro usuario. Los usuarios de organizaciones federadas verán la presencia de ese usuario en función de su actividad de Skype Empresarial, ya que el tráfico federado a un usuario en modo Islas se instalará en Skype Empresarial.

Por ejemplo, supongamos que el usuario A está en modo Islas. Si el usuario A está activo en Teams pero no ha iniciado sesión en Skype Empresarial, otros usuarios verían el usuario A como activo desde su cliente de Teams, pero en su cliente de Skype Empresarial verían el usuario A como sin conexión. Esto se hace por diseño, ya que no se puede llegar al usuario A si no ejecuta el cliente. 


### <a name="federation"></a>Federación

La federación de Teams a otro usuario que use Skype Empresarial requiere que el usuario de Teams se alome en línea en Skype Empresarial. TeamsUpgradePolicy controla el enrutamiento de las llamadas y chats federados entrantes. El comportamiento de enrutamiento federado es el mismo que para los escenarios de espacio empresarial, excepto en el modo "aplicaciones aisladas". Cuando los destinatarios están en modo Aplicaciones aisladas:

- Los chats y las llamadas iniciadas desde Teams se inician en Skype Empresarial si el destinatario se encuentra en un inquilino federado.
- Chats y llamadas iniciadas desde Teams llegan a Teams si el destinatario está en el mismo espacio empresarial.
- Los chats y las llamadas iniciadas desde Skype Empresarial siempre se inician en Skype Empresarial.

Un chat federado puede ser un hilo nativo o un hilo de interoperabilidad. Vea [Interoperabilidad frente a hilos de conversación nativos.](#interop-versus-native-conversation-threads)

- Si el receptor y el remitente están en modo de actualización de TeamsOnly, la conversación será una experiencia de chat nativa que incluye todas las funciones enriquecciones de mensajería y llamadas. Para obtener más información, lea [Experiencia de chat nativa para usuarios externos (federados) en Teams.](native-chat-for-external-users.md) 

- Si alguno de los participantes de la conversación NO está en el modo de actualización de TeamsOnly, la conversación seguirá siendo una experiencia de interoperabilidad con mensajes de solo texto. La interfaz de usuario expone chats federados de forma similar a los hilos de interoperabilidad del mismo inquilino, excepto que hay una nota que indica que el usuario es externo.

Para obtener más información, vea [Administrar el acceso externo](manage-external-access.md) en Microsoft Teams y experiencia de chat nativa para usuarios [externos (federados) en Teams.](native-chat-for-external-users.md)

### <a name="contacts"></a>Contactos

Teams y Skype Empresarial tienen listas separadas de contactos. Esto significa que las adiciones, eliminaciones y modificaciones de contactos realizadas en un sistema no se sincronizan con el otro sistema. Sin embargo, los contactos de Skype Empresarial se copian automáticamente en Teams cuando se produce uno de los dos eventos específicos: 

- Para cualquier usuario de Skype Empresarial Online, la primera vez que inicie sesión en Teams, los contactos de Skype Empresarial se copiarán en Teams.  Este comportamiento no está disponible para los usuarios con una cuenta local en Skype Empresarial Server.  

- Después de actualizar un usuario a TeamsOnly (ya sea mediante la asignación de TeamsUpgradePolicy o a través de Move-CsUser -MoveToTeams), la próxima vez que un usuario inicie sesión en Teams, los contactos existentes en Skype Empresarial se combinarán con los contactos existentes ya en Teams. Este comportamiento ocurre si la cuenta de Skype Empresarial del usuario se encuentra en casa local o en línea. 

En ambos casos, la transferencia de contactos de Skype Empresarial a Teams es asíncrona, por lo que puede que sea unos minutos antes de que los contactos aparezcan en Teams. Los dos eventos anteriores son los que desencadenan la copia.  

### <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)