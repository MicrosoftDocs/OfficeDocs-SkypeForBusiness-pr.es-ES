---
title: Hacer que el sistema de teléfono con planes de llamar a decisiones de servicio - Teams de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Elija entre planes de llamada y licencias, configurar ubicaciones de emergencia y características como correo de voz e identificador de llamadas, adquirir o transferir los números de teléfono.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e382992f3170f16718eac8d2c6f0902dbaff3b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="make-my-service-decisions"></a>Tomar decisiones de mi servicio

## <a name="calling-in-teams"></a>Llamar en Microsoft Teams

Con Teams de Microsoft, los usuarios pueden realizar y recibir llamadas de teléfono a o desde la red telefónica pública conmutada (PSTN). Los usuarios pueden usar sus propios números de teléfono dedicada para efectuar y recibir llamadas nacionales e internacionales de las aplicaciones de cliente de los equipos, con funciones avanzadas que incluyen correo de voz y llamadas de emergencia (911 mejorado).

> [!NOTE]
> La guía básica de los equipos más reciente para identificar las características de conferencia de Audio de equipos en el ámbito de la implementación puede encontrarse en <https://aka.ms/skype2teamsroadmap>.

## <a name="phone-system-in-teams"></a>Sistema telefónico en los equipos

Para que los usuarios de los equipos poder realizar y recibir llamadas PSTN, deben habilitarse para el sistema de teléfono, una característica de Office 365.

Para habilitar la conectividad a la red PSTN, su organización puede utilizar Microsoft como su proveedor de servicios de telecomunicaciones. Finalmente, también tendrá la opción de "traiga su propio" proveedor de servicios de telecomunicaciones para permitir la conexión a RTC para el sistema telefónico.

> [!IMPORTANT]
> La posibilidad de elegir su propio proveedor de servicios de telecomunicaciones para el sistema de teléfono estarán disponible en el futuro. Para obtener más información acerca de la cronología proyectada, revise el [Skype para empresas Roadmap de capacidades de los equipos de Microsoft](https://aka.ms/skype2teamsroadmap).

## <a name="phone-system-with-calling-plans"></a>Sistema telefónico con Planes de llamada

Para utilizar Microsoft como proveedor de servicios de la telecomunicación, debe obtener licencias de Plan de llamadas y asignarlos a los usuarios del sistema telefónico.

Hay dos tipos principales de planes de llamada:

-   Plan de llamadas nacional

-   Plan de llamadas nacional e internacional

Cada tipo de plan de llamadas asigna un número determinado de minutos de llamadas al mes a cada usuario que se ha asignado la licencia. Cuando se agota la asignación de minutos de llamada, el usuario no podrá realizar llamadas salientes, excepto para llamadas de emergencia, hasta que el ciclo de facturación de mes siguiente. Si desea que los usuarios puedan continuar y realizar llamadas salientes incluso después de que hayan agotado su asignación de minutos de llamada, o para permitir que los usuarios que tienen un plan de llamadas nacional realizar llamadas internacionales, puede configurar comunicaciones créditos para su organización.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilidad de Planes de llamada

Antes de planear la implementación de planes de llamada en los equipos, compruebe que el servicio de llamada a planes está disponible en su área revisando [la disponibilidad de país y región para conferencias de Audio y llamar a los planes](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Debido a restricciones legales, para llamar a planes que estén disponibles para las organizaciones multinacionales, el contrato para suscripciones a Office 365 debe basarse en un país o región donde está disponible el servicio llamando a los planes, o donde puede ser el servicio planes de llamada adquirido.

Después de confirmar que su organización puede obtener el servicio de llamada a planes, compilar la lista de ubicaciones de usuario u oficinas donde podrá implementa el servicio llamando a los planes basándose en la lista de regiones y países disponibles.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir qué ubicaciones de usuario u oficinas se implementa los planes de llamada de servicio.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones de usuario o las oficinas esté habilitada para el servicio de llamada a planes.</li></ul>|

> [!TIP]
> A continuación es un ejemplo de un sistema telefónico con planes de llamada lista de habilitación del sitio.
>|Oficina   |Ubicación |Servicio de sistema de teléfono  |
>|---------|---------|---------|
>|One Epping Road|Australia|Servicio de RTC antiguo|
>|100 Cyberport Road|RAE de Hong Kong|Servicio de RTC antiguo|
>|One Marina Boulevard|Singapur|Servicio de RTC antiguo|
>|32 London Bridge Street|Reino Unido|Sistema telefónico con Planes de llamada|
>|39 quai du Président Roosevelt|Francia|Sistema telefónico con Planes de llamada|

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con una llamada a planes de Office 365, todos los usuarios de su organización deben tener un único entrante directa marcando el número de teléfono (DID) y una dirección de emergencia validada correspondiente. Revise los [números de teléfono de voz de nube de administrar](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers) para planificar la adquisición de número de teléfono para la implementación de planes de llamada.

Para configurar números de teléfono para llamar a los planes, debe asignar una dirección de emergencia a cada número de teléfono antes de asignar al número a un usuario. Este paso es necesario para poder realizar llamadas de emergencia. La dirección de emergencia debe validarse para asegurarse de que está en el formato correcto para ser utilizado por los servicios de respuesta de emergencia.

> [!IMPORTANT]
> Llamar a los servicios de emergencia funciona de forma diferente en el servicio llamando a los planes que en los servicios de telefonía tradicional. Es importante que entienda estas diferencias y comunicarlas a todos los usuarios. Para obtener más información, consulte [emergencia llamando a términos y condiciones](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions) .

Además de suministrar una dirección de emergencia validada, puede definir las ubicaciones de emergencia y asociarlos con la dirección de emergencia validada para proporcionar una ubicación más exacta dentro de una dirección. Una ubicación de emergencia es, normalmente, el número de edificio, la planta, la sección del edificio o el número de oficina donde se encuentra el usuario.

Para obtener más información sobre ubicaciones de emergencia en relación con planes de llamada, consulte los siguientes artículos:

-   [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [Términos y condiciones de las llamadas de emergencias](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir la granularidad de la información de ubicación de emergencia recopilarse para ubicaciones de usuario u oficinas en el ámbito de la implementación de planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la dirección detallada de emergencia y emergencia ubicaciones para cada ubicación de usuario o de la oficina en el ámbito de la implementación de planes de llamada.</li></ul>|

> [!TIP]
> Puede utilizar la siguiente plantilla para documentar los detalles de los números de teléfono y detalles de ubicación de emergencia.
>|Usuario |Dirección y ubicación de emergencia |Número de teléfono |
>|-----|-------------------------------|-------------|
>|Emily Braun |1034/32 London Bridge Street, Londres, SE1, Reino Unido |+ 44 23 4567 8901 |
>|Lidia Holloway |1065/32 London Bridge Street, London, SE1, Reino Unido |+ 44 23 4567 89112 |
>|Louis Lahr |1023/32 London Bridge Street, Londres, SE1, Reino Unido |+ 44 23 4567 8921 |
>|Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | Por añadir |
>|Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | Por añadir |
>|Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | Por añadir |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Correo de voz

Correo de voz de sistema de teléfono, impulsado por servicios de correo de voz de Azure, admite depósitos de correo de voz a los buzones de Exchange sólo y no es compatible con sistemas de correo electrónico de terceros.

De forma predeterminada, el correo de voz de sistema telefónico funciona con Exchange Online; Sin embargo tiene un mínimo compatible Exchange local versión e implementación modelo para permitir la entrega de mensajes de correo de voz a los buzones de usuario en la implementación de Exchange local.

El correo de voz de Sistema telefónico cuenta con transcripción del correo de voz y esta opción está activada de forma predeterminada para todos los usuarios de la organización. Necesidades de su empresa pueden requerir que deshabilite la transcripción de correo de voz para usuarios específicos o a todos los usuarios en toda la organización. Si su organización ha decidido mantener la transcripción de voz habilitado, debe considerar también si deben habilitarse masking de palabras soeces de transcripción de correo de voz. Para obtener más detalles, consulte [configuración de directivas de buzón de voz en su organización](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) .

>[!NOTE]
> Se ha implementado un mecanismo de reserva para que el correo de voz de Sistema telefónico pueda reenviar mensajes mediante SMTP, lo que implica que los usuarios con un buzón de un sistema de correo electrónico de terceros podrán recibir sus mensajes de correo de voz. Este mecanismo no incluye el tiempo de actividad de servicio garantizado u otras funciones de correo de voz, como cambiar el saludo de correo de voz.

Para obtener más información acerca de correo de voz en una implementación de sistema de teléfono, vea [compatibilidad con Exchange Server de correo de voz de PBX de Azure](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si permitirá el correo de voz de sistema de teléfono en la implementación de planes de llamada.</li><li>Si utiliza Exchange local y la implementación existente no cumple los requisitos para admitir el correo de voz del sistema de teléfono, elija entre las opciones disponibles (actualización y configuración de compatibilidad de correo de voz del sistema de teléfono, migrar a Exchange Online o aproveche la mecanismo de reserva que se ha descrito anteriormente).</li><li>Decidir si podrá habilitar o deshabilitar la transcripción de correo de voz y masking de palabras soeces de transcripción de correo de voz en toda la organización o para usuarios específicos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>En su caso, documentar los puntos de decisión de Exchange para admitir el correo de voz del sistema telefónico.</li><li>Si podrá habilitar o deshabilitar correo de voz, transcripción de correo de voz y masking de palabras soeces transcripción de correo de voz para determinados usuarios, documentan esa lista de usuarios.</li></ul>|

> [!TIP]
> Detalles de correo de voz del sistema de teléfono para el sistema de teléfono con una llamada a los planes de implementación se pueden documentar de la forma siguiente.
>|Usuario |Buzón de Exchange |¿Habilitar correo de voz? |Transcripción de correo de voz |Enmascaramiento de palabras soeces de transcripción de correo de voz |
>|------------------|------------------|-------------------|----------|----------|
>|Emily Braun      |En línea      |Sí |Habilitado |Habilitado |
>|Lidia Holloway   |En línea      |Sí |Habilitado |Deshabilitado |
>|Louis Lahr       |Local |Sí |Habilitado |Habilitado |
>|Marcel Beauchamp |Local |Sí |Deshabilitado |N/D |
>|Rachelle Cormier |En línea      |Sí |Deshabilitado |N/D |
>|Isabell Potvin   |Local |Sí |Deshabilitado |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada. En algunos casos, hay requisitos de negocio legítimo para enmascarar el identificador para proteger la identidad de los llamadores utilizando el número de la línea principal de office: suele ser un número de servicio atendido por la configuración del Operador automático, como identificador de llamadas o bloquear el identificador de llamadas presentación en conjunto.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si es necesaria para la implementación de planes de llamada manipulación de identificador.</li><li>En su caso, decidir los tipos de manipulación de identificador (máscara de número de servicio o anónimo) a implementar.</li><li>En su caso, decidir qué usuarios requieren manipulación de identificador y el tipo de manipulación de identificador que se asignará a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente los usuarios para asignarse manipulación de identificador y el tipo de manipulación de identificador de llamadas para asignar.</li></ul>|

> [!TIP]
> El siguiente es un ejemplo de identificador de masking documentación de detalles.
>|Usuario  |Habilitar el enmascaramiento del identificador de llamada en llamadas salientes  |Tipo de enmascaramiento del identificador de llamada  |Permitir la invalidación por parte del usuario  | Habilitar el enmascaramiento del identificador de llamada en llamadas entrantes  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|No|N/D|Sí|No|
>|Lidia Holloway|Sí|Número de servicio (OrgAA, +44 20 7946 0000)|No|Sí|
>|Louis Lahr|No|N/D|Sí|No|
>|Marcel Beauchamp|Sí|Número de servicio (OrgAA, TBA)|No|Sí|
>|Rachelle Cormier|Sí|Anonimizar|Sí|No|
>|Isabell Potvin|Sí|Número de servicio (OrgAA, TBA)|No|Sí|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Licencias para funciones de voz de la nube

Conferencias de audio y sistema de teléfono son características de Office 365. Puede obtener una licencia por separado como servicios complementarios para los clientes que tengan Office 365 E3 o E1 planes de suscripción; ya están incluidos como parte del plan de suscripción de Office 365 E5.

Planes de llamada es un complemento a la característica de sistema de teléfono de Office 365, por lo que debe tener un sistema telefónico con licencia habilitado para utilizar planes de llamada.

Para admitir para conferencias de Audio adicionales y planes de llamada utilizan casos (Conferencia internacional dial-out, externa llamadas después de que se agoten asignaciones minutos Plan de llamadas etc.), puede configurar comunicaciones créditos para su organización.

## <a name="licensing-for-calling-plans"></a>Licencias de Planes de llamada

Si su organización va a utilizar Microsoft como proveedor de servicios de telecomunicaciones, necesitará obtener el Plan de llamadas complementos adecuados para los requisitos de negocio de los usuarios. Por lo general, no todo el mundo en una organización necesita hacer llamadas internacionales, por lo que puede suministrar la mayoría de los usuarios con licencias de Plan de llamadas nacionales.

Hay dos tipos de licencias de Plan de llamadas:

-   Plan de llamada nacional

-   Plan de llamada nacional e internacional

> [!NOTE]
> La definición de "nacional" para un usuario específico está determinada por la ubicación de uso de Office 365 asignada al usuario.

Cada tipo de Plan de llamada proporciona una asignación de minutos de llamada que los usuarios pueden usar al mes, ya sea para realizar llamadas nacionales o internacionales. Los costes de Plan de llamadas nacionales que menor comparado con el internacional y Plan de llamadas nacionales.

La flexibilidad de la suscripción y la asignación del tipo de Plan de llamadas más adecuado para los requerimientos del negocio de los usuarios individuales ayuda a su organización a controlar los costos de su implementación de planes de llamada.

Para cada inquilino de Office 365, la cantidad combinada de minutos de llamada se agrupa por país o región, y por tipo de Plan de llamada. Cuando un inquilino llega al límite de minutos de llamada mensual, el servicio de Planes de llamada se suspende hasta finalizar el mes (a excepción de las llamadas de emergencia). El servicio de llamada a planes se reanudará automáticamente el primer día del siguiente mes calendario.

Puede configurar comunicaciones créditos para sus organizaciones para que a los usuarios puedan realizar llamadas salientes después de la asignación de una llamada a minutos se agota sin tener que esperar hasta el mes próximo ciclo de facturación. Además, créditos de comunicaciones proporcionan los usuarios asignan el Plan de llamadas nacionales la capacidad de realizar llamadas internacionales, que, a continuación, se cargan mediante un modelo de "pago por minuto".

Para obtener más información sobre el sistema telefónico y llamar a los planes, consulte los siguientes artículos:

-   [Sistema de teléfono](https://products.office.com/skype-for-business/phone-system)

-   [Planes de llamada](https://products.office.com/skype-for-business/calling-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización no tiene la licencia requerida del sistema telefónico, decidir si adquirirá la licencia del sistema de teléfono por reforzar sus suscripciones a Office 365 existentes o al adquirir el servicio adicional de sistema de teléfono.</li><li>Decidir qué usuarios requieren una licencia de Plan de llamadas nacionales y que requieren una licencia nacional y Plan de llamadas internacionales.</li><li>Decidir si necesitará créditos de comunicaciones para la implementación de planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la división, departamento, oficina o grupos de usuarios, puede asignar una licencia de sistema de teléfono con Plan de llamadas nacionales o nacionales y Plan de llamadas internacionales.</li></ul>|

> [!TIP]
> En el ejemplo siguiente se puede utilizar para documentar la asignación de licencias para el sistema de teléfono con planes de llamar a usuarios.
>|Usuario |Oficina |Licencia de Office 365 |Plan de llamadas |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional e internacional |
>|Lidia Holloway |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional |
>|Louis Lahr |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema de teléfono |Plan de llamada nacional |
>|Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Plan de llamada nacional e internacional |
>|Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema de teléfono |Plan de llamada nacional |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Créditos de comunicaciones

Con créditos de comunicaciones, los usuarios puedan marcar desde una reunión de la conferencia de Audio para agregar otra persona en cualquier lugar del mundo (fuera del país originario del organizador de la reunión). Puede configurar créditos de comunicaciones de la organización para permitir a los usuarios realizar llamadas de salida después de que hayan agotado su asignación de llamar a minutos, sin tener que esperar hasta que el ciclo de facturación del próximo mes. Además, créditos de comunicaciones dar a los usuarios asignados con el Plan de llamadas nacionales la capacidad de realizar llamadas internacionales, que, a continuación, se cargan mediante un modelo de "pago por minuto".

La primera consideración que hay que tener en cuenta a la hora de implementar Créditos de comunicaciones es decidir la cantidad inicial de fondos que se deben adquirir. Si la organización decide usar recarga automática, podrá determinar la cantidad óptima midiendo el uso real. Supervisar el uso de créditos de comunicaciones con el tiempo y ajustar la cantidad de recarga según sea necesario.

Para la implementación de planes de llamada, puede controlar el uso de créditos de comunicaciones en una base por usuario, que le ayudará a asegurarse de que ha asignado estos créditos en alineación con las necesidades de su negocio.

Para obtener más información sobre créditos de comunicaciones, revisar [¿qué comunicaciones créditos?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si necesita créditos de comunicaciones para la implementación de conferencias de Audio o llamar a los planes.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documento permitirá comunicaciones créditos para los grupos de división, departamento, oficina o usuario.</li><li>Documentar el plan de comunicaciones créditos para su implementación de conferencias de Audio o llamar a los planes.</li></ul>|

> [!TIP]
> Utilice el siguiente ejemplo para documentar la lista de asignación de créditos de comunicaciones para usuarios de planes de llamada.
>|Usuario |Oficina |Plan de llamadas |Créditos de comunicaciones |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |Plan de llamada nacional e internacional |Habilitado |
>|Lidia Holloway |32 London Bridge Street |Plan de llamada nacional |Deshabilitado |
>|Louis Lahr |32 London Bridge Street |Plan de llamada nacional |Habilitado |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Plan de llamada nacional |Deshabilitado |
>|Rachelle Cormier |39 quai du Président Roosevelt |Plan de llamada nacional e internacional |Habilitado |
>|Isabell Potvin |39 quai du Président Roosevelt |Plan de llamada nacional |Deshabilitado |

<br>
> [!TIP]
> Los créditos de comunicaciones planificación números puede documentarse como en el ejemplo siguiente.
>|         |         |
>|---------|---------|
>|Cantidad inicial|1000 $|
>|Cantidad de umbral|400 $|
>|Cantidad de recarga automática|Por añadir|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Administrar números de teléfono de voz de nube

Si implementa el sistema de teléfono poniendo su propio proveedor de servicios de telecomunicaciones, gestión de números de teléfono permanecerá como-es.

Para implementaciones de conferencias de Audio y llamar a los planes, puede adquirir nuevos números de teléfono o transferir números de teléfono existentes (puerto).

Para permitir a los usuarios la manera en la que están acostumbrados a los números de teléfono de acceso telefónico, como omitir códigos de área para las llamadas locales, omitiendo el código de país para llamadas nacionales o incluso usa short dígitos al realizar la conferencia dial-out o llamar a otros usuarios de la organización: Puede configurar un plan de marcado personalizado y asignarlo a los usuarios.

## <a name="acquire-new-telephone-numbers"></a>Adquirir nuevos números de teléfono

Son los dos tipos de números de teléfono de soluciones de voz de nube de Microsoft:

-   Números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización.

-   Números de servicio, disponibles como teléfono y números de servicio gratuito, que tienen mayor capacidad de llamadas simultáneas que números de suscriptor y se pueden asignar a servicios como las conferencias de Audio, operadores automáticos o llamar a colas.

Para obtener más información acerca de los tipos de números de teléfono, ver [distintos tipos de números de teléfono utilizados para llamar a los planes](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Recuento total de números de teléfono que puede obtener dependen del tipo de número de teléfono y el número de licencias que ha comprado y asignado a los usuarios.

Para obtener más información sobre el número total de números de teléfono que puede obtener, consulte [cuántos números de teléfono puede conseguir?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de usuario o las oficinas donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>Decidir el tipo de números de teléfono de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones de usuario o las oficinas donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>Documente el tipo de números de teléfono de Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir los números de teléfono existentes

Si su organización desea transferir (o puerto) existente de números de teléfono a Microsoft, puede hacerlo enviando una solicitud de pedido de puerto a Microsoft.

Puede transferir todos los existentes números de teléfono a la vez (puerto completo), y, en algunos mercados, puede transferir un subconjunto de los números de teléfono existente (puerto parcial). Un puerto parcial puede ser útil en casos donde desea mover gradualmente los usuarios al sistema de teléfono con planes de llamada.

Un pedido único puerto puede transferir sólo los números de teléfono a un tipo de número de teléfono único. Si necesita transferir algunos de los números de teléfono como números de suscriptor y otros como números de servicio, se recomienda que complete primero la transferencia a Microsoft y, a continuación, realizar la conversión en cuanto los números están en el control de Microsoft.

Como una alternativa (si se admite un puerto parcial), puede enviar varias solicitudes de puerto, solicitud de un puerto a la vez. Sin embargo, este enfoque alternativo, prolongará su contrato con el proveedor de servicios de telecomunicaciones existentes.

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

Un Plan de marcado en la función de sistema de teléfono de Office 365 es un conjunto de reglas de normalización que traducen marcaba números de teléfono en un formato alternativo (normalmente en formato E.164) para la autorización de llamada y el enrutamiento de llamadas. El servicio de conferencia de Audio aprovecha las mismas capacidades de sistema de teléfono utilizadas para convertir los números de teléfono marcado en escenarios de acceso telefónico de salida de conferencia (por ejemplo, invitar a participantes a través de PSTN y marcado, la característica "Llamarme").

En la función de sistema de teléfono de Office 365, hay dos tipos de planes de marcado:

-   **Plan de marcado de servicio:** De forma predeterminada el plan de marcado que se aplica a los usuarios basándose en su ubicación de uso de Office 365 y no puede modificarse.

-   **Plan de marcado de inquilinos:** Se trata de un plan de marcado personalizable dentro de un arrendatario, que se divide en dos tipos:

    -   **Plan de marcado de inquilinos global:** El plan de marcado que se aplica a todos los usuarios de los inquilinos.

    -   **Plan de marcado de usuario inquilino:** El plan de marcado que se aplica únicamente a usuarios específicos.

El plan de marcado eficaz asignado a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 del usuario) y plan (que puede ser un plan de marcado de inquilinos global o el plan de marcado de usuario inquilino) de marcado de inquilinos.

![Tabla muestra tres combinaciones de servicio y los inquilinos planes de marcación.] (media/audio_conferencing_image8.png "Tabla muestra tres combinaciones de servicio y los inquilinos planes de marcación.")

> [!IMPORTANT]
> Puede haber un máximo de 25 reglas de normalización en cada plan de marcado de inquilinos; por lo tanto, es importante evitar la duplicación de las reglas de normalización que ya están disponibles como parte del servicio de plan de marcado.

Para obtener más información acerca de los planes de marcado, consulte [¿Cuáles son los planes de marcación?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización requiere que los planes de marcado personalizado (los requerimientos del negocio, los requisitos de adopción etc.).</li><li>En su caso, decidir el ámbito del plan de marcado de inquilinos (global del arrendatario o usuario inquilino) para soportar sus requerimientos de planes de marcado personalizada.</li><li>En su caso, decidir los planes de marcado de inquilinos que va a crear para admitir ubicaciones de usuario u oficinas en el ámbito de la implementación de voz de la nube.</li><li>En su caso, decidir qué usuarios requieren un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar los planes de marcado personalizada y las reglas de normalización asociados a configurarse como parte de la implementación de voz de nube.</li><li>Documente los usuarios asignar un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario.</li></ul>|

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
>|**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Número interno (x7000 â €"x 7999) para 39 quai du Président Roosevelt office, Issy-les-Moulineaux, Francia_|^(7\d{3})$<br>+3319999$1<br>True|
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

## <a name="document-service-decisions"></a>Decisiones del servicio de documento 

Utilice la información de las secciones anteriores de este artículo para documentar sus decisiones de servicio. En general, esta documentación contiene las secciones principales siguientes:

-   Lista de habilitación del sitio de Sistema telefónico con Planes de llamada

-   Asignación de licencias a usuarios de Sistema telefónico con Planes de llamada

-   Números de planificación de Créditos de comunicaciones

-   Adquisición de números de teléfono, número de teléfono y detalles de las ubicaciones de emergencia

-   Detalles de la configuración del correo de voz

-   Asignaciones de configuraciones de puentes de conferencia

-   Detalles de la configuración del enmascaramiento del identificador de llamada

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

<!--ENDOFSECTION-->