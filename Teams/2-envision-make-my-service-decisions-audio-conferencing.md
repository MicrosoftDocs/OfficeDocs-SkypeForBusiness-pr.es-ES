---
title: Tomar decisiones de servicio de conferencia de Audio - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Obtenga información sobre las reuniones, las licencias y la disponibilidad, configurar las opciones de puente de conferencia, adquirir o transferir los números de teléfono, elija inquilino planes de marcado.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 577ee414529223dbc435d8570a55adb6883fd8a2
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "19695625"
---
# <a name="make-my-service-decisions"></a>Tomar decisiones de mi servicio

Para planear la implementación técnica de conferencias de Audio, debe realizar una serie de decisiones de servicio antes de tiempo para preparar mejor a su organización a implementar una solución que cumple los requisitos de negocio definidos.

## <a name="audio-conferencing-in-teams"></a>Conferencias de audio en los equipos

Como parte de la definición de las características necesarias de conferencias de Audio en Microsoft Teams, uno de los primeros pasos consiste en evaluar la guía pública más reciente para determinar:

-   Qué características de conferencia de Audio en los equipos que se va a implementar para los usuarios en el ámbito.

-   Se esperaba requisitos de funcionalidad de usuario para conferencias de Audio en los equipos.

-   Confirmación de que las características de conferencia de Audio en los equipos que se describen en la guía pública más reciente cumplen el usuario, las funciones y los requisitos de ámbito, dentro de la escala de tiempo de la implementación.

> [!NOTE]
> La guía básica de los equipos más reciente para la identificación de las características de conferencia de Audio de los equipos en el ámbito para la implementación se puede encontrar en <https://aka.ms/skype2teamsroadmap>.

## <a name="meetings-in-teams"></a>Reuniones en Teams

Los equipos proporciona a los usuarios la capacidad de programar y unirse a reuniones en línea mediante el uso de vídeo de alta definición, opciones de conferencia de acceso telefónico de voz sobre IP (VoIP) y RTC.

Se pueden programar reuniones como las conferencias privadas (sólo los participantes invitados se pueden unir a) o reuniones de canal (abierto para todos los usuarios que tienen acceso al canal) y los usuarios también pueden iniciar reuniones improvisadas dentro de los canales.

> [!NOTE]
> Para obtener más información acerca de las características de las reuniones en los equipos, vea [Skype para la empresa a la guía básica de las capacidades de los equipos de Microsoft] https://aka.ms/skype2teamsroadmap).

Los participantes de la reunión puede participar en las reuniones de los equipos marcando en el teléfono de pago o el puente de conferencia de acceso telefónico gratuito los números de teléfono a través de landlines o teléfonos móviles. Además, los usuarios pueden permitir que el servicio de conferencia de Audio a iniciar la característica "Llamarme" para que puedan participar en una reunión mediante la necesidad de llamar a sus teléfonos (es útil cuando la conexión de datos no es confiable) el puente de conferencia o reunión permiten los organizadores de invitar a la reunión participantes mediante marcación a sus teléfonos.

> [!IMPORTANT]
> Conferencias de audio en los equipos no es compatible con los proveedores de servicios de audioconferencia (ACP).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilidad de Audioconferencia

Antes de planear la implementación de conferencias de Audio en los equipos, debe revisar la disponibilidad del servicio de conferencia de Audio como se detalla en la [disponibilidad de país y región para las conferencias de Audio y planes de llamada](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Debido a restricciones legales, para conferencias de Audio esté disponible para organizaciones multinacionales, el contrato de suscripciones a Office 365 debe ser proceden de países y regiones donde el servicio de conferencia de Audio no está disponible en el mercado.

Después de confirmar que la organización tiene derecho a obtener el servicio de conferencia de Audio, compilar la lista de ubicaciones de usuario o las oficinas donde implementará el servicio de conferencia de Audio, basada en la lista de disponibles países y regiones.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida qué oficinas o ubicaciones de usuario implementarán el servicio de Audioconferencia.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Decida qué oficinas o ubicaciones de usuario se habilitarán para el servicio de Audioconferencia.</li></ul>|

> [!TIP]
> A continuación es un ejemplo de una plantilla de lista de habilitación de sitio de conferencia de Audio:
>|Oficina   |Ubicación |Servicio de conferencia RTC  |
>|---------|---------|---------|
>|One Epping Road|Australia|Audioconferencia|
>|100 Cyberport Road|RAE de Hong Kong|Conferencia RTC antigua|
>|One Marina Boulevard|Singapur|Audioconferencia|
>|32 London Bridge Street|Reino Unido|Audioconferencia|
>|39 quai du Président Roosevelt|Francia|Audioconferencia|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licencias para Audioconferencia

Una [licencia de conferencias de Audio](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) está disponible como parte de los planes de suscripción de Office 365 E5, o como servicio complementario a planes de suscripción de Office 365 E1 o E3 de Office 365.

> [!NOTE]
> Conferencia de RTC o telefónico en los equipos no es compatible con los proveedores de servicios de audioconferencia (ACP).
> <br>Si está usando la Conferencia RTC para Skype Empresarial Online, puede beneficiarse al instante de Audioconferencia en Microsoft Teams.

Para proporcionar números de teléfono de puente de conferencia gratuito y para admitir la conferencia de salida para los números de teléfono internacional, debe establecer [Comunicaciones créditos](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) para su organización.

> [!IMPORTANT]
> Algunos países son atendidas por los números de teléfono de puente de conferencia gratuito sólo. Para admitir telefónico en estos países, debe usar créditos Communications.

La primera consideración al implementar Communications créditos consiste en decidir la cantidad inicial de los fondos que desea comprar. Si la organización decide usar automático recarga, debe decidir el desencadenador importe (menor de fondos) y la cantidad de recarga de automático. Su uso real determinará la cantidad de recarga de automático. Debe supervisar el uso de créditos de comunicaciones a través del tiempo y ajustar la cantidad de recarga según sea necesario.

Encontrará más información acerca de las comunicaciones créditos [aquí](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización aún no ha adquirido la conferencia de Audio necesarios licencias, decidir si las licencias de conferencias de Audio adquirirá pasando de suscripciones de Office 365 existentes o mediante la adquisición de licencias de complemento de conferencias de Audio.</li><li>Decidir si son necesarios para la implementación de conferencias de Audio créditos Communications. En tal caso, decida la cantidad inicial de fondos que se va a comprar. Cuando sea necesario, decida la cantidad para el umbral y la cantidad de autorecarga.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Los usuarios que se le asignen licencias de conferencias de Audio del documento.</li><li>Documentar el plan de comunicaciones créditos (cantidad inicial, cantidad de desencadenador, cantidad de recarga de automático)</li></ul>|

> [!TIP]
> Puede documentar la lista de asignación de licencia para los usuarios de conferencia de Audio mediante el siguiente ejemplo.
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

-   Los números de teléfono de puente de varios tipos de conferencia (teléfono de pago y gratuitos)

-   Números (dedicados y compartidos) de teléfono de varias categorías de puente de conferencia

-   Soporte para varios idiomas del puente de conferencia (principal y secundario)

-   Un número de teléfono predeterminado para el inquilino

> [!NOTE]
> Conferencia dedicada el recuento de los números de teléfono de puente hacia el límite de números de teléfono que se pueden adquirir por inquilino, según el número de licencias aplicables. Los números de teléfono gratuitos para puentes de conferencia necesitan los Créditos de comunicaciones.

Si debe transferir números de teléfono de puente de conferencia existente para el servicio de conferencia de Audio, suponiendo que cumplen los requisitos específicos de país, puede transferir estos números de teléfono de puente de conferencia existente a Microsoft.

> [!NOTE]
La complejidad de la transferencia de los números de teléfono a Microsoft en gran medida varía en función de país o región, compañía, número de circuitos implicados y muchos otros factores determinantes. Trabajar con su proveedor actual para investigar ¿durante cuánto tiempo se trata llevaría a cabo para ayudar a garantizar que iniciar el proceso de tiempo suficiente para satisfacer las escalas de tiempo.

Para obtener más información acerca de los números de teléfono de puente de conferencia, revise los siguientes artículos:

-   [Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [Números de teléfono para Audioconferencia](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obtener números de teléfono de servicio](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [Transferir números de teléfono a Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización necesita números de teléfono de puente de conferencia dedicada.</li><li>Decidir cómo se obtendrán los números de teléfono de puente de conferencia dedicada para oficinas o ubicaciones de usuario en el ámbito de la implementación de conferencias de Audio (que es, obtener de Microsoft o transferencia de números de teléfono existentes).</li><li>Si decide obtenerlas de Microsoft, decidir el método a usar (del formulario de envío o automatizada) para las ubicaciones de usuario o las oficinas en el ámbito de la implementación de conferencias de Audio.</li><li>Decidir las preferencias de idioma para configurar para cada número de teléfono de puente de conferencia dedicada.</li><li>Decidir el número de teléfono de puente de conferencia de inquilino de forma predeterminada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar el plan de patrón de adquisición de número de teléfono, que se detalla cómo se obtendrán los números de teléfono para cada ubicación de usuario o de office en el ámbito de la implementación de conferencias de Audio.</li><li>Si procede, complete el formulario de solicitud de número de teléfono nuevo: un formulario para cada ubicación o la oficina.</li><li>Documentan la configuración número del puente de conferencia detallada del teléfono (shared y dedicada números de teléfono de puente de conferencia, las preferencias de idioma para cada número de teléfono de puente de conferencia dedicada, número de teléfono de puente de conferencia de inquilinos predeterminado).</li></ul>|

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

Para adaptar aún más la experiencia del usuario, puede configurar las opciones de toda la organización para que se unan a las reuniones de conferencia de Audio (entrada y salida grabación de nombre de notificación y autor de la llamada de la reunión), la longitud PIN del organizador de la reunión y notificación de correo electrónico:

-   Las notificaciones de entrada y salida de la reunión están disponibles en la forma de nombre grabado, número de teléfono y tonos.

-   La longitud del PIN se puede configurar de 4 a 12 dígitos, siendo el PIN de 5 dígitos el predeterminado.

-   Notificación de los correos electrónicos enviados en la habilitación de la licencia de conferencias de Audio o cualquier otro cambio controlada por el administrador están habilitados de forma predeterminada. Puede deshabilitar esta característica y tomar el control de comunicaciones de los usuarios de su organización.

Para los usuarios que tengan asignados una licencia de conferencias de Audio, el teléfono de pago/toll-free números predeterminados, que se muestra en las coordenadas de conferencias de Audio, pueden configurarse para usar:

-   El valor predeterminado de nivel de inquilino.

-   Los números de teléfono de puente de conferencia asignados automáticamente.

-   Números de teléfono de puente en la conferencia configurado manualmente para cada usuario.

Puente de conferencia específica del usuario son normalmente útiles para las organizaciones globales o por todo el país donde los usuarios se distribuyen y deben proporcionar números locales como los números de teléfono de puente de conferencia de forma predeterminada en sus invitaciones a reuniones números de teléfono.

Los participantes que se unan a desde diferentes ciudades o extranjero pueden buscar números adicionales configurados en el nivel de inquilino, pero no aparecen estos números directamente en las invitaciones a reuniones. Las invitaciones a reuniones proporcionan un vínculo que lleva a los participantes a la página de **conferencia de los equipos de números de acceso telefónico** para ellos buscar el número de teléfono de puente de conferencia más cercano a su ubicación.

También puede configurar cómo sin autenticar los autores de llamadas son resueltos por cada organizador de la reunión individuales, si se debe requerir el organizador de la reunión para iniciar la reunión antes de que los autores de llamadas sin autenticar pueden ser admitidos o permiten no autenticado a los autores de llamadas para iniciar una reunión .

También puede aplicar configuraciones adicionales para cada usuario controlar el uso de números de teléfono de puente de conferencia gratuito y de salida de una conferencia.

> [!NOTE]
> Estos controles relacionados con los costes solo están disponibles en este momento para clientes de la versión preliminar. Puede inscribirse la organización en el programa de vista previa de https://www.skypepreview.com.

Con estos controles, puede decidir si los organizadores de reuniones pueden proporcionar números de teléfono de puente de conferencia gratuito para las reuniones organizadas por ellos, y si los participantes pueden marcar un número de las reuniones que organizan. El nivel de control de acceso telefónico de salida abarca desde completamente evitar llamadas salientes, para que sólo permite hacer llamadas a números nacionales, para lo que permite hacer llamadas a números nacionales e internacionales.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización requiere las notificaciones de entrada y salida, y, si lo hace, el tipo de notificación que se va a implementar (tonos, nombre grabado o número de teléfono).</li><li>Decidir la longitud de PIN de conferencia de Audio que cumpla los requisitos de seguridad de la organización.</li><li>Decidir si su organización desea tomar el control de las comunicaciones de usuario relacionados con el servicio de conferencia de Audio.</li><li>Decida qué números de teléfono para puentes de conferencia se asignarán a cada organizador de reuniones.</li><li>Decidir si es necesario usar números de teléfono de puente de conferencia gratuito para sus reuniones algunos los organizadores de reuniones.</li><li>Decidir si algunos los organizadores de reuniones es necesario permitir que los autores de llamadas sin autenticar iniciar una reunión.</li><li>Decidir si algunos los organizadores de reuniones necesitan desconexión de conferencias esté controlado.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la configuración de puentes de conferencia con todos los detalles (notificaciones de entrada y salida, longitud de PIN y notificación por correo electrónico de cambios en la configuración).</li><li>Los números de teléfono de puente de conferencia para ser asignado a cada organizador de la reunión y la configuración correspondiente para controlar la directiva para los autores de llamadas sin autenticar y gratuito de documentos y controles de marcado.</li></ul>|

> [!TIP]
> Como en el ejemplo siguiente se puede documentar la configuración de puente de conferencia.
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

## <a name="manage-cloud-voice-telephone-numbers"></a>Administrar números de teléfono de voz en la nube

Para la implementación de conferencias de Audio, puede elegir adquirir nuevos números de teléfono o números de teléfono existentes de transferencia/puerto.

Para permitir a los usuarios marcar números de teléfono de la forma en que están acostumbrados a, como se omite los códigos de área para las llamadas locales, se omite el código de país para realizar llamadas nacionales o incluso mediante breve dígito llaman al realizar la conferencia marcar un número, puede configurar un plan de marcado personalizado y asignar a los usuarios.

## <a name="acquire-new-telephone-numbers"></a>Adquirir nuevos números de teléfono

Los dos tipos de números de teléfono dentro de las soluciones de voz de la nube de Microsoft son:

-   Números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización.

-   Números de servicio, disponibles como números de un servicio gratuito, que tengan la mayor capacidad de llamadas concurrentes que números de suscriptor y que se pueden asignar a servicios, como conferencias de Audio, operadores automáticos o colas de llamadas y de pago.

Para obtener más información acerca de estos tipos de números de teléfono, vea [distintos tipos de números de teléfono utilizados para llamar a los planes](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

El recuento total de teléfono números que puede obtener dependen de los tipos de número de teléfono y el número de licencias ha comprado y ha asignado a los usuarios.

En cuanto a los números de servicio, debe planear cuidadosamente la implementación de conferencias de Audio. Evaluar si su negocio requiere números de teléfono de puente de conferencia dedicada; en caso contrario, su organización puede optar por usar números de teléfono de puente de conferencia compartida.

Para obtener más información acerca de la cantidad total de números de teléfono que puede obtener, vea [cuántos números de teléfono puede obtener?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de usuario o las oficinas de donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>Decidir el tipo de números de teléfono se obtienen de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar las ubicaciones de usuario o las oficinas de donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>El tipo de números de teléfono se obtienen de Microsoft de documento.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir los números de teléfono existentes

Si su organización desea transferir (o del puerto) existente de números de teléfono a Microsoft, puede hacerlo mediante el envío de una solicitud de orden de puerto a Microsoft.

Puede transferir todos los sus números de teléfono existentes a la vez (puerto completo), y, en algunos mercados, puede transferir un subconjunto de sus números de teléfono existente (puerto parcial). Un puerto parcial puede ser útil en los casos donde desea mover el puente de conferencia de conexión al servicio de conferencia de Audio.

Un orden de puerto único sólo puede transferir los números de teléfono a un tipo de número de teléfono único. Si necesita transferir algunas de sus números de teléfono como números de suscriptor y algunos como números de servicio, se recomienda que complete la transferencia a Microsoft en primer lugar y, a continuación, realizar la conversión tan pronto como los números son dentro de control de Microsoft.

Como alternativa, si se admite el puerto parcial, puede enviar varias solicitudes de puerto, solicitud de un puerto a la vez. Sin embargo, este enfoque alternativo va a prolongar su contrato con su proveedor de servicios de telecomunicaciones existente.

Portabilidad del número de teléfono es un tema complejo y requiere planeación minuciosa, la coordinación y administrar adecuadamente las expectativas de las partes interesadas. Para obtener más información, vea los siguientes artículos:

-   [Transferencia de los números de teléfono a Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Preguntas comunes sobre la transferencia de números de teléfono](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de usuario o las oficinas donde los números de teléfono existentes se transferirá a Microsoft.</li><li>Decidir el tipo de números de teléfono que se transfieran a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar las ubicaciones de usuario o las oficinas donde los números de teléfono existentes se transferirá a Microsoft.</li><li>El tipo de números de teléfono que se transfieran a Microsoft de documento.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planes de marcado

Un Plan de marcado de la característica de sistema telefónico de Office 365 es un conjunto de reglas de normalización que traduce marca números de teléfono en un formato alternativo (normalmente, el formato E.164) para la autorización de llamadas y el enrutamiento de llamadas. El servicio de conferencia de Audio aprovecha las mismas funciones que usa sistema telefónico para convertir los números de teléfono marcado en escenarios de salida de la conferencia (por ejemplo, invitar a participantes a través de RTC y marcado, la característica "Llamarme").

En la función de sistema de teléfono de Office 365, hay dos tipos de planes de marcado:

-   **Plan de marcado de servicio:** Es el valor predeterminado de plan de marcado que se aplica a los usuarios en función de su ubicación de uso de Office 365, y no puede modificarse.

-   **Plan de marcado de inquilino:** Se trata de un plan de marcado personalizable dentro de un inquilino, que se divide en dos tipos:

    -   **Plan de marcado de inquilino global:** El plan de marcado que se aplica a todos los usuarios en el inquilino.

    -   **Plan de marcado de usuario inquilino:** El plan de marcado que se aplica únicamente a usuarios específicos.

El plan de marcado efectivos asignado a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 de un usuario) y plan de marcado de inquilino (puede ser el plan de marcado global del inquilino o plan de marcado de usuario del inquilino).

![Tabla se muestran los planes de marcado de tres combinaciones de servicio e inquilino.] (media/audio_conferencing_image8.png "Tabla se muestran los planes de marcado de tres combinaciones de servicio e inquilino.")

> [!Important]
> Puede haber un máximo de 25 reglas de normalización en cada plan de marcado de inquilino; por lo tanto, es importante evitar la duplicación de reglas de normalización que ya están disponibles como parte del servicio de plan de marcado.

Para obtener más información acerca de los planes de marcado, consulte [¿Cuáles son los planes de marcado?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización requiere planes de marcado personalizado (requisitos empresariales, los requisitos de adopción y así sucesivamente).</li><li>En caso de necesitarlos, decida qué ámbito del plan de marcado de inquilino (inquilino global o usuario de inquilino) se ajusta a los requisitos de los planes de marcado personalizados.</li><li>Si procede, decidir los planes de marcado de inquilinos que va a crear para admitir oficinas o ubicaciones de usuario en el ámbito de la implementación de voz en la nube.</li><li>Si procede, decidir qué usuarios requieren un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar los planes de marcado personalizado y las reglas de normalización asociado a configurarse como parte de la implementación de voz en la nube.</li><li>Los usuarios para que se le ha asignado un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario del documento.</li></ul>|

> [!TIP]
> Si es aplicable a su proyecto, puede usar la plantilla siguiente para documentar las configuraciones de plan de marcado de inquilinos.
>|Nombre de plan de marcado de inquilino<br>_Descripción_  |Nombre de reglas de normalización<br>_Descripción_  |Patrón<br>Traducción<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_Plan de marcado de One Epping Road North Ryde, NSW, AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_Normalización de número local para NSW, Australia_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
>||**AU-TollFree**<br>_Normalización de número gratuito para Australia_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
>||**AU-Service**<br>_Normalización de número de servicio para Australia_|^ (000\|1 [0125] \d{1,8}) $<br>1 $<br>False|
>|**SG-Singapore-OMB**<br>_Plan de marcado de OMB Singapore, SG_|**SG-OMB-Internal**<br>_Número interno (x8000 â €"x 8999) para office OMB, Singapur_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_Normalización de número gratuito para Singapur_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
>||**SG-Service**<br>_Normalización de número de servicio para Singapur_|^ (1\d{3,4}\|9\d{2}) $<br>1 $<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Número interno (x7000 â €"x 7999) para 39 quai du presidente Roosevelt office, Issy-les-Moulineaux, Francia_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalización de número gratuito para Francia_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalización de número de servicio para Francia_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>1 $<br>False|

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

## <a name="document-service-decisions"></a>Decisiones del servicio de documento 

Use la información de las secciones anteriores de este artículo para documentar las decisiones de servicio. En general, esta documentación contiene las secciones principales siguientes:

-   Lista de habilitación del sitio de servicio de Audioconferencia

-   Lista de asignación de licencias para los organizadores de reuniones de Audioconferencia

-   Números de planificación de Créditos de comunicaciones

-   Detalles de puentes de conferencia

-   Configuración de puentes de conferencia

-   Asignaciones de configuraciones de puentes de conferencia

-   Planes de adquisición de números de teléfono

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

<!--ENDOFSECTION-->