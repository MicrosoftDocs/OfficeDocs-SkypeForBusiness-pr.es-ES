---
title: Tomar decisiones de servicio de conferencia de Audio - Teams de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Obtenga información sobre las reuniones, las licencias y la disponibilidad, configurar el puente de conferencia, adquirir o transferir los números de teléfono, elija inquilinos planes de marcado.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80a4007b328ec66bed0ccae0160491b4ee20f858
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="make-my-service-decisions"></a>Tomar decisiones de mi servicio

Para planear la implementación técnica de conferencia de Audio, debe realizar una serie de decisiones de servicio antes de tiempo para preparar mejor a su organización a implementar una solución que satisfaga sus requisitos de negocio definidos.

Como parte de la definición de las características de conferencia de Audio necesarias en Microsoft Teams, uno de los primeros pasos consiste en evaluar el plan público más reciente para determinar:

-   Las características de conferencia de Audio en los equipos que se va a implementar para los usuarios en el ámbito.

-   Espera que los requerimientos de funcionalidad de usuario para conferencias de Audio en equipos.

-   Confirmación de que las características de conferencia de Audio en los equipos que se describe en la guía pública más reciente cumplen su usuario, funcionalidad y requisitos de ámbito, en la línea de tiempo de la implementación.

> [!NOTE]
> La guía básica de los equipos más reciente para identificar las características de conferencia de Audio de equipos en el ámbito de la implementación puede encontrarse en <https://aka.ms/skype2teamsroadmap>.

## <a name="meetings-in-teams"></a>Reuniones en Teams

Equipos proporciona a los usuarios la capacidad para programar y unirse a reuniones en línea mediante el uso de vídeo de alta definición, opciones de acceso telefónico de la conferencia de voz sobre IP (VoIP) y PSTN.

Pueden programarse reuniones como reuniones privadas (pueden unirse sólo las partes invitadas) o reuniones de canal (abierto para todos los usuarios que tengan acceso al canal) y los usuarios también pueden iniciar reuniones improvisadas dentro de los canales.

> [!NOTE]
> Para obtener más información acerca de las características de las reuniones en los equipos, consulte el [Skype para empresas Roadmap de capacidades de los equipos de Microsoft] https://aka.ms/skype2teamsroadmap).

Los participantes de la reunión puede unirse a las reuniones de equipos marcando el pago o el puente de conferencia de acceso telefónico gratuito números de teléfono a través de teléfonos fijos o teléfonos móviles. Además, los usuarios pueden permitir que el servicio de conferencia de Audio a iniciar la característica "Llamarme", para que puedan participar en una reunión por la necesidad de llamar a sus teléfonos (útil cuando la conexión de datos no es confiable) el puente de conferencia o reunión deje que los organizadores invitar a la reunión participantes mediante llamadas a sus teléfonos.

> [!IMPORTANT]
> Conferencias de audio en equipos no es compatible con los proveedores de conferencias de audio de terceros (ACP).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilidad de Audioconferencia

Antes de planear la implementación de conferencias de Audio en los equipos, debe revisar la disponibilidad del servicio de conferencia de Audio como se detalla en [la disponibilidad de país y región para conferencias de Audio y llamar a los planes](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Debido a restricciones legales, para conferencias de Audio que estén disponibles para las organizaciones multinacionales, el contrato para suscripciones a Office 365 debe conseguirse de países y regiones donde el servicio de conferencia de Audio no está disponible en el mercado.

Después de confirmar que su organización es elegible para obtener el servicio de conferencia de Audio, compilar la lista de ubicaciones de usuario u oficinas donde se implementa el servicio de conferencia de Audio, basado en la lista de regiones y países disponibles.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida qué oficinas o ubicaciones de usuario implementarán el servicio de Audioconferencia.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Decida qué oficinas o ubicaciones de usuario se habilitarán para el servicio de Audioconferencia.</li></ul>|

> [!TIP]
> A continuación es un ejemplo de una plantilla de lista de habilitación de sitio conferencia de Audio:
>|Oficina   |Ubicación |Servicio de conferencia RTC  |
>|---------|---------|---------|
>|One Epping Road|Australia|Audioconferencia|
>|100 Cyberport Road|RAE de Hong Kong|Conferencia RTC antigua|
>|One Marina Boulevard|Singapur|Audioconferencia|
>|32 London Bridge Street|Reino Unido|Audioconferencia|
>|39 quai du Président Roosevelt|Francia|Audioconferencia|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licencias para Audioconferencia

Una [licencia de conferencia de Audio](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) está disponible como parte de un plan de suscripción de Office 365 E5, o como un servicio adicional a los planes de suscripción de Office 365 E1 o E3 de Office 365.

> [!NOTE]
> Conferencias PSTN o acceso telefónico en los equipos no es compatible con los proveedores de conferencias de audio de terceros (ACP).
> <br>Si está usando la Conferencia RTC para Skype Empresarial Online, puede beneficiarse al instante de Audioconferencia en Microsoft Teams.

Para proporcionar números de teléfono de puente de conferencia gratuito y admite conferencias acceso telefónico de salida para los números de teléfono internacionales, debe configurar [Comunicaciones créditos](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) para su organización.

> [!IMPORTANT]
> Algunos países son atendidas por los números de teléfono de puente de conferencia gratuito sólo. Para admitir acceso telefónico en estos países, debe utilizar comunicaciones de créditos.

La primera consideración al implementar comunicaciones créditos consiste en decidir el importe inicial de los fondos que desea comprar. Si la organización decide usar recarga automática, debe decidir la cantidad de desencadenador (menor cantidad de fondos) y la cantidad de recarga automática. Su uso real determinará el importe de la recarga automática. Debe supervisar el uso de créditos de comunicaciones con el tiempo y ajustar la cantidad de recarga según sea necesario.

Puede obtener más información acerca de los créditos de comunicaciones [aquí](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización no ha adquirido la conferencia de Audio requiere licencias, decidir si adquirirá licencias de conferencia de Audio recorriendo suscripciones existentes de Office 365, o mediante la adquisición de licencias adicionales de conferencia de Audio.</li><li>Decidir si son necesarias para la implementación de conferencias de Audio créditos de comunicaciones. En tal caso, decida la cantidad inicial de fondos que se va a comprar. Cuando sea necesario, decida la cantidad para el umbral y la cantidad de autorecarga.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Los usuarios que se asignarán licencias de conferencia de Audio del documento.</li><li>Documentar el plan de comunicaciones créditos (importe inicial, importe de desencadenador, importe de recarga automática)</li></ul>|

> [!TIP]
> Puede documentar la lista de asignación de licencias para usuarios de conferencia de Audio mediante el siguiente ejemplo.
>|Usuario  |Oficina  |Licencia de Office 365  |
>|---------|---------|---------|
>|Adele Vance|One Epping Road|Office 365 E5|
>|Alex Wilber|One Epping Road|Office 365 E3, complemento de Audioconferencia|
>|Ben Walters|One Epping Road|Office 365 E3, complemento de Audioconferencia|
>|Christie Cline|One Marina Boulevard|Office 365 E3, complemento de Audioconferencia|
>|Debra Berger|One Marina Boulevard|Office 365 E5|
>|Lee Gu|One Marina Boulevard|Office 365 E5|
>|Emily Braun|32 London Bridge Street|Office 365 E5|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5|
>|Louis Lahr|32 London Bridge Street|Office 365 E5|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferencia|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferencia|

<br>
> [!TIP]
> Los números de planificación de Créditos de comunicaciones se pueden documentar del modo siguiente:
>|         |         |
>|---------|---------|
>|Cantidad inicial|1000 $|
>|Cantidad de umbral|400 $|
>|Cantidad de recarga automática|Por añadir|

<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Números de teléfono para puentes de conferencia

El servicio de Audioconferencia en Office 365 incluye:

-   Números de teléfono de varios tipos de conferencias puente (peaje y gratuito)

-   (Dedicados y compartidos) los números de teléfono de varias categorías de puente de conferencia

-   Soporte para varios idiomas del puente de conferencia (principal y secundario)

-   Un número de teléfono predeterminado para el arrendatario

> [!NOTE]
> Conferencia dedicada el recuento de números de teléfono de puente al límite de números de teléfono que se pueden adquirir por el arrendatario, en función del número de licencias aplicables. Los números de teléfono gratuitos para puentes de conferencia necesitan los Créditos de comunicaciones.

Si debe transferir números de teléfono de puente de conferencia existente al servicio de conferencia de Audio, suponiendo que se cumplen los requisitos específicos del país: puede transferir estos números de teléfono de puente de conferencia existente a Microsoft.

> [!NOTE]
La complejidad de la transferencia de números de teléfono a Microsoft varía considerablemente según el país o región, transportista, número de circuitos implicados y muchos otros factores determinantes. Trabajar con su proveedor actual para investigar cuánto es probable que tomar para ayudar a garantizar que comience antes el proceso suficiente para satisfacer las escalas de tiempo.

Para más información acerca de los números de teléfono de puente de conferencia, consulte los siguientes artículos:

-   [Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [Números de teléfono para Audioconferencia](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obtener números de teléfono de servicio](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [Transferir números de teléfono a Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización necesita números de teléfono de puente de conferencia dedicada.</li><li>Decidir cómo se obtendrán los números de teléfono de puente de conferencia dedicada para ubicaciones de usuario u oficinas en el ámbito de la implementación de conferencias de Audio (que es, obtener de Microsoft o transferencia de números de teléfono existentes).</li><li>Si elige obtener de Microsoft, decida el método a utilizar (formulario de envío o automatizada) para ubicaciones de usuario o las oficinas en el ámbito de aplicación de conferencia de Audio.</li><li>Decidir las preferencias de idioma para configurar para cada número de teléfono de puente de conferencia dedicada.</li><li>Decidir el número de teléfono de puente de conferencia de inquilinos predeterminado.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar el plan maestro para la adquisición de número de teléfono, que detalla cómo se obtendrán los números de teléfono para cada ubicación de usuario o de la oficina en el ámbito de la implementación de conferencias de Audio.</li><li>Si corresponde, complete el formulario de solicitud de número de teléfono nuevo: un formulario para cada ubicación o la oficina.</li><li>Documente las configuraciones número del puente de conferencia detallada del teléfono (compartido y dedicado a números de teléfono de puente de conferencia, las preferencias de idioma para cada número de teléfono de puente de conferencia dedicada, número de teléfono de puente de conferencia de inquilinos predeterminado).</li></ul>|

A continuación es un ejemplo de una plantilla que puede utilizar para capturar los detalles de puente de conferencia.

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla para capturar los detalles de los puentes de conferencia:
>|Oficina   |Adquisición de número de puente y tipo de puente |Número de puente  |Idioma de puente|
>|---------|---------|---------|---------|
>|One Epping Road|Adquirir nuevo, dedicado|Por añadir|Inglés (Australia)|
>|One Marina Boulevard|Adquirir nuevo, compartido|Por añadir|Inglés (Estados Unidos), chino (simplificado, RPC)|
>|32 London Bridge Street|Puerto existente, dedicado|+44 20 7946 0001|Inglés (Reino Unido)|
>|39 quai du Président Roosevelt|Adquirir nuevo, dedicado|Por añadir|Francés (Francia), inglés (Reino Unido)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Configuración de puentes de conferencia

Para ajustar aún más la experiencia del usuario, puede configurar las opciones de toda la organización para unirse a reuniones de conferencia de Audio (entrada y salida grabación nombre llamada y la notificación de la reunión), la longitud PIN del organizador de la reunión y notificación por correo electrónico:

-   Las notificaciones de entrada y salida de la reunión están disponibles en la forma de nombre grabado, número de teléfono y tonos.

-   La longitud del PIN se puede configurar de 4 a 12 dígitos, siendo el PIN de 5 dígitos el predeterminado.

-   Notificación de correos electrónicos en la habilitación de la licencia de conferencia de Audio o cualquier otro cambio controlado por el administrador están habilitados de forma predeterminada. Puede deshabilitar esta característica y tomar el control de las comunicaciones de los usuarios de su organización.

Para los usuarios que están asignados a una licencia de conferencias de Audio, los llamadas gratuitas números predeterminados, que se muestra en las coordenadas de las conferencias de Audio, pueden configurarse para utilizar:

-   El valor predeterminado de nivel de inquilinos.

-   Los números de teléfono de puente de conferencia asignados automáticamente.

-   Números de teléfono de puente en la conferencia configurado manualmente para cada usuario.

Puente de conferencia específica del usuario teléfono los números son útiles en las organizaciones a nivel nacional o globales donde los usuarios se distribuyen y deben proporcionar números locales como los números de teléfono de puente de conferencia predeterminado en sus invitaciones a reuniones.

Pueden buscar los números adicionales configurados en el nivel de inquilinos participantes que se unan desde diferentes ciudades o en el extranjero, pero estos números no aparecen directamente en las invitaciones a reuniones. Las invitaciones a reuniones proporcionan un vínculo que lleva a los participantes a la página de **equipos de conferencia números de acceso telefónico** para ellos buscar el número de teléfono de puente de conferencia más cercano a su ubicación.

También puede configurar cómo sin autenticar llamadores se controlan por cada organizador individuales: si se requieren para iniciar la reunión antes de que los llamadores no autenticados pueden ser admitidos, o permitir que el organizador de la reunión no autenticado a los llamadores para iniciar una reunión .

También puede aplicar configuraciones adicionales para cada usuario a controlar el uso de números de teléfono de puente de conferencia gratuito y de acceso telefónico de salida de una conferencia.

> [!NOTE]
> Estos controles relacionados con los costes solo están disponibles en este momento para clientes de la versión preliminar. Puede inscribir a su organización en el programa de vista previa de https://www.skypepreview.com.

Con estos controles, puede decidir si los organizadores de la reunión pueden proporcionar números de teléfono de puente de conferencia gratuito para reuniones organizadas por ellos, y si pueden marcar los participantes de las reuniones que organizaron. El nivel de control de acceso telefónico de salida abarca desde evitar completamente marcado, hasta permitir sólo para hacer llamadas a números nacionales, para lo que permite hacer llamadas a números nacionales e internacionales.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización requiere notificaciones de entrada y salida, y, si lo hace, el tipo de notificación que deban aplicarse (tonos, número de teléfono o nombre grabado).</li><li>Decida la duración del Audio Conferencing NIP que cumpla sus requisitos de seguridad de la organización.</li><li>Decidir si la organización desea tomar el control de las comunicaciones de los usuarios relacionados con el servicio de conferencia de Audio.</li><li>Decida qué números de teléfono para puentes de conferencia se asignarán a cada organizador de reuniones.</li><li>Decidir si necesitan utilizar números de teléfono de puente de conferencia gratuito para sus reuniones algunos organizadores de la reunión.</li><li>Decidir si algunos organizadores necesitan permitir que los llamadores no autenticados iniciar una reunión.</li><li>Decidir si algunos organizadores necesitan conferencia acceso telefónico de salida para ser controlada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la configuración de puentes de conferencia con todos los detalles (notificaciones de entrada y salida, longitud de PIN y notificación por correo electrónico de cambios en la configuración).</li><li>Los números de teléfono de puente de conferencia para ser asignado a cada organizador de la reunión y la configuración correspondiente a la directiva de control de llamadas sin autenticar y gratuito de documentos y marcar los controles.</li></ul>|

> [!TIP]
> La configuración de puente de conferencia puede figurar como en el ejemplo siguiente.
>|         |         |
>|---------|---------|
>|Habilitar las notificaciones de entrada y salidas de las reuniones|Habilitado|
>|Tipo de anuncio de entrada/salida|Tonos|
>|Pedir a los autores de llamada que graben su nombre antes de unirse a la reunión|Deshabilitado|
>|Longitud de PIN|5|
>|Enviar correos automáticamente a los usuarios si cambia su configuración de acceso telefónico|Deshabilitado|

<br>
> [!TIP]
> Puede documentar la lista de asignación de configuración de puente de conferencia para los usuarios de conferencia de Audio mediante el siguiente ejemplo.
>|Usuario  |Oficina  |Número de pago predeterminado  |Número gratuito predeterminado  |Permitir número gratuito  |Los autores de llamadas sin autenticar no pasan por la sala de espera  |Llamadas desde la conferencia  |
>|---------|---------|---------|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Por añadir|Por añadir|Sí|Habilitado|Internacionales y nacionales|
>|Alex Wilber|One Epping Road|Por añadir|Por añadir|No|Deshabilitado|No se permiten|
>|Ben Walters|One Epping Road|Por añadir|Por añadir|No|Deshabilitado|No se permiten|
>|Christie Cline|One Marina Boulevard|Por añadir|Por añadir|Sí|Deshabilitado|Nacionales|
>|Debra Berger|One Marina Boulevard|Por añadir|Por añadir|Sí|Habilitado|Nacionales|
>|Lee Gu|One Marina Boulevard|Por añadir|Por añadir|Sí|Habilitado|Nacionales|
>|Emily Braun|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Habilitado|No se permiten|
>|Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Deshabilitado|No se permiten|
>|Louis Lahr|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Deshabilitado|No se permiten|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Por añadir|Por añadir|No|Deshabilitado|Nacionales|
>|Rachelle Cormier|39 quai du Président Roosevelt|Por añadir|Por añadir|Sí|Habilitado|Internacionales y nacionales|
>|Isabell Potvin|39 quai du Président Roosevelt|Por añadir|Por añadir|No|Deshabilitado|Nacionales|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Administrar números de teléfono de voz de nube

Para la implementación de conferencias de Audio, puede adquirir nuevos números de teléfono o números de teléfono existentes de transferencia/port.

Para que los usuarios puedan marcar números de teléfono de la forma en la que están acostumbrados a — como omitir códigos de área para las llamadas locales, omitiendo el código de país para llamadas nacionales o incluso utilizando dígitos corto de marcado cuando se realiza la conferencia marcando: puede configurar un plan de marcado personalizada y asignarlo a los usuarios.

## <a name="acquire-new-telephone-numbers"></a>Adquirir nuevos números de teléfono

Los dos tipos de números de teléfono dentro de las soluciones de voz de nube de Microsoft son:

-   Números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización.

-   Números de servicio, disponibles como teléfono y números de servicio gratuito, que tienen mayor capacidad de llamadas simultáneas que números de suscriptor y se pueden asignar a servicios como las conferencias de Audio, operadores automáticos o llamar a colas.

Para obtener más información acerca de estos tipos de números de teléfono, ver [distintos tipos de números de teléfono utilizados para llamar a los planes](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Recuento total de llamadas telefónicas de números que puede obtener dependen de los tipos de números de teléfono y el número de licencias ha comprado y asignado a los usuarios.

Cuando se trata de números de servicio, debe planear cuidadosamente su implementación de conferencias de Audio. Evaluar si su negocio requiere números de teléfono de puente de conferencia dedicada; Si no es así, la organización puede optar por usar números de teléfono de puente de conferencias compartidas.

Para obtener más información sobre el número total de números de teléfono que puede obtener, consulte [cuántos números de teléfono puede conseguir?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de usuario o las oficinas donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>Decidir el tipo de números de teléfono de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones de usuario o las oficinas donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>Documente el tipo de números de teléfono de Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir los números de teléfono existentes

Si su organización desea transferir (o puerto) existente de números de teléfono a Microsoft, puede hacerlo enviando una solicitud de pedido de puerto a Microsoft.

Puede transferir todos los existentes números de teléfono a la vez (puerto completo), y, en algunos mercados, puede transferir un subconjunto de los números de teléfono existente (puerto parcial). Un puerto parcial puede ser útil en casos donde desea mover el puente de conferencia de acceso telefónico al servicio de conferencia de Audio.

Un pedido único puerto puede transferir sólo los números de teléfono a un tipo de número de teléfono único. Si necesita transferir algunos de los números de teléfono como números de suscriptor y otros como números de servicio, se recomienda que complete primero la transferencia a Microsoft y, a continuación, realizar la conversión, como son los números de control de Microsoft.

Como alternativa, si se admite un puerto parcial, puede enviar varias solicitudes de puerto, solicitud de un puerto a la vez. Sin embargo, este enfoque alternativo, prolongará su contrato con el proveedor de servicios de telecomunicaciones existentes.

Traslado de número de teléfono es un tema complejo y requiere planificación minuciosa, la coordinación y administración de adecuadamente las expectativas de los agentes interesados. Para obtener más información, consulte los artículos siguientes:

-   [Transferir los números de teléfono para Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Preguntas comunes sobre la transferencia de números de teléfono](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de usuario o las oficinas donde se transferirán los números de teléfono existentes a Microsoft.</li><li>Decidir el tipo de números de teléfono de transferirse a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones de usuario o las oficinas donde se transferirán los números de teléfono existentes a Microsoft.</li><li>Documente el tipo de números de teléfono de transferirse a Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planes de marcado

A Dial Plan in the Phone System feature of Office 365 is a set of normalization rules that translates dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing. The Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial-out scenarios (for example, invite participants via PSTN and dial back, “call me” feature).

In the Phone System feature of Office 365, there are two types of dial plans:

-   **Service dial plan:** This is the default dial plan that’s applied to users based on their Office 365 usage location, and it can’t be modified.

-   **Tenant dial plan:** This is a customizable dial plan within a tenant, which is further divided into two types:

    -   **Plan de marcado de inquilinos global:** El plan de marcado que se aplica a todos los usuarios de los inquilinos.

    -   **Plan de marcado de usuario inquilino:** El plan de marcado que se aplica únicamente a usuarios específicos.

El plan de marcado eficaz asignado a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 del usuario) y el plan de marcado de inquilinos (puede ser el plan de marcado de inquilinos global o plan de marcado de usuario inquilino).

![Tabla muestra tres combinaciones de servicio y los inquilinos planes de marcación.] (media/audio_conferencing_image8.png "Tabla muestra tres combinaciones de servicio y los inquilinos planes de marcación.")

> [!Important]
> Puede haber un máximo de 25 reglas de normalización en cada plan de marcado de inquilinos; por lo tanto, es importante evitar la duplicación de las reglas de normalización que ya están disponibles como parte del servicio de plan de marcado.

Para obtener más información acerca de los planes de marcado, consulte [¿Cuáles son los planes de marcación?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización requiere que los planes de marcado personalizado (los requerimientos del negocio, los requisitos de adopción etc.).</li><li>En caso de necesitarlos, decida qué ámbito del plan de marcado de inquilino (inquilino global o usuario de inquilino) se ajusta a los requisitos de los planes de marcado personalizados.</li><li>En su caso, decidir los planes de marcado de inquilinos que va a crear para admitir ubicaciones de usuario u oficinas en el ámbito de la implementación de voz de la nube.</li><li>En su caso, decidir qué usuarios requieren un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar los planes de marcado personalizada y las reglas de normalización asociados a configurarse como parte de la implementación de voz de la nube.</li><li>Documente los usuarios asignar un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario.</li></ul>|

> [!TIP]
> Si es aplicable a su proyecto, puede utilizar la siguiente plantilla para documentar las configuraciones de plan de marcado de inquilinos.
>|Nombre de plan de marcado de inquilino<br>_Descripción_  |Nombre de reglas de normalización<br>_Descripción_  |Patrón<br>Traducción<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_Plan de marcado de One Epping Road North Ryde, NSW, AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_Normalización de número local para NSW, Australia_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_Normalización de número gratuito para Australia_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_Normalización de número de servicio para Australia_|^(000\|1[0125]\d{1,8})$<br>1 $<br>False|
>|**SG-Singapore-OMB**<br>_Plan de marcado de OMB Singapore, SG_|**SG-OMB-Internal**<br>_Número interno (x8000 â €"x 8999) para la oficina de OMB, Singapur_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_Normalización de número gratuito para Singapur_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_Normalización de número de servicio para Singapur_|^(1\d{3,4}\|9\d{2})$<br>1 $<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Internal number (x7000 â€“ x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalización de número gratuito para Francia_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalización de número de servicio para Francia_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>1 $<br>False|

<br>
> [!TIP]
> La plantilla de ejemplo siguiente se puede utilizar para documentar las asignaciones de planes de marcado de su proyecto:
>|Usuario  |Oficina  |Tipo de plan de marcado  |Nombre de plan de marcado  |
>|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
>|Alex Wilber|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
>|Ben Walters|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
>|Christie Cline|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
>|Debra Berger|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
>|Lee Gu|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Lidia Holloway|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Louis Lahr|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Document service decisions 

Use the information from the previous sections of this article to document your service decisions. In general, this documentation will contain the following main sections:

-   Lista de habilitación del sitio de servicio de Audioconferencia

-   Lista de asignación de licencias para los organizadores de reuniones de Audioconferencia

-   Números de planificación de Créditos de comunicaciones

-   Detalles de puentes de conferencia

-   Configuración de puentes de conferencia

-   Asignaciones de configuraciones de puentes de conferencia

-   Phone numbers acquisition plans

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

<!--ENDOFSECTION-->