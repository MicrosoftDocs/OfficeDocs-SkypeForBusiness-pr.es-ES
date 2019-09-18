---
title: 'Tomar decisiones relacionadas con el servicio de enrutamiento directo del sistema telefónico: Microsoft Teams'
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Obtenga más información sobre el enrutamiento directo, las licencias y las decisiones que se deben realizar.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c57b3c8950f7e1618f578862290e8fb1696b6bc0
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018784"
---
# <a name="make-my-service-decisions"></a>Tomar mi decisión de servicio

Para planear la implementación técnica del enrutamiento directo del sistema telefónico ("enrutamiento directo"), debe tomar una serie de decisiones de servicio antes de tiempo para preparar mejor su organización con el fin de implementar una solución que cumpla con los requisitos empresariales que ha definido.

## <a name="calling-in-teams"></a>Llamadas en Teams

Con Microsoft Teams, los usuarios pueden realizar y recibir llamadas telefónicas a la red de telefonía pública conmutada (RTC) o desde la misma. Los usuarios pueden usar sus propios números de teléfono dedicados para realizar y recibir llamadas de telefonía nacionales e internacionales (incluido el buzón de voz) desde la aplicación cliente de Teams.

## <a name="direct-routing"></a>Enrutamiento directo

Para que los usuarios de Teams puedan realizar y recibir llamadas de RTC, deben estar habilitadas para el sistema telefónico, una característica de Office 365.

Para habilitar la conectividad a la RTC, puede usar el enrutamiento directo para ofrecer a las personas de su organización la capacidad de realizar y recibir llamadas telefónicas fuera de la organización a través de la RTC.

Con el enrutamiento directo, la conectividad de RTC es facilitada por un proveedor de terceros, lo que le permite continuar usando sus troncos RTC existentes proporcionados por su proveedor de servicios RTC. Esto permite la implementación en países en los que el sistema telefónico con planes de llamadas ("planes de llamadas") no está disponible, o en implementaciones en las que es necesario mantener un contrato de proveedor de servicios RTC existente o mantener la interoperabilidad con ciertos sistemas locales Obligatorio.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Disponibilidad del enrutamiento directo

El enrutamiento directo está disponible en cualquier país en el que esté disponible Office 365. Consulte [disponibilidad internacional](https://products.office.com/business/international-availability) para obtener una lista de estos países.

Después de confirmar que su organización puede obtener la característica del sistema telefónico, compile la lista de ubicaciones o ubicaciones de los usuarios donde implementará el sistema telefónico, en función de la lista de países y regiones disponibles. Además, identifique los usuarios a los que va a habilitar los planes de llamadas o el enrutamiento directo de cada ubicación.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Identifique las ubicaciones de los usuarios o las oficinas en las que implementará el sistema telefónico.<li>Identifique los usuarios a los que va a habilitar los planes de llamadas o el enrutamiento directo para cada ubicación que tenga.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones de usuario o las oficinas que se van a habilitar para el sistema telefónico.<li>Documente la lista de usuarios a los que va a habilitar los planes de llamadas o el enrutamiento directo para cada ubicación que tenga</ul>|

> [!TIP]
> A continuación se muestra un ejemplo de una lista de habilitación de sitios de enrutamiento directo.
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

El sistema telefónico requiere que todos los usuarios de su organización tengan un número de teléfono de marcación directa (sí) exclusivo. Con el enrutamiento directo, el proveedor de servicios RTC proporciona los números de teléfono y los servicios de emergencia.

> [!NOTE]
> Con el enrutamiento directo, los usuarios pueden seguir usando sus propios números de teléfono, proporcionados por el proveedor de servicios RTC.
> 
> [!TIP]
> Puede usar la siguiente plantilla para documentar los detalles de los números de teléfono.
> 
> |Usuario |Número de teléfono |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |Louis Lahr | + 44 23 4567 8921 |
> |Marcel Beauchamp | Por añadir |
> |Rachelle Cormier | Por añadir |
> |Isabell Potvin | Por añadir |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Correo de voz

El buzón de voz de nube, basado en los servicios de buzón de voz de Azure, admite depósitos de buzón de voz solo y no admite sistemas de correo electrónico de terceros.

El buzón de voz de nube incluye la transcripción del buzón de voz, que está habilitada para todos los usuarios de su organización de forma predeterminada. Las necesidades de su empresa pueden requerir que deshabilite la transcripción del buzón de voz para usuarios específicos o para todos los miembros de la organización. Si su organización decidió mantener habilitada la transcripción del buzón de voz, también tiene que considerar si se debe habilitar el enmascaramiento de la transcripción del buzón de voz. Para obtener más información, consulte [configuración de directivas de buzón de voz en su organización](set-up-phone-system-voicemail.md) .

Para obtener más información sobre el buzón de voz en una implementación de sistema telefónico, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si va a habilitar el buzón de voz de nube en la implementación de enrutamiento directo.<li>Decida si va a habilitar o deshabilitar la transcripción del buzón de voz y la transcripción del buzón de voz la máscara de blasfemias en toda la organización o para usuarios específicos.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Si procede, documente los puntos de decisión para admitir el buzón de voz de nube.<li>Si va a habilitar o deshabilitar el buzón de voz, la transcripción del buzón de voz y la transcripción del buzón de voz blasfemia máscaras solo para usuarios específicos, documente la lista de usuarios.</ul>|

> [!TIP]
> Los detalles del buzón de voz de nube se pueden documentar en la tabla siguiente.
> 
> | **Usuario**         | **Buzón de Exchange** | **¿Habilitar buzón de voz?** | **Transcripción del buzón de voz** | **Buzón de voz la máscara de blasfemias** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Sí                   | Habilitado                     | Habilitado                                       |
> | Lidia Holloway   | Online               | Sí                   | Habilitado                     | Deshabilitado                                      |
> | Louis Lahr       | Local          | Sí                   | Habilitado                     | Habilitado                                       |
> | Marcel Beauchamp | Local          | Sí                   | Deshabilitado                    | N/D                                           |
> | Rachelle Cormier | Online               | Sí                   | Deshabilitado                    | N/D                                           |
> | Isabell Potvin   | Local          | Sí                   | Deshabilitado                    | N/D                                           |
> 
> [!NOTE]
> Para usar Teams y el buzón de voz, los usuarios deben tener buzones de Exchange. Vea [cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md) para obtener más información.

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Licencias para enrutamiento directo

Si su organización tiene previsto usar el enrutamiento directo, tendrá que obtener las licencias necesarias. Los usuarios de enrutamiento directo deben tener las siguientes licencias asignadas en Office 365:

-   Microsoft Phone System

-   Microsoft Teams

-   Audioconferencia

Se necesita una licencia de audioconferencia para agregar participantes externos a las reuniones programadas, ya sea mediante el marcado a ellas o proporcionando el número de acceso telefónico local. Cuando se llama a un participante externo, el servicio de audioconferencia realiza la llamada mediante capacidades de llamadas en línea. La licencia de audioconferencia es opcional y solo es necesaria para los usuarios que vayan a organizar conferencias de equipos que incluyan conferencias de audio.


> [!NOTE]
> Para proporcionar números de teléfono con un puente de conferencia gratuito y para permitir el acceso telefónico de las conferencias a números de teléfono internacionales, debe configurar [créditos de comunicaciones](what-are-communications-credits.md) para su organización.

Las conferencias de audio y el sistema telefónico se pueden conceder por separado como servicios complementarios para clientes existentes que tengan planes de suscripción de Office 365 E3 o E1; ya están incluidos como parte del plan de suscripción de Office 365 E5.

> [!TIP]
> También puede usar el enrutamiento directo para los usuarios que están habilitados para llamar a planes cuando enrutan las llamadas a PBX de terceros. Para obtener más información, consulte [licencias y otros requisitos del enrutamiento directo](direct-routing-plan.md#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización no tiene la licencia de sistema telefónica necesaria, decida si va a adquirir la licencia de sistema telefónico en sus suscripciones existentes de Office 365 o si adquiere el servicio de complemento del sistema telefónico.<li>Decida si necesitará créditos de comunicaciones para la implementación de enrutamiento directo.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la división, el Departamento, la oficina o los grupos de usuarios a los que asignará una licencia de sistema telefónico.<li>Si las conferencias de audio con números gratuitos están en el ámbito, documente la división, el Departamento, la oficina o los grupos de usuarios a los que desee habilitar créditos de comunicaciones.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Consideraciones de Office 365

Todos los usuarios que vayan a estar habilitados para el enrutamiento directo deben estar alojados en Office 365. En el caso de implementaciones híbridas con Skype empresarial Server local o Lync Server, necesita mover usuarios a Skype empresarial online antes de configurarlos para que usen el enrutamiento directo con Teams.

Todos los usuarios que están en el ámbito de las implementaciones de enrutamiento directo deben estar habilitados para Teams.

Su inquilino de Office 365 debe estar habilitado con uno o más dominios porque el \*dominio default. onmicrosoft.com no se puede usar con enrutamiento directo. Para obtener más información sobre los dominios y los inquilinos de Office 365, consulte [preguntas más frecuentes](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)sobre los dominios.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si es necesario migrar algún usuario a Skype empresarial online para admitir el enrutamiento directo.<li>Identifique los usuarios que deben habilitarse para los equipos.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la lista de usuarios que necesitan ir a Skype empresarial online y habilitarlos para Teams.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>Consideraciones sobre SBC

Debe usar controladores de borde de sesión compatibles y certificados (SBCs) que deben estar emparejados al servicio de enrutamiento directo para proporcionar conectividad RTC para los usuarios. Para obtener una lista de SBCs certificado, consulte [controladores de borde de sesión admitidos](direct-routing-plan.md#supported-session-border-controllers-sbcs).

Según el entorno, el número de ubicaciones y los requisitos de enrutamiento de voz, es posible que tenga que implementar varios SBCs para admitir su base de usuarios.

### <a name="sbc-domain-names"></a>Nombres de dominio de SBC

Cada SBC que empareje con enrutamiento directo debe tener un nombre DNS único. Los nombres DNS de SBC deben ser de uno de los nombres de dominio registrados en el inquilino de Office 365. Si su inquilino tiene asignados varios nombres de dominio, puede usar cualquiera de estos nombres de dominio al planear los nombres DNS de SBCs.

> [!IMPORTANT]
> No se permite el uso de *. onmicrosoft.com para el nombre DNS de SBC.

### <a name="certificates"></a>Certificados

Cada SBC implementado con enrutamiento directo requiere un certificado Obtenido de una lista de entidades de certificación admitidas. El certificado debe incluir el nombre DNS de SBC en los campos asunto, nombre alternativo de asunto o nombre común.

> [!NOTE]
> También se admite el uso de certificados comodín con SBCs.

Para obtener más información y una lista de las entidades de certificación compatibles, consulte [certificado público de confianza para SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>Puertos y direcciones IP de SBC

Cada SBC debe configurarse con una dirección IP pública a la que se pueda acceder desde los centros de trabajo de Office 365. También puede configurar la traducción de direcciones de red (NAT) para publicar su SBCs en los centros de trabajo de Office 365.

SBCs requiere conectividad bidireccional para comunicarse con los servicios en la nube para la señalización y los medios. La señalización es controlada por el componente denominado *SIP proxy*, y los medios lo administran los *procesadores multimedia*.

Debe definir números de Puerto específicos en cada SBC para las señales y los medios SIP, y configurar los firewalls para permitir el tráfico bidireccional a estos puertos y sus direcciones IP asociadas.

Para obtener más información, consulte [señalización SIP: FQDN](direct-routing-plan.md#sip-signaling-fqdns) y [tráfico multimedia: intervalos de puertos](direct-routing-plan.md#media-traffic-port-ranges).


> [!NOTE]
> Se recomienda establecer un límite máximo de sesión concurrente para cada SBC, basado en el modelo de SBC. Ese límite entonces desencadenaría una notificación cuando la SBC se esté ejecutando o cerca de su capacidad.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida en qué ubicaciones va a implementar SBCs.<li>Decida un nombre DNS para cada SBC que planee implementar.<li>En función de la decisión de nombre de dominio de SBC, decida si va a usar un certificado comodín para admitir todos los SBCs de su implementación o un certificado dedicado por SBC.<li>Decida en qué entidad emisora de certificados obtendrá los certificados de su SBCs.<li>Defina una pareja de dirección IP y Puerto pública para cada SBC que vaya a implementar y decida si va a asignar las direcciones IP públicas a la SBCs o usar NAT.<li>Identifique el número máximo de sesiones simultáneas que cada SBC admite o puede controlar.<li>Decidir qué SBCs se configurará con la omisión de medios.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las decisiones que se hayan tomado para el SBCs mediante la tabla de ejemplo siguiente.</ul>|


> [!TIP]
> Use la siguiente plantilla para documentar los detalles de SBC para la implementación de enrutamiento directo.
> 
> | **Nombre DNS de SBC (FQDN)** | **Marca y modelo de SBC** | **Certificado** | **Ubicación**  | **Dirección IP** | **Puerto de señalización SIP** | **ÉSTE?** | **Máximo de sesiones simultáneas** | **¿La omisión de medios está habilitada?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | DETERMINADO | \*. contoso.com | Ámsterdam | DETERMINADO | DETERMINADO | Sí | DETERMINADO | No |
> | SBC-Asia.contoso.com | DETERMINADO | \*. contoso.com | RAE de Hong Kong | DETERMINADO | DETERMINADO | No | DETERMINADO | Sí |
> | SBC-Africa.contoso.com | DETERMINADO | \*. contoso.com | Johannesburgo | DETERMINADO | DETERMINADO | Sí | DETERMINADO | Sí |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>Enrutamiento de voz

Debe configurar Microsoft Phone System para enrutar las llamadas al SBCs específico para el enrutamiento directo. Puede configurar rutas de voz en función de:

-   Patrón de número denominado.

-   Llamado número + el usuario que realiza la llamada.


El enrutamiento de llamadas consta de los siguientes elementos:

-   Directiva de enrutamiento de voz: contenedor para usos de RTC; puede asignarse a un usuario o a varios usuarios

-   Usos de RTC: contenedor de rutas de voz y usos de RTC; puede compartirse en diferentes directivas de enrutamiento de voz

-   Rutas de voz: patrón de número y conjunto de puertas de enlace RTC en línea para usarlas en llamadas en las que el número de llamada coincide con el patrón

-   El puntero de puerta de enlace RTC en línea en SBC, también almacena la configuración que se aplica cuando una llamada se coloca a través de SBC, como reenvío de identidad declarada en P (PAI) o códecs preferidos; se puede Agregar a las rutas de voz

Puede configurar las rutas de voz con el enrutamiento directo para coexistir con los planes de llamadas. Esa configuración permite a los planes de llamadas enrutar algunas de las llamadas al SBCs específico mediante enrutamiento directo.

> [!TIP]
> SBCs puede designarse como *activo* y como *backup*. Eso significa que cuando el SBC configurado como activo para este patrón numérico o patrón numérico + usuario específico, no está disponible, las llamadas se enrutarán a un SBC de copia de seguridad.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida las directivas de enrutamiento de voz, los usos de RTC y las rutas de voz que creará para admitir ubicaciones de usuario o oficinas en el ámbito de la implementación de enrutamiento directo.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar las directivas de enrutamiento de voz, usos de RTC y rutas de voz para su organización.<li>Documente los usuarios que se asignarán a cada directiva de enrutamiento de voz que defina.</ul>|

> [!TIP]
> Use la siguiente plantilla para documentar las directivas de voz para la implementación de enrutamiento directo.
> 
> | **Uso de RTC** | **Ruta de voz** | **Patrón de números** | **Prioridad** | **SBC** | **Descripción** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | Solo para Estados Unidos | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Ruta activa para números llamados + 1 425 XXX XX XX o + 1 206 XXX XX XX |
> | Solo para Estados Unidos | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | Ruta de copia de seguridad para los números + 1 425 XXX XX XX ó + 1 206 XXX XX XX |
> | Solo para Estados Unidos | "Otros + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Ruta de números llamados + 1 XXX XXX XX XX (excepto + 1 425 XXX XX XX o + 1 206 XXX XX XX) |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | Ruta para cualquier patrón de números |
> 
> [!IMPORTANT]
> Los usos de RTC en las directivas de enrutamiento de voz se aplican en orden y, si se encuentra una coincidencia en el primer uso, nunca se evalúan otros usos.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Directivas de llamadas y interoperabilidad

El enrutamiento directo solo es compatible con Microsoft Teams. Para realizar o recibir llamadas RTC mediante enrutamiento directo, debe configurar las directivas necesarias para asegurarse de que las llamadas entrantes se reciban en Teams.

> [!NOTE]
> Los usuarios que están habilitados para el enrutamiento directo no pueden realizar ni recibir llamadas de enrutamiento directos con Skype empresarial, por lo que se debe implementar el cliente de Teams.

Puede configurar los usuarios para que establezcan equipos como su cliente preferido para las llamadas mediante uno de los dos métodos siguientes:

-   Configurar el usuario para el modo solo de Teams

-   Configure Teams como el cliente de llamadas preferido asignando el TeamsCallingPolicy y TeamsInteropPolicy.

Para obtener más información, consulte [asignar el modo solo de Teams a los usuarios para garantizar la superficie de llamadas en Microsoft Teams](direct-routing-configure.md#assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir qué método usar para establecer Teams como cliente preferido para las llamadas.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente los usuarios que se configurarán con directivas de interoperabilidad y llamadas.</ul>|

> [!IMPORTANT]
> Cuando un usuario se ha configurado para el modo solo para equipos, este usuario ya no puede iniciar sesión en Skype empresarial.

Para que los usuarios vean la pestaña llamadas en el cliente de Teams, debe habilitar las llamadas privadas en el nivel de organización para el inquilino. Para obtener más información sobre cómo habilitar las llamadas privadas, consulte [Habilitar la llamada de Microsoft Teams](direct-routing-configure.md) .


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisiones del servicio de documentos

Use la información de las secciones anteriores de este artículo para documentar las decisiones de servicio. En general, en esta documentación se incluyen las siguientes secciones principales:

-   Sistema telefónico con la lista de habilitación del sitio de planes de llamadas

-   Detalles de configuración del buzón de voz

-   Asignación de licencias para usuarios de enrutamiento directo de sistema telefónico

-   Detalles de configuración de SBC

-   Directiva de enrutamiento de voz y detalles de enrutamiento

-   Detalles de la Directiva de interoperabilidad y llamadas

<!--ENDOFSECTION-->
