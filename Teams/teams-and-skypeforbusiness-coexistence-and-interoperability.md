---
title: Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalles de Skype Empresarial y las opciones de coexistencia de Microsoft Teams y la interoperabilidad resultante entre Skype Empresarial y Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: f91297a0b2fa5178195b10b61817cc11a30acfbc
ms.sourcegitcommit: 303579b3ecd4e0af43710d4b078610f63e9d0eca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2022
ms.locfileid: "68853368"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad

![Diagrama de recorrido de la actualización, en el que se hace hincapié en la fase de definición del proyecto.](media/upgrade-banner-project-definition.png "Fases del itinerario de la actualización, con énfasis en la fase de definición del proyecto")

Este artículo forma parte de la fase de definición de proyecto de su vía de actualización. Complete después de crear una coalición de patrocinadores y un equipo de proyecto y definir el ámbito, los objetivos y el plan para el proyecto. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)

Si su organización usa Skype Empresarial hoy y está empezando a usar Teams junto con Skype Empresarial (o está empezando a actualizar a Teams), es importante comprender cómo coexisten las dos aplicaciones, cuándo y cómo interoperan, y cómo administrar la migración de los usuarios hasta su actualización final desde Skype Empresarial a Teams.

> [!Tip]
> Vea la siguiente sesión para obtener información sobre [coexistencia e interoperabilidad](https://aka.ms/teams-upgrade-coexistence-interop).
>
> Además, puede unirse a nosotros para realizar talleres interactivos en directo en los que compartiremos orientación, mejores prácticas y recursos diseñados para iniciar la planeación e implementación de la actualización.
>
> Para empezar, únase en primer lugar a la sesión [Planificar la actualización](./upgrade-workshops-landing-page.yml).

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Coexistencia de Teams y Skype Empresarial información general

Desde la retirada de Skype Empresarial Online, todos los usuarios de una organización puramente en línea (es decir, una organización que no tiene una implementación local de Skype Empresarial) tienen un modo de existencia conjunto de TeamsOnly. El modo TeamsOnly garantiza que los usuarios tengan la funcionalidad completa de Teams. Sin embargo, las organizaciones con una implementación local de Skype Empresarial Server pueden tener usuarios que todavía están alojados en local; estos usuarios no pueden ser TeamsOnly. Los usuarios con una cuenta de Skype Empresarial Server local pueden tener un modo de coexistencia *distinto de TeamsOnly.* En las siguientes secciones se describen los modos de coexistencia que están disponibles antes de decidir actualizar localmente Skype Empresarial Usuarios a TeamsOnly, y las capacidades que ofrece cada modo. Además, en las secciones se describe la interoperabilidad (interoperabilidad) que se produce entre los usuarios de Skype Empresarial clientes y los usuarios de los clientes de Teams, y cómo afecta la interoperabilidad al modo de coexistencia elegido.

Teams ofrece capacidades de colaboración, chat, llamadas y funcionalidades de reunión.  La funcionalidad de chat, llamadas y reuniones también estaba disponible históricamente en Skype Empresarial. En función de la configuración que elija al proporcionar Teams, estas capacidades se pueden superponer con las funcionalidades proporcionadas por Skype Empresarial para un usuario determinado. El modo de coexistencia predeterminado para los usuarios locales es Islas. El modo islas permite al usuario ejecutar Teams junto con Skype Empresarial con funciones similares disponibles en ambos clientes, es decir, las capacidades se superponen. Sin embargo, se puede asignar a un usuario otros modos de coexistencia para evitar que esta funcionalidad se superponga para el usuario, en cuyo caso la interoperabilidad entre Teams y Skype Empresarial está disponible. Por ejemplo, si tiene una Skype Empresarial Server activos locales con una implementación Telefonía IP empresarial compleja, pero desea que los usuarios disfruten de las reuniones modernas lo antes posible, es posible que desee evaluar el uso de la Skype Empresarial con el modo de colaboración y reuniones de Teams, también conocido como [ Reuniones en primer lugar](meetings-first.md).

Le recomendamos que revise los siguientes modos de coexistencia para ayudar a determinar qué ruta es la adecuada para su organización.

> [!Important]
> Los modos de coexistencia siguen existiendo tras la retirada de Skype Empresarial Online, pero los usuarios alojados en línea solo pueden tener un modo de TeamsOnly. Ya no es posible asignar ningún modo distinto de TeamsOnly a un usuario alojado en línea.  Como era el caso antes de la retirada de Skype Empresarial Online, a los usuarios alojados en local se les puede asignar cualquier modo *que no sea TeamsOnly*.


### <a name="teams-only"></a>Solo Teams

**Teams Only** es el único modo disponible para los usuarios en línea puros. Un usuario **de Teams solo** (en el pasado, a veces denominado usuario *actualizado*) tiene acceso a todas las capacidades de Teams y puede seguir comunicándose con cualquier otro usuario (ya sea en la misma organización o en una organización externa) que sigan usando Skype Empresarial (siempre que los usuarios de Skype Empresarial no estén en modo **Islas**). **Teams Solo** los usuarios reciben llamadas y chats entrantes en Teams y también programan reuniones en Teams. No pueden iniciar chats o llamadas ni programar reuniones en Skype Empresarial. 

**Teams Solo** los usuarios pueden conservar el Skype Empresarial cliente para unirse a Skype Empresarial reuniones que ya tengan o puedan recibir en el futuro (es decir, de terceros o posiblemente de usuarios locales Skype Empresarial Server de su propia organización). *Sin embargo, después de que Microsoft quite la infraestructura de Skype Empresarial Online para un usuario determinado de Teams, solo los usuarios de Teams solo podrán unirse a Skype Empresarial reuniones de forma anónima.* Después del 30 de junio de 2022, los usuarios recién creados de TeamsOnly ya no recibirán el aprovisionamiento de la infraestructura de Skype Empresarial Online. Si se les invita a estos usuarios a una reunión de Skype Empresarial, tendrán que unirse de forma anónima. Después de octubre de 2022, los usuarios movidos de local a la nube (es decir, se convierten en TeamsOnly) ya no se aprovisionarán con el Skype Empresarial infraestructura en línea.  Si se invita a estos usuarios a una reunión de Skype Empresarial, también tendrán que unirse de forma anónima.

Tan pronto como su organización esté lista para que algunos o todos los usuarios usen Teams como su única herramienta de comunicaciones y colaboración, actualice esos usuarios al modo **Solo teams** . Si está actualizando desde el modo **Islas** , le recomendamos que primero saturará la adopción de Teams en toda la organización antes de comenzar el proceso de actualización. Esta adopción evita escenarios de comunicación rotos debido a que **el modo Islas** no proporciona interoperabilidad.

Cuando se encuentra en el modo **Solo equipos** , Teams es la aplicación predeterminada para el protocolo SIP/Tel. Teams administra los vínculos de la tarjeta de contacto de un usuario en Outlook para llamadas o chats.

Para ver consideraciones adicionales sobre cómo cambiar al modo **Solo teams** , consulte [Consideraciones del modo solo de Teams](teams-only-mode-considerations.md).

![Captura de pantalla del mensaje de confirmación de Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype Empresarial cliente que se ejecuta en un modo especial después de actualizar el usuario como usuario de Teams")


### <a name="islands-mode"></a>Modo islas

En **el modo Islas**, los usuarios pueden ejecutar Teams junto con Skype Empresarial como dos soluciones independientes que ofrecen capacidades similares y superpuestas. Entre las funcionalidades se incluyen presencia, chat, llamadas y reuniones. Los usuarios de Teams también pueden aprovechar las nuevas capacidades de colaboración, como equipos y canales, acceso a archivos en Microsoft 365 y aplicaciones.

En este modo de coexistencia, cada una de las aplicaciones cliente funciona como una isla independiente. Skype Empresarial conversaciones con Skype Empresarial y Teams con Teams. Se espera que los usuarios ejecuten ambos clientes en todo momento y pueden comunicarse de forma nativa en el cliente desde el que se inició la comunicación. Por lo tanto, no hay necesidad de interoperabilidad en el modo **islas** .

Para evitar una experiencia de Skype Empresarial confusa o regresiva, el Skype Empresarial controla las siguientes integraciones que no se gestionan en el modo **islas** de Teams:

- Comunicaciones externas (federadas).
- Servicios de voz RTC y aplicaciones de voz, integración de Office.
- Controles HID para dispositivos USB.
- Otras integraciones.

Teléfono Microsoft Teams Sistema no es compatible con Teams en el modo **islas**. 

> [!Important]
>  - En **el modo Islas**, todos los mensajes y llamadas de los usuarios federados (personas de fuera de la organización) se entregan a Skype Empresarial. Después de actualizar al modo **Solo teams** , todos los mensajes y llamadas de fuera de su organización se entregan a Teams.
>  - Es posible que desee exigir que los usuarios de las islas programen siempre reuniones en Teams asignándoles una instancia de TeamsMeetingPolicy con preferredMeetingProviderForIslandsMode=Teams. Esto garantiza que todos los usuarios programen reuniones con Teams, que admite el inicio de sesión autenticado y la unión a reuniones para cualquier usuario de la organización, independientemente de si el usuario es TeamsOnly o sigue usando Skype Empresarial Server. En cambio, después de que Microsoft retire la infraestructura heredada Skype Empresarial Online para organizaciones híbridas a partir de octubre de 2022, los usuarios de TeamsOnly solo podrán unirse a Skype Empresarial reuniones de forma anónima.


### <a name="skype-for-business-only"></a>Solo Skype Empresarial

En este modo de coexistencia, los usuarios permanecen en Skype Empresarial (no Teams) para las funcionalidades de chat, reunión y llamada, y no usan Teams para equipos y canales. Este modo está disponible hoy; sin embargo, en la implementación actual, los equipos y canales no se desactivan automáticamente para el usuario. Esto se puede lograr usando la directiva de configuración de aplicaciones para ocultar equipos y archivos.

Este modo se puede usar antes de iniciar una implementación administrada de Teams para impedir que los usuarios empiecen a usar Teams con antelación a la preparación integrada. Este modo también es una forma de habilitar la participación autenticada en las reuniones de Teams para Skype Empresarial usuarios, siempre que los usuarios tengan licencia para Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype Empresarial con la colaboración de Teams

Use este modo para presentar Teams en su entorno mientras sigue usando su inversión existente en Skype Empresarial. Deje Skype Empresarial sin cambios para las capacidades de chat, llamadas y reuniones. Agregue las capacidades de colaboración de Teams:

- Equipos y canales.
- Acceso a archivos en Microsoft 365 o Office 365.
- Aplicaciones. Capacidades de comunicaciones de Teams: chat privado, llamadas y programación de reuniones.

El chat privado, las llamadas y la programación de reuniones de Teams están desactivados de forma predeterminada en este modo.

Las organizaciones que empiezan con Skype Empresarial Server locales tienen este modo como alternativa al modo **Islas** si quieren proporcionar a sus usuarios interoperabilidad y previsibilidad para sus comunicaciones durante la migración. Este modo también proporciona una escala de tiempo predecible para su actualización a Teams (en lugar de depender de la saturación de adopción en **el modo Islas** ).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype Empresarial con reuniones y colaboración de Teams, también conocidas como Reuniones en primer lugar

En este modo, las funciones de llamada y chat privado permanecen en Skype Empresarial mientras que Teams se usa para programar y realizar reuniones, así como para colaborar mediante conversaciones basadas en canales.  Este modo de coexistencia ayuda a acelerar la disponibilidad de las capacidades de reunión y colaboración de Teams en su organización y permite a los usuarios aprovechar la experiencia superior de reuniones de Teams:

- Gran calidad.
- Transcripción y traducción.
- Fondo borroso.
- Experiencia de usuario superior en todas las plataformas, incluidos dispositivos móviles y exploradores.

Teams y Skype Empresarial beneficiarse de una gama de funcionalidades "mejor juntas", como la conciliación de presencia, la retención/retención automática y la compatibilidad con dispositivos HID en ambas aplicaciones. Si lo desea, puede ocultar equipos y canales mediante la directiva de configuración de aplicaciones de Teams.

Este modo de coexistencia es especialmente útil para organizaciones con Skype Empresarial implementaciones locales con Telefonía IP empresarial. Es probable que estas organizaciones tarden algún tiempo en actualizar a Teams y quieran beneficiarse de las reuniones de Teams superiores lo antes posible.

> [!NOTE]
> A partir de octubre de 2022, se recomienda este modo para todos los usuarios locales a los que se asignó anteriormente **Skype Empresarial Solo** o **Skype Empresarial con** los modos de colaboración de Teams. Este modo ofrece la misma funcionalidad que los otros dos, excepto que las reuniones nuevas programadas por el usuario serán reuniones de Teams en lugar de reuniones Skype Empresarial. Esto garantiza que los usuarios programen sus reuniones como reuniones de Teams, que admite el inicio de sesión autenticado y la unión a reuniones para cualquier usuario de la organización, independientemente de si el usuario es TeamsOnly o sigue usando Skype Empresarial Server.  En cambio, a medida que Microsoft retira la infraestructura heredada de Skype Empresarial Online, los usuarios de TeamsOnly ya no podrán autenticarse al unirse a Skype Empresarial reuniones, pero podrán unirse de forma anónima. Para obtener más información, consulte [Qué esperar después de la retirada](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

> [!TIP]
> Para ayudarle a identificar el modo de actualización recomendado en función de las capacidades que desea habilitar en Teams mientras Skype Empresarial aún está en uso, use el [Asistente para actualización de Skype a Teams](https://aka.ms/SkypeToTeamsWizard).

Para obtener más información sobre los modos de coexistencia, los requisitos previos y la administración, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md) y [Establecer la configuración de coexistencia y actualización](./setting-your-coexistence-and-upgrade-settings.md).

|Icono de punto de decisión |Definición de iconos |Descripción |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto de decisión|<ul><li>¿Qué modoes de coexistencia se ajustan mejor a las necesidades de su organización y de los usuarios?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Paso siguiente|<ul><li>Elija el mejor enfoque para su viaje de actualización.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidad de Teams y Skype Empresarial

La interoperabilidad es la capacidad de Teams y Skype Empresarial usuarios de la misma organización para comunicarse entre Teams y Skype Empresarial.

La interoperabilidad se rige por el modo de coexistencia (también conocido como modo de actualización) del receptor. No hay interoperabilidad cuando el receptor está en modo **Islas** .

> [!Note]
> Cuando se implementa en cualquier modo de coexistencia excepto **Islas**, Teams y Skype Empresarial pueden [interoperar](#interoperability-of-teams-and-skype-for-business), lo que permite a los usuarios chatear y llamarse entre sí, y garantizar que las comunicaciones permanezcan fluidas en toda la organización durante el viaje de actualización a Teams. Los modos de coexistencia rigen la interoperabilidad. El modo de coexistencia del receptor determina si la interoperabilidad estará disponible. Por ejemplo, si el receptor está en un modo en el que el chat solo está disponible en un cliente (por ejemplo, Teams), la interoperabilidad del chat estará disponible generalmente en caso de que el iniciador use el otro cliente (en este caso, Skype Empresarial) para iniciar el chat. Por otro lado, si el receptor está en el modo en el que el chat está disponible en ambos clientes (modo islas), la interoperabilidad no estará disponible para el chat. El mensaje será recibido por el receptor en el mismo cliente en el que el iniciador inició el chat. Por lo tanto, una comunicación adecuada en el modo **Islas** requiere la saturación de adopción de Teams; es decir, todos los usuarios usan y supervisan activamente ambos clientes.

> [!Note]
> **Para tener la experiencia de coexistencia más reciente, la versión del cliente debe ser el cliente más reciente disponible en el canal de implementación de Office del usuario.**

#### <a name="native-interop-and-interop-escalation"></a>Escalación de interoperabilidad y interoperabilidad nativa

Existen dos tipos de experiencias de interoperabilidad: nativa y de interoperabilidad.

- Se produce una experiencia _de interoperabilidad nativa_ en el cliente que el usuario está usando actualmente. Un usuario estará en el cliente de Skype Empresarial y el otro en Teams. Una experiencia de interoperabilidad nativa no los llevará a otro cliente para comunicarse. Los usuarios podrán dirigir su conversación en el cliente que estén usando actualmente. Las experiencias de interoperabilidad nativa son llamadas y chats uno a uno.
- Una experiencia de _escalación de interoperabilidad_ significa que, como parte de ayudar a los usuarios a realizar una acción avanzada (como compartir su escritorio), el cliente facilita la creación de una reunión a la que los usuarios pueden unirse para continuar la experiencia en esa reunión. La reunión se crea en la plataforma del iniciador de la acción. El usuario o los usuarios que no se encuentran en esa plataforma reciben un vínculo para unirse a una reunión. Al hacer clic en este vínculo, se unirá a la reunión en un cliente compatible (explorador, aplicación web o cliente completo, según la configuración). La escalación de interoperabilidad de Skype Empresarial requiere un cliente reciente. La escalación de interoperabilidad de Teams ya está disponible. Ambos son compatibles con las experiencias de interoperabilidad en el espacio empresarial y con los espacios empresariales de comunicación federada.

#### <a name="native-interop-experiences"></a>Experiencias de interoperabilidad nativa

En función de los modos de coexistencia asignados a los usuarios (como se describió anteriormente), están disponibles las siguientes experiencias de interoperabilidad nativa:

Skype Empresarial los usuarios pueden chatear uno a uno con los usuarios de Teams y viceversa. Un chat de interoperabilidad debe pasar por una puerta de enlace de interoperabilidad que formen parte de los servicios en la nube de Teams (y, por lo tanto, solo existe en línea). Los chats de interoperabilidad son texto sin formato: no se admiten el texto enriquecido ni los emoticonos. A los usuarios en Teams y en Skype Empresarial se les notifica que la conversación es una conversación de interoperabilidad.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype Empresarial los usuarios pueden realizar llamadas de voz y videollamadas uno a uno a los usuarios de Teams, y los usuarios de Teams pueden hacer lo mismo.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Las experiencias de interoperabilidad con usuarios locales en una organización con una combinación de usuarios locales y de Teams requieren que el entorno local esté en modo híbrido con Teams. Para obtener más información, [configure la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Estas experiencias de interoperabilidad están disponibles para los usuarios que tienen asignado uno de los siguientes modos de coexistencia: **Skype Empresarial con la colaboración de Teams**, **Skype Empresarial con reuniones y colaboración de Teams**, **solo Skype Empresarial** o **solo en Teams**. No hay interoperabilidad para los usuarios en modo **Islas** .

#### <a name="native-interop-experience-limitations"></a>Limitaciones de la experiencia de interoperabilidad nativa

Debido a la diferencia en los protocolos y la tecnología, no es posible admitir todas las capacidades de forma nativa. En concreto, las siguientes funcionalidades no están disponibles:

- Markdown, el texto enriquecido y el conjunto completo de emoticonos no son compatibles ni con Teams ni con Skype Empresarial. No se admiten otras características nativas del cuadro de redacción en los chats de Teams.
- El uso compartido de la pantalla (uso compartido de aplicaciones o de escritorio) entre Teams y Skype Empresarial no se admite de forma nativa. Sin embargo, se soporta a través de la escalada de interoperabilidad.
- Los chats grupales (conversaciones de varias partes) en Teams solo pueden incluir participantes que usan Teams.
- Las conversaciones de mensajería instantánea de varios participantes (chats grupales) en Skype Empresarial solo pueden incluir participantes que usan Skype Empresarial. Sin embargo, la escalación de interoperabilidad a varias partes está disponible desde Skype Empresarial.
- No se admite el escalado de una llamada de voz o videollamada de punto a punto en curso a una llamada de varios participantes que implique tanto a Teams como a Skype Empresarial usuarios.
- No se admite la transferencia de archivos para chats de dos entidades o datos adjuntos de archivos en chats grupales, desde Teams a Skype Empresarial y viceversa.
- No existe interoperabilidad con Skype Empresarial chat persistente.

Para todas estas limitaciones (excepto el chat persistente), una posible solución es que un usuario inicie una reunión e invite al otro usuario a unirse a ella.

Esta solución alternativa es la base para la escalada de interoperabilidad. En particular, el uso compartido de la pantalla y la escalación a multiparty no se pueden lograr de forma nativa, pero se admiten a través de la escalación de interoperabilidad.

#### <a name="interop-escalation-experiences"></a>Experiencias de escalación de interoperabilidad

La escalación de interoperabilidad consiste en complementar las capacidades de interoperabilidad nativa con escalaciones administradas a reuniones. Las reuniones ofrecen experiencias enriquecidas disponibles para cualquier persona, independientemente del cliente que tengan.

Cuando el usuario de Teams activa la escalación de interoperabilidad, se crea una reunión de Teams. Cuando el usuario Skype Empresarial lo activa, se crea una reunión de Skype Empresarial. En ambos casos, la reunión creada es una reunión **de Reunirse ahora** , que no se refleja en el calendario del usuario.

La otra parte recibe el vínculo para unirse a la reunión a través del chat de interoperabilidad y se une haciendo clic en ese vínculo. Si el Skype Empresarial usuario tiene una cuenta de Teams y es invitado por el usuario de Teams, se unirá a la reunión autenticada. En caso contrario, se unirán como participante anónimo. Los usuarios de Teams casi siempre tienen una cuenta de Skype Empresarial y un cliente de Skype Empresarial que pueden usar para unirse a una reunión de Skype Empresarial como participante autenticado, pero también pueden unirse como participante anónimo, por ejemplo, mediante la aplicación Reunión de Skype.

Una vez que las partes se han unido a la reunión, pueden llevar a cabo cualquier actividad admitida en las reuniones, como compartir contenido o escritorio, compartir archivos o transferir, agregar otros participantes, etc.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalación de interoperabilidad desde Skype Empresarial

La escalación de interoperabilidad y interoperabilidad de Skype Empresarial se actualizó en la compilación de julio de 2019 de C2R mensual. Anteriormente, Skype Empresarial no sabían con antelación que el grupo remoto estaba usando Teams. Sólo supuso que a partir de la señalización recibida después de establecerse una sesión.

Cuando la señalización indicaba que la respuesta provenía (o a través) de la puerta de enlace de interoperabilidad, mostraba la barra de negocios amarilla (pancarta) que indicaba que la otra parte no estaba usando Skype Empresarial. Con la evolución de nuestro servicio, esto resultó en falsos positivos en los que los usuarios de Skype Empresarial verían la barra de negocio cuando estaban conectados al servicio Correo de voz en la nube u otros servicios de voz en la nube, en lugar de a un usuario **de Teams solo** real.

Para evitar falsos positivos, el servicio de presencia ahora informa al cliente de Skype Empresarial cuando la otra parte es un usuario real **de Teams Only**. Esto permite a Skype Empresarial crear una conversación de interoperabilidad y que la ventana de conversación sea específica de la interoperabilidad.

![Captura de pantalla de un mensaje de Teams para crear una conversación de interoperabilidad con un usuario de Skype Empresarial.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si el usuario Skype Empresarial quiere compartir su escritorio, por ejemplo, se le informará de que iniciaremos una reunión y se le guiará por los pasos.

![Captura de pantalla de un mensaje de Teams para iniciar la reunión con un usuario de Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Mientras tanto, el usuario de Teams recibe un mensaje de chat entrante con el vínculo a la reunión y se guía para que se una.

Esta escalación a una reunión de Skype Empresarial está disponible tanto para las llamadas federadas entre espacios empresariales como para los chats y las llamadas federadas entre inquilinos. Está activada de forma predeterminada y no hay ninguna configuración que el administrador tenga que aprovisionar.

#### <a name="interop-escalation-from-teams"></a>Escalación de interoperabilidad desde Teams

La escalación de interoperabilidad de Teams a una reunión de Teams ahora está disponible cuando el usuario de Teams selecciona el botón compartir escritorio en un subproceso de interoperabilidad dentro del espacio empresarial con un usuario Skype Empresarial o en un subproceso de federación de interoperabilidad entre inquilinos. La escalación de interoperabilidad se admite desde una conversación de chat 1:1 o desde una llamada 1:1.

La funcionalidad es compatible con el cliente de escritorio de Teams para Windows, el cliente de escritorio de Teams para Mac y el cliente web de Teams en exploradores donde se admite el uso compartido de contenido, mientras que está en comunicación con cualquier versión de cliente de Skype Empresarial.

En los subprocesos de interoperabilidad y en los subprocesos de interoperabilidad de federación, el usuario de Teams tiene ahora los controles (botón) para iniciar el uso compartido de contenido. Cuando el usuario de Teams selecciona el botón, se le presenta un menú adicional que le informa de que para compartir contenido, tendrá que iniciar una reunión de Teams.

Si los usuarios estaban en una llamada, el menú les advertirá de que su llamada actual entre Teams y Skype Empresarial finalizará cuando se pongan en una reunión de Teams. Si lo desea, puede avisar al Skype Empresarial usuario antes de aceptarlo.

![Captura de pantalla de un mensaje de Teams para compartir una reunión con un usuario de Skype Empresarial.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Tras la aceptación, se colocan en la reunión de Teams; deben empezar a compartir desde la bandeja de uso compartido de la reunión.

Mientras tanto, el Skype Empresarial usuario recibe un mensaje de chat entrante con el vínculo a la reunión y se le guía para que se una.

Esta escalación a una reunión de Teams está disponible tanto para las llamadas federadas entre espacios empresariales como para las llamadas y chats entre inquilinos. Está activada de forma predeterminada y no hay ninguna configuración que el administrador tenga que aprovisionar. Sin embargo, se desactiva para el usuario si el administrador establece ``-AllowPrivateMeetNow`` en ``CsTeamsMeetingPolicy`` ``$false``.

Después de revisar este artículo, vea [Elegir el recorrido de la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Guía de migración e interoperabilidad](./migration-interop-guidance-for-teams-with-skype.md), [Coexistencia con Skype Empresarial](coexistence-chat-calls-presence.md) y [Establecer la configuración de coexistencia y actualización](./setting-your-coexistence-and-upgrade-settings.md) para obtener detalles sobre la implementación. También recomendamos el siguiente vídeo: [Vídeo: Administrar la coexistencia y la interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Detalles técnicos de Teams y Skype Empresarial coexistencia

En las siguientes secciones se resume el comportamiento que se puede experimentar al ejecutar Teams y Skype Empresarial clientes en la misma organización, independientemente del modo y el método de actualización que se use:

- [Reuniones](#meetings)
- [Interoperabilidad](#interoperability)
- [Interoperabilidad frente a hilos de conversación nativos](#interop-versus-native-conversation-threads)
- [Presence](#presence)
- [Federación](#federation)
- [Contactos](#contacts)

### <a name="meetings"></a>Reuniones

Independientemente de su modo, los usuarios siempre pueden unirse a cualquier tipo de reunión a la que estén invitados, tanto si se trata de Skype Empresarial como de Teams.  Sin embargo, los usuarios deben unirse a la reunión con un cliente correspondiente que coincida con el tipo de reunión:

- Si la reunión es de Teams, todos los participantes (tanto si son usuarios de TeamsOnly, Islas o Skype Empresarial) usan el cliente de Teams para unirse a la reunión. Si Teams no está instalado, el usuario se dirigirá a la web al intentar unirse a una reunión.

- Si la reunión es una reunión Skype Empresarial, todos los participantes (tanto si son TeamsOnly, Islas o usuarios de Skype Empresarial) usan el cliente de Skype Empresarial para unirse a la reunión. Si el cliente de Skype Empresarial no está instalado, se le dirigirá a la web para que se una a través de la aplicación de Reunión de Skype. 

  En algunos casos, los participantes en el modo TeamsOnly solo podrán unirse a Skype Empresarial reuniones con aplicación web de Skype Empresarial o la aplicación Reuniones de Skype como usuario anónimo. Finalmente, este caso será verdadero para todos los usuarios en el modo TeamsOnly. Para obtener más información, vea [Skype Empresarial retirada en línea](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

Al organizar reuniones, el tipo de reunión que se programa se basa en el modo del organizador, como se muestra en la tabla siguiente:

| Modo de organizador    |      Comportamiento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Todas las reuniones programadas en Teams. Skype Empresarial complemento no está disponible en Outlook. |
| SfbWithTeamsCollab, SfbOnly | Todas las reuniones programadas en Skype Empresarial. El complemento de Teams no está disponible en Outlook. Considere la posibilidad de usar SfbWithTeamsCollabAndMeetings en su lugar, lo que permite a todos los usuarios, tanto locales como teamsonly, usar Teams para reuniones.|
| Aplicaciones aisladas | De forma predeterminada, las reuniones se pueden programar en Skype Empresarial o teams. Ambos complementos están disponibles en Outlook. Sin embargo, opcionalmente puede exigir que los usuarios de Islas siempre programen reuniones en Teams al asignarles una instancia de TeamsMeetingPolicy con preferredMeetingProviderForIslandsMode=Teams.|

### <a name="interoperability"></a>Interoperabilidad

Como se describe anteriormente en [Interoperabilidad de Teams y Skype Empresarial](#interoperability-of-teams-and-skype-for-business), Teams admite la interoperabilidad con Skype Empresarial en determinados escenarios. Comunicación de interoperabilidad hace referencia a un chat o llamada entre un usuario de Skype Empresarial y un usuario de Teams. La comunicación de interoperabilidad solo es posible entre dos usuarios; no se admite el chat o las llamadas de varios usuarios ni la adición de usuarios adicionales.

Se crea una llamada o chat de interoperabilidad entre dos usuarios cuando se cumplen las siguientes condiciones:

- Un usuario usa Teams y el otro usa Skype Empresarial.

- El modo del destinatario de la comunicación inicial no es Islas (de lo contrario, la comunicación se colocaría en el mismo cliente) si ambos usuarios se encuentran en la misma organización. En escenarios federados, el usuario que envía está usando Teams y el destinatario no está en el modo TeamsOnly.

- El usuario de Teams tampoco tiene una cuenta de Skype Empresarial alojado en local.

Dentro de la comunicación de interoperabilidad, el chat es solo texto sin formato. Además, el uso compartido de archivos y la pantalla compartida no son posibles *en el chat de interoperabilidad en sí*. Sin embargo, los usuarios de una conversación de interoperabilidad pueden conseguir fácilmente compartir archivos y/o pantallas creando una reunión a petición, desde el chat de interoperabilidad, como se describe a continuación:

- Si el usuario de Teams intenta compartir su pantalla, se crea automáticamente una reunión a petición de Teams y se envía un vínculo de invitación a esa reunión al cliente del usuario de Skype Empresarial. Al hacer clic en el vínculo, el usuario Skype Empresarial abrirá Teams y se unirá a la reunión. Ambos usuarios se encuentran ahora en una reunión de Teams y pueden compartirlos según sea necesario.

- Si el usuario de Skype Empresarial usa un cliente de 2018 o posterior e intenta compartir cualquier contenido, se crea automáticamente una reunión a petición Skype Empresarial y se envía un vínculo de invitación a esa reunión al cliente del usuario de Teams. Al hacer clic en el vínculo, el usuario de Teams intentará unirse a la reunión de Skype Empresarial. Si el usuario de Teams tiene instalado el cliente de Skype Empresarial, se abrirá y se le pedirá al usuario que inicie sesión (si aún no lo ha hecho).  Si el usuario de Teams no tiene el cliente de Skype Empresarial instalado, se le pedirá al usuario que use la versión web. Una vez que ambos usuarios han iniciado sesión, se encuentran en una reunión de Skype Empresarial y pueden compartirlos según sea necesario.

### <a name="interop-versus-native-conversation-threads"></a>Interoperabilidad frente a hilos de conversación nativos

Como las comunicaciones de interoperabilidad no admiten todas las características de la conversación nativa de Teams, el cliente de Teams mantiene conversaciones separadas para la comunicación entre equipos y teams para Skype Empresarial. Estas conversaciones se representan de forma diferente en la interfaz de usuario: los subprocesos de interoperabilidad se pueden diferenciar de un subproceso nativo normal de Teams mediante:

- Falta de controles para texto enriquecido, uso compartido de archivos y pantalla, incapacidad para agregar usuarios.
- Una modificación en el icono del usuario de destino, que muestra una "S" para Skype Empresarial.

Estas diferencias se muestran en las siguientes capturas de pantalla:

Una conversación nativa de Teams a Teams con la prueba G3 del usuario

![Diagrama que muestra una conversación nativa de Teams a Teams.](media/teams-upgrade-native-thread.png)

Una conversación de interoperabilidad con la misma prueba de Usuario G3

![Diagrama que muestra una conversación de interoperabilidad de Teams a Teams.](media/teams-upgrade-interop-thread.png)

Una vez creada una conversación, su tipo nunca cambia. Una vez creada, un subproceso de interoperabilidad en Teams siempre se redirigirá al cliente de Skype Empresarial del usuario de destino. Una conversación nativa siempre se enrutará al cliente de Teams del usuario de destino.  Si cambia el modo de un usuario destinatario, las conversaciones existentes de Teams para ese usuario ya no funcionarán y se mostrará una nota en ese chat con un vínculo para iniciar una nueva conversación nativa, tal como se muestra en la siguiente captura de pantalla.

![Diagrama que muestra un chat con un usuario de Skype Empresarial actualizado.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presence

La presencia de un usuario determinado se basa en la actividad del usuario en el servicio a través del cliente. A continuación, se publica la presencia para que otros usuarios la vean.  Skype Empresarial y Teams son servicios independientes con clientes independientes, por lo que cada servicio tiene su propio estado de presencia para un usuario.   También hay sincronización entre los servicios de presencia en Teams y en Skype Empresarial Online.  Esto permite que un servicio publique potencialmente la presencia del usuario del otro servicio si es necesario.

El comportamiento de publicación de presencia se basa en el modo del usuario. Existen tres casos básicos:

- Si un usuario está en modo TeamsOnly, todos los demás usuarios verán la presencia de Teams para ese usuario, independientemente del cliente que usen.

- Si un usuario se encuentra en cualquiera de los modos Skype Empresarial, todos los demás usuarios verán Skype Empresarial presencia de ese usuario, independientemente del cliente que usen.

- Si un usuario está en modo Islas, la presencia publicada en Skype Empresarial y Teams son independientes, por lo que la presencia que se muestre a los usuarios de la misma organización dependerá del cliente del otro usuario. Los usuarios de organizaciones federadas verán la presencia de ese usuario en función de su actividad de Skype Empresarial, ya que el tráfico federado a un usuario del modo Islas se encuentra en Skype Empresarial.

Por ejemplo, suponga que el usuario A está en modo islas. Si el usuario A está activo en Teams pero no ha iniciado sesión en Skype Empresarial, otros usuarios verían al usuario A activo desde su cliente de Teams, pero en su Skype Empresarial cliente verían el usuario A como desconectado. Esto es por motivos de diseño, ya que no se puede contactar con el usuario A si no está ejecutando el cliente.


### <a name="federation"></a>Federación

La federación de Teams a otro usuario con Skype Empresarial requiere que el usuario de Teams esté alojado en línea en Skype Empresarial. TeamsUpgradePolicy controla el enrutamiento de las llamadas y chats federados entrantes. El comportamiento de enrutamiento federado es el mismo que para los escenarios de espacio empresarial, excepto en el modo "aplicaciones aisladas". Cuando los destinatarios están en modo Aplicaciones aisladas:

- Los chats y las llamadas iniciadas desde Teams se inician en Skype Empresarial si el destinatario se encuentra en un inquilino federado.
- Chats y llamadas iniciadas desde Teams llegan a Teams si el destinatario está en el mismo espacio empresarial.
- Los chats y las llamadas iniciadas desde Skype Empresarial siempre llegan a Skype Empresarial.

Un chat federado puede ser un subproceso nativo o un subproceso de interoperabilidad. Vea [Interoperabilidad frente a hilos de conversación nativos](#interop-versus-native-conversation-threads).

- Si el receptor y el remitente se encuentran en el modo de actualización de TeamsOnly, la conversación será una experiencia de chat nativa, que incluye todas las capacidades de llamada y mensajería enriquecidas. Para obtener más información, lea [Experiencia de chat nativa para usuarios externos (federados) en Teams](native-chat-for-external-users.md).

- Si alguno de los participantes de la conversación NO está en El modo de actualización de TeamsOnly, la conversación sigue siendo una experiencia de interoperabilidad con mensajes de solo texto. La interfaz de usuario expone los chats federados de forma similar a los subprocesos de interoperabilidad del mismo espacio empresarial, excepto que hay una nota que indica que el usuario es externo.

Para obtener más información, consulte [Administrar el acceso externo en Microsoft Teams](manage-external-access.md) y [Experiencia de chat nativa para usuarios externos (federados) en Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contactos

Teams y Skype Empresarial tienen listas de contactos independientes. Esto significa que las adiciones, eliminaciones y modificaciones de contactos realizadas en un sistema no se sincronizan con el otro sistema. Sin embargo, los contactos de Skype Empresarial se copian automáticamente en Teams cuando se produce alguno de los dos eventos específicos:

- Para cualquier usuario de Skype Empresarial Online, la primera vez que inicie sesión en Teams, los contactos de Skype Empresarial se copiarán en Teams. Este comportamiento no está disponible para los usuarios con una cuenta local en Skype Empresarial Server.

- Después de actualizar un usuario a TeamsOnly (ya sea a través de la asignación de TeamsUpgradePolicy o a través de Move-CsUser -MoveToTeams), la próxima vez que un usuario inicie sesión en Teams, los contactos existentes en Skype Empresarial se combinarán con contactos existentes que ya estén en Teams. Este comportamiento ocurre tanto si el usuario se movió a TeamsOnly desde local o en línea.

En ambos casos, la transferencia de contactos de Skype Empresarial a Teams es asíncrona, por lo que puede pasar unos minutos antes de que los contactos aparezcan en Teams. Los dos eventos anteriores son los que desencadenan la copia.

### <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
