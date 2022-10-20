---
title: Guía de accesibilidad para administradores de Microsoft Teams
ms.author: meghan
author: meganrmhan
ms.reviewer: eljones
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Mejore la accesibilidad en Microsoft Teams activando los subtítulos y la transcripción, proporcionando acceso a reuniones a intérpretes de lenguaje de signos y leyendas CART, reduciendo las distracciones, mejorando la participación y compartiendo recursos.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- M365-collaboration
ms.openlocfilehash: 7b089785695e9bef985107b5f1db8e5659c48c33
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614738"
---
# <a name="accessibility-guide-for-microsoft-teams-admins"></a>Guía de accesibilidad para administradores de Microsoft Teams

Como administrador de Microsoft Teams para su organización, puede ayudar a que su entorno de Teams sea lo más inclusivo y accesible posible para todos los usuarios. Siga las guías y recursos siguientes para configurar Microsoft Teams para una accesibilidad óptima.

> [!NOTE]
> Muchas de las opciones de accesibilidad están activadas de forma predeterminada, pero puede comprobar que no se han desactivado siguiendo los pasos de esta guía.

## <a name="turn-on-captions-and-transcription-for-meetings-and-calls"></a>Activar subtítulos y transcripción para reuniones y llamadas

Cree reuniones inclusivas y llamadas para usuarios con discapacidades para que todos puedan participar y contribuir.

### <a name="turn-on-live-captions-for-meetings"></a>Activar subtítulos en directo para las reuniones

Los subtítulos en directo son texto generado automáticamente en tiempo real de lo que se dice en una reunión. Aparecen unas cuantas líneas a la vez para un usuario que las ha activado y no se guardan.

Para activar los subtítulos en directo para los usuarios:

1. En el Centro de administración de Microsoft Teams, vaya a **Reuniones** y, después, seleccione la lista desplegable **Directivas de reunión**.

2. Seleccione la directiva que desea modificar.

3. Vaya a la sección **Participantes & invitados** .

4. Cambie **los subtítulos en directo** a **No habilitado, pero el usuario puede invalidar.**

5. Seleccione **Guardar**.

> [!TIP]
> Comparta el siguiente vínculo para que los usuarios puedan aprender a [activar los subtítulos en directo durante las reuniones](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop).

> [!NOTE]
> Los subtítulos en directo están disponibles para las reuniones que se realizan en un servicio comercial y en organizaciones de la nube de la comunidad gubernamental (GCC) de EE. UU.

### <a name="turn-on-transcription-for-calls"></a>Activar la transcripción para llamadas

La transcripción es texto grabado generado automáticamente de lo que se dijo en una llamada. Cuando se activa, la transcripción está disponible para que los usuarios la revisen una vez finalizada una llamada.

Para activar la transcripción para los usuarios:

1. En el Centro de administración de Microsoft Teams, vaya a **Voz** y, después, seleccione la lista desplegable **Directivas de llamadas**.

2. Seleccione la directiva que desea modificar.

3. Activa **la transcripción** **y, a** continuación, selecciona **Guardar**.

### <a name="why-captions-and-transcripts-are-important"></a>Por qué son importantes los subtítulos y las transcripciones

Los subtítulos y las transcripciones son versiones de texto de las palabras que alguien está hablando. Ofrecen a los usuarios la opción de ver texto además de audio solo o en lugar de hacerlo. Los subtítulos también benefician a las personas sordas o con dificultades auditivas, proporcionando información adicional sobre lo que algunos usuarios reciben del intérprete de lenguaje de signos o del subtítulo cartón con el que podrían trabajar.

Los subtítulos y la transcripción son útiles en una amplia variedad de situaciones, pero pueden ser especialmente útiles para:

- Personas sordos o con dificultades auditivas

- Personas con discapacidades de aprendizaje

- Personas que están en un entorno ruidoso o distraído y necesitan revisar la información compartida después de que finalice una reunión

Para obtener más información, consulte los vínculos siguientes:

- [Configuración de la directiva de reunión para la grabación y la transcripción](/Microsoftteams/meetings-policies-recording-and-transcription)

- [Directrices de accesibilidad al contenido web (WCAG) 1.2.4.: Subtítulos (en directo)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

## <a name="give-meeting-access-to-sign-language-interpreters-and-cart-communication-access-real-time-translation-captioners"></a>Conceder acceso a la reunión a intérpretes de lenguaje de signos y a los subtítulos de CART (Communication Access Real-time Translation)

Conceda a los intérpretes de lenguaje de signos y a los intérpretes de cartón (acceso de comunicación en tiempo real) acceso a las reuniones de Microsoft Teams para que puedan trabajar de forma más eficaz junto con los usuarios sordos o con dificultades auditivas.

### <a name="admit-sign-language-interpreters-and-cart-captioners-to-meetings"></a>Admitir intérpretes de lenguaje de signos y subtítulos de CART en reuniones

Es probable que los intérpretes de lenguaje de signos y los subtítulos de CART no funcionen para su organización, pero puede invitarlos a las reuniones de Microsoft Teams [dándoles acceso de invitado](/MicrosoftTeams/guest-access).

Una vez que se ha concedido acceso de invitado, para admitir intérpretes de lenguaje de signos y subtítulos de CART a las reuniones:

1. En el Centro de administración de Microsoft Teams, vaya a **Reuniones** y, después, seleccione la lista desplegable **Directivas de reunión**.

2. Seleccione la directiva que desea modificar.

3. Vaya a la sección **Participantes & invitados** .

4. Elija la opción en **Admitir automáticamente a las personas** que mejor se adapten a los requisitos de seguridad y cumplimiento de su organización. Puede seleccionar una de las siguientes opciones:

   - Todos los usuarios (no recomendado)

   - Personas en mi organización e invitados (recomendado)

   - Usuarios de mi organización y de organizaciones de confianza e invitados

   - Usuarios en mi organización

   - Solo organizador

   - Solo usuarios invitados

5. Seleccione **Guardar**.

> [!NOTE]
> La configuración **Admitir usuarios automáticamente** no se aplica a los usuarios de acceso telefónico local.

### <a name="turn-on-ip-video-feed-for-your-users"></a>Activar la fuente de vídeo IP para los usuarios

Ofrezca a los intérpretes de idiomas de signos la capacidad de compartir la fuente de vídeo IP durante las reuniones de Microsoft Teams para que puedan comunicarse con usuarios sordos o con dificultades auditivas.

Para comprobar si la fuente de vídeo IP está activada:

1. En el Centro de administración de Microsoft Teams, vaya a **Reuniones** y, después, seleccione la lista desplegable **Directivas de reunión**.

2. Seleccione la directiva que desea modificar.

3. Vaya a la sección **Audio & vídeo** .

4. Comprueba que **el vídeo IP** esté **activado** y, a continuación, selecciona **Guardar**.

> [!TIP]
> Comparta los siguientes vínculos con los usuarios para que puedan ajustar cómo usan Teams para maximizar su capacidad de participar, centrarse y colaborar en reuniones:
> - [Personalizar la vista de reunión](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)
> - [Usar subtítulos de cartografía](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

### <a name="why-its-important-to-include-sign-language-interpreters-and-cart-captioners"></a>¿Por qué es importante incluir intérpretes de lenguaje de signos y leyendas CART?

Es posible que algunos usuarios prefieran usar subtítulos cart porque pueden ser más precisos para jerga, acentos y mucho más específicos que los subtítulos generados automáticamente.

Los usuarios cuyo método de comunicación principal es el lenguaje de signos, requieren la interpretación del lenguaje de signos, que requiere la presencia de un intérprete humano.

Para obtener más información, consulte [la Guía de accesibilidad al contenido web (WCAG) 1.2.6.: Interpretación del lenguaje de signos](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded).

## <a name="reduce-distractions-in-meetings"></a>Reducir las distracciones en las reuniones

Fomente la participación de los usuarios activando los filtros de vídeo para reducir las distracciones en las reuniones de Teams.

### <a name="turn-on-video-filters"></a>Activar filtros de vídeo

Los filtros de vídeo ayudan a reducir las distracciones durante las reuniones.

Para activar los filtros de vídeo:

1. En el Centro de administración de Microsoft Teams, vaya a **Reuniones** y, después, seleccione la lista desplegable **Directivas de reunión**.

2. Seleccione la directiva que desea modificar.

3. Vaya a la sección **Uso compartido de contenido** .

4. Elija la opción en **Seleccionar filtros de vídeo** que mejor se adapte a los requisitos de seguridad y cumplimiento de su organización. Seleccione una de las siguientes opciones:

   - Solo difuminado de fondo

   - Desenfoque de fondo e imágenes predeterminadas

   - Todos los filtros

5. Seleccione **Guardar**.

> [!TIP]
> Comparta los siguientes vínculos para que los usuarios puedan ajustar sus preferencias de reunión de Teams para reducir las distracciones:
> - [Cambiar los efectos de fondo en las reuniones de Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)
> - [Reducir el ruido de fondo en las reuniones de Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

### <a name="why-its-helpful-to-reduce-distractions"></a>¿Por qué resulta útil reducir las distracciones?

Es posible que a algunas personas de su organización le resulte difícil concentrarse durante las videollamadas y reuniones debido al movimiento, la luz y otras distracciones en los fondos de los participantes. El uso de filtros de vídeo ayuda a los usuarios a controlar las distracciones y a participar plenamente.

*Los efectos de fondo* pueden ayudar a las personas a centrarse en el altavoz en lugar de en el fondo del orador. Microsoft Teams tiene una biblioteca de fondos y los usuarios también pueden cargar los suyos propios.

*El desenfoque de fondo* ayuda a mejorar la visibilidad y el enfoque durante reuniones o llamadas, ya que reduce las distracciones en segundo plano, pero mantiene a los usuarios concentrados.

Los filtros de vídeo son útiles en una amplia variedad de situaciones, pero pueden ser especialmente útiles para:

- Personas que son neurodiversos

- Personas sordos o con dificultades auditivas

Para obtener más información, vea [Guía de accesibilidad al contenido web (WCAG) 1.4.8.: Presentación visual](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html).

## <a name="improve-participation-in-microsoft-teams-meetings"></a>Mejorar la participación en las reuniones de Microsoft Teams

Fomente la participación de los usuarios con más opciones de control y flexibilidad activando **Chat en reuniones y directivas** de mensajería como edición de chat, **Lector inmersivo** y emojis.

### <a name="turn-on-chat-in-meetings"></a>Activar el chat en reuniones

El chat facilita que muchos usuarios hagan preguntas o agreguen información en las reuniones de Teams.

Para comprobar si el chat en la reunión está activado:

1. En el Centro de administración de Microsoft Teams, vaya a **Reuniones** y, después, seleccione la lista desplegable **Directivas de reunión**.

2. Seleccione la directiva que desea modificar.

3. Vaya a la sección **Participantes & invitados** .

4. Elija la opción de **Chatear en reuniones** que mejor se adapte a los requisitos de seguridad y cumplimiento de su organización. Puede seleccionar una de las siguientes opciones:

   - Activarlo para todos los usuarios (recomendado)

   - Desactívala para todos los usuarios (no se recomienda)

   - Actígalo para todos los usuarios excepto los anónimos

5. Seleccione **Guardar**.

### <a name="use-messaging-policies-for-increased-flexibility-and-control"></a>Usar directivas de mensajería para aumentar la flexibilidad y el control

Las opciones de chat flexibles hacen que sea más fácil para muchos usuarios comprender los mensajes de otros, revisar sus propios mensajes y expresarse.

Para comprobar si estas opciones de chat flexibles están activadas:

En el **Centro de administración de Microsoft Teams**:

1. En el Centro de administración de Microsoft Teams, vaya a **Directivas de mensajería**.

2. Seleccione la directiva que desea modificar.

3. Compruebe que los siguientes elementos están **activados**:

   - **Eliminar mensajes enviados**

   - **Editar mensajes enviados**

   - **Chat**

   - **Giphy en conversaciones**

   - **Memes en conversaciones**

   - **Adhesivos en conversaciones**

   - **Vistas previas de url**

   - **Traducir mensajes**

   - **Lector inmersivo para mensajes**

4. Seleccione **Guardar**.

> [!TIP]
> Comparta el vínculo [para escribir texto alternativo eficaz](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2) con su organización para ayudar a los usuarios a comprender los mensajes que no son de texto compartidos en el chat.

### <a name="why-alternate-participation-options-matter"></a>¿Por qué son importantes las opciones de participación alternativa?

Las opciones de chat flexibles proporcionan a los usuarios una mayor flexibilidad en la forma en que usan el contenido del chat en la reunión y un mayor control sobre cómo participan en una reunión con chat.

*El chat en la reunión* ofrece a las personas otra forma de participar en la discusión de la reunión. Para algunas personas con discapacidades, el chat podría ser preferible a la voz o el lenguaje de signos como forma de contribuir a las discusiones de la reunión.

*Lector inmersivo*, una herramienta diseñada para personas con dislexia y disgrafía, ayuda a que el texto sea más fácil de entender. También incluye traducción en línea para las personas que prefieren comunicarse en otro idioma. Algunas de las características clave de Lector inmersivo son:

- Agregar la opción para que el contenido se lea en voz alta

- Cambiar el tamaño del texto y el color de fondo

- Dividir palabras en sílabas

- Aumentar el espacio entre las letras

- Resaltar una o más líneas de texto

- Resaltar elementos de la oración

Las opciones de chat flexibles son útiles en una amplia variedad de situaciones, pero pueden ser especialmente útiles para:

- Personas ciegos o con deficiencias visuales

- Personas que son neurodiversos (es decir, tienen dislexia o disgrafía)

Para obtener más información, vea [Directrices de accesibilidad al contenido web (WCAG) 1.1.1: Alternativas de texto](https://www.w3.org/TR/WCAG21/#text-alternatives).

## <a name="share-resources-with-users-to-further-accessibility-awareness"></a>Compartir recursos con los usuarios para aumentar el conocimiento de accesibilidad

Hay pasos adicionales que los usuarios pueden seguir para mejorar su experiencia en accesibilidad. Comparta los vínculos siguientes con su organización y los usuarios invitados.

### <a name="reference-links"></a>Vínculos de referencia

Answer Desk Accesibilidad de Microsoft tiene guías para el usuario final para personalizar su experiencia para satisfacer sus necesidades de accesibilidad:

- [Activar subtítulos en directo durante las reuniones](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)

- [Personalizar la vista de reunión](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)

- [Usar subtítulos de cartografía](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

- [Cambiar los efectos de fondo en las reuniones de Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)

- [Reducir el ruido de fondo en las reuniones de Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

- [Escribir texto alternativo eficaz](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2)

- [Herramientas de accesibilidad para Microsoft Teams](https://support.microsoft.com/office/accessibility-tools-for-microsoft-teams-2d4009e7-1300-4766-87e8-7a217496c3d5?ui=en-us&rs=en-us&ad=us)

### <a name="reference-web-content-accessibility-guidelines-wcag"></a>Directrices de accesibilidad al contenido web de referencia (WCAG)

WCAG es una serie de estándares internacionales diseñados para mejorar la accesibilidad web. El criterio de éxito al que se hace referencia en esta guía incluye:

- [WCAG 1.2.4.: Subtítulos (en directo)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

- [WCAG 1.2.6.: Interpretación del lenguaje de signos](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)

- [WCAG 1.4.8.: Presentación visual](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)

- [WCAG 1.1.1.: Alternativas de texto](https://www.w3.org/TR/WCAG21/#text-alternatives)
