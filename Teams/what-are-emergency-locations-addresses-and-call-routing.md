---
title: Planear y administrar las llamadas de emergencia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Obtenga información sobre las llamadas de emergencia, incluida información sobre las direcciones de emergencia, el enrutamiento de llamadas de emergencia y las llamadas de emergencia dinámicas.
ms.openlocfilehash: f059f55281df2925511b85941fefbb675d781852
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125455"
---
# <a name="manage-emergency-calling"></a>Administrar las llamadas de emergencia

En este artículo se describen los conceptos que debe conocer para administrar las llamadas&mdash; de emergencia e incluye información sobre las direcciones de emergencia, las direcciones dinámicas de emergencia y el enrutamiento de llamadas de emergencia. En este artículo se usan los siguientes términos:

- **Dirección de emergencia** : dirección civilla dirección&mdash; física o postal de un domicilio comercial de la organización.

  Por ejemplo, la dirección *12345 North Main Street, Redmond, WA 98052* se usa para redirigir las llamadas de emergencia a las autoridades de emergencia adecuadas y para ayudar a localizar al autor de la llamada de emergencia.

- **Lugar** : suele ser un piso, un edificio, un ala o un número de oficina. El lugar está asociado con una dirección de emergencia para proporcionar una ubicación más exacta dentro de un edificio. Puede tener un número ilimitado de lugares asociados a una dirección de emergencia. Por ejemplo, si su organización tiene varios edificios, es posible que desee incluir información de lugares para cada edificio y cada planta dentro de cada edificio.  

- **Ubicación de emergencia** : una ubicación es una dirección&mdash; civil con un lugar opcional. Si su empresa tiene más de una ubicación física, es probable que necesite más de una ubicación de emergencia. 

  Al crear una dirección de emergencia, se crea automáticamente un id. de ubicación único para esta dirección. Si agrega un lugar a una dirección&mdash; de emergencia por ejemplo, si agrega un piso a una dirección&mdash; de edificio, se crea un id. de ubicación para la combinación de la dirección de emergencia y el lugar.  En este ejemplo, habrá dos identificadores de ubicación: uno para la dirección civil; para la dirección civil asociada y el lugar asociado.

  Al asignar una ubicación de emergencia a un usuario o sitio, este id. de ubicación único está asociado al usuario o sitio.

- **Dirección registrada** : una dirección de emergencia que se asigna a cada usuario. A veces, una dirección registrada se denomina dirección de emergencia estática o dirección de registro. (Actualmente, las direcciones registradas no son compatibles con el enrutamiento directo. Vuelve pronto para ver si hay actualizaciones).

>[!Note]
>Hay algunas diferencias en la forma de administrar las llamadas de emergencia dependiendo de si usa los planes de llamadas de Microsoft, Conexión con operador o enrutamiento directo para su [conectividad con RTC](pstn-connectivity.md). Estas consideraciones se describen en este artículo.

## <a name="emergency-address-validation"></a>Validación de dirección de emergencia

Para asignar una dirección de emergencia a un usuario o a un identificador de red, debe asegurarse de que la dirección de emergencia esté marcada como "validada". La validación de dirección garantiza que la dirección sea legítima y que no se pueda modificar después de asignarla. 

Si define una dirección de emergencia mediante la característica de búsqueda de la asignación de direcciones en el centro de administración de Teams, la dirección se marcará automáticamente como validada. Dado que no puede modificar una dirección&mdash; de emergencia validada si cambia el formato o la representación de la dirección, debe crear una nueva dirección con el formato actualizado.


## <a name="emergency-address-geo-codes"></a>Códigos geográficos de direcciones de emergencia

Cada dirección de emergencia puede tener asociado un código geográfico (latitud y longitud). Estos códigos geográficos se usan en algunos países para ayudar a enrutar llamadas de emergencia con ubicaciones dinámicas. 

Si define una dirección de emergencia mediante la característica de búsqueda del mapa de direcciones del centro de administración de Teams, el código geográfico se asocia automáticamente a una dirección de emergencia. También puede asociar códigos geográficos a una dirección si define la dirección mediante PowerShell. 

Microsoft recomienda crear direcciones de emergencia mediante la característica de búsqueda de mapas en Teams centro de administración, que garantizará que las direcciones tengan formato, validado y los códigos geográficos adecuados. 

>[!Important]
>Para asignar una ubicación de emergencia a un identificador de red para llamadas de emergencia dinámicas, la dirección de emergencia debe contener un código geográfico adecuado.


## <a name="considerations-for-calling-plans"></a>Consideraciones para planes de llamadas

En las siguientes secciones se describe cómo administrar las llamadas de emergencia de los usuarios del Plan de llamadas de Microsoft. Para averiguar si los planes de llamadas de Microsoft son la solución adecuada para su empresa, consulte [Opciones de conectividad con RTC](pstn-connectivity.md).


### <a name="emergency-call-enablement-for-calling-plans"></a>Habilitación de llamadas de emergencia para planes de llamadas

Cada usuario del plan de llamadas se habilita automáticamente para las llamadas de emergencia y se requiere que tenga una dirección de emergencia registrada asociada a su número de teléfono asignado. 

Cuando la ubicación está asociada al número de teléfono depende del país o la región:

- En la Estados Unidos y Canadá, por ejemplo, se requiere una ubicación de emergencia cuando se asigna un número a un usuario.

- En otros países&mdash;, como en Europa, Oriente Medio y África (EMEA),&mdash; se requiere una ubicación de emergencia cuando se obtiene el número de teléfono de Microsoft 365 o cuando se transfiere desde otro proveedor de servicios u operador.


### <a name="dynamic-emergency-calling-for-calling-plans"></a>Llamadas de emergencia dinámicas para planes de llamadas

Las llamadas de emergencia dinámicas para planes de llamadas proporcionan la capacidad de configurar y enrutar llamadas de emergencia basadas en la ubicación actual del cliente de Teams. La capacidad de realizar enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado o de notificar al personal de la mesa de seguridad varía según el país de uso del usuario de la Teams.  

La ubicación dinámica para enrutar llamadas de emergencia se admite en la Estados Unidos tal como se indica a continuación. 

- Si un cliente de Teams para un usuario del plan de llamadas Estados Unidos adquiere dinámicamente una dirección de emergencia dentro del Estados Unidos, esa dirección se usa para el enrutamiento de emergencia en lugar de la dirección registrada, y la llamada se enrutará automáticamente al PSAP en el área de servicio de la dirección.

- Si un cliente de Teams para un usuario del plan de llamadas Estados Unidos no adquiere dinámicamente una dirección de emergencia dentro de la Estados Unidos, la dirección de emergencia registrada se usa para ayudar a mostrar y enrutar la llamada. Sin embargo, la llamada se comprobará para determinar si es necesaria una dirección actualizada antes de conectar al autor de la llamada al PSAP adecuado.

La ubicación dinámica para enrutar llamadas de emergencia es compatible en Canadá igual que en la Estados Unidos, con la excepción siguiente: todas las llamadas de emergencia se realizarán en el país antes de transferirse al PSAP.

Para obtener más información, consulte [Planear y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-calling-plans"></a>Enrutamiento de llamadas de emergencia para planes de llamadas

Cuando un usuario del plan de llamadas de Teams marca un número de emergencia, la manera en que la llamada se enruta al PSAP depende de lo siguiente:

- Si el cliente de Teams determina dinámicamente la dirección de emergencia.

- Si la dirección de emergencia es la dirección registrada asociada con el número de teléfono del usuario.

- La red de llamadas de emergencia de ese país.

Por ejemplo:

**En la Estados Unidos:**

- Si un cliente de Teams se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente se enrutan automáticamente al PSAP que sirve esa ubicación geográfica.

- Si un cliente de Teams no se encuentra en una ubicación de emergencia dinámica definida por el inquilino, un centro de llamadas nacional examina las llamadas de emergencia de ese cliente para determinar la ubicación del autor de la llamada antes de transferirla al PSAP que sirve esa ubicación geográfica.

- Si un autor de la llamada de emergencia no puede actualizar su ubicación de emergencia al centro de detección, la llamada se transferirá al PSAP que sirva la dirección registrada del autor de la llamada.

**En Canadá, Irlanda y el Reino Unido**, las llamadas de emergencia se comprueban primero para determinar la ubicación actual del usuario antes de conectar la llamada al centro de emergencias adecuado.

**En Francia, Alemania y España**, las llamadas de emergencia se redirigen directamente al PSAP que sirve la dirección de emergencia asociada con el número, independientemente de la ubicación del autor de la llamada.

**En los Países Bajos**, las llamadas de emergencia se redirigen directamente al PSAP para el código de área local del número, independientemente de la ubicación del autor de la llamada.

**En Australia**, las direcciones de emergencia las configura y enruta el partner transportista.

**En Japón**, no se admiten las llamadas de emergencia.


Para obtener más información, vea:

- [Planes de llamadas](calling-plan-landing-page.md)
- [Configurar planes de llamadas](set-up-calling-plans.md)
- [Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Consideraciones para Conexión con operador

En las siguientes secciones se describe cómo administrar las llamadas de emergencia para los usuarios de Conexión con operador. Para averiguar si Conexión con operador es la solución adecuada para su empresa, consulte [Opciones de conectividad con RTC](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-operator-connect"></a>Habilitación de llamadas de emergencia para Conexión con operador

Cada usuario Conexión con operador se habilita automáticamente para las llamadas de emergencia. Las llamadas de emergencia se redirigen automáticamente al Conexión con operador operador para un número determinado.

La posibilidad de que un administrador de inquilinos establezca la dirección registrada de un usuario Conexión con operador dependerá de las capacidades asignadas al número cuando el operador las cargue en un inventario de clientes. En función de esta configuración, el administrador de inquilinos puede o no ser requeridoo&mdash; puede&mdash; establecer, modificar o eliminar la ubicación de emergencia de un usuario. 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Llamadas de emergencia dinámicas para Conexión con operador

Las llamadas de emergencia dinámicas para Conexión con operador proporcionan la capacidad de configurar y enrutar llamadas de emergencia en función de la ubicación actual del cliente de Teams. La capacidad de realizar enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado o de notificar al personal de la mesa de seguridad varía según el país de uso del usuario de la Teams. 

La ubicación dinámica para enrutar llamadas de emergencia se admite en la Estados Unidos tal como se indica a continuación. 

- Si un cliente de Teams para un usuario de Estados Unidos adquiere dinámicamente una dirección de emergencia dentro de la Estados Unidos, esa dirección se usa para el enrutamiento de emergencia en lugar de la dirección registrada, y la llamada se enrutará automáticamente al PSAP en el área de servicio de la dirección.

- Si un cliente de Teams para un usuario Estados Unidos no adquiere dinámicamente una dirección de emergencia dentro de la Estados Unidos, la dirección de emergencia registrada se usa para ayudar a pantalla y enrutar la llamada. Sin embargo, la llamada se comprobará para determinar si es necesaria una dirección actualizada antes de conectar al autor de la llamada al PSAP adecuado.

La ubicación dinámica para enrutar llamadas de emergencia es compatible en Canadá igual que en la Estados Unidos con las siguientes excepciones: todas las llamadas de emergencia se analizan a nivel nacional antes de transferirse al PSAP.

Para obtener más información, consulte [Planear y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-operator-connect"></a>Enrutamiento de llamadas de emergencia para Conexión con operador

Cuando un usuario de Teams Conexión con operador marca un número de emergencia, la manera en que la llamada se enruta al PSAP depende de lo siguiente:

- Si el cliente de Teams determina dinámicamente la dirección de emergencia.

- Si la dirección de emergencia es la dirección registrada asociada con el número de teléfono del usuario.

- La red de llamadas de emergencia de ese país.

- En el Estados Unidos y Canadá, el enrutamiento dinámico forma parte del servicio del operador. No es necesario adquirir este servicio de otro proveedor de servicios.

- Si un cliente de Teams se encuentra en una ubicación de emergencia dinámica definida por el inquilino:

   - En la Estados Unidos, las llamadas de emergencia de ese cliente se enrutan automáticamente al PSAP que sirve esa ubicación geográfica.
   - En Canadá, todas las llamadas de emergencia las realizará un centro de llamadas nacional antes de transferir la llamada al PSAP que sirva en esa ubicación geográfica.

- Si un cliente de Teams no se encuentra en una ubicación de emergencia dinámica definida por el inquilino, un centro de llamadas nacional examina las llamadas de emergencia de ese cliente para determinar la ubicación del autor de la llamada antes de transferirla al PSAP que sirve esa ubicación geográfica.

- Si un autor de la llamada de emergencia no puede actualizar su ubicación de emergencia al centro de detección, la llamada se transferirá al PSAP que sirva la dirección registrada del autor de la llamada.


## <a name="considerations-for-direct-routing"></a>Consideraciones para el enrutamiento directo

En las siguientes secciones se describe cómo administrar las llamadas de emergencia de los usuarios de Enrutamiento directo. Para averiguar si el enrutamiento directo es la solución adecuada para su empresa, consulte [Opciones de conectividad con RTC](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-direct-routing"></a>Habilitación de llamadas de emergencia para enrutamiento directo

Para el enrutamiento directo, debe definir directivas de llamadas de emergencia para los usuarios mediante una [directiva de enrutamiento de llamadas de emergencia de Teams](manage-emergency-call-routing-policies.md) para definir los números de emergencia y su destino de enrutamiento asociado. (Actualmente, las ubicaciones de emergencia registradas no son compatibles con los usuarios de enrutamiento directo).

Puede asignar una directiva de enrutamiento de llamadas de emergencia a una cuenta de usuario de Enrutamiento directo, a un sitio de red o a ambos. Cuando un cliente de Teams inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red donde se encuentra el cliente de la siguiente manera:

- Si una directiva de enrutamiento de llamadas de emergencia está asociada al sitio, la directiva del sitio se usa para configurar las llamadas de emergencia.

- Si no hay ninguna directiva de enrutamiento de llamadas de emergencia asociada con el sitio, si el cliente está conectado a un sitio no definido o si el número marcado no coincide con ninguno de los números de emergencia definidos en la directiva de enrutamiento de llamadas de emergencia asociada al sitio, la directiva de enrutamiento de llamadas de emergencia asociada a la cuenta de usuario se usa para configurar las llamadas de emergencia. 

- Si el cliente de Teams no puede obtener una directiva de enrutamiento de llamadas de emergencia, entonces el usuario no está habilitado para las llamadas de emergencia.


### <a name="dynamic-emergency-calling-for-direct-routing"></a>Llamadas de emergencia dinámicas para enrutamiento directo

Las llamadas de emergencia dinámicas para enrutamiento directo proporcionan la capacidad de configurar y enrutar las llamadas de emergencia en función de la ubicación actual del cliente de Teams. La capacidad de realizar enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado o de notificar al personal de la mesa de seguridad varía según el país de uso del usuario de la Teams.

Para los usuarios de enrutamiento directo, la ubicación dinámica para enrutar llamadas de emergencia solo se admite en los Estados Unidos siguientes:

-   Si un cliente de Teams para un usuario de enrutamiento directo de Estados Unidos adquiere dinámicamente una dirección de emergencia dentro de la Estados Unidos, esa dirección se usa para el enrutamiento de emergencia y la llamada se enrutará automáticamente al PSAP en el área de servicio de la dirección.

-   Si un cliente de Teams para un usuario de enrutamiento directo de Estados Unidos no adquiere dinámicamente una dirección de emergencia dentro de la Estados Unidos, la llamada se detectará para determinar si es necesaria una dirección actualizada antes de conectar al autor de la llamada al PSAP adecuado.

La ubicación dinámica para enrutar llamadas de emergencia es compatible en Canadá igual que en la Estados Unidos, con la excepción siguiente: todas las llamadas de emergencia se realizarán en el país antes de transferirse al PSAP.

Para obtener más información, consulte [Configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-direct-routing"></a>Enrutamiento de llamadas de emergencia para enrutamiento directo

La directiva de enrutamiento de llamadas de emergencia para enrutamiento directo hace referencia a un uso de RTC en línea, que debe tener la configuración de enrutamiento directo adecuada para redirigir correctamente las llamadas de emergencia a las puertas de enlace RTC adecuadas. En particular, debe asegurarse de que hay un OnlineVoiceRoute para la cadena de marcado de emergencia. Para obtener más información, consulte [Configurar enrutamiento directo](direct-routing-configure.md). 

> [!NOTE]
> Teams clientes ya no anteponen el signo "+" delante de los números de emergencia (es decir, +911). Por lo tanto, Teams llamadas de emergencia ya no enviarán un "+" antes del número 911. Asegúrese de que los patrones de ruta de voz reflejen este cambio.

La capacidad de enrutar de forma dinámica las llamadas de emergencia para los usuarios de enrutamiento directo varía según la red de llamadas de emergencia de un país determinado. Hay dos soluciones disponibles:

- [Proveedores de servicios de enrutamiento de emergencia (solo ee. UU.)](#emergency-routing-service-providers)
- [Aplicaciones de número de identificación de ubicación de emergencia](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Proveedores de servicios de enrutamiento de emergencia

En el Estados Unidos, hay numerosos proveedores de servicios de enrutamiento de emergencia (ERSP) certificados que pueden enrutar automáticamente las llamadas de emergencia en función de la ubicación del autor de la llamada.

- Si se integra un proveedor de servicios de enrutamiento de emergencia en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación adquirida dinámicamente se redirigirán automáticamente al Punto de respuesta de seguridad pública (PSAP) que sirve esa ubicación.

-  Las llamadas de emergencia sin una ubicación adquirida dinámicamente se comprueban primero para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución adecuado en función de la ubicación actualizada.

Para obtener más información, consulte [Controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-applications"></a>Aplicaciones de número de identificación de ubicación de emergencia

Los controladores de borde de sesión (SBCs) pueden incluir aplicaciones de número de identificación de ubicación de emergencia (ELIN). Si una aplicación ELIN de SBC está integrada en una implementación de enrutamiento directo, debe configurar las direcciones de emergencia y los números de teléfono asociados en la aplicación ELIN y, después, cargar los registros ELIN en la base de datos de llamadas de emergencia en la respectiva RTC. Teams ubicaciones de emergencia con un identificador ELIN deben coincidir con las de la aplicación ELIN.

Cuando una llamada de emergencia con una ubicación adquirida dinámicamente se dirige al SBC adecuado, la aplicación ELIN:

- Analiza la ubicación de emergencia del autor de la llamada.
- Hace coincidir la ubicación con un registro ELIN.
- Sustituye el número de la persona que realiza la llamada de emergencia por el número de teléfono ELIN.
- Enruta la llamada al PSAP que sirve esa ubicación y, a continuación, los distribuidores obtienen la ubicación del registro ELIN cargado.

Al devolver una llamada al número de emergencia, la aplicación ELIN hará lo contrario llamado sustitución de números a la del autor de la llamada de emergencia original. 

Para obtener más información, consulte [Controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notificación de escritorio de seguridad

La notificación de escritorio de seguridad está disponible con los planes de llamadas de Microsoft, Conexión con operador y enrutamiento directo.

Use una directiva de llamadas de emergencia Teams (TeamsEmergencyCallingPolicy) para configurar a quién se le notificará durante una llamada de emergencia y cómo se le notificará: solo chat, conferencias y silenciadas, conferencias y silenciadas, pero con la capacidad de reactivar el audio. También puede especificar un número RTC externo de un usuario o grupo para llamar y unirse a la llamada de emergencia. Tenga en cuenta que la parte RTC no puede reactivar el audio.

Se puede conceder una directiva de llamadas de emergencia a una cuenta de usuario de Teams, asignada a un sitio de red o a ambos.  Cuando un cliente de Teams inicia o cambia una conexión de red, Teams realiza una búsqueda del sitio de red donde se encuentra el cliente:

- Si una directiva de llamadas de emergencia está asociada a un sitio de red, la directiva del sitio se usa para configurar la notificación de escritorio de seguridad.

- Si no hay ninguna directiva de llamadas de emergencia asociada al sitio o si el cliente está conectado a un sitio no definido, la directiva de llamadas de emergencia asociada a la cuenta de usuario se usa para configurar la notificación de escritorio de seguridad.  

- Si el cliente Teams no puede obtener una directiva de llamadas de emergencia, el usuario no está habilitado para la notificación de escritorio de seguridad.

Durante una llamada de emergencia, se conferencia un escritorio de seguridad en la llamada y la experiencia del usuario del escritorio de seguridad se controla en función de la directiva de llamadas de emergencia Teams. Se inicia un chat grupal con cada miembro del servicio de seguridad y la ubicación del autor de la llamada de emergencia se comparte a través de una notificación de mensaje importante.  Si se configura una opción de conferencia como parte de la directiva, se llama también a cada usuario del departamento de seguridad como parte de la conferencia.

### <a name="custom-emergency-disclaimer"></a>Declinación de responsabilidades de emergencia personalizada

Los administradores pueden agregar un banner personalizado en el inquilino para que sus usuarios habiliten E911. Los usuarios pueden descartar el banner cuando confirmen su dirección y el mensaje emergente volverá a aparecer cuando se reinicie Teams. Para habilitar esta característica, establezca la **declinación de responsabilidades del servicio de emergencia** en la directiva de llamadas de emergencia de Teams y escriba un mensaje de cadena que se mostrará a los usuarios. Este campo es opcional al configurar una directiva personalizada y el campo de cadena está limitado a 250 caracteres.

> [!NOTE]
> Actualmente, esto se puede configurar mediante PowerShell con la directiva EnhancedEmergencyServicesDisclaimer. En el futuro, esto también se podrá configurar en el centro de administración de Teams.

    
## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia ](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
