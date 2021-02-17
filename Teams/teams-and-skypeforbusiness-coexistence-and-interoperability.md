---
title: Interoperabilidad entre Skype Empresarial y Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalles de las opciones de coexistencia de Skype Empresarial y Microsoft Teams, y la interoperabilidad resultante entre Skype Empresarial y Teams.
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
ms.openlocfilehash: 7ffc673ade43e8acdb258c9364b3023ba21da2a7
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260352"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprender la coexistencia e interoperabilidad de Microsoft Teams y Skype Empresarial

![Diagrama de itinerario de actualización, énfasis en la fase de definición del proyecto](media/upgrade-banner-project-definition.png "Fases del itinerario de la actualización, con énfasis en la fase de definición del proyecto")

Este artículo forma parte de la fase de definición de proyecto de su vía de actualización. Complete después de crear una campaña de patrocinio y un equipo de proyecto, y defina el ámbito, los objetivos y el plan para el proyecto. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)

Si su organización usa Skype Empresarial hoy y está empezando a usar Teams junto con Skype Empresarial o está empezando a actualizar a Teams, es importante comprender los siguientes elementos:

- Cómo coexisten las dos aplicaciones.
- Cuándo y cómo interactúan.
- Cómo administrar la migración de los usuarios hasta su actualización final de Skype Empresarial a Teams.

> [!Tip]
> Vea la siguiente sesión para obtener información sobre [coexistencia e interoperabilidad.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Además, puede unirse a nosotros en talleres interactivos y en directo en los que compartiremos orientación, procedimientos recomendados y recursos diseñados para iniciar la planeación e implementación de actualizaciones.
>
> Para empezar, únase en primer lugar a la sesión [Planificar la actualización](https://aka.ms/SkypeToTeamsPlanning).

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistencia de Teams y Skype Empresarial

 Teams ofrece funcionalidades de colaboración, chat, llamadas y reuniones. Dependiendo de cómo elija implementar Teams, estas funcionalidades pueden superponerse a las que ofrece Skype Empresarial para un usuario determinado. El modo predeterminado es ejecutar Teams junto con Skype Empresarial con las funcionalidades superpuestas. Sin embargo, se puede asignar a un usuario uno de los diferentes modos de coexistencia (también conocidos como modos de actualización) que se diseñaron para garantizar que estas capacidades no se superponen para ese usuario (en cuyo caso está disponible la interoperabilidad entre Teams y Skype Empresarial). Por ejemplo, si tiene activos locales [significativos](meetings-first.md) de Skype Empresarial Server con una implementación de Telefonía IP empresarial compleja, pero desea que los usuarios disfruten de las reuniones modernas lo antes posible, es posible que desee evaluar Reuniones primero como una ruta alternativa.

Le recomendamos que revise los siguientes modos de coexistencia para ayudar a determinar qué ruta es la adecuada para su organización.

> [!Important]
> La introducción de nueva tecnología o la realización de cambios en su entorno de Skype Empresarial existente y familiar, a la vez que ofrece nuevos beneficios empresariales excelentes, puede interrumpir a los usuarios. Dedime tiempo para evaluar la disponibilidad del usuario e implementar un plan de comunicación y aprendizaje antes de implementar cualquiera de los cambios descritos en este artículo. Además, le animamos encarecidamente a realizar una prueba piloto de su plan con un grupo de usuarios seleccionado antes de implementarlo en toda la organización.

### <a name="islands-mode"></a>Modo de islas

De forma predeterminada, los usuarios pueden ejecutar Teams junto con Skype Empresarial como dos soluciones independientes que ofrecen capacidades similares y superpuestas. Las funciones incluyen presencia, chat, llamadas y reuniones. Los usuarios de Teams también pueden aprovechar las nuevas capacidades de colaboración, como los equipos y canales, el acceso a archivos en Microsoft 365 u Office 365 y las aplicaciones.

En este modo de coexistencia, denominado **Islas,** cada una de las aplicaciones cliente funciona como una isla independiente. Skype Empresarial habla con Skype Empresarial y teams habla con Teams. Se espera que los usuarios ejecuten ambos clientes en todo momento y que puedan comunicarse de forma nativa en el cliente desde el que se inició la comunicación. Por lo tanto, no es necesario ningún tipo de interoperabilidad en el **modo islas.**

Para evitar una experiencia de Skype Empresarial confusa o regresión, Skype Empresarial administra las integraciones siguientes que no se administran en el **modo** de Islas Teams:

- Comunicaciones externas (federadas).
- Servicios de voz RTC y aplicaciones de voz, integración de Office.
- Controles HID para dispositivos USB.
- Otras muchas integraciones.  

Sistema telefónico no es compatible con Teams en el **modo de Islas.** **El** modo Islas no admite Telefonía IP empresarial cliente es Skype Empresarial.

> [!Important]
> En **el modo** Islas, todos los mensajes y llamadas de usuarios federados (personas fuera de su organización) se entregan a Skype Empresarial. Después de actualizar **al modo Solo** equipos, todos los mensajes y llamadas de fuera de su organización se entregan a Teams.

> [!Tip]
> La ruta recomendada por los clientes de  Skype Empresarial Online es comenzar con el modo predeterminado de islas, impulsar la saturación de adopción de Teams en la organización y, a continuación, pasar rápidamente al modo solo de **Teams.** Los clientes locales e híbridos, especialmente los más complejos, podrían beneficiarse al implementar  el modo de colaboración de Skype Empresarial con **Teams** como punto de partida en lugar  del modo Islas y avanzar desde allí hasta el modo Skype Empresarial con colaboración y reuniones de **Teams** (es decir, Reuniones en primer lugar), si corresponde, y al modo Solo equipos cuando la organización esté lista para adoptar Teams.

### <a name="teams-only"></a>Solo equipos

Un **usuario solo de Teams** (también llamado usuario actualizado) tiene acceso a todas las capacidades de Teams.  Pueden conservar el cliente de Skype Empresarial para unirse a reuniones en Skype Empresarial que hayan sido organizadas por usuarios no actualizados o partes externas. Un usuario actualizado puede seguir en contacto con otros usuarios de la organización que aún usan Skype Empresarial mediante las capacidades  de interoperabilidad entre Teams y Skype Empresarial (siempre que los usuarios de Skype Empresarial no estén en modo Islas). Sin embargo, un usuario actualizado no puede iniciar un chat, una llamada o una reunión de Skype Empresarial.

Tan pronto como su organización esté lista para que algunos o todos los usuarios usen Teams como su única herramienta de comunicaciones y colaboración, actualice esos usuarios al **modo Solo** equipos. Si va a actualizar desde el modo **Islas,** le recomendamos que saturar primero la adopción de Teams en toda la organización antes de comenzar el proceso de actualización. Esta adopción evita los escenarios de comunicación rotos debido a **que el** modo Islas no proporciona interoperabilidad.

En el **modo Solo equipos,** Teams es la aplicación predeterminada para el protocolo SIP/tel. Teams administra los vínculos de la tarjeta de contacto de un usuario en Outlook para llamadas o chats.

Para ver consideraciones adicionales sobre cómo pasar **al modo Solo** equipos, vea las consideraciones del modo Solo [equipos.](teams-only-mode-considerations.md)

![Captura de pantalla del mensaje de confirmación de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente de Skype Empresarial que se ejecuta en modo especial después de actualizar el usuario como usuario solo de Teams")

### <a name="skype-for-business-only"></a>Solo Skype Empresarial

En este modo de coexistencia, los usuarios permanecen en Skype Empresarial (no Teams) para funcionalidades de chat, reuniones y llamadas, y no usan Teams para equipos y canales. Este modo está disponible hoy; sin embargo, en la implementación actual, los equipos y canales no se desactivarán automáticamente para el usuario. Esto puede lograrse usando la directiva de configuración de la aplicación para ocultar equipos y archivos.

Este modo puede usarse antes de iniciar una implementación administrada de Teams para evitar que los usuarios empiecen a usar Teams antes de haber creado la preparación. Este modo también es una forma de habilitar la participación autenticada en las reuniones de Teams para los usuarios de Skype Empresarial, siempre que los usuarios tienen licencia para Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype Empresarial con colaboración de Teams

Use este modo para presentar Teams en su entorno mientras continúa usando su inversión existente en Skype Empresarial. Deje Skype Empresarial sin cambios para las funcionalidades de chat, llamadas y reuniones. Agregar capacidades de colaboración de Teams:

- Equipos y canales.
- Acceso a archivos en Microsoft 365 u Office 365.
- Aplicaciones. Capacidades de comunicaciones de Teams: chat privado, llamadas y programación de reuniones.

El chat privado, las llamadas y la programación de reuniones en Teams están desactivados de forma predeterminada en este modo.

Las organizaciones con un punto de partida de Skype Empresarial Server  local o híbrido deben considerar este modo como una alternativa al modo islas si quieren ofrecer a sus usuarios interoperabilidad y  predictibilidad para sus comunicaciones, así como tener una escala de tiempo predecible para su actualización a Teams (en lugar de depender de la saturación de adopción en el modo islas).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype Empresarial con colaboración y reuniones de Teams, también conocido como Reuniones en primer lugar

Use este modo de coexistencia para acelerar la disponibilidad de las capacidades de reunión y colaboración de Teams en su organización. El modo de coexistencia permite a los usuarios aprovechar la experiencia superior de reuniones de Teams:

- Muy buena calidad.
- Transcripción y traducción.
- Fondo difuminado.
- Experiencia de usuario superior en todas las plataformas, incluidos los dispositivos móviles y los exploradores.

Además de usar Teams para conversaciones basadas en canales y equipos en este modo, los usuarios usarán Teams para programar y llevar a cabo sus reuniones. Las llamadas y chats privados permanecen en Skype Empresarial. Teams y Skype Empresarial se benefician de una gama de funcionalidades "juntos mejor", como la conciliación de presencia, la retención automática y la compatibilidad con dispositivos HID en ambas aplicaciones. Es posible ocultar equipos y canales, si lo desea, con la directiva de configuración de la aplicación.

Este modo de coexistencia es especialmente útil para las organizaciones con implementaciones locales de Skype Empresarial con Telefonía IP empresarial. Es probable que estas organizaciones dedímen algún tiempo a actualizar a Teams y quieran aprovechar lo antes posible las reuniones superiores de Teams.

> [!TIP]
> Para ayudarle a identificar el modo de actualización recomendado en función de las funciones que desea habilitar en Teams mientras skype empresarial todavía está en uso, aproveche el Asistente para actualización de Skype a [Teams.](https://aka.ms/SkypeToTeamsWizard)

Para obtener más información sobre los modos de coexistencia, los requisitos previos y la administración, consulte la guía de migración e interoperabilidad para las organizaciones que usan Teams junto con [Skype](https://aka.ms/SkypeToTeams-Interop) Empresarial y cómo configurar su coexistencia y [actualización.](https://aka.ms/SkypeToTeams-SetCoexistence)

|Icono de punto de decisión |Definición de icono |Descripción |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto de decisión|<ul><li>¿Qué modo(s) de coexistencia se adapta mejor a las necesidades de su organización y de los usuarios?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Paso siguiente|<ul><li>Elija el mejor método para su viaje de actualización.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidad de Teams y Skype Empresarial

La interoperabilidad es la capacidad de los usuarios de Teams y Skype Empresarial en la misma organización de comunicarse entre Teams y Skype Empresarial.

La interoperabilidad se rige por el modo de coexistencia (también conocido como modo de actualización) del receptor. No hay ninguna interoperabilidad cuando el receptor está en modo **islas.**

> [!Note]
> Cuando se implementan en un modo de coexistencia excepto en las **Islas,** Teams y Skype Empresarial pueden [interactuar,](#interoperability-of-teams-and-skype-for-business)lo que permite a los usuarios chatear con ellos y llamarse entre sí, y garantizar que las comunicaciones permanezcan fluidas en toda la organización durante el viaje de actualización a Teams. Los modos de coexistencia rigen la interoperabilidad. El modo de coexistencia del receptor determina si la interoperabilidad estará disponible. Por ejemplo, si el receptor está en un modo en que el chat solo está disponible en un cliente (por ejemplo, Teams), la interoperabilidad del chat estará generalmente disponible en caso de que la conversación use el otro cliente (en este caso, Skype Empresarial) para iniciar el chat. Por otro lado, si el receptor está en el modo en que el chat está disponible en ambos clientes (modo Islas), la interoperabilidad no estará disponible para el chat. El receptor recibirá el mensaje en el mismo cliente en el que el destinatario ha iniciado el chat. Por lo tanto, una comunicación correcta **en el modo de** islas requiere la saturación de la adopción de Teams; es decir, todos los usuarios usan y supervisan activamente ambos clientes.

> [!Note]
> **Para tener la experiencia de coexistencia más reciente, la versión del cliente debe ser el cliente disponible más reciente en el canal de implementación de Office del usuario.**

### <a name="native-interop-and-interop-escalation"></a>Interoperabilidad nativa y escalación de interoperabilidad

Existen dos tipos de experiencias de interoperabilidad: nativa y escalación de interoperabilidad.

- Una _experiencia de interoperabilidad_ nativa tiene lugar en el cliente que el usuario está usando actualmente. Un usuario estará en el cliente de Skype Empresarial y el otro en Teams. Una experiencia de interoperabilidad nativa no las llevará a otro cliente para comunicarse. Los usuarios podrán dirigir la conversación en el cliente que usan actualmente. Las experiencias de interoperabilidad nativas son llamadas y chats uno a uno.
- Una experiencia de _escalación_ de interoperabilidad significa que, como parte de la ayuda a los usuarios a realizar una acción avanzada (como compartir el escritorio), el cliente facilita la creación de una reunión a la que los usuarios pueden unirse para continuar la experiencia en dicha reunión. La reunión se crea en la plataforma de la web donde se crea la acción. El usuario o los usuarios que no están en esa plataforma reciben un vínculo para unirse a la reunión. Al hacer clic en este vínculo, se unirán a la reunión en un cliente compatible (explorador, aplicación web o cliente completo, según la configuración). La escala de interoperabilidad de Skype Empresarial requiere un cliente reciente. Ya está disponible la escala de interoperabilidad desde Teams. Ambos son compatibles con experiencias de interoperabilidad dentro del espacio empresarial y con comunicaciones federadas entre inquilinos.

### <a name="native-interop-experiences"></a>Experiencias de interoperabilidad nativas

Según los modos de coexistencia asignados a los usuarios (como se ha descrito anteriormente), están disponibles las siguientes experiencias de interoperabilidad nativas:

Los usuarios de Skype Empresarial pueden chatear uno a uno con los usuarios de Teams y viceversa. Un chat de interoperabilidad necesita pasar por una puerta de enlace de interoperabilidad que forma parte de los servicios en la nube de Teams (y, por tanto, solo existe en línea). Los chats de interoperabilidad son de texto sin formato: no se admiten texto enriquecido ni emoticonos. A los usuarios de Teams y Skype Empresarial se les notifica que la conversación es una conversación interoperabilidad.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Los usuarios de Skype Empresarial pueden realizar llamadas y videollamadas uno a uno a los usuarios de Teams, y los usuarios de Teams pueden hacer lo mismo.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Las experiencias de interoperabilidad con una implementación local de Skype Empresarial requieren que el entorno local esté en modo híbrido con Microsoft 365 u Office 365 Skype Empresarial. Para obtener más información, [vea las instrucciones sobre migración e interoperabilidad.](https://aka.ms/SkypeToTeams-Interop)

Estas **experiencias** de interoperabilidad están disponibles para y entre los usuarios que tienen asignados uno de los siguientes modos de coexistencia: Skype Empresarial con colaboración de **Teams,** Skype Empresarial con colaboración y reuniones de Teams, **Skype** Empresarial solo o Solo **equipos.** No hay interoperabilidad con los usuarios en el **modo Islas.**

### <a name="native-interop-experience-limitations"></a>Limitaciones de la experiencia de interoperabilidad nativa

Debido a la diferencia en los protocolos y la tecnología, no es posible admitir todas las capacidades de forma nativa. En concreto, las siguientes funcionalidades no están disponibles:

- Markdown, el texto enriquecido y el conjunto de emoticonos completo no son compatibles ni con Teams ni con Skype Empresarial. No se admiten otras características nativas del cuadro de redacción en los chats de Teams.
- La pantalla compartida (escritorio o uso compartido de aplicaciones) entre Teams y Skype Empresarial no se admite de forma nativa. Sin embargo, es compatible con la escala de interoperabilidad.
- Los chats grupales (conversaciones de varios participantes) en Teams solo pueden incluir participantes que estén usando Teams.
- Las conversaciones de mensajería instantánea de varios participantes (chats grupales) en Skype Empresarial solo pueden incluir participantes que estén usando Skype Empresarial. Sin embargo, la escala de interoperabilidad a varias partes está disponible desde Skype Empresarial.
- No se admite escalar una llamada de punto a punto o una videollamada continua a una llamada de varios participantes que implique a usuarios de Teams y Skype Empresarial.
- No se admite la transferencia de archivos para chats de dos participantes o datos adjuntos en chats grupales, de Teams a Skype Empresarial (y viceversa).
- No hay ninguna interoperabilidad con el chat persistente de Skype Empresarial.

Para todas estas limitaciones (excepto el chat persistente), una posible solución es que un usuario inicie una reunión e invite al otro usuario a unirse a ella.

Esta solución alternativa es la base para la escala de interoperabilidad. En particular, el uso compartido de la pantalla y la escala a varios partes no se pueden lograr de forma nativa, pero se admiten a través de la escala de interoperabilidad.

### <a name="interop-escalation-experiences"></a>Experiencias de escalación de interoperabilidad

La escalación de interoperabilidad consiste en complementar las capacidades de interoperabilidad nativa con escalaciones administradas a reuniones. Las reuniones ofrecen experiencias enriquectivas disponibles para cualquier persona, independientemente del cliente que tengan.

Cuando el usuario de Teams activa la escala de interoperabilidad, se crea una reunión de Teams. Cuando el usuario de Skype Empresarial lo activa, se crea una reunión de Skype Empresarial. En ambos casos, la reunión creada es una reunión **Reunirse** ahora, que no se refleja en el calendario del usuario.

La otra parte recibe el vínculo de unión a la reunión a través del chat interoperabilidad y las combinaciones haciendo clic en ese vínculo. Si el usuario de Skype Empresarial tiene una cuenta de Teams y es invitado por el usuario de Teams, se unirá a la reunión autenticada. En caso contrario, se unirán como participantes anónimos. Por el contrario, los usuarios de Teams casi siempre tienen una cuenta de Skype Empresarial y un cliente de Skype Empresarial que pueden usar para unirse a una reunión de Skype Empresarial como participante autenticado, pero también podrían unirse como participantes anónimos, por ejemplo, usando la aplicación Reunión de Skype.

Una vez que las partes se han unido a la reunión, pueden llevar a cabo cualquier actividad admitida en las reuniones, como compartir el escritorio o el contenido, compartir archivos o transferir, agregar otros participantes, y así sucesivamente.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalación de interoperabilidad de Skype Empresarial

La interoperabilidad y la escala de interoperabilidad de Skype Empresarial se actualizó en la compilación mensual C2R de julio de 2019. Anteriormente, Skype Empresarial no tenía el conocimiento anticipado de que la entidad remota estaba usando Teams. Solo se superó la señalización recibida tras establecer una sesión.

Cuando la señalización indicaba que la respuesta provenía (o a través) de la puerta de enlace interoperabilidad, se mostraría la barra de negocios amarilla (pancarta) que indicaba que la otra parte no estaba usando Skype Empresarial. Con la evolución de nuestro servicio, esto dio como resultado falsos positivos en los que los usuarios de Skype Empresarial veían la barra de negocio cuando estaban conectados al servicio de correo de voz en la nube u otros servicios de voz en la nube, en lugar de a un usuario real de **Teams Only.**

Para evitar estos falsos positivos, el servicio de presencia ahora informa al cliente de Skype Empresarial cuando la otra parte es solo un usuario real de **Teams.** Esto permite que Skype Empresarial tenga en cuenta que necesita crear una conversación de interoperabilidad antes de que se haya creado y que la ventana de conversación sea específica de interoperabilidad.

![Captura de pantalla del mensaje de Teams para crear una conversación interoperabilidad con un usuario de Skype Empresarial](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si el usuario de Skype Empresarial desea compartir su escritorio, por ejemplo, se le informará de que iniciaremos una reunión y le guiaremos por los pasos.

![Captura de pantalla del mensaje de Teams para iniciar una reunión con un usuario de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Mientras tanto, el usuario de Teams recibe un mensaje de chat entrante con el vínculo a la reunión y recibe instrucciones para unirse.

Este escalamiento a una reunión de Skype Empresarial está disponible tanto para la interoperabilidad en el espacio empresarial como para las llamadas federadas entre inquilinos y los chats. Está disponible de forma predeterminada y no hay ninguna configuración que el administrador tenga que aprovisionar.

#### <a name="interop-escalation-from-teams"></a>Escalación de interoperabilidad desde Teams

La escala de interoperabilidad de Teams a una reunión de Teams ahora está disponible cuando el usuario de Teams selecciona el botón compartir escritorio en un hilo de interoperabilidad dentro del espacio empresarial con un usuario de Skype Empresarial o en una conversación de federación de interoperabilidad entre inquilinos. La escala de interoperabilidad es compatible desde una conversación de chat 1:1 o desde una llamada 1:1.

Esta funcionalidad se admite en el cliente de escritorio de Teams para Windows, en el cliente de escritorio de Teams para Mac y en el cliente web de Teams en exploradores donde se admite el uso compartido de contenido, mientras que en las comunicaciones con cualquier versión del cliente de Skype Empresarial.

En conversaciones de interoperabilidad y en conversaciones de interoperabilidad de federación, el usuario de Teams ahora tiene los controles (botón) para iniciar el uso compartido de contenido. Cuando el usuario de Teams selecciona el botón, se muestra un menú adicional que le informa de que, para compartir contenido, tendrá que iniciar una reunión de Teams.

Si los usuarios se encontraban en una llamada, el menú también les advertirá de que su llamada actual entre Teams y Skype Empresarial finalizará cuando se pongan en una reunión de Teams. Si lo elige, puede avisar al usuario de Skype Empresarial antes de aceptarlo.

![Captura de pantalla del mensaje de Teams para compartir una reunión con un usuario de Skype Empresarial](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Tras la aceptación, se colocarán en la reunión de Teams; deben empezar a compartir desde la bandeja de uso compartido de la reunión.

Mientras tanto, el usuario de Skype Empresarial recibe un mensaje de chat entrante con el vínculo a la reunión y recibe instrucciones para unirse.

Este escalamiento a una reunión de Teams está disponible tanto para la interoperabilidad en el espacio empresarial como para las llamadas federadas y chats entre inquilinos. Está disponible de forma predeterminada y no hay ninguna configuración que el administrador tenga que aprovisionar. Sin embargo, se desactivará para el usuario si el administrador ``-AllowPrivateMeetNow`` lo ``CsTeamsMeetingPolicy`` establece en ``$false`` .

Después de revisar este artículo, vea estos artículos relacionados:

- [Elegir su recorrido de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Guía de migración e interoperabilidad](https://aka.ms/SkypeToTeams-Interop)
- [Coexistencia con Skype Empresarial](coexistence-chat-calls-presence.md)
-  [Establecer la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) para los detalles de la implementación.

## <a name="related-links"></a>Vínculos relacionados

[Vídeo: Administrar coexistencia e interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
