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

En este artículo se describen los conceptos que debe conocer para administrar las llamadas de emergencia, como información sobre las direcciones de emergencia, las direcciones de emergencia dinámicas y el enrutamiento &mdash; de llamadas de emergencia. En este artículo se usa la terminología siguiente:

- **Dirección de** emergencia: dirección civil, dirección física o postal de un &mdash; domicilio social de su organización.

  Por ejemplo, la dirección  *12345 North Main Street, Redmond, WA 98052* se usa para enrutar las llamadas de emergencia a las autoridades de emergencia correspondientes y para ayudar a localizar al autor de la llamada.

- **Lugar:** normalmente un piso, edificio, ala o número de oficina. El lugar está asociado con una dirección de emergencia para proporcionar una ubicación más exacta dentro de un edificio. Puede tener un número ilimitado de lugares asociados con una dirección de emergencia. Por ejemplo, si su organización tiene varios edificios, es posible que desee incluir información sobre el lugar para cada edificio y para cada planta dentro de cada edificio.  

- **Ubicación de** emergencia: una ubicación es una dirección civil &mdash; con un lugar opcional. Si su empresa tiene más de una ubicación física, es probable que necesite más de una ubicación de emergencia. 

  Al crear una dirección de emergencia, se crea automáticamente un Id. de ubicación única para esta dirección.  Si agrega un lugar a una dirección de emergencia, por ejemplo, si agrega un piso a una dirección del edificio, se creará un Id. de ubicación para la combinación de la dirección de emergencia y &mdash; &mdash; el lugar.  En este ejemplo, habrá dos direcciones postales: una para la dirección civil; uno para la dirección civil unida y el lugar asociado.

  Al asignar una ubicación de emergencia a un usuario o sitio, es el Id. de ubicación único el que está asociado con el usuario o sitio.

- **Dirección registrada:** una dirección de emergencia que se asigna a cada usuario del plan de llamadas; a veces se denomina dirección de emergencia estática o dirección de registro.  (Las direcciones registradas no se aplican a los usuarios de enrutamiento directo).

Puede crear direcciones de emergencia para los usuarios del plan de llamadas mediante el Centro de administración de Teams.  

>[!Note]
>Hay algunas diferencias en cómo se administran las llamadas de emergencia dependiendo de si usa planes de llamadas de sistema telefónico o de enrutamiento directo de sistema telefónico para su conectividad con RTC. Estas consideraciones se describen a lo largo de este artículo.

## <a name="emergency-address-validation"></a>Validación de direcciones de emergencia

Para asignar una dirección de emergencia a un usuario o a un identificador de red, debe asegurarse de que la dirección de emergencia se marque como "validada".  La validación de dirección garantiza que la dirección es legítima y que no se puede modificar una vez asignada. 

Si define una dirección de emergencia mediante la característica de búsqueda de mapas de direcciones en el Centro de administración de Teams, la dirección se marcará automáticamente como validada. No puede modificar una dirección de emergencia validada. Por lo tanto, si cambia el formato o la representación de la dirección, debe crear una nueva dirección con el formato actualizado.


## <a name="emergency-address-geo-codes"></a>Códigos geográficos de dirección de emergencia

Cada dirección de emergencia puede tener un código geográfico (latitud y longitud) asociado con ella. Estos códigos geográficos se usan en algunos países para ayudar a enrutar llamadas de emergencia con ubicaciones dinámicas. 

Si define una dirección de emergencia mediante la característica de búsqueda de mapas de direcciones en el Centro de administración de Teams, el código geográfico se asocia automáticamente a una dirección de emergencia. También puede asociar códigos geográficos a una dirección si define la dirección mediante PowerShell. Sin embargo, Microsoft recomienda crear direcciones de emergencia para llamar al plan mediante la característica de búsqueda de mapas en el Centro de administración de Teams, que garantiza que las direcciones tengan formato, se validan y tengan los códigos geográficos adecuados.  

>[!Important]
>Para asignar una ubicación de emergencia a un identificador de red para las llamadas de emergencia dinámicas, la dirección de emergencia debe contener un código geográfico adecuado.


## <a name="considerations-for-calling-plans"></a>Consideraciones para planes de llamadas

Para saber si los planes de llamadas están disponibles en su área, consulte la disponibilidad del país y [la región para los planes de llamadas.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


### <a name="emergency-call-enablement"></a>Habilitación de llamadas de emergencia

Cada usuario del plan de llamadas se habilita automáticamente para las llamadas de emergencia y debe tener una dirección de emergencia registrada asociada con su número de teléfono asignado. 

Cuando la ubicación debe asociarse al número de teléfono depende del país o la región:

- En los Estados Unidos y Canadá, por ejemplo, se requiere una ubicación de emergencia cuando se asigna un número a un usuario.

- En otros países (como en Europa, Oriente Medio y África (EMEA), se requiere una ubicación de emergencia cuando se obtiene el número de teléfono de Microsoft 365 u Office 365, o cuando se transfiere desde otro proveedor de servicios u operador.

### <a name="dynamic-emergency-calling"></a>Llamadas de emergencia dinámicas

Las llamadas de emergencia dinámicas para los planes de llamadas de Microsoft proporcionan la capacidad de configurar y enrutar llamadas de emergencia en función de la ubicación actual del cliente de Teams. La capacidad de enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado o de notificar al personal del servicio de seguridad varía según el país de uso del usuario de Teams.  

Para los usuarios del plan de llamadas, solo se admite en Estados Unidos una ubicación dinámica para el enrutamiento de llamadas de emergencia. (Para obtener información sobre las llamadas de emergencia dinámicas y el enrutamiento directo, vea [Consideraciones para el enrutamiento directo.](#considerations-for-direct-routing)

- Si un cliente de Teams para un usuario de un plan de llamadas de Estados Unidos adquiere de forma dinámica una dirección de emergencia dentro de los Estados Unidos, esa dirección se usa para el enrutamiento de emergencia en lugar de la dirección registrada, y la llamada se enruta automáticamente al PSAP en el área de servicio de la dirección.

- Si un cliente de Teams para un usuario del plan de llamadas de Estados Unidos no adquiere de forma dinámica una dirección de emergencia dentro de los Estados Unidos, la dirección de emergencia registrada se usa para ayudar a pantalla y enrutar la llamada. Sin embargo, la llamada se pantallará para determinar si se necesita una dirección actualizada antes de conectar el autor de la llamada al PSAP adecuado.

En los Estados Unidos, debe configurar la dirección civil que forma parte de las ubicaciones de emergencia que están asignadas a identificadores de red e incluir los códigos &mdash; geográficos asociados. Para obtener más información, vea [Planear y configurar llamadas de emergencia dinámicas.](configure-dynamic-emergency-calling.md)


### <a name="emergency-call-routing"></a>Enrutamiento de llamadas de emergencia

Cuando un usuario del plan de llamadas de Teams marca un número de emergencia, el modo en que la llamada se enruta al PSAP depende de lo siguiente:

- Si el cliente de Teams determina dinámicamente la dirección de emergencia.

- Si la dirección de emergencia es la dirección registrada asociada al número de teléfono del usuario.

- La red de llamadas de emergencia de ese país.

  **En los Estados Unidos:**

  - Si un cliente de Teams se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente se enruta automáticamente al PSAP que sirve para esa ubicación geográfica. 

  - Si un cliente de Teams no se encuentra en una ubicación de emergencia dinámica definida por el inquilino, un centro de llamadas nacional mida las llamadas de emergencia de ese cliente para determinar la ubicación del autor de la llamada antes de transferirla al PSAP que sirve a esa ubicación geográfica.

  - Si el autor de la llamada de emergencia no puede actualizar su ubicación de emergencia en el centro de filtrado, la llamada se transferirá al PSAP que cumple con la dirección registrada del autor de la llamada.

  **En Canadá, Irlanda** y el Reino Unido, primero se pantallan las llamadas de emergencia para determinar la ubicación actual del usuario antes de conectar la llamada al centro de emergencias apropiado. 

  **En Francia, Alemania** y España, las llamadas de emergencia se enrutadas directamente al PSAP que sirve a la dirección de emergencia asociada con el número, independientemente de la ubicación del autor de la llamada.

  **En los Países Bajos,** las llamadas de emergencia se enrutadas directamente al PSAP para el código de área local del número, independientemente de la ubicación del autor de la llamada.

  **En Australia,** el operador asociado configura y enruta las direcciones de emergencia.

  **En Japón,** no se admiten llamadas de emergencia.


Para obtener más información, vea:

- [Planes de llamadas](calling-plan-landing-page.md)

- [Diferentes tipos de números de teléfono que se usan para planes de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Consideraciones para el enrutamiento directo

Si los planes de llamadas no están disponibles en su área o si desea mantener su operador actual, considere [el enrutamiento directo.](direct-routing-landing-page.md) Para obtener más información, vea [Configurar el enrutamiento directo y](direct-routing-configure.md) administrar las directivas de enrutamiento de llamadas de [emergencia.](manage-emergency-call-routing-policies.md)

### <a name="emergency-call-enablement-and-configuration"></a>Configuración y habilitación de llamadas de emergencia

Debe definir directivas de llamadas de emergencia para los usuarios de enrutamiento directo mediante una directiva de enrutamiento de llamadas de emergencia de Teams (TeamsEmergencyCallRoutingPolicy) para definir números de emergencia y su destino de enrutamiento asociado. (Tenga en cuenta que las ubicaciones de emergencia registradas no son compatibles con los usuarios de enrutamiento directo).

Puede asignar una directiva de enrutamiento de llamadas de emergencia a una cuenta de usuario de enrutamiento directo de Teams, a un sitio de red o a ambos. Cuando un cliente de Teams inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red en el que se encuentra el cliente de la siguiente manera:

- Si una directiva de enrutamiento de llamadas de emergencia está asociada al sitio, la directiva de sitio se utiliza para configurar las llamadas de emergencia.

- Si no hay ninguna directiva de enrutamiento de llamada de emergencia asociada al sitio, o si el cliente está conectado a un sitio no definido, se utiliza la directiva de enrutamiento de llamada de emergencia asociada a la cuenta de usuario para configurar las llamadas de emergencia. 

- Si el cliente de Teams no puede obtener una directiva de enrutamiento de llamadas de emergencia, el usuario no está habilitado para las llamadas de emergencia.

### <a name="dynamic-emergency-calling"></a>Llamadas de emergencia dinámicas

Los clientes de Teams para los usuarios de enrutamiento directo pueden adquirir una dirección de emergencia dinámica que se puede usar para enrutar dinámicamente las llamadas en función de la ubicación del autor de la llamada. Para obtener más información, vea [Configurar llamadas de emergencia dinámicas.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing"></a>Enrutamiento de llamadas de emergencia

La directiva de enrutamiento de llamadas de emergencia hace referencia a un uso de RTC en línea, que debe tener la configuración de enrutamiento directo adecuada para enrutar correctamente las llamadas de emergencia a las puertas de enlace RTC correspondientes. En particular, debe asegurarse de que hay un OnlineVoiceRoute para la cadena de marcado de emergencia. Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md) 

(Nota: Los clientes de Teams anteponen el signo "+" delante de los números de emergencia de forma similar a como lo hace el cliente de Skype Empresarial; es decir, +911. Este comportamiento se modificará en los próximos meses para que las llamadas de emergencia de Teams ya no envíen un "+" antes del número; es decir, 911).

La capacidad para enrutar dinámicamente las llamadas de emergencia para los usuarios de enrutamiento directo varía según la red de llamadas de emergencia de un país determinado. Hay dos soluciones disponibles:

- Proveedores de servicios de enrutamiento de emergencia (solo para Estados Unidos) 
- Aplicaciones de puerta de enlace de número de identificación de ubicación de emergencia (ELIN)

#### <a name="emergency-routing-service-providers"></a>Proveedores de servicios de enrutamiento de emergencia

En los Estados Unidos, hay numerosos proveedores de servicios de enrutamiento de emergencia (ERSP) certificados que pueden enrutar automáticamente las llamadas de emergencia en función de la ubicación del autor de la llamada.

- Si se integra un proveedor de servicios de enrutamiento de emergencia en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación adquirida dinámicamente se enruta automáticamente al punto de respuesta de seguridad pública (PSAP) que sirve a esa ubicación.

-  Las llamadas de emergencia sin una ubicación adquirida dinámicamente se pantallan primero para determinar la ubicación actual del usuario antes de conectar la llamada al centro de emergencias adecuado según la ubicación actualizada.

Para obtener más información, vea [Controladores de borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)


#### <a name="emergency-location-identification-number-elin-applications"></a>Aplicaciones de número de identificación de ubicación de emergencia (ELIN)

Los controladores de borde de sesión pueden incluir aplicaciones de número de identificación de ubicación de emergencia (ELIN). Si una aplicación de ELIN SBC está integrada en una implementación de enrutamiento directo, debe configurar las direcciones de emergencia y los números de teléfono asociados en la aplicación ELIN y, a continuación, cargar los registros ELIN a la base de datos de llamadas de emergencia en la RTC correspondiente.  Las ubicaciones de emergencia de Teams con un identificador ELIN deben coincidir con las de la aplicación ELIN.

Cuando una llamada de emergencia con una ubicación adquirida dinámicamente se enruta al SBC adecuado, la aplicación ELIN:

- Analiza la ubicación de emergencia del autor de la llamada.
- Hace que la ubicación coincida con un registro ELIN.
- Sustituye el número del autor de la llamada de emergencia por el número de teléfono de ELIN.
- Enruta la llamada al PSAP que sirve a esa ubicación y, a continuación, los distribuidores obtienen la ubicación del registro ELIN cargado.

Tras una llamada al número de emergencia, la aplicación ELIN realizará la sustitución inversa del número llamado número por el del autor de la llamada de emergencia original. 

Para obtener más información, vea [Controladores de borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)


## <a name="security-desk-notification"></a>Notificación del servicio de seguridad

La notificación de servicio de seguridad está disponible tanto con los planes de llamadas de Microsoft como con el enrutamiento directo de sistema telefónico.

Usa una directiva de llamadas de emergencia de Teams (TeamsEmergencyCallingPolicy) para configurar a quién se le notificará durante una llamada de emergencia y cómo se le notifica: solo chatear, en conferencias en las que se ha silenciado o en conferencia, o bien en conferencia con otros usuarios, pero con la capacidad de activar el sonido.  También puede especificar un número RTC externo de un usuario o grupo para llamar y unirse a la llamada de emergencia. 

Se puede otorgar una directiva de llamadas de emergencia a una cuenta de usuario de Teams, asignada a un sitio de red o a ambas.  Cuando un cliente de Teams inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red en el que se encuentra el cliente:

- Si una directiva de llamadas de emergencia está asociada a un sitio de red, la directiva de sitio se usará para configurar la notificación del servicio de seguridad.

- Si no hay ninguna directiva de llamadas de emergencia asociada al sitio o si el cliente está conectado a un sitio no definido, se usará la directiva de llamadas de emergencia asociada a la cuenta de usuario para configurar la notificación del servicio de seguridad.  

- Si el cliente de Teams no puede obtener una directiva de llamadas de emergencia, el usuario no está habilitado para recibir una notificación del servicio de seguridad.

Durante una llamada de emergencia, el servicio de seguridad se convierte en conferencia en la llamada y la experiencia del usuario del servicio de seguridad se controla en función de la directiva de llamadas de emergencia de Teams. Se inicia un chat grupal con cada miembro del servicio de seguridad y se comparte la ubicación del autor de la llamada de emergencia mediante una notificación de mensaje importante.  Si se configura una opción de conferencia como parte de la directiva, se llamará además a cada usuario del servicio de seguridad como parte de la conferencia.

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia ](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
