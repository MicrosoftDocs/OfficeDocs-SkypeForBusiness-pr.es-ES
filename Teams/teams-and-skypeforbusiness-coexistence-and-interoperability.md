---
title: Interoperabilidad entre Skype empresarial y Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalles de Skype empresarial y las opciones de coexistencia de Microsoft Teams y la interoperabilidad entre Skype empresarial y Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e9a1d50469490e3e68163cf7b51a0fc6cac9af7
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158758"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Comprender Microsoft Teams y la coexistencia e interoperabilidad de Skype empresarial

![Diagrama de itinerario de actualización, énfasis en la fase de definición del proyecto](media/upgrade-banner-project-definition.png "Fases del itinerario de la actualización, con énfasis en la fase de definición del proyecto")

Este artículo forma parte de la fase de definición de proyecto de su viaje de actualización, una actividad que ha completado después de crear un Coalition de patrocinio y un equipo de proyecto y definir el ámbito, los objetivos y la visión de su proyecto. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)

Si su organización usa Skype empresarial hoy y está empezando a usar Teams con Skype empresarial — o está comenzando a actualizar a Teams, es importante comprender cómo cooperan las dos aplicaciones, Cuándo y cómo interoperan, y cómo administrar la migración de los usuarios hasta su eventual actualización de Skype empresarial a los equipos.

> [!Tip]
> Mire la siguiente sesión para obtener información sobre la [coexistencia y la interoperabilidad](https://aka.ms/teams-upgrade-coexistence-interop).
>
> Además, puede participar en talleres interactivos y en vivo en los que compartiremos orientación, procedimientos recomendados y recursos diseñados para la planificación e implementación de la actualización de lanzamiento.
>
> Para empezar, únase en primer lugar a la sesión [Planificar la actualización](https://aka.ms/SkypeToTeamsPlanning).

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistencia de Teams y Skype empresarial

Además de las capacidades de colaboración, Teams ofrece funciones de chat, llamadas y reuniones. En función de cómo decida implementar Teams, estas capacidades pueden superponerse a las capacidades que proporciona Skype empresarial para un usuario determinado. El modo predeterminado es ejecutar Teams junto con Skype empresarial con las capacidades superpuestas. sin embargo, a un usuario se le puede asignar uno de los diversos modos de coexistencia (también conocidos como modos de actualización) que se diseñaron para garantizar que estas funcionalidades no se solapen para ese usuario (en cuyo caso está disponible la interoperabilidad entre Teams y Skype empresarial). Por ejemplo, si tiene muchos activos locales de Skype empresarial Server con una compleja implementación de telefonía IP empresarial pero desea que los usuarios disfruten de las reuniones modernas lo antes posible, puede que desee evaluar las [reuniones en primer lugar](meetings-first.md) como una ruta alternativa.

Le recomendamos que revise los siguientes modos de coexistencia para determinar qué ruta de acceso es adecuada para su organización.

> [!Important]
> La presentación de nuevas tecnologías o la realización de cambios en el entorno existente de Skype para empresas, a la vez que ofrece excelentes beneficios comerciales nuevos, puede ser perjudicial para los usuarios. Tome el tiempo de evaluar la preparación del usuario e implementar un plan de comunicación y aprendizaje antes de implementar cualquiera de los cambios descritos en este artículo. Además, le recomendamos encarecidamente que planee su plan con un grupo de usuarios seleccionado antes de implementarlo en toda la organización.

### <a name="islands-mode"></a>Modo islas

De forma predeterminada, los usuarios pueden ejecutar equipos junto con Skype empresarial como dos soluciones independientes que ofrecen capacidades similares y superpuestas, como presencia, chat, llamadas y reuniones. Los usuarios de Teams también pueden aprovechar las nuevas capacidades de colaboración, como los equipos y los canales, el acceso a los archivos de Microsoft 365 u Office 365 y las aplicaciones.

En este modo de coexistencia, denominado **islas**, cada una de las aplicaciones cliente funciona como una isla independiente. Skype empresarial habla con Skype empresarial y Teams se comunica con Teams. Se espera que los usuarios ejecuten ambos clientes en todo momento y se puedan comunicar de forma nativa en el cliente desde el que se inició la comunicación. Por lo tanto, no hay necesidad de interoperabilidad en el modo **islas** .

Para evitar una experiencia de Skype empresarial confusa o recargada, las comunicaciones externas (federadas), los servicios de voz RTC y las aplicaciones de voz, la integración de Office, los controles HID para dispositivos USB y otras integraciones más siguen siendo manejadas por Skype empresarial y no están disponibles en los equipos en el modo **islas** . El sistema telefónico no es compatible con equipos en el modo **islas** ; en este modo, el único cliente de voz empresarial es Skype empresarial.

> [!Important]
> En el modo **islas** , todos los mensajes y las llamadas de usuarios federados (personas de fuera de la organización) se envían a Skype empresarial. Después de actualizar a modo **solo para equipos** , todos los mensajes y las llamadas de fuera de la organización se envían a teams.

> [!Tip]
> La ruta recomendada para los clientes de Skype empresarial online es empezar con el modo **islas** predeterminadas, los equipos de unidades de disco adoptan la saturación de la organización y, a continuación, se desplazan rápidamente al modo de **solo equipos** . En el caso de los clientes híbridos y locales, especialmente los más complejos, pueden beneficiarse de la implementación de **Skype empresarial con** el modo de colaboración de Teams como punto de partida en lugar del modo **islas** y del progreso a **Skype empresarial con el modo de colaboración y reuniones de Teams** (es decir, las reuniones en primer lugar), si es necesario, y al modo **solo de equipos** cuando

### <a name="teams-only"></a>Solo equipos

Un usuario **solo de equipos** (también denominado usuario *actualizado* ) tiene acceso a todas las capacidades de Teams. Pueden retener el cliente de Skype empresarial para unirse a reuniones de Skype empresarial organizadas por usuarios externos o no actualizados. Un usuario actualizado puede seguir comunicándose con otros usuarios de la organización que siguen usando Skype empresarial con las funciones de interoperabilidad entre Teams y Skype empresarial (siempre que estos usuarios de Skype empresarial no estén en modo **islas** ). Sin embargo, un usuario actualizado no puede iniciar una conversación, una llamada o una reunión de Skype empresarial.

Tan pronto como su organización esté lista para que algunos o todos los usuarios usen Teams como la única herramienta de comunicación y colaboración, puede actualizar esos usuarios al modo de **solo equipos** . Si está actualizando desde el modo **islas** , le recomendamos que primero saturara la adopción de Teams en toda la organización antes de comenzar el proceso de actualización. Esto evita la ruptura de los escenarios de comunicación debido a que el modo **islas** no proporciona interoperabilidad.

Cuando se encuentra en el modo **solo de Teams** , Teams es la aplicación predeterminada para el protocolo SIP/Tel. Esto significa que los vínculos de la tarjeta de contacto de un usuario en Outlook para la llamada o la conversación serán gestionados por Teams.

Para obtener más información sobre cómo cambiar al modo **solo de Teams** , vea [consideraciones del modo solo de Teams](teams-only-mode-considerations.md).

![Captura de pantalla del mensaje de confirmación de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente de Skype empresarial que se ejecuta en un modo especial después de que el usuario se actualice como un usuario de solo equipo")

### <a name="skype-for-business-only"></a>Solo Skype Empresarial

En este modo de coexistencia, los usuarios permanecen en Skype empresarial, no en los equipos, en las capacidades de chat, reunión y llamada, y no usan Teams para equipos y canales. Este modo está disponible hoy; sin embargo, en la implementación actual, los equipos y los canales no se desactivan automáticamente para el usuario. Esto se puede conseguir usando la Directiva permisos de la aplicación para ocultar equipos y canales.

Este modo se puede usar antes de iniciar una implementación administrada de Teams para evitar que los usuarios comiencen a usar Teams por adelantado, o como una forma de habilitar la participación autenticada en reuniones de Teams para los usuarios de Skype empresarial, siempre y cuando los usuarios tengan una licencia de Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype empresarial con colaboración de Teams

Use este modo para presentar equipos en su entorno mientras continúa aprovechando la inversión existente en Skype empresarial. En este modo, no se cambia Skype empresarial para las funciones de chat, llamadas y reuniones, y usted agrega capacidades de colaboración de Teams: equipos y canales, acceso a los archivos de Microsoft 365 u Office 365 y aplicaciones. Las capacidades de comunicaciones de Teams (conversación privada, llamadas y programación de reuniones) están desactivadas de forma predeterminada en este modo.

Las organizaciones con un punto de partida de Skype empresarial Server local o híbrido deben considerar este modo como alternativa al modo **islas** si desean ofrecer a sus usuarios la interoperabilidad y la predicción de las comunicaciones, así como disponer de un calendario predecible para su actualización a Teams (en lugar de confiar en la saturación de la adopción en el modo **islas** ).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype empresarial con la colaboración y las reuniones de Teams, también conocidas como reuniones en primer lugar

Use este modo de coexistencia para acelerar la disponibilidad de las capacidades de reunión de los equipos de su organización, además de sus capacidades de colaboración, lo que permite a los usuarios aprovechar la experiencia de reuniones de equipos superiores: excelente calidad, capacidades innovadoras como transcripción, traducción o desenfoque de fondo, y una experiencia de usuario superior en todas las plataformas, incluidos los exploradores y dispositivos móviles

Junto con el uso de Teams para las conversaciones basadas en equipos y canales en este modo, los usuarios usarán Teams para programar y dirigir sus reuniones. Las llamadas y chats privados permanecen en Skype empresarial. Los equipos y Skype empresarial se benefician de una variedad de capacidades de "mejor conjunto", como la reconciliación de presencia, la retención o dessuspensión automática y la compatibilidad con dispositivos HID en ambas aplicaciones. Tenga en cuenta que es posible ocultar equipos y canales si así lo desea mediante la Directiva de permisos de aplicación.

Este modo de coexistencia es especialmente útil para las organizaciones con las implementaciones locales de Skype empresarial con telefonía IP empresarial, que probablemente tardarán algún tiempo en actualizarse a teams y desean beneficiarse de las reuniones superiores de los equipos tan pronto como sea posible.

> [!TIP]
> Para ayudar a identificar el modo de actualización recomendado en función de las capacidades que desea habilitar en Teams mientras Skype empresarial aún está en uso, aproveche el [Asistente de actualización de Skype to Teams](https://aka.ms/SkypeToTeamsWizard).

Para obtener más información sobre los modos de coexistencia, los requisitos previos y la administración, consulte [Guía de migración e interoperabilidad para las organizaciones que usan Teams junto con Skype empresarial](https://aka.ms/SkypeToTeams-Interop) y [establecer la coexistencia y la actualización de la configuración](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Punto de decisión|<ul><li>¿Qué modo o modos de coexistencia se adaptan mejor a las necesidades de los usuarios y de su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Paso siguiente|<ul><li>Elige el mejor enfoque para tu viaje de actualización.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidad de Teams y Skype empresarial

La interoperabilidad es la capacidad de que los equipos y los usuarios de Skype empresarial de la misma organización se comuniquen entre equipos y Skype empresarial.

La interoperabilidad está regida por el modo de coexistencia (también conocido como modo de actualización) del destinatario. No hay interoperabilidad cuando el receptor está en modo **islas** .

> [!Note]
> Cuando se implementa en cualquier modo de coexistencia excepto **islas**, los equipos y Skype empresarial pueden [interoperar](#interoperability-of-teams-and-skype-for-business), lo que permite a los usuarios conversar y llamar entre sí, y garantizar que las comunicaciones permanezcan fluidas en toda la organización durante el viaje de actualización a teams. Los modos de coexistencia rigen la interoperabilidad. El modo de coexistencia del receptor determina si estará disponible la interoperabilidad. Por ejemplo, si el receptor está en un modo en el que la conversación solo está disponible en un cliente (por ejemplo, Teams), la interoperabilidad de chat estará disponible generalmente en caso de que el iniciador use el otro cliente (en este caso, Skype empresarial) para iniciar la conversación. Por otro lado, si el receptor está en el modo en el que la conversación está disponible en ambos clientes (modo Islas), la interoperabilidad no estará disponible para el chat. El destinatario recibirá el mensaje en el mismo cliente en el que el iniciador inició la conversación. Por lo tanto, la comunicación adecuada en el modo **islas** requiere la saturación de la adopción de equipos; es decir, todos los usuarios que usan y supervisan activamente a ambos clientes.

> [!Note]
> **Para tener la última experiencia de coexistencia, la versión del cliente debe ser el último cliente disponible en el canal de implementación de Office del usuario.**

### <a name="native-interop-and-interop-escalation"></a>Interoperabilidad nativa y escalabilidad de interoperabilidad

Existen dos tipos de experiencias de interoperabilidad: nativas y de interoperabilidad.

- La experiencia de _interoperabilidad nativa_ se produce en el cliente que el usuario está usando actualmente. Un usuario estará en el cliente de Skype empresarial, el otro en Teams. Una experiencia de interoperabilidad nativa no las llevará a otro cliente para comunicarse, los usuarios podrán realizar su conversación en el cliente que actualmente están usando. Las experiencias de interoperabilidad nativas son chats uno a uno y llamadas.
- Una experiencia de _escalado de interoperabilidad_ significa que, como parte de ayudar a los usuarios a realizar una acción avanzada (como compartir su escritorio), el cliente facilita la creación de una reunión a la que los usuarios pueden unirse para continuar con la experiencia de esa reunión. La reunión se crea en la plataforma del iniciador de la acción. El usuario o los usuarios que no se encuentren en la plataforma recibirán un vínculo de unirse a la reunión. A medida que hacen clic en este vínculo, se unen a la reunión en un cliente compatible (explorador, aplicación web o cliente completo, según la configuración). La escalabilidad de interoperabilidad de Skype empresarial requiere un cliente reciente. Ahora está disponible el escalado de interoperabilidad de Teams. Ambas son compatibles con las experiencias de interoperabilidad de en el inquilino y para los usuarios de la comunicación federada.

### <a name="native-interop-experiences"></a>Experiencias de interoperabilidad nativas

En función de los modos de coexistencia asignados a los usuarios (como se ha descrito anteriormente), están disponibles las siguientes experiencias de interoperabilidad nativa:

Los usuarios de Skype empresarial pueden chatear uno a uno con los usuarios de Teams, y viceversa. Un chat de interoperabilidad debe atravesar un Gateway de interoperabilidad que forma parte de los servicios en la nube de Teams (y, por lo tanto, solo está conectado). Los chats interoperativos son texto sin formato: el texto enriquecido y los emoticonos no se admiten. Se notifica a los usuarios de Teams y a Skype empresarial que la conversación es una conversación de interoperabilidad.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Los usuarios de Skype empresarial pueden hacer llamadas y videollamadas individuales a los usuarios de Teams, y viceversa.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Las experiencias de interoperabilidad con una implementación local de Skype empresarial requieren que el entorno local esté en modo híbrido con Microsoft 365 u Office 365 Skype empresarial. Para obtener más información, consulte [Guía de migración e interoperabilidad](https://aka.ms/SkypeToTeams-Interop).

Estas experiencias de interoperabilidad están disponibles para los usuarios que tienen uno de los siguientes modos de coexistencia: **Skype empresarial con colaboración de Teams**, **Skype empresarial con colaboración y reuniones de Teams**, **solo Skype**empresarial o solo para **equipos**. No hay ninguna interoperabilidad para los usuarios en el modo **islas** .

### <a name="native-interop-experience-limitations"></a>Limitaciones de la experiencia de interoperabilidad nativa

Debido a la diferencia en los protocolos y la tecnología, no es posible admitir de forma nativa todas las funciones. En concreto, las siguientes características no están disponibles:

- No se admite el descuento, el texto enriquecido ni el conjunto de emoticonos completo de equipos o de Skype empresarial. No se admiten otras características nativas del cuadro de redacción en los chats de Teams.
- La pantalla compartida (escritorio o uso compartido de aplicaciones) entre equipos y Skype empresarial no se admite de forma nativa. Sin embargo, es compatible con la escala de interoperabilidad.
- Los chats grupales (conversaciones de varios participantes) en Teams solo pueden incluir participantes que usen Teams.
- Las conversaciones de mensajería instantánea de varios participantes (chats grupales) en Skype empresarial solo pueden incluir participantes que usen Skype empresarial. Sin embargo, la escalabilidad de interoperabilidad a varios participantes está disponible en Skype empresarial.
- No se admite la escala de una llamada de voz o videollamada de punto a punto continuado a una llamada de varios participantes que implique a equipos y usuarios de Skype empresarial.
- No se admite la transferencia de archivos para chats de dos participantes o datos adjuntos en chats grupales, de equipos a Skype para empresas, y viceversa.
- No existe una interoperabilidad con el chat persistente de Skype empresarial.

Para todas estas limitaciones (excepto para conversaciones persistentes), una posible solución es que un usuario inicie una reunión e invite a otro usuario a unirse a ella.

Esta solución alternativa constituye la base para el escalamiento de interoperabilidad. En concreto, el uso compartido de la pantalla y la escala a varias partes no se pueden realizar de manera nativa, pero sí se admiten a través de la escala de interoperabilidad.

### <a name="interop-escalation-experiences"></a>Experiencias de escala de interoperabilidad

La escalabilidad de interoperabilidad consiste en complementar las capacidades de interoperabilidad nativas con escalas administradas para reuniones. Las reuniones ofrecen experiencias ricas a disposición de cualquier persona, independientemente del cliente que tengan.

Cuando el usuario de Teams desencadena una escala de interoperabilidad, se crea una reunión de Teams. Cuando lo desencadena el usuario de Skype empresarial, se crea una reunión de Skype empresarial. En ambos casos, la reunión creada es una reunión **reunirse ahora** , que no se refleja en el calendario del usuario.
 
La otra persona recibe el vínculo unirse a la reunión a través de una conversación interactiva y las combinaciones haciendo clic en ese vínculo. Si el usuario de Skype empresarial tiene una cuenta de Teams y lo ha invitado el usuario de Teams, se unirán a la reunión autenticada. De lo contrario, se unirán como un participante anónimo. A la inversa, los usuarios de Teams casi siempre tienen una cuenta de Skype empresarial y un cliente de Skype empresarial que pueden usar para unirse a una reunión de Skype empresarial como participante autenticado, pero también se pueden unir como participante anónimo, por ejemplo, con la aplicación de reunión de Skype.

Una vez que las partes se unen a la reunión, pueden realizar cualquier actividad que se admita en las reuniones, como el uso compartido de escritorio o de contenido, el uso compartido de archivos o la transferencia, agregar otros participantes, etc.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalabilidad de interoperabilidad desde Skype empresarial

La escalabilidad de interoperabilidad y interoperabilidad de Skype empresarial se actualizó en la compilación de julio de 2019 de C2R mensual. Antes, Skype empresarial no tenía conocimiento anticipado de que la persona remota estaba usando Teams. Solo surmised que de la señal recibida después de que se haya establecido una sesión.

Cuando la señalización indicó que la respuesta procedía de la puerta de enlace de interoperabilidad (o a través de ella), mostraría la barra de empresa amarilla (banner) indicando que la otra persona no estaba usando Skype empresarial. Con la evolución de nuestro servicio, esto daba lugar a falsos positivos en los que los usuarios de Skype empresarial verían la barra de empresa cuando se conectaban al servicio de buzón de voz de nube o a otros servicios de voz en la nube, en lugar de hacerlo a un solo usuario de **equipos** reales.
 
Para evitar estos falsos positivos, el servicio de presencia está informando al cliente de Skype empresarial cuando la otra persona es un solo usuario real de **equipos** . Esto permite que Skype empresarial tenga en cuenta que necesita crear una conversación de interoperabilidad antes de que se haya creado, y la ventana de conversación para que sea específica para la interoperabilidad.

![Captura de pantalla del mensaje de Teams para crear una conversación interoperativa con un usuario de Skype empresarial](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Si el usuario de Skype empresarial quiere compartir su escritorio por ejemplo, se le informa de que iniciaremos una reunión y se guiarán por los pasos.

![Captura de pantalla del mensaje de Teams para iniciar la reunión con un usuario de Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Mientras tanto, el usuario de Teams recibe un mensaje de chat entrante con el vínculo a la reunión y se le guiará para unirse.

Esta escalación a una reunión de Skype empresarial está disponible para la interoperabilidad en espacio empresarial y las llamadas y conversaciones federadas entre inquilinos. Está activada de forma predeterminada y no hay ninguna opción que el Administrador tenga que aprovisionar.

#### <a name="interop-escalation-from-teams"></a>Escalado de interoperabilidad de Teams

La escalabilidad de interoperabilidad de Teams a una reunión de Teams ahora está disponible cuando el usuario de Teams selecciona el botón compartir escritorio en un subproceso de interoperabilidad en el inquilino con un usuario de Skype empresarial o en un subproceso de Federación de intercompañía. Se admite la escalabilidad de interoperabilidad desde una conversación de chat de 1:1 o desde una llamada de 1:1.

La funcionalidad es compatible con el cliente de escritorio de Teams para Windows, en el cliente de escritorio de Teams para Mac y en el cliente web de Teams en exploradores donde se admite el uso compartido de contenido, mientras se comunica con cualquier versión de cliente de Skype empresarial.

En los subprocesos de interoperabilidad y en los subprocesos de interoperabilidad de la Federación, el usuario de Teams tiene ahora controles (botón) para iniciar el uso compartido de contenido. Cuando el usuario de Teams selecciona el botón, se le presenta un menú adicional que le informa de que para compartir contenido, necesitará iniciar una reunión de Teams.

Si los usuarios estuvieron en una llamada, el menú también le advierte de que su llamada actual entre Teams y Skype empresarial finalizará a medida que se pongan en una reunión de Teams. Si así lo desean, pueden avisar al usuario de Skype empresarial antes de aceptarlo.

![Captura de pantalla del mensaje de Teams para compartir una reunión con un usuario de Skype empresarial](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Una vez aceptada, se ponen en la reunión de Teams; deben empezar a compartir desde la bandeja de uso compartido de la reunión.
 
Mientras tanto, el usuario de Skype empresarial recibe un mensaje de chat entrante con el vínculo a la reunión y se le guiará para unirse.

Esta escalación a una reunión de Teams está disponible para la interoperabilidad en espacio empresarial y las llamadas y conversaciones federadas entre inquilinos. Está activada de forma predeterminada y no hay ninguna opción que el Administrador tenga que aprovisionar. Sin embargo, se desactiva para el usuario si el administrador establece ``-AllowPrivateMeetNow`` en ``CsTeamsMeetingPolicy`` ``$false`` .

Después de revisar este artículo, vea [elegir las instrucciones para la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [migración e interoperabilidad](https://aka.ms/SkypeToTeams-Interop), así como la [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md), y [configurar la coexistencia y la configuración de actualización para los](https://aka.ms/SkypeToTeams-SetCoexistence) detalles de implementación.

## <a name="related-links"></a>Vínculos relacionados

[Vídeo: administrar la coexistencia y la interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
