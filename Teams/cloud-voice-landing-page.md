---
title: Planear la solución de voz en Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Obtenga más información sobre las características de voz en la nube de Microsoft Teams y las decisiones de implementación que se tomarán para su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e16a2aea0d367c720cf36c8010670a34472ab43a
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701338"
---
# <a name="plan-your-teams-voice-solution"></a>Planear la solución de voz de Teams 

Este artículo le ayudará a decidir qué solución de voz de Microsoft es la adecuada para su organización. Una vez que lo haya decidido, el artículo proporciona una hoja de ruta al contenido que le permitirá implementar la solución elegida.

> [!NOTE]
> Para obtener instrucciones sobre cómo planear una solución de voz de Teams como parte de su plan general para actualizar a Teams desde Skype Empresarial Server, consulte Consideraciones de RTC para actualizar a Teams desde Skype Empresarial [local.](upgrade-to-Teams-on-prem-pstn-considerations.md)

Es posible que quiera la solución más sencilla &mdash; Sistema telefónico con Plan de llamadas. Esta es la solución todo en la nube de Microsoft que proporciona funcionalidad de central de conmutación (PBX) y llamadas a la red telefónica conmutada (RTC), tal como se muestra en el siguiente diagrama. Con esta solución, Microsoft es su operador de RTC.

![Diagrama 1 que muestra Sistema telefónico con plan de llamadas](media/voice-solutions-simple.png)

Si responde sí a lo siguiente, Entonces Sistema telefónico con plan de llamadas es la solución adecuada para usted:

- El plan de llamadas está disponible en tu región.
- No es necesario conservar su operador RTC actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Sin embargo, su situación podría ser más compleja. Por ejemplo, es posible que tenga oficinas en ubicaciones donde el plan de llamadas no está disponible. O puede necesitar una solución combinada que admita una implementación compleja y nacional con diferentes requisitos para diferentes ubicaciones geográficas. Microsoft admite una combinación de soluciones: 

- Sistema telefónico con plan de llamadas
- Sistema telefónico con su propio operador RTC con enrutamiento directo
- Una solución combinada que usa sistema telefónico con plan de llamadas y sistema telefónico con enrutamiento directo

## <a name="what-do-you-need-to-read"></a>¿Qué necesita leer?

**Obligatorio para todos.** Algunas de las secciones de este artículo pertenecen a todas las organizaciones. Por ejemplo, todos deben leer sobre sistema telefónico y comprender las opciones para conectarse a la red telefónica conmutada (RTC). 


| Obligatorio para todos | Descripción |
| :------------|:-------|
| [**Sistema telefónico**](#phone-system) | Tecnología de Microsoft para habilitar el control de llamadas y las capacidades de la central de conmutación (PBX) en la nube de Microsoft 365 con Microsoft Teams. |
| [**Opciones de conectividad de red telefónica conmutada (RTC)**](#public-switched-telephone-network-connectivity-options) | Una opción entre usar Microsoft como su operador de telefonía o conectar su propio operador de telefonía a Microsoft Teams mediante el enrutamiento directo. Combinadas con Sistema telefónico, las opciones de conectividad con RTC permiten a los usuarios realizar llamadas de teléfono en todo el mundo.|

**Según sus requisitos.** Algunas de las secciones de este artículo son pertinentes en función de los requisitos y la implementación existentes. Por ejemplo, Location-Based enrutamiento directo solo es necesario para los clientes de enrutamiento directo en ubicaciones geográficas que no permitan la omisión de pago.

Tenga en cuenta cuál de estas configuraciones adicionales podría necesitar:

![El diagrama 2 muestra componentes de voz adicionales, como números de teléfono de Microsoft, planes de marcado y enrutamiento de llamadas, entre otros.](media/voice-consider-additional-components.png)

| Según los requisitos | Descripción |
| :------------|:-------|
| [**Números de teléfono de Microsoft**](#phone-numbers-from-microsoft) | Cómo obtener y administrar números de teléfono de Microsoft y cómo transferir números existentes a Microsoft. Lea esto si necesita obtener números de teléfono para Microsoft Calling Plan, transferir números existentes, obtener números de servicio, y así sucesivamente. |
| [**Planes de marcado y enrutamiento de llamadas**](#dial-plans-and-call-routing) | Cómo configurar y administrar planes de marcado que traduzcan los números de teléfono marcados a un formato alternativo (normalmente en formato E.164) para la autorización y el enrutamiento de llamadas. Lea esto si necesita comprender qué son los planes de marcado y si necesita especificar planes de marcado para su organización.|
| [**Llamadas de emergencia**](#emergency-calling) | Cómo administrar y configurar las llamadas de emergencia &mdash; en función de la opción de conectividad con RTC. Lea esta sección si usa Microsoft Calling Plan o Enrutamiento directo y necesita comprender cómo administrar las llamadas de emergencia de su organización. |
| [**Enrutamiento basado en la ubicación para enrutamiento directo**](#location-based-routing-for-direct-routing) |Cómo usar el enrutamiento Location-Based de destino (LBR) para restringir la omisión de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. Lea esta sección si su organización está usando enrutamiento directo en una ubicación que no permita la omisión de pago.
| [**Topología de red para características de voz en la nube**](#network-topology-for-voice-features) | Si su organización está implementando Location-Based (LBR) para enrutamiento directo o llamadas de emergencia dinámicas, debe configurar la configuración de red para su uso con estas características en Microsoft Teams. Lea esta sección si va a implementar LBR para enrutamiento directo o si está implementando llamadas de emergencia dinámicas con un plan de llamadas o enrutamiento directo. |
| [**Migrar la solución de voz existente**](#migrate-your-existing-voice-solution-to-teams) | Lo que debe tener en cuenta al migrar su solución de voz a Teams.  Lea esta sección si va a migrar desde una solución de voz existente a Teams. 



> [!Important]
> Este artículo se centra en las soluciones de voz con Microsoft Teams. Aunque las soluciones con Skype Empresarial Online siguen estando disponibles (como se describe en las soluciones de telefonía de [Microsoft),](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)es importante comprender que Skype Empresarial Online se retirará el 31 de julio de 2021.  Después de esa fecha, el servicio de Skype Empresarial Online ya no estará accesible. Además, ya no se admite la conectividad con RTC entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y &mdash; &mdash; Skype Empresarial Online. Este artículo presenta las soluciones de voz de Teams y cómo puede conectar su red de telefonía local, si es necesario, a Teams mediante el enrutamiento directo.


## <a name="phone-system"></a>Sistema telefónico

Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de central de conmutación (PBX) en la nube de Microsoft 365 u Office 365 con Microsoft Teams.

Sistema telefónico funciona con clientes de Teams o Skype Empresarial y dispositivos certificados. Sistema telefónico le permite reemplazar su sistema PBX existente con un conjunto de características directas desde Microsoft 365 u Office 365. 

Las llamadas entre usuarios de su organización se gestionan internamente en Sistema telefónico y nunca van a la red telefónica conmutada (RTC). Esto se aplica a las llamadas entre usuarios de su organización ubicados en diferentes áreas geográficas, quitando los costes de larga distancia en estas llamadas internas.

En este artículo se presentan las siguientes características y funcionalidades clave de Sistema telefónico, así como las decisiones de implementación que debe tener en cuenta:

- [Operadores automáticos y las colas de llamadas](#auto-attendants-and-call-queues)
- [Correo de voz en la nube](#cloud-voicemail)
- [Identidad de llamada](#calling-identity)

![El diagrama 3 muestra que el sistema telefónico contiene operadores automáticos y consultas de llamadas, correo de voz en la nube e identidad de llamadas](media/phone-system-contains.png)

Para obtener información sobre todas las características de Sistema telefónico y cómo configurar Sistema telefónico, vea los artículos siguientes:

- [Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)
- [Configurar Sistema telefónico en su organización](setting-up-your-phone-system.md)<br>
  Describe cómo comprar y asignar licencias de Sistema telefónico, administrar números de teléfono y configurar créditos de comunicación para números gratuitos. 

Para obtener información sobre la administración de dispositivos compatibles, consulte Administrar sus dispositivos [en Microsoft Teams](devices/device-management.md) y Teams [Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Operadores automáticos y colas de llamadas

Los operadores automáticos le permiten configurar opciones de menú para enrutar llamadas en función de la entrada del autor de la llamada. Las colas de llamadas son áreas de espera para los autores de llamadas. Cuando se usan de forma conjunta, los operadores automáticos y las colas de llamadas pueden dirigir fácilmente a los autores de llamadas a la persona o el departamento correspondiente de su organización.

Para obtener información sobre los operadores automáticos y las colas de llamadas, vea los artículos siguientes:

- [Plan para operadores automáticos y colas de llamadas de Teams](plan-auto-attendant-call-queue.md)
- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md) 
- [Caso práctico Contoso: operadores automáticos y colas de llamadas](voice-case-study-call-queues.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó operadores automáticos y colas de llamadas para su solución de voz.

### <a name="cloud-voicemail"></a>Correo de voz en la nube

Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only. No es compatible con sistemas de correo electrónico de terceros. 

El correo de voz en la nube cuenta con la opción de transcripción del correo de voz, la cual está activada de forma predeterminada para todos los usuarios de la organización. Es posible que las necesidades de su empresa requieran que deshabilite la transcripción del correo de voz para usuarios específicos o para todos los usuarios de toda la organización.

Para los usuarios solo en línea, el correo de voz en la nube se configura y aprovisiona automáticamente para los usuarios después de que se les asigne una licencia de Sistema telefónico. Para los usuarios de sistemas telefónicos con un buzón de Exchange, necesitará realizar pasos de configuración adicionales. 

Para obtener más información sobre el correo de voz en la nube y su configuración, vea los artículos siguientes:

- [Planear el Correo de voz en la nube](set-up-phone-system-voicemail.md)
- [Establecer directivas de correo de voz en su organización](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada. Para obtener información sobre cómo configurar el identificador de llamada o para cambiar o bloquear el identificador de llamada, vea Establecer el identificador de llamada [de un usuario.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opciones de conectividad de red telefónica conmutada pública

Sistema telefónico proporciona funcionalidades pbx completas para su organización. Sin embargo, para permitir que los usuarios realicen llamadas fuera de su organización, debe conectar Sistema telefónico a la red telefónica conmutada (RTC). Para conectar Sistema telefónico a RTC, puede elegir una de las siguientes opciones:

- [**Sistema telefónico con plan de llamadas.**](#phone-system-with-calling-plan) Una solución todo en la nube con Microsoft como su operador de RTC.

- [**Sistema telefónico con su propio operador RTC mediante**](#phone-system-with-own-pstn-carrier-with-direct-routing) enrutamiento directo para conectar su entorno local a Teams.

También puede elegir una combinación de opciones, que le permite diseñar una solución para un entorno complejo, o administrar una migración de varios pasos (más información sobre la migración más adelante).

### <a name="phone-system-with-calling-plan"></a>Sistema telefónico con plan de llamadas 

Como se ha descrito anteriormente en este artículo, Sistema telefónico con plan de llamadas es la solución de voz todo en la nube de Microsoft para los usuarios de Teams. Esta es la opción más sencilla que conecta Microsoft Phone System a la red telefónica conmutada (RTC) para habilitar las llamadas a teléfonos fijos y móviles de todo el mundo. Con esta opción, Microsoft proporciona la funcionalidad de central de conmutación (PBX) para su organización y actúa como su operador de telefonía RTC, tal como se muestra en el siguiente diagrama:

![El diagrama 4 muestra sistema telefónico con operadores automáticos, colas de llamadas, identificación de llamadas y más, y Microsoft como el operador RTC](media/voice-solution-microsoft-complete.png)

Si responde sí a lo siguiente, Entonces Sistema telefónico con plan de llamadas es la solución adecuada para usted:

- El plan de llamadas está disponible en tu región.
- No es necesario conservar su operador RTC actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Con esta opción: 

- Microsoft Phone System se obtiene con planes de llamadas nacionales o internacionales agregados que permiten llamar a teléfonos de todo el mundo (según el nivel de servicio que se licencia).

- No es necesario implementar ni mantenimiento una implementación local porque el plan de llamadas funciona con &mdash; Microsoft 365 u Office 365.

- Nota: Si es necesario, puede elegir conectar un controlador de borde de sesión (SBC) compatible a través del enrutamiento directo para interoperabilidad con PBX de terceros, dispositivos analógicos y otros equipos de telefonía de terceros compatibles con SBC.

Esta opción requiere una conexión sin interrupciones a Microsoft 365 u Office 365.

Para obtener más información sobre el plan de llamadas, consulte los artículos siguientes:

- [¿Qué plan de llamada es adecuado para usted?](calling-plan-landing-page.md)
- [Cómo comprar un plan de llamadas](calling-plans-for-office-365.md)
- [Países y regiones donde el Plan de llamadas está disponible](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Configurar el plan de llamadas](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema telefónico con un operador RTC propio con enrutamiento directo

Esta opción conecta Microsoft Phone System a su red de telefonía mediante enrutamiento directo, como se muestra en el siguiente diagrama: 

![El diagrama 5 muestra Sistema telefónico con enrutamiento directo](media/voice-solution-with-direct-routing.png)

Si responde sí a las siguientes preguntas, entonces Sistema telefónico con enrutamiento directo es la solución adecuada para usted:

- Desea usar Teams con Sistema telefónico.
- Debe conservar su operador RTC actual.
- Quiere mezclar el enrutamiento, con algunas llamadas a través del plan de llamadas, algunas a través de su operador.
- Necesita interactuar con PBX y/o equipos de terceros, como los pagers de sobrecarga, dispositivos analógicos, y así sucesivamente.

Con esta opción:

- Conecte su propio SBC compatible con Microsoft Phone System sin necesidad de software local adicional.

- Puede usar prácticamente cualquier operador de telefonía con Microsoft Phone System.

- Puede configurar y administrar esta opción, o puede configurarla y administrarla su operador o socio (pregunte si su operador o partner proporciona esta opción).

- Puede configurar la interoperabilidad entre el equipo de telefonía, como un PBX de &mdash; terceros, dispositivos analógicos &mdash; y Microsoft Phone System.


Esta opción requiere lo siguiente:

- Conexión sin interrupciones a Microsoft 365 u Office 365.

- Implemente y mantenga un SBC compatible.

- Un contrato con un operador externo.
  (A menos que se implemente como opción para proporcionar conexión a PBX de terceros, dispositivos analógicos u otro equipo de telefonía para los usuarios que están en Sistema telefónico con plan de llamadas).

Para obtener más información sobre enrutamiento directo, vea los artículos siguientes:

- [Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)
- [Planear el enrutamiento directo](direct-routing-plan.md)
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Administrar directivas de enrutamiento de voz para su uso con Enrutamiento directo](manage-voice-routing-policies.md)
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Números de teléfono de Microsoft

Microsoft tiene disponibles dos tipos de números de *teléfono:* números de suscriptor (usuarios), que se pueden asignar a los usuarios de su organización, y números de servicio, disponibles como números de servicio gratuitos y de pago.  Los números de servicio tienen una mayor capacidad de llamadas simultáneas que los números de suscriptor y se pueden asignar a servicios como Audioconferencia, Operadores automáticos o Colas de llamadas.

Tendrá que decidir lo siguiente:

- ¿Qué ubicaciones de usuario necesitan números de teléfono nuevos de Microsoft?
- ¿Qué tipo de número de teléfono (suscriptor o servicio) necesito? 
- ¿Cómo puedo realizar la portabilidad de números de teléfono existentes a Teams?

Para obtener más información sobre la administración de números de teléfono en su organización, como obtener números nuevos o transferir números de salida, vea los siguientes artículos:

- [Administrar los números de teléfono de la organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Distintos tipos de números de teléfono usados para plan de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md)
- [Transferir números de teléfono a Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Planes de marcado y enrutamiento de llamadas

Un plan de marcado es un conjunto de reglas de normalización que traducen los números de teléfono marcados a un formato alternativo (normalmente en formato E.164) para la autorización y el enrutamiento de llamadas.

Tendrá que decidir lo siguiente: 

- ¿Mi organización necesita un plan de marcado personalizado?
- ¿Qué usuarios requieren un plan de marcado personalizado?
- ¿Qué plan de marcado inquilino debe asignarse a cada usuario?

Para obtener más información, vea los artículos siguientes: 

- [¿Qué son los planes de marcado?](what-are-dial-plans.md)
- [Plan para planes de marcado de inquilino](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Crear y administrar planes de marcado](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Llamadas de emergencia

La forma de configurar las llamadas de emergencia varía en función de la opción de conectividad con RTC: Plan de llamadas de Microsoft o Enrutamiento directo. Las llamadas de emergencia dinámicas para el plan de llamadas de Microsoft y el enrutamiento directo del sistema telefónico proporcionan la capacidad de configurar y enrutar llamadas de emergencia y notificar al personal de seguridad según la ubicación actual del cliente de Teams. Para obtener más información sobre conceptos y terminología de las llamadas de emergencia y cómo configurar las llamadas de emergencia dinámicas, vea los artículos siguientes:

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
- [Caso práctico Contoso: Llamadas de emergencia](voice-case-study-emergency-calling.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó llamadas de emergencia para su organización.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based para enrutamiento directo

En algunos países y regiones, es ilegal omitir el proveedor de red telefónica conmutada (RTC) para disminuir los costes de las llamadas de larga distancia. Location-Based enrutamiento directo le permite restringir la omisión de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. Para obtener más información sobre cómo planear y configurar el Location-Based de enrutamiento de red (LBR), vea los artículos siguientes:

- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Caso práctico Contoso: Location-Based de correo electrónico](voice-case-study-location-based-routing.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó un enrutamiento Location-Based para su organización.

## <a name="network-topology-for-voice-features"></a>Topología de red para características de voz

Si implementa llamadas de emergencia dinámicas o enrutamiento Location-Based directo, debe configurar las opciones de red para usarlas con estas características en Microsoft Teams. Para obtener información sobre cómo configurar la configuración de red para regiones de red, sitios de red, subredes de red y direcciones IP de confianza, vea los artículos siguientes:

- [Configuración de red para las características de voz en la nube de Microsoft Teams: Conceptos y terminología](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube en Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrar su solución de voz existente a Teams

Para una organización que está actualizando a Teams, el objetivo final es mover todos los usuarios al modo TeamsOnly. Usar Sistema telefónico con Teams solo es compatible cuando el usuario está en modo TeamsOnly. Si necesita información básica sobre cómo actualizar a Teams, empiece aquí:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Acerca del marco de actualización](upgrade-framework.md)
- [Actualizar de Skype Empresarial a Teams para administradores de TI](upgrade-to-teams-on-prem-overview.md)

Al migrar su solución de voz, hay cuatro escenarios posibles de llamadas al pasar al modo TeamsOnly:

- [**Un usuario de Skype Empresarial Online con un plan de llamadas de Microsoft.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) Tras la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft.

- **[Un usuario de Skype Empresarial Online,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** con funcionalidad de voz local a través de Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.

- **[Un usuario de Skype Empresarial local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** con Telefonía IP empresarial que pasará a estar conectado y mantendrá la conectividad con RTC local. Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local a la nube y coordinar ese movimiento con la migración del usuario a Enrutamiento directo. 

- **[Un usuario de Skype Empresarial local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** con Telefonía IP empresarial que se trasladará a Internet y que utiliza un plan de llamadas de Microsoft.  Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local a la nube y coordinar que se mueva con A) el puerto del número de teléfono de ese usuario a un plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor desde las regiones disponibles.

Para obtener más información sobre cómo implementar la migración de voz para cada uno de estos escenarios, incluida información sobre cuándo necesita configurar la conectividad híbrida y cómo migrar usuarios con funcionalidad de voz local a Enrutamiento directo, vea los artículos &mdash; &mdash; siguientes:

- [Consideraciones de RTC al actualizar a Teams: para administradores de TI](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Caso práctico de migración de voz de Contoso](voice-case-study-overview.md)<br>
  El caso práctico describe cómo una corporación multinacional ficticia, Contoso, implementó una solución de voz de Teams para su organización. Contiene los artículos siguientes:

  - [Plan de actualización de Teams](voice-case-study-migration-plan.md)
  - [Opciones de conectividad de Sistema telefónico y RTC](voice-case-study-phone-system.md)
  - [Implementación de enrutamiento basado en la ubicación](voice-case-study-location-based-routing.md)
  - [Llamadas de emergencia](voice-case-study-emergency-calling.md)
  - [Operadores automáticos y las colas de llamadas](voice-case-study-call-queues.md)
  - [Audioconferencia](voice-case-study-audio-conferencing.md)












