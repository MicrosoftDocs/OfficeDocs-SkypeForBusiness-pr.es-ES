---
title: 'Tomar decisiones relacionadas con el servicio de enrutamiento directo del sistema telefónico: Microsoft Teams'
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Obtenga información sobre el enrutamiento directo, administración de licencias, y las decisiones que deben realizarse.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a2371c72f24b19b9e3c4fe836a59cbc800ad1c4
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401793"
---
# <a name="make-my-service-decisions"></a>Tomar decisiones de mi servicio

Para planear la implementación técnica del teléfono del sistema enrutamiento directo ("enrutamiento directo"), debe realizar una serie de decisiones de servicio antes de tiempo para preparar mejor su organización para implementar una solución que cumpla los requisitos de negocio que ha definido.

## <a name="calling-in-teams"></a>Al llamar a los equipos

Con Microsoft Teams, los usuarios pueden realizar y recibir llamadas de teléfono a o desde la red telefónica conmutada (RTC). Los usuarios pueden utilizar sus propios números de teléfono dedicado para realizar y recibir llamadas de teléfono nacionales e internacionales (incluido el correo de voz) de la aplicación de los equipos cliente.

## <a name="direct-routing"></a>Enrutamiento directo

Para que los usuarios de los equipos que puedan realizar y recibir llamadas de RTC, deben estar habilitados para el sistema telefónico, una característica de Office 365.

Para habilitar la conectividad a la RTC, puede usar el enrutamiento directo para otorgar a los usuarios de la organización la capacidad de realizar y recibir llamadas de teléfono fuera de la organización a través de la RTC.

Con el enrutamiento directo, conectividad de RTC se facilita gracias a un proveedor de terceros, que proporciona la capacidad de seguir utilizando sus troncos RTC existentes proporcionadas por el proveedor de servicios de RTC. Esto permite la implementación en países donde el sistema telefónico con una llamada a planes ("llamar a planes de") no están disponibles, o en las implementaciones donde debe mantener un contrato del proveedor de servicio RTC existente o es la interoperabilidad con ciertos sistemas locales Obligatorio.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Disponibilidad de enrutamiento directo

Enrutamiento directo está disponible en cualquier país donde Office 365 está disponible. Para obtener una lista de estos países, vea [disponibilidad internacional](https://products.office.com/business/international-availability) .

Después de confirmar que su organización puede obtener la característica del sistema de teléfono, compilar la lista de ubicaciones de usuario o las oficinas donde podrá implementar sistema telefónico, en función de la lista de disponibles países y regiones. También se identifican los usuarios que se va a habilitar el enrutamiento directa o planes de llamada para cada ubicación que tiene.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Identifique las ubicaciones de usuario o en el que se implementa el sistema de teléfono de oficinas.<li>Identificar los usuarios que se va a habilitar el enrutamiento directa o planes de llamada para cada ubicación que tiene.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar las ubicaciones de usuario o las oficinas a habilitarse para el sistema telefónico.<li>La lista de usuarios que se va a habilitar el enrutamiento directa o planes de llamada para cada ubicación que tiene de documentos</ul>|

> [!TIP]
> A continuación es un ejemplo de una lista de habilitación enrutamiento directo del sitio.
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

Sistema telefónico requiere que cada usuario en su organización tiene un único entrante directa marcando el número de teléfono (DID). Con el enrutamiento directo, los números de teléfono y los servicios de emergencia proporcionados por su proveedor de servicios de RTC.

> [!NOTE]
> Con el enrutamiento directo, los usuarios pueden seguir utilizando sus propios números de teléfono, proporcionadas por el proveedor de servicio RTC.
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

Correo de voz en la nube, con tecnología de servicios de correo de voz de Azure, es compatible con depósitos de correo de voz a los buzones de Exchange y no es compatible con sistemas de correo electrónico de otro fabricante.

Correo de voz en la nube incluye transcripción de correo de voz, que está habilitado para todos los usuarios de la organización de forma predeterminada. Las necesidades de negocio pueden requerir que deshabilite la transcripción de correo de voz para usuarios específicos o todos los usuarios en toda la organización. Si su organización ha decidido mantener habilitado de transcripción de correo de voz, debe también tener en cuenta si debe habilitarse enmascaramiento de contenido ofensivo de transcripción de correo de voz. Para obtener más información, vea [configuración de directivas de correo de voz en su organización](set-up-phone-system-voicemail.md) .

Para obtener más información acerca de correo de voz en una implementación del sistema de teléfono, vea [Configurar el correo de voz en la nube](set-up-phone-system-voicemail.md).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si debe habilitar correo de voz de la nube en su implementación de enrutamiento directo.<li>Decidir si se debe habilitar o deshabilitar transcripción de correo de voz y enmascaramiento de contenido ofensivo transcripción de correo de voz en toda la organización o para usuarios específicos.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Si procede, documente los puntos de decisión para admitir el correo de voz en la nube.<li>Si se debe habilitar o deshabilitar el correo de voz, correo de voz transcripción y enmascaramiento de contenido ofensivo transcripción de correo de voz para determinados usuarios, documentos que la lista de los usuarios.</ul>|

> [!TIP]
> Detalles de correo de voz en la nube para la implementación de planes de llamada se pueden documentar como se muestra en la siguiente tabla.
> 
> | **Usuario**         | **Buzón de Exchange** | **¿Habilitar correo de voz?** | **Transcripción de correo de voz** | **Enmascaramiento de contenido ofensivo de transcripción de correo de voz** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Sí                   | Habilitado                     | Habilitado                                       |
> | Lidia Holloway   | Online               | Sí                   | Habilitado                     | Deshabilitado                                      |
> | Louis Lahr       | Local          | Sí                   | Habilitado                     | Habilitado                                       |
> | Marcel Beauchamp | Local          | Sí                   | Deshabilitado                    | N/D                                           |
> | Rachelle Cormier | Online               | Sí                   | Deshabilitado                    | N/D                                           |
> | Isabell Potvin   | Local          | Sí                   | Deshabilitado                    | N/D                                           |
> 
> [!NOTE]
> Para usar los equipos y correo de voz, los usuarios deben tener los buzones de Exchange. Para obtener más información, vea [cómo Exchange y los equipos de Microsoft para interactuar](exchange-teams-interact.md) .

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Concesión de licencias para el enrutamiento directo

Si su organización se va a usar el enrutamiento directo, debe obtener licencias necesarias. Los usuarios de enrutamiento directo deben tener las siguientes licencias asignadas en Office 365:

-   Sistema telefónico de Microsoft

-   Microsoft Teams

-   Audioconferencia

Licencia de conferencia de audio es necesaria para agregar los participantes externos a las reuniones programadas, mediante marcación a ellos o al proporcionar el número telefónico. Cuando un participante externo se marca a, el servicio de conferencia de Audio coloca la llamada mediante el uso de las funciones de llamadas en línea. Licencia de conferencia de audio es opcional y solo se requiere para los usuarios que se va a organizar los equipos las conferencias que incluyen conferencias de Audio.


> [!NOTE]
> Para proporcionar números de teléfono de puente de conferencia gratuito y para admitir la conferencia de salida para los números de teléfono internacional, debe establecer [Comunicaciones créditos](what-are-communications-credits.md) para su organización.

Conferencia de audio y sistema telefónico pueden tener licencia por separado como servicios complementarios para los clientes que tengan Office 365 E3 o E1 planes de suscripción; ya están incluidos como parte del plan de suscripción de Office 365 E5.

> [!TIP]
> También puede usar el enrutamiento directo para los usuarios que están habilitados para llamar a planes al enrutar sus llamadas a sistemas PBX de terceros. Para obtener más detalles, vea [Licensing y otros requisitos de enrutamiento directo](direct-routing-plan.md#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización no tiene la licencia del sistema de teléfono necesaria, decidir si la licencia del sistema de teléfono adquirirá pasando seguridad sus suscripciones a Office 365 existentes o al adquirir el servicio de complemento de sistema telefónico.<li>Decidir si necesitará Communications créditos para su implementación de enrutamiento directo.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Los grupos de división, departamento, office o de usuario se le asigna una licencia de sistema telefónico de documentos.<li>Si la conferencia de Audio con los números gratuitos está en el ámbito, los grupos de división, departamento, office o usuario podrá habilitar Communications créditos de documentos.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Consideraciones relacionadas con Office 365

Cualquier usuario que va a estar habilitada para el enrutamiento directo debe estar alojado en Office 365. Para las implementaciones híbridas con Skype local para Business Server o Lync Server, debe mover los usuarios a Skype para profesionales Online antes de configurar para usar el enrutamiento directa con los equipos.

Todos los usuarios que están en el ámbito de las implementaciones de enrutamiento directo deben estar habilitados para los equipos.

Debe estar habilitado el inquilino de Office 365 con uno o más dominios, debido a que el valor predeterminado \*. dominio onmicrosoft.com no se puede usar con el enrutamiento directo. Para obtener más información acerca de dominios y los inquilinos de Office 365, consulte [Preguntas más frecuentes de dominios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir si los usuarios necesitan migrarse a Skype para empresarial en línea admitir el enrutamiento directo.<li>Identificar los usuarios que deben habilitarse para los equipos.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>La lista de usuarios que necesiten mover a Skype para profesionales en línea y habilitarse para los equipos de documentos.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>Consideraciones de SBC

Debe usar controladores de borde de sesión compatibles y certificados (SBCs) que deben estar emparejados con el servicio de enrutamiento directo para proporcionar conectividad con RTC para los usuarios. Para obtener una lista de SBCs certificadas, vea [Admite controladores de borde de sesión](direct-routing-plan.md#supported-session-border-controllers-sbcs).

Según el entorno, el número de ubicaciones y los requisitos de enrutamiento de voz, es posible que necesite implementar varios SBCs para admitir la base de usuarios.

### <a name="sbc-domain-names"></a>Nombres de dominio SBC

Cada SBC que emparejar con el enrutamiento directo debe tener un nombre DNS único. Los nombres DNS de SBC deben ser de uno de los nombres de dominio registrados en el inquilino de Office 365. Si se ha asignado el inquilino de varios nombres de dominio, puede usar cualquiera de estos nombres de dominio al planear los nombres DNS de su SBCs.

> [!IMPORTANT]
> El uso de *. onmicrosoft.com para el nombre DNS de SBC no está permitido.

### <a name="certificates"></a>Certificados

Cada SBC implementado con el enrutamiento directo requiere un certificado obtenido de una lista de entidades de certificación compatibles. El certificado debe incluir el nombre DNS de SBC en el asunto, el nombre alternativo de sujeto o los campos de nombre común.

> [!NOTE]
> También se admite el uso de certificados con caracteres comodín con SBCs.

Para obtener más información y una lista de entidades de certificación compatibles, vea [pública certificado de confianza para el SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>Puertos y direcciones IP de SBC

Cada SBC debe configurarse mediante el uso de una dirección IP pública accesible desde los centros de datos de Office 365. También puede configurar la traducción de direcciones de red (NAT) para publicar sus SBCs en centros de datos de Office 365.

SBCs requieren conectividad bidireccional para comunicarse con los servicios de nube para la señalización y los medios. Señalización se controla mediante el componente denominado *Proxy SIP*y administran los medios por los *Procesadores de medios*.

Debe definir los números de puerto específico en cada SBC para la señalización SIP y medios y configurar los servidores de seguridad para permitir el tráfico bidireccional a estos puertos y sus direcciones IP asociadas.

Para obtener más información, consulte [de señalización SIP: FQDN y los puertos de firewall](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) y [el tráfico de medios: intervalos de puertos](direct-routing-plan.md#media-traffic-port-ranges).


> [!NOTE]
> Se recomienda establecer un límite máximo de sesiones simultáneas de cada SBC, basada en el modelo SBC. Este límite, a continuación, podría desencadenar una notificación cuando se ejecuta el SBC en o cerca de su capacidad.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir en qué ubicaciones podrá implementar SBCs.<li>Decidir un nombre DNS para cada SBC que planea implementar.<li>En función de la decisión de nombre de dominio SBC, decida si va a usar un certificado de comodín para admitir todos los SBCs en su implementación o un certificado por SBC dedicado.<li>Decidir qué entidad de certificación pública podrá obtener los certificados para sus SBCs desde.<li>Definir un par de puerto/dirección IP público para cada SBC que implementar y decidir si debe asignar las direcciones IP públicas para el SBCs o utilizar NAT.<li>Identificar el número máximo de sesiones simultáneas que admite cada SBC o pueden controlar.<li>Decidir qué SBCs se configurarán mediante el uso de desvío de medios.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Cada decisión que se realizan para el SBCs mediante el uso en la siguiente tabla de ejemplo del documento.</ul>|


> [!TIP]
> Utilice la siguiente plantilla en los detalles SBC para la implementación de enrutamiento directo del documento.
> 
> | **Nombre DNS de SBC (FQDN)** | **SBC marca y modelo** | **Certificado** | **Ubicación**  | **Dirección IP** | **Puerto de señalización SIP** | **¿NAT?** | **Sesiones simultáneas de Max** | **¿Desvío de medios habilitado?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC Europe.contoso.com | TBD | \*. contoso.com | Ámsterdam | TBD | TBD | Sí | TBD | No |
> | SBC Asia.contoso.com | TBD | \*. contoso.com | RAE de Hong Kong | TBD | TBD | No | TBD | Sí |
> | SBC Africa.contoso.com | TBD | \*. contoso.com | Johannesburgo | TBD | TBD | Sí | TBD | Sí |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>Enrutamiento de voz

Debe configurar el sistema de teléfono de Microsoft para enrutar las llamadas a la SBCs específicos para el enrutamiento directo. Puede configurar rutas de voz en función de:

-   Patrón de número llamado.

-   Patrón de número llamado + el usuario que realiza la llamada.


Enrutamiento de llamadas se compone de los siguientes elementos:

-   Directiva de enrutamiento de voz: contenedor de usos de RTC; se pueden asignar a un usuario o a varios usuarios

-   Usos de RTC: contenedor de rutas de voz y los usos de RTC; se pueden compartir en diferentes directivas de enrutamiento de voz

-   Rutas: patrón de número y un conjunto de puertas de enlace RTC en línea que se usará para las llamadas, donde el número de llamada coincide con el patrón de voz

-   Puerta de enlace de RTC Online - puntero en SBC, también almacena la configuración que se aplica cuando se realiza una llamada a través de SBC, como hacia delante P-Asserted-Identity (PAI) o códecs preferido; se pueden agregar a las rutas de voz

Puede configurar las rutas de voz con el enrutamiento directo para coexistir con planes de llamada. Que la configuración permite llamar a los planes enrutar algunas de las llamadas a la SBCs específicos mediante el uso de enrutamiento directo.

> [!TIP]
> SBCs se pueden designar como *activo* y *copia de seguridad*. Esto significa que cuando la SBC que está configurado como activo para este patrón de número, o número de la trama + usuario específico: no está disponible, las llamadas se enrutarán a un SBC copia de seguridad.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir el enrutamiento de directivas, usos de RTC y rutas de voz que se va a crear a ubicaciones de usuario de soporte técnico o en el ámbito de la implementación directa enrutamiento de voz.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar las directivas de enrutamiento de voz, usos de RTC y rutas de voz para su organización.<li>Los usuarios que se asignará para cada directiva de enrutamiento de voz que se definen del documento.</ul>|

> [!TIP]
> Usar la siguiente plantilla para documentar las directivas de voz para la implementación de enrutamiento directo.
> 
> | **Uso de RTC** | **Ruta de voz** | **Patrón de números** | **Prioridad** | **SBC** | **Descripción** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | NOSOTROS solo | "Redmond 1" | \^\\+ 1 (425\|206) (\\d.{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Ruta activa para números de llamada +1 425 XXX XX XX o +1 206 XXX XX XX |
> | NOSOTROS solo | "Redmond 2" | \^\\+ 1 (425\|206) (\\d.{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | Ruta de reserva para los números llamados +1 425 XXX XX XX o +1 206 XXX XX XX |
> | NOSOTROS solo | "Otros + 1" | \^\\+ 1 (\\d.{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Enrutar para números de llamada + 1 XXX XXX XX XX (excepto +1 425 XXX XX XX o +1 206 XXX XX XX) |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | Ruta para cualquier patrón de número |
> 
> [!IMPORTANT]
> Los usos de RTC en las directivas de enrutamiento de voz se aplican en orden, y si se encuentra una coincidencia en el primer uso, nunca se evalúan otros usos.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Interoperabilidad y llamar a las directivas

Enrutamiento directo sólo es compatible con Microsoft Teams. Para realizar o recibir llamadas de RTC a través de enrutamiento directa, debe configurar las directivas necesarias para asegurarse de que las llamadas entrantes se reciben en los equipos.

> [!NOTE]
> Los usuarios que están habilitados para el enrutamiento directo no se puede realizar o recibir dirigir las llamadas de enrutamiento mediante el uso de Skype para la empresa y, por lo tanto, debe ser implementado el cliente de los equipos.

Puede configurar los usuarios para configurar los equipos como su cliente preferido para las llamadas mediante uno de los dos métodos siguientes:

-   Configurar el usuario para el modo sólo los equipos

-   Configurar los equipos como cliente preferido llamado mediante la asignación de la TeamsCallingPolicy y la TeamsInteropPolicy.

Para obtener más información, vea [establecer los equipos de Microsoft como el preferido llamar al cliente para los usuarios](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir qué método utilizará para establecer los equipos como cliente preferido para las llamadas.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Los usuarios a configurarse con las directivas de interoperabilidad y llamar al método del documento.</ul>|

> [!IMPORTANT]
> Cuando un usuario está configurado para el modo de solo los equipos, este usuario ya no puede iniciar sesión para Skype para la empresa.

Para que los usuarios se ve la ficha llamadas en el cliente de los equipos, tiene que habilitar privada de llamada en un nivel de organización para el inquilino. Para obtener más información acerca de cómo habilitar las llamadas privadas, consulte [Habilitar Calling para equipos de Microsoft](direct-routing-configure.md) .


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisiones del servicio de documento

Use la información de las secciones anteriores de este artículo para documentar las decisiones de servicio. En general, esta documentación contiene las secciones principales siguientes:

-   Sistema telefónico con planes de llamar a la lista de habilitación de sitios

-   Detalles de configuración de correo de voz

-   Asignación de licencias para usuarios de enrutamiento directo de teléfono del sistema

-   Detalles de configuración de SBC

-   Directiva y detalles de enrutamiento de voz

-   Detalles de la directiva de interoperabilidad y llamada

<!--ENDOFSECTION-->
