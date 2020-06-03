---
title: Planear y administrar las llamadas de emergencia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Más información sobre las llamadas de emergencia, incluida información sobre las direcciones de emergencia, el enrutamiento de llamadas de emergencia y las llamadas de emergencia dinámicas.
ms.openlocfilehash: 889446ca08289ccb15128bee8ca6b6170398c599
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539497"
---
# <a name="manage-emergency-calling"></a>Administrar las llamadas de emergencia

Este artículo describe conceptos que necesita saber para administrar las llamadas de emergencia &mdash; incluye información sobre las direcciones de emergencia, las direcciones de emergencia dinámicas y el enrutamiento de llamadas de emergencia. En este artículo se usa la siguiente terminología:

- **Dirección de emergencia** : una ciudad es &mdash; la dirección física o postal de un lugar de trabajo para su organización.

  Por ejemplo, la dirección *12345 North Main Street, Redmond, WA 98052* se usa para enrutar llamadas de emergencia a las autoridades de distribución correspondientes y para ayudar a localizar a la persona que llama de emergencia.

- **Lugar** , normalmente un número de piso, edificio, ala o oficina. El lugar está asociado con una dirección de emergencia para proporcionar una ubicación más exacta dentro de un edificio. Puedes tener un número ilimitado de lugares asociados con una dirección de emergencia. Por ejemplo, si su organización tiene varios edificios, es posible que desee incluir información de ubicación para cada edificio y para cada planta en cada edificio.  

- **Ubicación de emergencia** : una ubicación es una dirección cívica &mdash; con un lugar opcional. Si tu empresa tiene más de una ubicación física, es probable que necesites más de una ubicación de emergencia. 

  Al crear una dirección de emergencia, se crea automáticamente un identificador de ubicación único para esta dirección.  Si agrega un lugar a una dirección de emergencia &mdash; por ejemplo, si agrega un piso a una dirección de edificio, &mdash; se creará un identificador de ubicación para la combinación de la dirección de emergencia y el lugar.  En este ejemplo, habrá dos identificadores de Ubicación: uno para la dirección cívica; una para la dirección de la ciudad y la ubicación asociada.

  Al asignar una ubicación de emergencia a un usuario o sitio, este es el único identificador de ubicación asociado con el usuario o el sitio.

- **Dirección registrada** : una dirección de emergencia asignada a cada usuario del plan de llamadas; a veces se lo conoce como dirección de emergencia estática o dirección de registro.  (Las direcciones registradas no se aplican a los usuarios de enrutamiento directo).

Las direcciones de emergencia se crean para llamar a los usuarios del plan mediante el centro de administración de Teams.  

>[!Note]
>Existen algunas diferencias en la forma de administrar las llamadas de emergencia, en función de si usa planes de llamadas de sistema telefónico o un enrutamiento directo de sistema telefónico para su conectividad con RTC. Estas consideraciones se describen en este artículo.

## <a name="emergency-address-validation"></a>Validación de la dirección de emergencia

Para asignar una dirección de emergencia a un usuario o a un identificador de red, debe asegurarse de que la dirección de emergencia está marcada como "validada".  La validación de dirección asegura que la dirección es legítima y que no se puede modificar una vez asignada. 

Si define una dirección de emergencia mediante la característica de búsqueda de mapas de direcciones en el centro de administración de Teams, la dirección se marca automáticamente como validada. No puede modificar una dirección de emergencia validada. Por lo tanto, si el formato o la representación de la dirección cambia, debe crear una dirección nueva con el formato actualizado.


## <a name="emergency-address-geo-codes"></a>Códigos geográficas de dirección de emergencia

Cada dirección de emergencia puede tener un código geográfico (latitud y longitud) asociado a ella. Estos códigos geográficas se usan en algunos países para ayudar en el enrutamiento de llamadas de emergencia con ubicaciones dinámicas. 

Si define una dirección de emergencia mediante la característica de búsqueda del mapa de direcciones en el centro de administración de Teams, el código geográfico se asocia automáticamente con una dirección de emergencia. También puede asociar códigos geográficas a una dirección si define la dirección mediante PowerShell. Sin embargo, Microsoft recomienda crear direcciones de emergencia para el plan de llamadas mediante la característica asignar búsqueda del centro de administración de Teams, que garantizará que las direcciones se han formateado, validado y tienen los códigos geográficas apropiados.  

>[!Important]
>Para asignar una ubicación de emergencia a un identificador de red para llamadas de emergencia dinámicas, la dirección de emergencia debe contener un código geográfico adecuado.


## <a name="considerations-for-calling-plans"></a>Consideraciones para las llamadas a planes

Para saber si los planes de llamadas están disponibles en su área, consulte [disponibilidad de países y regiones para los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).


### <a name="emergency-call-enablement"></a>Habilitación de llamadas de emergencia

Cada usuario del plan de llamadas se habilita automáticamente para hacer llamadas de emergencia y debe tener una dirección de emergencia registrada asociada a su número de teléfono asignado. 

Cuando la ubicación debe estar asociada a un número de teléfono, depende del país o de la región:

- En Estados Unidos y Canadá, por ejemplo, se requiere una ubicación de emergencia cuando se asigna un número a un usuario.

- Para otros países, &mdash; como en Europa, Oriente Medio y África (EMEA), &mdash; se requiere una ubicación de emergencia cuando obtiene el número de teléfono de Office 365 o cuando se transfiere desde otro proveedor u operador de servicios.

### <a name="dynamic-emergency-calling"></a>Llamadas de emergencia dinámicas

Las llamadas de emergencia dinámicas para los planes de llamadas de Microsoft proporcionan la capacidad de configurar y enrutar llamadas de emergencia basadas en la ubicación actual del cliente de Teams. La capacidad de llevar a cabo el enrutamiento automático para el correspondiente punto de respuesta de seguridad pública (PSAP) o para notificar personal de escritorio de seguridad varía según el país de uso del usuario de Teams.  

Para los usuarios del plan de llamadas, la ubicación dinámica para el enrutamiento de llamadas de emergencia solo se admite en Estados Unidos de la siguiente manera. Para obtener información sobre las llamadas de emergencia dinámicas y el enrutamiento directo, consulte consideraciones sobre el [enrutamiento directo](#considerations-for-direct-routing).

- Si un cliente de Teams para un usuario de un plan de llamadas de Estados Unidos adquiere dinámicamente una dirección de emergencia dentro de los Estados Unidos, esa dirección se usa para enrutamiento de emergencia en lugar de la dirección registrada, y la llamada se redirigirá automáticamente a la PSAP del área correspondiente de la dirección.

- Si un cliente de Teams para un plan de llamadas de Estados Unidos no adquiere dinámicamente una dirección de emergencia dentro de los Estados Unidos, la dirección de emergencia registrada se usa para ayudar a la pantalla y enrutar la llamada. Sin embargo, la llamada se filtrará para determinar si es necesaria una dirección actualizada antes de conectar la persona que llama a la PSAP adecuada.

En los Estados Unidos, debe configurar la dirección cívica que forma parte de las ubicaciones de emergencia asignadas a identificadores de red &mdash; e incluir los códigos geográficas asociados. Para obtener más información, consulte [planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).


### <a name="emergency-call-routing"></a>Enrutamiento de llamadas de emergencia

Cuando un usuario de plan de llamadas de equipos marca un número de emergencia, la manera en que se dirige la llamada a la PSAP depende de lo siguiente:

- Si el cliente de Teams determina de forma dinámica la dirección de emergencia.

- Si la dirección de emergencia es la dirección registrada asociada con el número de teléfono del usuario.

- La red de llamadas de emergencia de ese país.

  **En los Estados Unidos:**

  - Si un cliente de Teams se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente se enrutan automáticamente al PSAP que atiende esa ubicación geográfica. 

  - Si un cliente de Teams no se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente las puede filtrar un centro de atención nacional para determinar la ubicación de la persona que llama antes de transferir la llamada a la PSAP que atiende a esa ubicación geográfica.

  - Si una persona que llama de emergencia no puede actualizar su ubicación de emergencia al centro de detección, la llamada se transferirá al PSAP que atiende a la dirección registrada del autor de la llamada.

  **En Canadá, Irlanda y en el Reino Unido**, primero se filtran las llamadas de emergencia para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución correspondiente. 

  **En Francia, Alemania y España**, las llamadas de emergencia se dirigen directamente al PSAP que atiende la dirección de emergencia asociada con el número, independientemente de la ubicación del autor de la llamada.

  **En los países bajos**, las llamadas de emergencia se dirigen directamente al PSAP para el código de área local del número, independientemente de la ubicación del autor de la llamada.

  **En Australia**, el socio del transportista configura y dirige las direcciones de emergencia.

  **En Japón**, no se admiten las llamadas de emergencia.


Para obtener más información, vea:

- [Planes de llamadas](calling-plan-landing-page.md)

- [Diferentes tipos de números de teléfono que se usan para planes de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Términos y condiciones de llamadas de emergencia](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Consideraciones para el enrutamiento directo

Si los planes de llamadas no están disponibles en su área o desea mantener el operador actual, considere el [enrutamiento directo](direct-routing-landing-page.md). Para obtener más información, consulte [configurar el enrutamiento directo](direct-routing-configure.md) y [administrar las directivas de enrutamiento de llamadas de emergencia](manage-emergency-call-routing-policies.md).

### <a name="emergency-call-enablement-and-configuration"></a>Habilitación y configuración de llamadas de emergencia

Debe definir directivas de llamadas de emergencia para los usuarios de enrutamiento directo mediante una directiva de enrutamiento de llamadas de emergencia (TeamsEmergencyCallRoutingPolicy) para definir los números de emergencia y el destino de enrutamiento asociado. (Tenga en cuenta que las ubicaciones de emergencia registradas no son compatibles con los usuarios de enrutamiento directo).

Puede asignar una directiva de enrutamiento de llamadas de emergencia a una cuenta de usuario de enrutamiento directo, a un sitio de red o a ambas. Cuando un cliente de equipo inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red donde se encuentra el cliente de la siguiente manera:

- Si una directiva de enrutamiento de llamadas de emergencia está asociada al sitio, se usa la Directiva del sitio para configurar las llamadas de emergencia.

- Si no hay ninguna directiva de enrutamiento de llamadas de emergencia asociada al sitio, o si el cliente está conectado a un sitio no definido, se usa la Directiva de enrutamiento de llamadas de emergencia asociada a la cuenta de usuario para configurar las llamadas de emergencia. 

- Si el cliente de Teams no puede obtener una directiva de enrutamiento de llamadas de emergencia, quiere decir que el usuario no está habilitado para hacer llamadas de emergencia.

### <a name="dynamic-emergency-calling"></a>Llamadas de emergencia dinámicas

Los clientes de Team para usuarios con enrutamiento directo pueden adquirir una dirección de emergencia dinámica, que se puede usar para enrutar llamadas dinámicamente en función de la ubicación de la persona que llama. Para obtener más información, consulte [configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing"></a>Enrutamiento de llamadas de emergencia

La Directiva de enrutamiento de llamadas de emergencia hace referencia a un uso de RTC en línea, que debe tener la configuración de enrutamiento directa adecuada para enrutar correctamente las llamadas de emergencia a las puertas de enlace o gateways PSTN correspondientes. En particular, debes asegurarte de que haya un OnlineVoiceRoute para la cadena de marcado de emergencia. Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md). 

(Nota: los clientes de equipos encierran el inicio de sesión "+" delante de los números de emergencia de forma similar a como lo hace el cliente de Skype empresarial, es decir, + 911. Este comportamiento se modificará en los próximos meses, de modo que las llamadas de emergencia de Teams ya no enviarán "+" antes del número; es decir, 911.)

La capacidad de enrutar de manera dinámica llamadas de emergencia para usuarios de enrutamiento directo varía según la red de llamadas de emergencia dentro de un país determinado. Hay dos soluciones disponibles:

- Proveedores de servicios de enrutamiento de emergencia (solo para Estados Unidos) 
- Aplicaciones de puerta de enlace de número de identificación de ubicación de emergencia (ELIN)

#### <a name="emergency-routing-service-providers"></a>Proveedores de servicios de enrutamiento de emergencia

En los Estados Unidos, hay numerosos proveedores de servicios de enrutamiento de emergencia certificados (ERSPs) que pueden enrutar automáticamente las llamadas de emergencia basándose en la ubicación de la persona que llama.

- Si un proveedor de servicios de enrutamiento de emergencia se integra en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación de adquisición dinámica se dirigirán automáticamente al punto de respuesta de seguridad pública (PSAP) que atiende esa ubicación.

-  Para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución adecuado, deberás hacer llamadas de emergencia sin una ubicación de adquisición dinámica

Para obtener más información, consulte [controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-elin-applications"></a>Aplicaciones de número de identificación de ubicación de emergencia (ELIN)

Los controladores de borde de sesión (SBCs) pueden incluir aplicaciones de número de identificación de ubicación de emergencia (ELIN). Si una aplicación de ELIN de SBC se integra en una implementación de enrutamiento directo, debe configurar las direcciones de emergencia y los números de teléfono asociados en la aplicación de ELIN y, a continuación, cargar los registros de ELIN en la base de datos de llamadas de emergencia en la PSTN correspondiente.  Las ubicaciones de emergencia de Teams con un identificador de ELIN deben coincidir con las de la aplicación ELIN.

Cuando una llamada de emergencia con un lugar adquirido dinámicamente se dirige al SBC correspondiente, la aplicación ELIN:

- Analiza la ubicación de emergencia de la persona que llama.
- Coincide con la ubicación de un registro ELIN.
- Sustituye el número de la persona que llama de emergencia por el número de teléfono de la ELIN.
- Enruta la llamada al PSAP que atiende a esa ubicación y, a continuación, los distribuidores obtienen la ubicación del registro de ELIN cargado.

Al recibir una llamada al número de emergencia, la aplicación de ELIN hará la sustitución de números que se llama invertida a la de la persona que llama de emergencia original. 

Para obtener más información, consulte [controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notificación del centro de seguridad

La notificación del servicio de seguridad está disponible con los planes de llamadas de Microsoft y el enrutamiento directo del sistema telefónico.

Usted usa una política de llamadas de emergencia de Teams (TeamsEmergencyCallingPolicy) para configurar quién debe recibir una notificación durante una llamada de emergencia y cómo se la notificará: solo chat, Conferencia en conferencia y silenciada, o en conferencia y silenciado, pero con la capacidad de reactivar el audio.  También puede especificar un número de RTC externo de un usuario o un grupo al que llamar y unirse a la llamada de emergencia. 

Se puede conceder una directiva de llamadas de emergencia a una cuenta de usuario de Teams, a un sitio de red o a ambas.  Cuando un cliente de equipo inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red donde se encuentra el cliente:

- Si hay una directiva de llamadas de emergencia asociada con un sitio de red, se usa la Directiva del sitio para configurar la notificación del servicio de seguridad.

- Si no hay ninguna directiva de llamadas de emergencia asociada al sitio, o si el cliente está conectado a un sitio no definido, se usa la Directiva de llamadas de emergencia asociada a la cuenta de usuario para configurar la notificación del escritorio de seguridad.  

- Si el cliente de Teams no puede obtener una directiva de llamadas de emergencia, el usuario no está habilitado para recibir notificaciones sobre el servicio de seguridad.

Durante una llamada de emergencia, un servicio de seguridad se une a la llamada y la experiencia del usuario del escritorio se controla en función de la política de llamadas de emergencia de Teams. Una conversación grupal se inicia con cada miembro del centro de seguridad y la ubicación de la persona que llama de emergencia se comparte a través de una notificación de mensaje importante.  Si una opción de conferencia está configurada como parte de la Directiva, también se llamará a cada usuario del escritorio de seguridad como parte de la Conferencia.

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar las directivas de enrutamiento de llamadas de emergencia](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
