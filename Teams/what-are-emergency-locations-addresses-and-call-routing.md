---
title: Planear y administrar llamadas de emergencia
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
- m365initiative-voice
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
description: Obtenga información sobre las llamadas de emergencia, incluida la información sobre las direcciones de emergencia, el enrutamiento de llamadas de emergencia y las llamadas de emergencia dinámicas.
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031606"
---
# <a name="manage-emergency-calling"></a>Administrar llamadas de emergencia

En este artículo se describen conceptos que debe conocer para administrar las llamadas de emergencia, que incluye información sobre direcciones de emergencia, direcciones de emergencia dinámicas y enrutamiento de &mdash; llamadas de emergencia. En este artículo se usa la terminología siguiente:

- **Dirección de emergencia:** una dirección civil que es la dirección física o de calle &mdash; de un lugar de negocios para su organización.

  Por ejemplo, la dirección  *12345 North Main Street, Redmond, WA 98052* se usa para enrutar llamadas de emergencia a las autoridades de envío adecuadas y para ayudar a localizar al autor de la llamada de emergencia.

- **Lugar:** normalmente un número de piso, edificio, ala u oficina. Place está asociado con una dirección de emergencia para dar una ubicación más exacta dentro de un edificio. Puede tener un número ilimitado de lugares asociados con una dirección de emergencia. Por ejemplo, si su organización tiene varios edificios, es posible que desee incluir información de colocación para cada edificio y para cada planta dentro de cada edificio.  

- **Ubicación de emergencia:** una ubicación es una dirección civil &mdash; con un lugar opcional. Si su empresa tiene más de una ubicación física, es probable que necesite más de una ubicación de emergencia. 

  Al crear una dirección de emergencia, se crea automáticamente un id. de ubicación único para esta dirección.  Si agrega un lugar a una dirección de emergencia, por ejemplo, si agrega un piso a una dirección de edificio, se creará un id. de ubicación para la combinación de la dirección de emergencia &mdash; &mdash; y el lugar.  En este ejemplo, habrá dos direcciones de ubicación: una para la dirección civil; una para la dirección civil unida y el lugar asociado.

  Cuando asigna una ubicación de emergencia a un usuario o sitio, es este id. de ubicación único que está asociado con el usuario o el sitio.

- **Dirección registrada:** una dirección de emergencia asignada a cada usuario del plan de llamadas; a veces se conoce como una dirección de emergencia estática o una dirección de registro.  (Las direcciones registradas no se aplican a los usuarios de Enrutamiento directo).

Puede crear direcciones de emergencia para los usuarios del plan de llamadas mediante el Teams de administración.  

>[!Note]
>Hay algunas diferencias en la forma de administrar las llamadas de emergencia dependiendo de si usa planes de llamadas Sistema telefónico o Sistema telefónico enrutamiento directo para su conectividad RTC. Estas consideraciones se describen a lo largo de este artículo.

## <a name="emergency-address-validation"></a>Validación de direcciones de emergencia

Para asignar una dirección de emergencia a un usuario o a un identificador de red, debe asegurarse de que la dirección de emergencia está marcada como "validada".  La validación de direcciones garantiza que la dirección es legítima y que no se puede modificar después de asignarla. 

Si define una dirección de emergencia mediante la característica de búsqueda de asignación de direcciones en el centro de administración de Teams, la dirección se marcará automáticamente como validada. No puede modificar una dirección de emergencia validada. Por lo tanto, si cambia el formato o la representación de la dirección, debe crear una nueva dirección con el formato actualizado.


## <a name="emergency-address-geo-codes"></a>Códigos geográficos de direcciones de emergencia

Cada dirección de emergencia puede tener asociado un código geográfico (latitud y longitud). Estos códigos geográficos se usan en algunos países para ayudar a enrutar llamadas de emergencia con ubicaciones dinámicas. 

Si define una dirección de emergencia mediante la característica de búsqueda de mapa de direcciones en el centro de administración de Teams, el código geográfico se asocia automáticamente con una dirección de emergencia. También puede asociar códigos geográficos a una dirección si define la dirección mediante PowerShell. Sin embargo, Microsoft recomienda crear direcciones de emergencia para Teams plan de llamadas mediante la característica de búsqueda de mapas en un centro de administración, que garantizará que las direcciones tengan formato, validación y los códigos geográficos adecuados.  

>[!Important]
>Para asignar una ubicación de emergencia a un identificador de red para llamadas de emergencia dinámicas, la dirección de emergencia debe contener un código geográfico adecuado.


## <a name="considerations-for-calling-plans"></a>Consideraciones sobre planes de llamadas

Para saber si los planes de llamadas están disponibles en su área, vea Disponibilidad de país y [región para planes de llamadas.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


### <a name="emergency-call-enablement"></a>Habilitación de llamadas de emergencia

Cada usuario del Plan de llamadas se habilita automáticamente para las llamadas de emergencia y es necesario que tenga una dirección de emergencia registrada asociada con su número de teléfono asignado. 

Cuando la ubicación debe estar asociada al número de teléfono depende del país o región:

- En Estados Unidos y Canadá, por ejemplo, se requiere una ubicación de emergencia cuando se asigna un número a un usuario.

- Para otros países ,como Europa, Oriente Medio y África (EMEA), se requiere una ubicación de emergencia cuando recibe el número de teléfono de Microsoft 365 o Office 365, o cuando se transfiere desde otro proveedor de servicios u operador.

### <a name="dynamic-emergency-calling"></a>Llamadas de emergencia dinámicas

Las llamadas de emergencia dinámicas para planes de llamadas de Microsoft ofrecen la capacidad de configurar y enrutar llamadas de emergencia en función de la ubicación actual del Teams cliente. La capacidad de enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado o de notificar al personal del servicio de seguridad varía según el país de uso del Teams usuario.  

Para los usuarios del Plan de llamadas, la ubicación dinámica para el enrutamiento de llamadas de emergencia solo es compatible en Los Estados Unidos de la siguiente manera. (Para obtener información sobre las llamadas de emergencia dinámicas y el enrutamiento directo, vea [Consideraciones para el enrutamiento directo.](#considerations-for-direct-routing)

- Si un cliente de Teams para un usuario del Plan de llamadas de Estados Unidos adquiere dinámicamente una dirección de emergencia dentro de los Estados Unidos, esa dirección se usa para enrutamiento de emergencia en lugar de la dirección registrada y la llamada se enruta automáticamente al PSAP en el área de servicio de la dirección.

- Si un cliente de Teams para un usuario del Plan de llamadas de Estados Unidos no adquiere dinámicamente una dirección de emergencia dentro de los Estados Unidos, la dirección de emergencia registrada se usa para ayudar a pantalla y enrutar la llamada. Sin embargo, la llamada se mostrará en pantalla para determinar si se necesita una dirección actualizada antes de conectar al autor de la llamada al PSAP correspondiente.

En Estados Unidos, debe configurar la dirección civil que forma parte de las ubicaciones de emergencia asignadas a identificadores de red e incluir los &mdash; códigos geográficos asociados. Para obtener más información, vea Planear y configurar llamadas de [emergencia dinámicas.](configure-dynamic-emergency-calling.md)


### <a name="emergency-call-routing"></a>Enrutamiento de llamadas de emergencia

Cuando un Teams del Plan de llamadas marca un número de emergencia, la forma en que la llamada se enruta al PSAP depende de lo siguiente:

- Si la dirección de emergencia la determina dinámicamente Teams cliente.

- Si la dirección de emergencia es la dirección registrada asociada al número de teléfono del usuario.

- La red de llamadas de emergencia de ese país.

  **En Estados Unidos:**

  - Si un cliente Teams se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente se enruta automáticamente al PSAP que sirve a esa ubicación geográfica. 

  - Si un cliente de Teams no se encuentra en una ubicación de emergencia dinámica definida por el inquilino, un centro de llamadas nacional proyecta las llamadas de emergencia de ese cliente para determinar la ubicación del autor de la llamada antes de transferir la llamada al PSAP que sirve a esa ubicación geográfica.

  - Si un autor de la llamada de emergencia no puede actualizar su ubicación de emergencia al centro de detección, la llamada se transferirá al PSAP que sirve la dirección registrada del autor de la llamada.

  **En Canadá, Irlanda** y el Reino Unido, las llamadas de emergencia se proyectan primero para determinar la ubicación actual del usuario antes de conectar la llamada al centro de envío adecuado. 

  **En Francia, Alemania** y España, las llamadas de emergencia se enruta directamente al PSAP que sirve la dirección de emergencia asociada con el número, independientemente de la ubicación del autor de la llamada.

  **En los Países Bajos,** las llamadas de emergencia se enruta directamente al PSAP para obtener el código de área local del número, independientemente de la ubicación del autor de la llamada.

  **En Australia,** las direcciones de emergencia están configuradas y enrutadas por el partner transportista.

  **En Japón,** las llamadas de emergencia no son compatibles.


Para obtener más información, vea:

- [Planes de llamadas](calling-plan-landing-page.md)

- [Diferentes tipos de números de teléfono que se usan para planes de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Consideraciones para enrutamiento directo

Si los planes de llamadas no están disponibles en su área o desea mantener su operador existente, considere [Enrutamiento directo.](direct-routing-landing-page.md) Para obtener más información, vea [Configurar enrutamiento directo](direct-routing-configure.md) y administrar directivas de enrutamiento de llamadas de [emergencia.](manage-emergency-call-routing-policies.md)

### <a name="emergency-call-enablement-and-configuration"></a>Habilitación y configuración de llamadas de emergencia

Debe definir directivas de llamadas de emergencia para los usuarios de enrutamiento directo mediante una directiva de enrutamiento de llamadas de emergencia de Teams (TeamsEmergencyCallRoutingPolicy) para definir los números de emergencia y su destino de enrutamiento asociado. (Tenga en cuenta que las ubicaciones de emergencia registradas no son compatibles con los usuarios de Enrutamiento directo).

Puede asignar una directiva de enrutamiento de llamadas de emergencia a Teams cuenta de usuario de Enrutamiento directo, un sitio de red o ambos. Cuando un Teams inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red donde se encuentra el cliente de la siguiente manera:

- Si una directiva de enrutamiento de llamadas de emergencia está asociada al sitio, la directiva de sitio se usa para configurar las llamadas de emergencia.

- Si no hay ninguna directiva de enrutamiento de llamadas de emergencia asociada al sitio o si el cliente está conectado en un sitio no definido, la directiva de enrutamiento de llamadas de emergencia asociada a la cuenta de usuario se usa para configurar las llamadas de emergencia. 

- Si el Teams no puede obtener una directiva de enrutamiento de llamadas de emergencia, el usuario no está habilitado para las llamadas de emergencia.

### <a name="dynamic-emergency-calling"></a>Llamadas de emergencia dinámicas

Teams para los usuarios de Enrutamiento directo pueden adquirir una dirección de emergencia dinámica, que se puede usar para enrutar llamadas dinámicamente en función de la ubicación del autor de la llamada. Para obtener más información, vea [Configurar llamadas de emergencia dinámicas.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing"></a>Enrutamiento de llamadas de emergencia

La directiva de enrutamiento de llamadas de emergencia hace referencia a un uso rtc en línea, que debe tener la configuración de enrutamiento directo adecuada para enrutar correctamente las llamadas de emergencia a las puertas de enlace RTC adecuadas. En particular, debe asegurarse de que hay un OnlineVoiceRoute para la cadena de marcado de emergencia. Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md) 

(Nota: Teams clientes anteponen el signo "+" delante de los números de emergencia de forma similar a Skype Empresarial cliente; es decir, +911. Este comportamiento se modificará en los próximos meses para que Teams llamadas de emergencia ya no envíen un "+" anterior al número; es decir, 911).

La capacidad de enrutar llamadas de emergencia de forma dinámica para los usuarios de Enrutamiento directo varía según la red de llamadas de emergencia de un país determinado. Hay dos soluciones disponibles:

- Proveedores de servicios de enrutamiento de emergencia (solo ee. UU.) 
- Aplicaciones de puerta de enlace de número de identificación de ubicación de emergencia (ELIN)

#### <a name="emergency-routing-service-providers"></a>Proveedores de servicios de enrutamiento de emergencia

En los Estados Unidos, hay numerosos proveedores de servicios de enrutamiento de emergencia (ERSP) certificados que pueden enrutar automáticamente las llamadas de emergencia en función de la ubicación del autor de la llamada.

- Si un proveedor de servicios de enrutamiento de emergencia está integrado en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación adquirida dinámicamente se enruta automáticamente al Punto de respuesta de seguridad pública (PSAP) que sirve a esa ubicación.

-  Las llamadas de emergencia sin una ubicación adquirida dinámicamente se primero se proyectan para determinar la ubicación actual del usuario antes de conectar la llamada al centro de envío adecuado en función de la ubicación actualizada.

Para obtener más información, vea [Controladores de borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)


#### <a name="emergency-location-identification-number-elin-applications"></a>Aplicaciones de número de identificación de ubicación de emergencia (ELIN)

Los controladores de borde de sesión (SBC) pueden incluir aplicaciones de número de identificación de ubicación de emergencia (ELIN). Si una aplicación ELIN de SBC está integrada en una implementación de enrutamiento directo, debe configurar las direcciones de emergencia y los números de teléfono asociados en la aplicación ELIN y, a continuación, cargar los registros ELIN en la base de datos de llamadas de emergencia en la RTC correspondiente.  Teams de emergencia con un identificador ELIN deben coincidir con las de la aplicación ELIN.

Cuando una llamada de emergencia con una ubicación adquirida dinámicamente se enruta al SBC adecuado, la aplicación ELIN:

- Analiza la ubicación de emergencia del autor de la llamada.
- Coincide la ubicación con un registro ELIN.
- Sustituye el número de llamada de emergencia por el número de teléfono ELIN.
- Enruta la llamada al PSAP que sirve esa ubicación y, a continuación, los despachadores obtienen la ubicación del registro ELIN cargado.

Tras una llamada de nuevo al número de emergencia, la aplicación ELIN realizará la sustitución de número llamada inversa por la del autor de la llamada de emergencia original. 

Para obtener más información, vea [Controladores de borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)


## <a name="security-desk-notification"></a>Notificación de escritorio de seguridad

La notificación de escritorio de seguridad está disponible con planes de llamadas de Microsoft y Sistema telefónico enrutamiento directo.

Use una directiva de llamadas de emergencia de Teams (TeamsEmergencyCallingPolicy) para configurar a quién se le debe notificar durante una llamada de emergencia y cómo se les notifica: solo chatear, conferenciar y silenciar, o conferenciar en y silenciar, pero con la capacidad de activar lamute.  También puede especificar un número RTC externo de un usuario o grupo para llamar y unirse a la llamada de emergencia. 

Se puede conceder una directiva de llamadas de emergencia a Teams cuenta de usuario, asignada a un sitio de red o a ambas.  Cuando un Teams inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red donde se encuentra el cliente:

- Si una directiva de llamadas de emergencia está asociada a un sitio de red, la directiva de sitio se usa para configurar la notificación de escritorio de seguridad.

- Si no hay ninguna directiva de llamadas de emergencia asociada con el sitio o si el cliente está conectado en un sitio no definido, la directiva de llamadas de emergencia asociada a la cuenta de usuario se usa para configurar la notificación de escritorio de seguridad.  

- Si el Teams no puede obtener una directiva de llamadas de emergencia, el usuario no está habilitado para la notificación de escritorio de seguridad.

Durante una llamada de emergencia, se realiza una conferencia en un escritorio de seguridad en la llamada y la experiencia del usuario del escritorio de seguridad se controla en función de la Teams de llamadas de emergencia. Se inicia un chat grupal con cada miembro del escritorio de seguridad y la ubicación del autor de la llamada de emergencia se comparte a través de una notificación de mensaje importante.  Si se configura una opción de conferencia como parte de la directiva, se llamará además a cada usuario del escritorio de seguridad como parte de la conferencia.

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia ](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
