---
title: 'Tomar decisiones relacionadas con el servicio de Sistema telefónico con planes de llamada: Microsoft Teams'
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Elige entre planes y licencias de llamadas, configura ubicaciones de emergencia y características como el buzón de voz y la identificación de llamadas, adquiere o transfiere números de teléfono.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc618a4b68c8a620568eba5ae2ed52d17096b30
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232360"
---
# <a name="make-my-service-decisions"></a>Tomar mi decisión de servicio

Para planear la implementación técnica del sistema telefónico con planes de llamadas, debe tomar una serie de decisiones de servicio antes de tiempo para preparar mejor a su organización con el fin de implementar una solución que cumpla con los requisitos empresariales definidos.

## <a name="calling-in-teams"></a>Llamadas en Teams

Con Microsoft Teams, los usuarios pueden realizar y recibir llamadas telefónicas a la red de telefonía pública conmutada (RTC) o desde la misma. Los usuarios pueden usar sus propios números de teléfono dedicados para realizar y recibir llamadas telefónicas nacionales e internacionales de las aplicaciones cliente de Teams, con características avanzadas que incluyen el buzón de voz.

> [!NOTE]
> Encontrará la última guía básica de equipos para identificar Teams Phone System con las características de plan de llamadas en el <https://aka.ms/O365Roadmap>ámbito de la implementación en.

## <a name="phone-system-in-teams"></a>Sistema telefónico en Teams

Para que los usuarios de Teams puedan realizar y recibir llamadas de RTC, deben estar habilitadas para el sistema telefónico, una característica de Office 365.

Para habilitar la conectividad a la RTC, su organización puede usar Microsoft como su proveedor de servicios de telecomunicaciones. Finalmente, también tendrá la opción de "traiga su propio" proveedor de servicios de telecomunicaciones para habilitar la conectividad con RTC para el sistema telefónico.

> [!IMPORTANT]
> La capacidad de usar su propio proveedor de servicios de telecomunicaciones para el sistema telefónico con su implementación de equipos también está disponible con el enrutamiento directo del sistema telefónico. Para obtener más información sobre el enrutamiento directo, consulte la [Guía de enrutamiento directo](2-envision-make-my-service-decisions-direct-routing.md).

## <a name="phone-system-with-calling-plans"></a>Sistema telefónico con planes de llamadas

Para usar Microsoft como su proveedor de servicios de telecomunicaciones, necesita obtener las licencias del plan de llamadas y asignarlas a los usuarios del sistema telefónico.

Existen dos tipos principales de planes de llamadas:

-   Plan de llamadas nacionales

-   Plan de llamadas nacionales e internacionales

Cada tipo de plan de llamadas asigna un determinado número de minutos de llamadas por mes a cada uno de los usuarios que tienen asignada la licencia. Cuando se agote la asignación de minutos de llamadas, el usuario no podrá realizar llamadas salientes (excepto para llamadas de emergencia) hasta el ciclo de facturación del próximo mes. Si desea que los usuarios puedan seguir realizando llamadas salientes incluso después de que hayan agotado su asignación de minutos de llamadas o para que los usuarios que tengan un plan de llamadas nacionales realicen llamadas internacionales, puede configurar créditos de comunicaciones para su organización.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilidad de los planes de llamadas

Antes de planear la implementación de planes de llamadas en Teams, compruebe que el servicio de planes de llamadas esté disponible en su área revisando [disponibilidad de países y regiones para los planes de llamadas y](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)videoconferencias.

> [!IMPORTANT]
> Debido a restricciones legales, para que los planes de llamadas estén disponibles para organizaciones multinacionales, el contrato de suscripciones de Office 365 debe estar basado en un país o una región donde el servicio de planes de llamadas esté disponible o donde el servicio de planes de llamadas pueda Adquirí.

> [!NOTE]
> Si los planes de llamadas no están disponibles en su área, puede usar el [enrutamiento directo de sistema telefónico](2-envision-make-my-service-decisions-direct-routing.md) para permitir a los usuarios que usen equipos con capacidades RTC.

Después de confirmar que su organización puede obtener el servicio de planes de llamadas, compile la lista de ubicaciones o ubicaciones de usuarios donde implementará el servicio de planes de llamadas, en función de la lista de países y regiones disponibles.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida en qué ubicaciones del usuario u oficinas va a implementar el servicio de planes de llamadas.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones de usuario o las oficinas que se deben habilitar para el servicio de planes de llamadas.</li></ul>|

> [!TIP]
> A continuación se muestra un ejemplo de un sistema telefónico con la lista de habilitación de sitios de planes de llamadas.
> 
> | **Office**                     | **Ubicación**   | **Servicio de sistema telefónico** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Australia      | Servicio RTC heredado |
> | 100 Cyberport Road             | RAE de Hong Kong  | Enrutamiento directo del Sistema telefónico |
> | One Marina Boulevard           | Singapur      | Enrutamiento directo del Sistema telefónico |
> | 32 London Bridge Street        | Reino Unido | Sistema telefónico con planes de llamadas |
> | 39 quai du Président Roosevelt | Francia         | Sistema telefónico con planes de llamadas |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con los planes de llamadas en Office 365, todos los usuarios de su organización necesitan tener un número de teléfono de marcado directo (sí) exclusivo y una dirección de emergencia validada correspondiente. Revise [administrar números de teléfono de voz de nube](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers) para planificar la adquisición de números de teléfono para la implementación de los planes de llamadas.

Si está configurando números de teléfono para los planes de llamadas, debe asignar una dirección de emergencia a cada número de teléfono antes de asignar el número a un usuario. Esto es necesario para admitir las llamadas de emergencia. La dirección de emergencia debe validarse para asegurarse de que está en el formato correcto para su uso por parte de los servicios de respuesta de emergencia.

> [!IMPORTANT]
> Las llamadas a servicios de emergencia funcionan de manera diferente en el servicio de planes de llamadas que en los servicios telefónicos tradicionales. Es importante que comprenda estas diferencias y las comunique a todos los usuarios. Para obtener más información [, consulta las cláusulas y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md) .

Además de proporcionar una dirección de emergencia validada, puede definir ubicaciones de emergencia y asociarlas a la dirección de emergencia validada para proporcionar una ubicación más exacta dentro de una dirección. Una ubicación de emergencia es, normalmente, el número de edificio, la planta, la sección del edificio o el número de oficina donde se encuentra el usuario.

Para obtener más información sobre las ubicaciones de emergencia en relación con los planes de llamadas, consulte los artículos siguientes:

-   [¿Qué son las direcciones, las ubicaciones de emergencia y el enrutamiento de llamadas?](what-are-emergency-locations-addresses-and-call-routing.md)

-   [Términos y condiciones de llamadas de emergencia](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir la granularidad de la información de ubicación de emergencia que se recopilará para las ubicaciones de los usuarios o las oficinas en el ámbito de la implementación de planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la dirección de emergencia detallada y las ubicaciones de emergencia de cada ubicación de usuario u oficina en el ámbito de la implementación de los planes de llamada.</li></ul>|

> [!TIP]
> Puede usar la siguiente plantilla para documentar los detalles de los números de teléfono y los detalles de la ubicación de emergencia.
> 
> |Usuario |Ubicación y dirección de emergencia |Número de teléfono |
> |-----|-------------------------------|-------------|
> |Emily Braun |1034/32 Londres Bridge Street, Londres, SE1, Reino Unido |+ 44 23 4567 8901 |
> |Lidia Holloway |1065/32 Londres Bridge Street, Londres, SE1, Reino Unido |+ 44 23 4567 89112 |
> |Louis Lahr |1023/32 Londres Bridge Street, Londres, SE1, Reino Unido |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | Por añadir |
> |Rachelle Cormier |07N15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | Por añadir |
> |Isabell Potvin |07F05E/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia | Por añadir |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Correo de voz

El buzón de voz de nube, basado en los servicios de buzón de voz de Azure, admite depósitos de buzón de voz solo y no admite sistemas de correo electrónico de terceros.

De forma predeterminada, el buzón de voz de nube funciona con Exchange Online; sin embargo, tiene un modelo de implementación y una versión local admitidos de Exchange que permiten la entrega de mensajes de voz a buzones de usuario en la implementación de Exchange local.

El buzón de voz de nube incluye la transcripción del buzón de voz, que está habilitada para todos los usuarios de su organización de forma predeterminada. Las necesidades de su empresa pueden requerir que deshabilite la transcripción del buzón de voz para usuarios específicos o para todos los miembros de la organización. Si su organización decidió mantener habilitada la transcripción del buzón de voz, también tiene que considerar si se debe habilitar el enmascaramiento de la transcripción del buzón de voz. Para obtener más información, consulte [configuración de directivas de buzón de voz en su organización](set-up-phone-system-voicemail.md) .

>[!NOTE]
> Se ha implementado un mecanismo de reserva para que el buzón de voz de la nube pueda reenviar mensajes mediante SMTP, lo que significa que los usuarios que tengan un buzón en un sistema de correo electrónico de terceros recibirán sus mensajes de voz. Este mecanismo no incluye el tiempo de actividad del servicio garantizado ni otras características del buzón de voz, como cambiar el saludo del buzón de voz.

Para obtener más información sobre el buzón de voz en la implementación de un sistema telefónico, consulte [sistema telefónico con planes de llamadas](calling-plan-landing-page.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si va a habilitar el buzón de voz de nube en la implementación de los planes de llamadas.</li><li>Si usa Exchange local y la implementación existente no cumple con los requisitos necesarios para admitir el buzón de voz de nube, elija entre las opciones disponibles (actualizar y configurar el soporte técnico del buzón de voz en la nube, migrar a Exchange online o aprovechar la reserva). mecanismo descrito anteriormente).</li><li>Decida si va a habilitar o deshabilitar la transcripción del buzón de voz y la transcripción del buzón de voz la máscara de blasfemias en toda la organización o para usuarios específicos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Si procede, documente los puntos de decisión de Exchange para admitir el buzón de voz de la nube.</li><li>Si va a habilitar o deshabilitar el buzón de voz, la transcripción del buzón de voz y la transcripción del buzón de voz blasfemia máscaras solo para usuarios específicos, documente la lista de usuarios.</li></ul>|

> [!TIP]
> Los detalles del buzón de voz de la nube para el sistema telefónico con la implementación de planes de llamadas se pueden documentar como sigue.
> 
> |Usuario |Buzón de Exchange |¿Habilitar buzón de voz? |Transcripción del buzón de voz |Buzón de voz la máscara de blasfemias |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |Sí |Habilitado |Habilitado |
> |Lidia Holloway   |Online      |Sí |Habilitado |Deshabilitado |
> |Louis Lahr       |Local |Sí |Habilitado |Habilitado |
> |Marcel Beauchamp |Local |Sí |Deshabilitado |N/D |
> |Rachelle Cormier |Online      |Sí |Deshabilitado |N/D |
> |Isabell Potvin   |Local |Sí |Deshabilitado |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identidad de llamadas

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificación de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada. En algunos casos, hay requisitos empresariales legítimos para enmascarar la identificación de llamadas con el fin de proteger la identidad de las personas que llaman con el número de línea principal de Office (normalmente es un número de servicio revisado por la configuración del operador automático), como la identificación de llamadas, o para bloquear la identificación de llamadas presentación por completo.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si la manipulación de identificación de llamadas es necesaria para la implementación de los planes de llamadas.</li><li>Si corresponde, decida qué tipos de manipulación de identificación de llamadas (máscara con número de servicio o anonymize) se van a implementar.</li><li>Si corresponde, decida qué usuarios requieren la manipulación de identificación de llamadas y el tipo de manipulación de identificación de llamadas que se asignará a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente los usuarios a los que se les va a asignar la manipulación de identificación de llamadas y el tipo de manipulación de identificación de llamadas.</li></ul>|

> [!TIP]
> Este es un ejemplo de la documentación de detalles de la identificación de llamadas.
> 
> |Usuario  |Habilitar máscaras de identificación de llamadas salientes  |Tipo de enmascaramiento de identificación de llamadas  |Permitir invalidación de usuario  | Habilitar máscaras de identificación de llamadas entrantes  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|No|N/D|Sí|No|
> |Lidia Holloway|Sí|Número del servicio (OrgAA, + 44 20 7946 0000)|No|Sí|
> |Louis Lahr|No|N/D|Sí|No|
> |Marcel Beauchamp|Sí|Número de servicio (OrgAA, TBA)|No|Sí|
> |Rachelle Cormier|Sí|Anonymize|Sí|No|
> |Isabell Potvin|Sí|Número de servicio (OrgAA, TBA)|No|Sí|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Licencias para funcionalidades de voz en la nube

El sistema telefónico y las conferencias de audio son características de Office 365. Pueden recibir una licencia por separado como servicios complementarios para clientes existentes que tengan planes de suscripción de Office 365 E3 o E1; ya están incluidos como parte del plan de suscripción de Office 365 E5.

Planes de llamadas es un complemento para la característica de sistema telefónico en Office 365, por lo que debe tener habilitada una licencia de sistema telefónico para usar planes de llamadas.

Para admitir planes de llamadas y videollamadas adicionales (casos de uso de conferencias internacionales, llamadas externas, después de llamar a las asignaciones de minutos de planes, y así sucesivamente), puede configurar créditos de comunicaciones para su organización.

## <a name="licensing-for-calling-plans"></a>Licencias para planes de llamadas

Si su organización tiene previsto usar Microsoft como proveedor de servicios de telecomunicaciones, tendrá que obtener complementos de planes de llamadas adecuados a los requisitos empresariales de los usuarios. Por lo general, no todos los usuarios de una organización necesitan realizar llamadas internacionales, por lo que puede aprovisionar la mayoría de los usuarios con licencias nacionales del plan de llamadas.

Existen dos tipos de licencias del plan de llamadas:

-   Plan de llamada nacional

-   Plan de llamada nacional e internacional

> [!NOTE]
> Lo que se considera "nacional" para un usuario específico viene determinado por la ubicación de uso de Office 365 asignada por el usuario.

Cada tipo de plan de llamadas proporciona una asignación de minutos de llamadas que los usuarios pueden usar por mes, ya sea para realizar llamadas nacionales o llamadas internacionales. El plan de llamadas nacionales cuesta menos en comparación con el plan de llamadas nacionales e internacionales.

La flexibilidad de suscribir y asignar el tipo de plan de llamadas más adecuado para los requisitos empresariales de los usuarios individuales ayuda a su organización a controlar los costos de la implementación de los planes de llamadas.

Para cada inquilino de Office 365, el número combinado de minutos de llamadas se agrupa por país o región y por tipo de plan de llamadas. Cuando se alcance el límite de minutos de llamadas mensuales para el inquilino, se suspenderá el servicio de planes de llamadas (excepto para llamadas de emergencia) durante el resto del mes. El servicio de planes de llamadas se reanudará automáticamente el primer día del próximo mes calendario.

Puede configurar créditos de comunicaciones para sus organizaciones con el fin de permitir que los usuarios realicen llamadas salientes después de que se agote la asignación de minutos de llamadas sin tener que esperar hasta el próximo ciclo de facturación. Además, los créditos de comunicaciones otorgan a los usuarios el plan de llamadas nacionales, la capacidad de hacer llamadas internacionales, que se cobran a través de un modelo "pago por minuto".

Para obtener más información sobre los planes de llamadas y del sistema telefónico, consulte los artículos siguientes:

-   [Sistema telefónico](https://products.office.com/en-us/skype-for-business/phone-system)

-   [Planes de llamadas](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización no tiene la licencia de sistema telefónica necesaria, decida si va a adquirir la licencia de sistema telefónico en sus suscripciones existentes de Office 365 o si adquiere el servicio de complemento del sistema telefónico.</li><li>Decidir qué usuarios requieren una licencia de plan de llamadas nacionales y cuáles requieren una licencia de plan de llamadas nacional e internacional.</li><li>Decida si necesitará créditos de comunicaciones para la implementación de los planes de llamadas.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la división, el Departamento, la oficina o los grupos de usuarios a los que asignará una licencia de sistema telefónico con un plan de llamadas nacionales o un plan de llamadas nacionales e internacionales.</li></ul>|

> [!TIP]
> Puede usar el ejemplo siguiente para documentar la asignación de licencia para el sistema telefónico con los usuarios de planes de llamadas.
> 
> |Usuario |Oficina |Licencia de Office 365 |Plan de llamadas |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional e internacional |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional |
> |Louis Lahr |32 London Bridge Street |Office 365 E5 |Plan de llamada nacional |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema telefónico |Plan de llamada nacional |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Plan de llamada nacional e internacional |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema telefónico |Plan de llamada nacional |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Créditos de comunicaciones

Mediante el uso de créditos de comunicaciones, los usuarios pueden llamar desde una reunión de conferencias de audio para agregar a otra persona desde cualquier lugar del mundo (fuera del país de origen del organizador de la reunión). Puede configurar créditos de comunicaciones para su organización con el fin de permitir que los usuarios realicen llamadas salientes después de agotar su asignación de minutos de llamadas, sin tener que esperar hasta el ciclo de facturación del próximo mes. Además, los créditos de comunicaciones proporcionan a los usuarios asignados con el plan de llamadas nacionales la capacidad de hacer llamadas internacionales, que se cobran a continuación mediante un modelo "pago por minuto".

La primera consideración que hay que tener en cuenta a la hora de implementar Créditos de comunicaciones es decidir la cantidad inicial de fondos que se deben adquirir. Si tu organización decide usar la recarga automática, determinarás la cantidad óptima midiendo el uso real. Controla el uso de tus créditos en las comunicaciones a lo largo del tiempo y ajusta tu cantidad de recarga según sea necesario.

Para la implementación de los planes de llamadas, puede controlar el uso de créditos de comunicaciones para cada usuario, lo que le ayudará a asegurarse de que ha asignado estos créditos en función de las necesidades de su empresa.

Para obtener más información sobre los créditos de comunicaciones, consulte [¿Qué son los créditos de las comunicaciones?](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si necesita créditos de comunicaciones para su implementación de planes de llamadas o conferencias de audio.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la división, el Departamento, la oficina o los grupos de usuarios para los que va a habilitar créditos de comunicaciones.</li><li>Documente su plan de créditos de comunicaciones para su implementación de planes de llamadas o conferencias de audio.</li></ul>|

> [!TIP]
> Use el ejemplo siguiente para documentar la lista de asignaciones de créditos de comunicaciones para los usuarios de planes de llamadas.
> 
> |Usuario |Oficina |Plan de llamadas |Créditos de comunicaciones |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Plan de llamada nacional e internacional |Habilitado |
> |Lidia Holloway |32 London Bridge Street |Plan de llamada nacional |Deshabilitado |
> |Louis Lahr |32 London Bridge Street |Plan de llamada nacional |Habilitado |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Plan de llamada nacional |Deshabilitado |
> |Rachelle Cormier |39 quai du Président Roosevelt |Plan de llamada nacional e internacional |Habilitado |
> |Isabell Potvin |39 quai du Président Roosevelt |Plan de llamada nacional |Deshabilitado |

<br>

> [!TIP]
> Los números de planes de crédito de comunicaciones se pueden documentar como en el siguiente ejemplo.
>
> |         |         |
> |---------|---------|
> |Cantidad inicial|1000 $|
> |Cantidad de umbral|400 $|
> |Cantidad de recarga automática|Por añadir|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Administrar números de teléfono de voz de nube

Si implementas un sistema telefónico con tu propio proveedor de servicios de telecomunicaciones, la administración de números de teléfono permanecerá tal cual.

Para las implementaciones de conferencias de audio y planes de llamadas, puede elegir adquirir nuevos números de teléfono o transferir (Port) números de teléfono existentes.

Para permitir que los usuarios marquen números de teléfono de la forma en que están acostumbrados, como por ejemplo, omitir códigos de área para llamadas locales, omitir el código de país para llamadas nacionales o incluso usar el marcado de corto número al realizar llamadas en conferencia o llamar a otros usuarios de la organización, puede configurar un plan de marcado personalizado y asignarlo a los usuarios.

## <a name="acquire-new-telephone-numbers"></a>Adquirir nuevos números de teléfono

Los dos tipos de números de teléfono de las soluciones de voz en la nube de Microsoft son:

-   Números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización.

-   Números de servicio, disponibles como números de servicio de pago y gratuitos, que tienen una capacidad de llamadas simultáneas superior a los números de suscriptor y se pueden asignar a servicios como audioconferencias, operadores automáticos o colas de llamadas.

Para obtener más información sobre los tipos de números de teléfono, vea [diferentes tipos de números de teléfono para los planes de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md).

El recuento total de números de teléfono que puede obtener depende del tipo de número de teléfono y de la cantidad de licencias que haya comprado y asignado a los usuarios.

Para obtener más información sobre el recuento total de números de teléfono que puede obtener, consulte ¿cuántos [números de teléfono puede obtener?](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de los usuarios o las oficinas en las que recibirán nuevos números de teléfono de Microsoft.</li><li>Decidir el tipo de números de teléfono que se van a adquirir de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones o ubicaciones de los usuarios en las que recibirán nuevos números de teléfono de Microsoft.</li><li>Documente el tipo de números de teléfono que se van a adquirir de Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir números de teléfono existentes

Si su organización desea transferir (o trasladar) números de teléfono existentes a Microsoft, puede hacerlo enviando una solicitud de portabilidad a Microsoft.

Puede transferir todos los números de teléfono existentes a la vez (puerto completo) y, en algunos mercados, puede transferir un subconjunto de los números de teléfono existentes (puerto parcial). Un puerto parcial puede ser útil en aquellos casos en los que desea mover gradualmente los usuarios a un sistema telefónico con planes de llamadas.

Una única solicitud de portabilidad puede transferir los números de teléfono a un único tipo de número de teléfono. Si necesita transferir algunos números de teléfono como números de suscriptor y otros como números de servicio, le recomendamos que complete primero la transferencia a Microsoft y que, después, realice la conversión en cuanto los números estén en el control de Microsoft.

Como alternativa (si se admite el puerto parcial), puede enviar varias solicitudes de portabilidad, una solicitud de puerto a la vez. Sin embargo, este enfoque alternativo prolongará tu contrato con tu proveedor de servicios de telecomunicaciones existente.

El traslado de números de teléfono es un tema complejo y requiere una planificación, coordinación y una administración adecuada de las expectativas de los participantes. Para obtener más información, vea los artículos siguientes:

-   [Transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md)

-   [Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de los usuarios o las oficinas donde se transferirán los números de teléfono existentes a Microsoft.</li><li>Decidir el tipo de números de teléfono que se transferirán a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones o ubicaciones de los usuarios donde se transferirán los números de teléfono existentes a Microsoft.</li><li>Documente el tipo de números de teléfono que se transferirán a Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planes de marcado

Un plan de marcado de la característica de sistema telefónico de Office 365 es un conjunto de reglas de normalización que convierten los números de teléfono marcados en un formato alternativo (normalmente, formato E. 164) para la autorización de llamadas y el enrutamiento de llamadas. El servicio de audioconferencia aprovecha las mismas capacidades usadas por el sistema telefónico para traducir números de teléfono marcados en escenarios de aceptación de llamada en conferencia (por ejemplo, invitar a participantes a través de RTC y llamar a la característica "Llamarme").

En la característica del sistema telefónico de Office 365, hay dos tipos de planes de marcado:

-   **Plan de marcado de servicios:** Este es el plan de marcado predeterminado que se aplica a los usuarios en función de su ubicación de uso de Office 365 y no se puede modificar.

-   **Plan de marcado de inquilino:** Este es un plan de marcado personalizable dentro de un espacio empresarial, que se divide en dos tipos:

    -   **Inquilino-plan de marcado global:** El plan de marcado que se aplica a todos los usuarios del inquilino.

    -   **Inquilino-plan de marcado de usuario:** El plan de marcado que solo se aplica a usuarios específicos.

El plan de marcado eficaz asignado a los usuarios es la combinación del plan de marcado de servicios (basado en la ubicación de uso de Office 365 de un usuario) y el plan de marcado de inquilino (que puede ser un plan de marcado global de inquilinos o un plan de marcado de usuario).

En la ![tabla se muestran tres combinaciones de planes de servicio y de acceso telefónico de inquilino.] En la (media/audio_conferencing_image8.png "tabla se muestran tres combinaciones de planes de servicio y de acceso telefónico de inquilino.")

> [!IMPORTANT]
> Puede haber un máximo de 25 reglas de normalización en cada plan de marcado de inquilino; por lo tanto, es importante evitar duplicar las reglas de normalización que ya están disponibles como parte del plan de marcado del servicio.

Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si su organización requiere planes de marcado personalizados (requisitos empresariales, requisitos de adopción, etc.).</li><li>Si corresponde, decida el ámbito del plan de marcado de inquilino (inquilino global o de inquilino-usuario) para cumplir los requisitos de los planes de marcado personalizados.</li><li>Si corresponde, decida los planes de marcado de inquilino que creará para admitir ubicaciones de usuario o oficinas en el ámbito de la implementación de voz en la nube.</li><li>Si corresponde, decida qué usuarios requieren un plan de marcado personalizado y el plan de marcado de inquilino que se asignará a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente los planes de marcado personalizados y las reglas de normalización asociadas que se deben configurar como parte de la implementación de voz en la nube.</li><li>Documente los usuarios a los que se les va a asignar un plan de marcado personalizado y el plan de marcado de inquilino que se asignará a cada usuario.</li></ul>|

> [!TIP]
> Si es aplicable a su proyecto, puede usar la siguiente plantilla para documentar las configuraciones de los planes de marcado de inquilino.
> 
> |Nombre de plan de marcado de inquilino<br>_Descripción_  |Nombre de reglas de normalización<br>_Descripción_  |Patrón<br>Traducción<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_Plan de marcado de One Epping Road North Ryde, NSW, AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia_|^ (7 \ d{3}) $<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalización de número local para NSW, Australia_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalización de número gratuito para Australia_|^ (1 [38] \d{4,8}) \d * $<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalización de número de servicio para Australia_|^ (000\|1 [0125] \d{1,8}) $<br>1 $<br>False|
> |**SG-Singapore-OMB**<br>_Plan de marcado de OMB Singapore, SG_|**SG-OMB-Internal**<br>_Número interno (x8000 â € "x8999) para OMB Office, Singapur_|^ (8 \ d{3}) $<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalización de número gratuito para Singapur_|^ (1? 800 \ d{7}) \d * $<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalización de número de servicio para Singapur_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>1 $<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Número interno (x7000 â € "x7999) para 39 Quai du Président Roosevelt Office, Issy-les-Moulineaux, Francia_|^ (7 \ d{3}) $<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalización de número gratuito para Francia_|^ 0? (80 \ d{7}) \d * $<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalización de número de servicio para Francia_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>1 $<br>False|

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

## <a name="document-service-decisions"></a>Decisiones del servicio de documentos 

Use la información de las secciones anteriores de este artículo para documentar las decisiones de servicio. En general, en esta documentación se incluyen las siguientes secciones principales:

-   Sistema telefónico con la lista de habilitación del sitio de planes de llamadas

-   Asignación de licencias para el sistema telefónico con usuarios de planes de llamadas

-   Números de planificación de Créditos de comunicaciones

-   Adquisición de números de teléfono, números de teléfono y detalles de la ubicación de emergencia

-   Detalles de configuración del buzón de voz

-   Detalles de configuración de máscaras de identificación de llamadas

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

<!--ENDOFSECTION-->