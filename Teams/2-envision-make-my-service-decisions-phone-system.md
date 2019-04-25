---
title: 'Tomar decisiones relacionadas con el servicio de Sistema telefónico con planes de llamada: Microsoft Teams'
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Elija desde planes de llamada y licencias, configurar las ubicaciones de emergencia y características, como el identificador de correo de voz y el autor de la llamada, adquirir o transferir los números de teléfono.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98a66e0335daf0e74c96d0a2dad18f89bd1f4c5f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242420"
---
# <a name="make-my-service-decisions"></a>Tomar decisiones de mi servicio

Para planear la implementación técnica del sistema telefónico con planes de llamada, debe realizar una serie de decisiones de servicio con anterioridad para una mejor preparación de su organización para implementar una solución que cumple los requisitos de negocio definidos.

## <a name="calling-in-teams"></a>Al llamar a los equipos

Con Microsoft Teams, los usuarios pueden realizar y recibir llamadas de teléfono a o desde la red telefónica conmutada (RTC). Los usuarios pueden utilizar sus propios números de teléfono dedicado para realizar y recibir llamadas telefónicas internacionales y nacionales de las aplicaciones de cliente de los equipos, con características avanzadas que incluyen el correo de voz.

> [!NOTE]
> La guía básica de los equipos más reciente para la identificación del sistema de teléfono de los equipos con las características de planeación de la llamada en el ámbito para la implementación se puede encontrar en <https://aka.ms/O365Roadmap>.

## <a name="phone-system-in-teams"></a>Sistema telefónico en los equipos

Para que los usuarios de los equipos que puedan realizar y recibir llamadas de RTC, deben estar habilitados para el sistema telefónico, una característica de Office 365.

Para habilitar la conectividad a la RTC, la organización puede usar Microsoft como su proveedor de servicios de telecomunicaciones. Finalmente, también tendrá la opción "Traer su propia" proveedor de servicios de telecomunicaciones para habilitar la conectividad con RTC para el sistema telefónico.

> [!IMPORTANT]
> La capacidad de usar su propio proveedor de servicios de telecomunicaciones para el sistema telefónico con la implementación de los equipos también está disponible con el enrutamiento directo teléfono del sistema. Para obtener más información sobre el enrutamiento directo, revise las [instrucciones de enrutamiento directo](2-envision-make-my-service-decisions-direct-routing.md).

## <a name="phone-system-with-calling-plans"></a>Sistema telefónico con planes de llamada

Para usar Microsoft como proveedor de servicios de sus telecomunicaciones, debe obtener licencias de llamar a planear y asignarlos a los usuarios del sistema telefónico.

Hay dos tipos principales de planes de llamada:

-   Plan de llamadas nacional

-   Plan de llamadas nacional e internacional

Cada tipo de plan de llamadas asigna un número determinado de minutos de llamada al mes a cada usuario que se ha asignado la licencia. Cuando se agota la asignación de minutos de llamada, el usuario no podrá realizar llamadas salientes, excepto para las llamadas de emergencia, hasta el próximo mes de facturación de ciclo. Si desea que los usuarios puedan continuar y realizar llamadas salientes incluso después de que ha agotado su asignación de minutos de llamada o para permitir que los usuarios que tienen un plan de llamada nacional realizar llamadas internacionales, puede configurar Communications créditos para su organización.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilidad de los planes de llamada

Antes de planear la implementación de una llamada a los planes en los equipos, compruebe que el servicio planes de llamada está disponible en su zona mediante la revisión de [disponibilidad de país y región para las conferencias de Audio y planes de llamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Debido a restricciones legales, para llamar a los planes para que estén disponibles para las organizaciones multinacionales, se debe basar el contrato de suscripciones a Office 365 en un país o región donde está disponible el servicio de planes de llamada o donde puede ser el servicio de planes de llamada adquirir.

> [!NOTE]
> Si al llamar a planes no están disponibles en su zona, puede usar [Enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md) para permitir que los usuarios con equipos con capacidades de RTC.

Después de confirmar que su organización puede obtener el servicio al llamar a planes, compilar la lista de ubicaciones de usuario o las oficinas donde aquí implementar el servicio de planes de llamada, en función de la lista de disponibles países y regiones.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir qué ubicaciones de usuario o las oficinas se implementa los planes de llamada de servicio en.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Las ubicaciones de usuario u oficinas a habilitarse para el servicio al llamar a planes de documentos.</li></ul>|

> [!TIP]
> A continuación es un ejemplo de un sistema telefónico con planes de llamar a la lista de habilitación de sitios.
> 
> | **Office**                     | **Ubicación**   | **Servicio del sistema de teléfono** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Australia      | Servicio de RTC heredado |
> | 100 Cyberport Road             | RAE de Hong Kong  | Enrutamiento directo del Sistema telefónico |
> | One Marina Boulevard           | Singapur      | Enrutamiento directo del Sistema telefónico |
> | 32 London Bridge Street        | Reino Unido | Sistema telefónico con planes de llamada |
> | 39 quai du Président Roosevelt | Francia         | Sistema telefónico con planes de llamada |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con una llamada a los planes en Office 365, todos los usuarios de su organización deben tener un único entrante directa marcando el número de teléfono (DID) y una dirección de emergencia validada correspondiente. Revise los [números de teléfono de voz en la nube de administrar](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers) para planear la adquisición de número de teléfono para la implementación de planes de llamada.

Cuando está configurando los números de teléfono para llamar a los planes, debe asignar una dirección de emergencia a cada número de teléfono antes de asignar al número a un usuario. Esto es necesario para admitir llamadas de emergencia. La dirección de emergencia debe validarse para asegurarse de que se encuentra en el formato correcto para ser usados por los servicios de respuesta de emergencia.

> [!IMPORTANT]
> Llamar a los servicios de emergencia funciona de forma diferente en el servicio al llamar a los planes que en servicios de telefonía tradicional. Es importante que entienda estas diferencias y comunicarlas a todos los usuarios. Para obtener más información, consulte [emergencia llamar a términos y condiciones](emergency-calling-terms-and-conditions.md) .

Además de proporcionar una dirección de emergencia validada, puede definir las ubicaciones de emergencia y asociarlos a la dirección de emergencia validada para proporcionar una ubicación más exacta dentro de una dirección. Una ubicación de emergencia es, normalmente, el número de edificio, la planta, la sección del edificio o el número de oficina donde se encuentra el usuario.

Para obtener más información acerca de las ubicaciones de emergencias en relación con los planes de llamada, revise los siguientes artículos:

-   [¿Qué son las direcciones, las ubicaciones de emergencia y el enrutamiento de llamadas?](what-are-emergency-locations-addresses-and-call-routing.md)

-   [Términos y condiciones de llamadas de emergencia](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir la granularidad de la información de ubicación de emergencia recopilarse para ubicaciones de usuario o las oficinas en el ámbito de la implementación de planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar la dirección detallada de emergencia y las ubicaciones de emergencia para cada ubicación de usuario o de office en el ámbito de la implementación de planes de llamada.</li></ul>|

> [!TIP]
> Puede usar la siguiente plantilla para documentar los detalles de los números de teléfono y detalles de las ubicaciones de emergencia.
> 
> |Usuario |Dirección y la ubicación de emergencia |Número de teléfono |
> |-----|-------------------------------|-------------|
> |Emily Braun |Calle de puente de Londres 1034/32, London, SE1, Reino Unido |+ 44 23 4567 8901 |
> |Lidia Holloway |Calle de puente de Londres 1065/32, London, SE1, Reino Unido |+ 44 23 4567 89112 |
> |Louis Lahr |Calle de puente de Londres 1023/32, London, SE1, Reino Unido |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, Issy 92130-LECS-Moulineaux, Francia | Por añadir |
> |Rachelle Cormier |07N15D/39 quai du Président Roosevelt, Issy 92130-LECS-Moulineaux, Francia | Por añadir |
> |Isabell Potvin |07F05E/39 quai du Président Roosevelt, Issy 92130-LECS-Moulineaux, Francia | Por añadir |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Correo de voz

Correo de voz en la nube, con tecnología de servicios de correo de voz de Azure, es compatible con depósitos de correo de voz a los buzones de Exchange y no es compatible con sistemas de correo electrónico de otro fabricante.

De forma predeterminada, el correo de voz en la nube funciona con Exchange Online; Sin embargo, tiene un mínimo Exchange local versión e implementación modelo compatible para permitir la entrega de mensajes de correo de voz a los buzones de usuario en la implementación de Exchange local.

Correo de voz en la nube incluye transcripción de correo de voz, que está habilitado para todos los usuarios de la organización de forma predeterminada. Las necesidades de negocio pueden requerir que deshabilite la transcripción de correo de voz para usuarios específicos o todos los usuarios en toda la organización. Si su organización ha decidido mantener habilitado de transcripción de correo de voz, debe también tener en cuenta si deben habilitarse enmascaramiento de contenido ofensivo de transcripción de correo de voz. Para obtener más información, vea [configuración de directivas de correo de voz en su organización](set-up-phone-system-voicemail.md) .

>[!NOTE]
> Se ha implementado un mecanismo de reserva para que el correo de voz en la nube puede volver a enviar los mensajes mediante el uso de SMTP, lo que significa que los usuarios que tienen un buzón de correo en un sistema de correo electrónico de otro fabricante recibirán sus mensajes de correo de voz. Este mecanismo no incluye el tiempo de actividad de servicio garantizado u otras funciones de correo de voz, como cambiar el saludo del correo de voz.

Para obtener más información acerca de correo de voz en una implementación del sistema de teléfono, vea [Sistema de teléfono con planes de llamada](calling-plan-landing-page.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si va habilitar correo de voz de la nube en su implementación de planes de llamada.</li><li>Si el uso de Exchange local y la implementación existente no cumple los requisitos para admitir el correo de voz en la nube, elija entre las opciones disponibles (actualización y el programa de instalación para la compatibilidad de correo de voz en la nube, migrar a Exchange Online, o sacar provecho de la reserva mecanismo que se ha descrito anteriormente).</li><li>Decidir si se debe habilitar o deshabilitar transcripción de correo de voz y enmascaramiento de contenido ofensivo transcripción de correo de voz en toda la organización o para usuarios específicos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Si procede, documente los puntos de decisión de Exchange para admitir el correo de voz en la nube.</li><li>Si se debe habilitar o deshabilitar correo de voz, correo de voz transcripción y enmascaramiento de contenido ofensivo transcripción de correo de voz para determinados usuarios, documentos que la lista de los usuarios.</li></ul>|

> [!TIP]
> En la nube detalles de correo de voz para el sistema de teléfono con una llamada a los planes de implementación se puede documentar como el siguiente.
> 
> |Usuario |Buzón de Exchange |¿Habilitar correo de voz? |Transcripción de correo de voz |Enmascaramiento de contenido ofensivo de transcripción de correo de voz |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |Sí |Habilitado |Habilitado |
> |Lidia Holloway   |Online      |Sí |Habilitado |Deshabilitado |
> |Louis Lahr       |Local |Sí |Habilitado |Habilitado |
> |Marcel Beauchamp |Local |Sí |Deshabilitado |N/D |
> |Rachelle Cormier |Online      |Sí |Deshabilitado |N/D |
> |Isabell Potvin   |Local |Sí |Deshabilitado |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes utilizan el número de teléfono asignado como llamada identidad (identificador de autor de la llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada. En algunos casos, existen requisitos de negocio legítimo para enmascarar el identificador de autor de la llamada para proteger la identidad de los autores de llamadas mediante el número de línea principal de office: suele ser un número de servicio atendido por la configuración del operador automático — como identificador de autor de la llamada, o bien para bloquear el identificador de autor de la llamada presentación por completo.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si es necesario para la implementación de una llamada a los planes de manipulación de identificador de autor de la llamada.</li><li>Si procede, decidir los tipos de manipulación de identificador de autor de la llamada (enmascarar con el número de servicio o definir como anónimo) que se va a implementar.</li><li>Si procede, decidir qué usuarios requieren manipulación de identificador de autor de la llamada y el tipo de manipulación de identificador de autor de la llamada que se asignará a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Los usuarios para que se le ha asignado manipulación de identificador de autor de la llamada y el tipo de manipulación de identificador de autor de la llamada para asignar del documento.</li></ul>|

> [!TIP]
> El siguiente es un ejemplo de documentación de detalles del enmascaramiento de identificador de autor de la llamada.
> 
> |Usuario  |Habilitar el enmascaramiento de identificador de autor de la llamada saliente  |Tipo de enmascaramiento de identificador de autor de la llamada  |Permitir invalidación de usuario  | Habilitar el enmascaramiento de identificador de autor de la llamada entrante  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|No|N/D|Sí|No|
> |Lidia Holloway|Sí|Número de servicio (OrgAA, + 44 20 7946 0000)|No|Sí|
> |Louis Lahr|No|N/D|Sí|No|
> |Marcel Beauchamp|Sí|Número de servicio (OrgAA, TBA)|No|Sí|
> |Rachelle Cormier|Sí|Definir como anónimo|Sí|No|
> |Isabell Potvin|Sí|Número de servicio (OrgAA, TBA)|No|Sí|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Concesión de licencias para las funciones de voz en la nube

Conferencia de audio y el sistema de teléfono son las características de Office 365. Puede tener licencia por separado como servicios complementarios para los clientes que tengan Office 365 E3 o E1 planes de suscripción; ya están incluidos como parte del plan de suscripción de Office 365 E5.

Planes de llamada es un complemento a la característica de sistema telefónico en Office 365, por lo que debe tener un sistema telefónico con licencia habilitado para usar planes de llamada.

Para admitir para conferencias de Audio adicionales y llamar a los planes de usan (Conferencia internacional de salida, externo de llamada después de llamar a planear asignaciones minutos agotar y así sucesivamente) de los casos, puede configurar Communications créditos para su organización.

## <a name="licensing-for-calling-plans"></a>Concesión de licencias para planes de llamada

Si su organización va a utilizar Microsoft como proveedor de servicios de telecomunicaciones, necesita obtener una llamada a planear los complementos adecuados a los requisitos de negocio de los usuarios. Por lo general, no todo el mundo en una organización necesita realizar llamadas internacionales, por lo que puede aprovisionar la mayoría de los usuarios con licencias de llamar a planear nacionales.

Hay dos tipos de licencias de planeación de la llamada:

-   Plan de llamada nacional

-   Plan de llamada nacional e internacional

> [!NOTE]
> ¿Qué se considera "interno" para un usuario concreto está determinada por la ubicación del usuario asignada Office 365 uso.

Cada tipo de planeación de la llamada proporciona una asignación de una llamada al minutos que los usuarios pueden usar al mes, ya sea para hacer llamadas nacionales o las llamadas internacionales. Los costos de llamar a planear nacionales que menor en comparación con el Plan de llamar a nacional e internacional.

La flexibilidad de la suscripción y asignar al tipo de planeación de la llamada más adecuado para los requisitos de negocio de los usuarios individuales ayuda a su organización a controlar los costos de su implementación de planes de llamada.

Para cada inquilino de Office 365, el número total de minutos que realiza la llamada se agrupa por país o región y por tipo de planeación de la llamada. Cuando se alcanza el capital minutos llamada mensual para el inquilino, llamar a los planes de servicio (excepto para llamadas de emergencia) se suspenderá durante el resto del mes. El servicio de planes de llamada se reanudará automáticamente en el primer día del mes de calendario siguiente.

Puede configurar Communications créditos para las organizaciones habilitar a los usuarios realizar llamadas salientes a después de la asignación de una llamada al minutos se agota sin tener que esperar hasta el mes próximo ciclo de facturación. Además, créditos Communications proporcionan asignar a los usuarios el Plan de llamar a nacionales la capacidad de realizar llamadas internacionales, que, a continuación, se cargan mediante un modelo de "pago por minuto".

Para obtener más información sobre el sistema telefónico y planes de llamada, revise los siguientes artículos:

-   [Sistema telefónico](https://products.office.com/en-us/skype-for-business/phone-system)

-   [Planes de llamadas](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización no tiene la licencia del sistema de teléfono necesaria, decidir si la licencia del sistema de teléfono adquirirá pasando seguridad sus suscripciones a Office 365 existentes o al adquirir el servicio de complemento de sistema telefónico.</li><li>Decidir qué usuarios requieren una licencia de llamar a planear nacionales y que requieren una licencia nacionales y llamar a planear internacional.</li><li>Decidir si necesitará créditos de comunicaciones para la implementación de planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la división, departamento, office o grupos de usuarios, puede asignar una licencia de sistema telefónico con el Plan para llamar a nacionales o doméstico y llamar a planear internacional.</li></ul>|

> [!TIP]
> Puede usar el siguiente ejemplo en la asignación de licencias para el sistema telefónico con planes de llamar a los usuarios del documento.
> 
> |Usuario |Oficina |Licencia de Office 365 |Plan de llamada |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional e internacional |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional |
> |Louis Lahr |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema de teléfono |Plan de llamada nacional |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Plan de llamada nacional e internacional |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema de teléfono |Plan de llamada nacional |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Créditos de comunicaciones

Con créditos Communications, los usuarios pueden marcar un número de una reunión de conferencia de Audio para agregar otra persona desde cualquier lugar en el mundo (fuera del país de origen del organizador de la reunión). Puede configurar Communications créditos para su organización para permitir a los usuarios realizar llamadas salientes a después de que han agotado su asignación de la llamada a minutos, sin tener que esperar hasta que el ciclo de facturación del próximo mes. Además, Communications créditos conceder a los usuarios asignados con el Plan de llamar a nacionales la capacidad de realizar llamadas internacionales, que, a continuación, se cargan mediante un modelo de "pago por minuto".

La primera consideración que hay que tener en cuenta a la hora de implementar Créditos de comunicaciones es decidir la cantidad inicial de fondos que se deben adquirir. Si la organización decide usar automático recarga, determinará la cantidad óptima midiendo el uso real. Supervisar el uso de créditos de comunicaciones a través del tiempo y ajustar la cantidad de recarga según sea necesario.

Para la implementación de planes de llamada, puede controlar el uso de créditos Communications en una base por usuario, que le ayudará a asegurarse de que haya asignado estos créditos en alineación con las necesidades de negocio.

Para obtener más información acerca de las comunicaciones créditos, revise [¿Cuáles son las comunicaciones créditos?](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si necesita Communications créditos para su implementación de conferencias de Audio o planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Los grupos de división, departamento, office o usuario para que podrá habilitar Communications créditos de documentos.</li><li>Documentar el plan de comunicaciones créditos para su implementación de conferencias de Audio o planes de llamada.</li></ul>|

> [!TIP]
> Use el siguiente ejemplo en la lista de asignación de créditos de comunicaciones para planes de llamar a los usuarios del documento.
> 
> |Usuario |Oficina |Plan de llamada |Créditos de comunicaciones |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Plan de llamada nacional e internacional |Habilitado |
> |Lidia Holloway |32 London Bridge Street |Plan de llamada nacional |Deshabilitado |
> |Louis Lahr |32 London Bridge Street |Plan de llamada nacional |Habilitado |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Plan de llamada nacional |Deshabilitado |
> |Rachelle Cormier |39 quai du Président Roosevelt |Plan de llamada nacional e internacional |Habilitado |
> |Isabell Potvin |39 quai du Président Roosevelt |Plan de llamada nacional |Deshabilitado |

<br>

> [!TIP]
> Los créditos Communications planeación números se puede documentar como en el ejemplo siguiente.
>
> |         |         |
> |---------|---------|
> |Cantidad inicial|1000 $|
> |Cantidad de umbral|400 $|
> |Cantidad de recarga automática|Por añadir|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Administrar números de teléfono de voz en la nube

Si implementa el sistema telefónico al poner su propio proveedor de servicios de telecomunicaciones, administración de números de teléfono permanecerá como-es.

Para implementaciones de conferencias de Audio y planes de llamada, puede elegir adquirir nuevos números de teléfono o transferir los números de teléfono existentes (puerto).

Permitir a los usuarios la forma en que están acostumbrados a los números de teléfono de marcado, como se omite los códigos de área para las llamadas locales, se omite el código de país para realizar llamadas nacionales o incluso usa short dígitos marcado al realizar la salida de la conferencia o llamar a otros usuarios de la organización: Puede configurar un plan de marcado personalizado y asignar a los usuarios.

## <a name="acquire-new-telephone-numbers"></a>Adquirir nuevos números de teléfono

Los dos tipos de números de teléfono en las soluciones de voz de la nube de Microsoft son:

-   Números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización.

-   Números de servicio, disponibles como números de un servicio gratuito, que tengan la mayor capacidad de llamadas concurrentes que números de suscriptor y que se pueden asignar a servicios, como conferencias de Audio, operadores automáticos o colas de llamadas y de pago.

Para obtener más información acerca de los tipos de números de teléfono, vea [distintos tipos de números de teléfono utilizados para llamar a los planes](different-kinds-of-phone-numbers-used-for-calling-plans.md).

La cantidad total de números de teléfono que puede obtener depende del tipo de número de teléfono y el número de licencias que ha comprado y asignado a los usuarios.

Para obtener más información acerca de la cantidad total de números de teléfono que puede obtener, vea [cuántos números de teléfono puede obtener?](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de usuario o las oficinas de donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>Decidir el tipo de números de teléfono se obtienen de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar las ubicaciones de usuario o las oficinas de donde se obtendrán los nuevos números de teléfono de Microsoft.</li><li>El tipo de números de teléfono se obtienen de Microsoft de documento.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir los números de teléfono existentes

Si su organización desea transferir (o del puerto) existente de números de teléfono a Microsoft, puede hacerlo mediante el envío de una solicitud de orden de puerto a Microsoft.

Puede transferir todos los sus números de teléfono existentes a la vez (puerto completo), y, en algunos mercados, puede transferir un subconjunto de sus números de teléfono existente (puerto parcial). Un puerto parcial puede ser útil en los casos donde desea mover gradualmente los usuarios al sistema de teléfono con planes de llamada.

Un orden de puerto único sólo puede transferir los números de teléfono a un tipo de número de teléfono único. Si necesita transferir algunas de sus números de teléfono como números de suscriptor y algunos como números de servicio, se recomienda que complete la transferencia a Microsoft en primer lugar y, a continuación, realizar la conversión tan pronto como los números se encuentran en el control de Microsoft.

Como alternativa (si es compatible con el puerto parcial), puede enviar varias solicitudes de puerto, solicitud de un puerto a la vez. Sin embargo, este enfoque alternativo va a prolongar su contrato con su proveedor de servicios de telecomunicaciones existente.

Portabilidad del número de teléfono es un tema complejo y requiere planeación minuciosa, la coordinación y administrar adecuadamente las expectativas de las partes interesadas. Para obtener más información, vea los siguientes artículos:

-   [Transferencia de los números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md)

-   [Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de usuario o las oficinas donde los números de teléfono existentes se transferirá a Microsoft.</li><li>Decidir el tipo de números de teléfono que se transfieran a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar las ubicaciones de usuario o las oficinas donde los números de teléfono existentes se transferirá a Microsoft.</li><li>El tipo de números de teléfono que se transfieran a Microsoft de documento.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planes de marcado

Un Plan de marcado de la característica de sistema telefónico de Office 365 es un conjunto de reglas de normalización que traducir marca números de teléfono en un formato alternativo (normalmente, el formato E.164) para la autorización de llamadas y el enrutamiento de llamadas. El servicio de conferencia de Audio aprovecha las mismas funciones que usa sistema telefónico para convertir los números de teléfono marcado en escenarios de salida de la conferencia (por ejemplo, invitar a participantes a través de RTC y marcado, la característica "Llamarme").

En la función de sistema de teléfono de Office 365, hay dos tipos de planes de marcado:

-   **Plan de marcado de servicio:** Es el valor predeterminado de plan de marcado que se aplica a los usuarios en función de su ubicación de uso de Office 365, y no puede modificarse.

-   **Plan de marcado de inquilino:** Se trata de un plan de marcado personalizable dentro de un inquilino, que se divide en dos tipos:

    -   **Plan de marcado de inquilino global:** El plan de marcado que se aplica a todos los usuarios en el inquilino.

    -   **Plan de marcado de usuario inquilino:** El plan de marcado que se aplica únicamente a usuarios específicos.

El plan de marcado efectivos asignado a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 de un usuario) y plan (que puede ser un plan de marcado inquilino global o en el plan de marcado de usuario del inquilino) de marcado de inquilinos.

![Tabla se muestran los planes de marcado de tres combinaciones de servicio e inquilino.] (media/audio_conferencing_image8.png "Tabla se muestran los planes de marcado de tres combinaciones de servicio e inquilino.")

> [!IMPORTANT]
> Puede haber un máximo de 25 reglas de normalización en cada plan de marcado de inquilino; por lo tanto, es importante evitar la duplicación de reglas de normalización que ya están disponibles como parte del servicio de plan de marcado.

Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si la organización requiere planes de marcado personalizado (requisitos empresariales, los requisitos de adopción y así sucesivamente).</li><li>Si procede, decidir el ámbito del plan de marcado de inquilino (inquilino global o usuario inquilino) para admitir los requisitos para los planes de marcado personalizado.</li><li>Si procede, decidir los planes de marcado de inquilino que va a crear para admitir oficinas o ubicaciones de usuario en el ámbito de la implementación de voz en la nube.</li><li>Si procede, decidir qué usuarios requieren un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar los planes de marcado personalizado y las reglas de normalización asociado a configurarse como parte de la implementación de voz en la nube.</li><li>Los usuarios para que se le ha asignado un plan de marcado personalizado y el plan de marcado de inquilinos que se asignará para cada usuario del documento.</li></ul>|

> [!TIP]
> Si es aplicable a su proyecto, puede usar la plantilla siguiente para documentar las configuraciones de plan de marcado de inquilinos.
> 
> |Nombre de plan de marcado de inquilino<br>_Descripción_  |Nombre de reglas de normalización<br>_Descripción_  |Patrón<br>Traducción<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_Plan de marcado de One Epping Road North Ryde, NSW, AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalización de número local para NSW, Australia_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalización de número gratuito para Australia_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalización de número de servicio para Australia_|^ (000\|1 [0125] \d{1,8}) $<br>1 $<br>False|
> |**SG-Singapore-OMB**<br>_Plan de marcado de OMB Singapore, SG_|**SG-OMB-Internal**<br>_Número interno (x8000 â €"x 8999) para office OMB, Singapur_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalización de número gratuito para Singapur_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalización de número de servicio para Singapur_|^ (1\d{3,4}\|9\d{2}) $<br>1 $<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Número interno (x7000 â €"x 7999) para 39 quai du presidente Roosevelt office, Issy-les-Moulineaux, Francia_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalización de número gratuito para Francia_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalización de número de servicio para Francia_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>1 $<br>False|

<br>

> [!TIP]
> La plantilla de ejemplo siguiente se puede utilizar para documentar las asignaciones de planes de marcado de su proyecto:
>
> |Usuario  |Oficina  |Tipo de plan de marcado  |Nombre de plan de marcado  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
> |Debra Berger|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
> |Lee Gu|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Plan de marcado de servicio|N/D|
> |Lidia Holloway|32 London Bridge Street|Plan de marcado de servicio|N/D|
> |Louis Lahr|32 London Bridge Street|Plan de marcado de servicio|N/D|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisiones del servicio de documento 

Use la información de las secciones anteriores de este artículo para documentar las decisiones de servicio. En general, esta documentación contiene las secciones principales siguientes:

-   Sistema telefónico con planes de llamar a la lista de habilitación de sitios

-   Asignación de licencias para el sistema telefónico con planes de llamar a los usuarios

-   Números de planificación de Créditos de comunicaciones

-   Adquisición de número de teléfono, números de teléfono y detalles de las ubicaciones de emergencia

-   Detalles de configuración de correo de voz

-   Identificador de autor de la llamada detalles de configuración de transparencias

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

<!--ENDOFSECTION-->