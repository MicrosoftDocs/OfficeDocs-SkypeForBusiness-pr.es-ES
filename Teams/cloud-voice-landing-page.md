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
description: Obtenga más información sobre las características de voz en la nube de Microsoft Teams y las decisiones de implementación que realizará para su organización.
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

Este artículo le ayudará a decidir qué solución de voz de Microsoft es la adecuada para su organización. Una vez que haya decidido, el artículo le proporciona una guía básica para el contenido que le permitirá implementar la solución elegida.

> [!NOTE]
> Para obtener instrucciones sobre cómo planear una solución de voz de Teams como parte de su plan general para actualizar a teams desde Skype empresarial Server, consulte [consideraciones sobre RTC para actualizar a teams desde Skype empresarial local](upgrade-to-Teams-on-prem-pstn-considerations.md).

Es posible que desee el sistema telefónico de la solución más simple &mdash; con plan de llamadas. Esta es la solución todo en la nube de Microsoft que proporciona la funcionalidad de la conmutación de sucursales privadas (PBX) y las llamadas a la red de telefonía pública conmutada (RTC), como se muestra en el siguiente diagrama. Con esta solución, Microsoft es tu operador PSTN.

![El diagrama 1 muestra el sistema telefónico con el plan de llamadas](media/voice-solutions-simple.png)

Si responde afirmativamente a lo siguiente, el sistema telefónico con el plan de llamadas es la solución adecuada para usted:

- El plan de llamadas está disponible en tu región.
- No es necesario que conserve su operador PSTN actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Sin embargo, es posible que su situación sea más compleja. Por ejemplo, puede que tenga oficinas en ubicaciones en las que el plan de llamadas no está disponible. O puede que necesite una solución combinada que admita una implementación compleja multinacional, con diferentes requisitos para diferentes ubicaciones geográficas. Microsoft admite una combinación de soluciones: 

- Sistema telefónico con plan de llamadas
- Sistema telefónico con su propio operador de RTC con enrutamiento directo
- Una solución combinada que usa el sistema telefónico con un plan de llamadas y un sistema telefónico con enrutamiento directo

## <a name="what-do-you-need-to-read"></a>¿Qué necesita leer?

**Necesario para todos.** Algunas de las secciones de este artículo pertenecen a todas las organizaciones. Por ejemplo, todo el mundo debe leer acerca del sistema telefónico y comprender las opciones para conectarse a la red de telefonía pública conmutada (RTC). 


| Necesario para todos los | Descripción |
| :------------|:-------|
| [**Sistema telefónico**](#phone-system) | La tecnología de Microsoft para habilitar el control de llamadas y las capacidades de central de conmutación (PBX) en la nube de Microsoft 365 con Microsoft Teams. |
| [**Opciones de conectividad de la red de telefonía pública conmutada (RTC)**](#public-switched-telephone-network-connectivity-options) | Elegir entre usar Microsoft como su operador de telefonía o conectar su propio operador de telefonía a Microsoft Teams mediante enrutamiento directo. En combinación con el sistema telefónico, las opciones de conectividad RTC permiten a los usuarios hacer llamadas telefónicas en todo el mundo.|

**En función de sus necesidades.** Algunas de las secciones de este artículo son pertinentes en función de la implementación y los requisitos existentes. Por ejemplo, Location-Based enrutamiento solo es necesario para los clientes de enrutamiento directo en ubicaciones geográficas que no permiten omisión de pago.

Considere cuál de estas configuraciones adicionales puede necesitar:

![El diagrama 2 muestra componentes de voz adicionales, como números de teléfono de Microsoft, planes de marcado y enrutamiento de llamadas, etc.](media/voice-consider-additional-components.png)

| En función de sus necesidades | Descripción |
| :------------|:-------|
| [**Números de teléfono de Microsoft**](#phone-numbers-from-microsoft) | Cómo obtener y administrar números de teléfono de Microsoft y cómo transferir números existentes a Microsoft. Lea esto si necesita obtener números de teléfono para el plan de llamadas de Microsoft, transferir números existentes, obtener números de servicio, etc. |
| [**Planes de marcado y enrutamiento de llamadas**](#dial-plans-and-call-routing) | Cómo configurar y administrar planes de marcado que traducen números de teléfono marcados a un formato alternativo (por lo general, formato E. 164) para la autorización de llamadas y el enrutamiento de llamadas. Lea esto si necesita comprender qué son los planes de marcado y si necesita especificar planes de marcado para su organización.|
| [**Llamadas de emergencia**](#emergency-calling) | Cómo administrar y configurar &mdash; las llamadas de emergencia según su opción de conectividad RTC. Lea esta sección si está usando el plan de llamadas de Microsoft o el enrutamiento directo y necesita comprender cómo administrar las llamadas de emergencia para su organización. |
| [**Enrutamiento basado en la ubicación para el enrutamiento directo**](#location-based-routing-for-direct-routing) |Cómo usar Location-Based Routing (LBR) para restringir el omisión de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. Lea esta sección si su organización usa el enrutamiento directo en un lugar que no permite la omisión de pago.
| [**Topología de red para características de voz en la nube**](#network-topology-for-voice-features) | Si su organización está implementando Location-Based enrutamiento (LBR) para el enrutamiento directo o las llamadas de emergencia dinámicas, debe configurar las opciones de red para su uso con estas características de Microsoft Teams. Lea esta sección si va a implementar LBR para el enrutamiento directo o si está implementando llamadas de emergencia dinámicas con un plan de llamadas o un enrutamiento directo. |
| [**Migrar la solución de voz existente**](#migrate-your-existing-voice-solution-to-teams) | Qué tiene que pensar al migrar su solución de voz a teams.  Lea esta sección si va a migrar desde una solución de voz existente a teams. 



> [!Important]
> Este artículo se centra en las soluciones de voz con Microsoft Teams. Aunque las soluciones con Skype empresarial online siguen estando disponibles (según se describe en [soluciones de telefonía de Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), es importante comprender que Skype empresarial online se retirará el 31 de julio de 2021.  Después de esa fecha, el servicio de Skype empresarial online ya no será accesible. Además, ya no se admite la conectividad RTC entre el entorno local, ya &mdash; sea a través de Skype empresarial Server o Cloud Connector Edition, &mdash; y Skype empresarial online. En este artículo se presentan las soluciones de voz de Teams y cómo puede conectar su red de telefonía local, si es necesario, a los equipos con enrutamiento directo.


## <a name="phone-system"></a>Sistema telefónico

Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de PBX (Private Branch Exchange) en la nube de Microsoft 365 o de Office 365 con Microsoft Teams.

El sistema telefónico funciona con equipos o con clientes y dispositivos certificados de Skype empresarial. El sistema telefónico le permite reemplazar el sistema PBX existente por un conjunto de características que se proporcionan directamente desde Microsoft 365 u Office 365. 

Las llamadas entre usuarios de su organización se controlan internamente en el sistema telefónico y nunca van a la red de telefonía pública conmutada (RTC). Esto se aplica a las llamadas entre usuarios de la organización que se encuentran en áreas geográficas diferentes, eliminando los costos de larga distancia de estas llamadas internas.

En este artículo se presentan las siguientes características y funciones de clave de sistema telefónica, así como las decisiones de implementación que debe tener en cuenta:

- [Operadores automáticos y las colas de llamadas](#auto-attendants-and-call-queues)
- [Correo de voz en la nube](#cloud-voicemail)
- [Identidad de llamadas](#calling-identity)

![El diagrama 3 muestra el sistema telefónico contiene los operadores automáticos y las consultas de llamadas, el buzón de voz de nube y la identidad de llamadas](media/phone-system-contains.png)

Para obtener más información sobre todas las características del sistema telefónico y cómo configurar el sistema telefónico, consulte los artículos siguientes:

- [Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)
- [Configurar el sistema telefónico de su organización](setting-up-your-phone-system.md)<br>
  Describe cómo comprar y asignar licencias de sistema telefónico, administrar números de teléfono y establecer créditos de comunicación para números gratuitos. 

Para obtener información sobre la administración de dispositivos compatibles, consulte [administrar los dispositivos en Microsoft Teams](devices/device-management.md) y [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Operadores automáticos y colas de llamadas

Los operadores automáticos permiten configurar opciones de menú para enrutar llamadas según la entrada de la persona que llama. Las colas de llamadas son áreas de espera para las personas que llaman. Si se usan conjuntamente, los operadores automáticos y las colas de llamadas pueden enrutar fácilmente a las personas que llaman a la persona o al departamento correspondiente de su organización.

Para obtener información sobre los operadores automáticos y las colas de llamadas, vea los artículos siguientes:

- [Planear los operadores automáticos de Teams y las colas de llamadas](plan-auto-attendant-call-queue.md)
- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md) 
- [Caso práctico de Contoso: los operadores automáticos y las colas de llamadas](voice-case-study-call-queues.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, los operadores automáticos implementados y las colas de llamadas para su solución de voz.

### <a name="cloud-voicemail"></a>Correo de voz en la nube

El buzón de voz de nube, basado en los servicios de buzón de voz de Azure, solo admite los depósitos de buzón de voz para Exchange mailboxes. No admite sistemas de correo electrónico de terceros. 

El buzón de voz de nube incluye la transcripción del buzón de voz, que está habilitada para todos los usuarios de su organización de forma predeterminada. Las necesidades de su empresa pueden requerir que deshabilite la transcripción del buzón de voz para usuarios específicos o para todos los miembros de la organización.

Para los usuarios solo en línea, el buzón de voz de nube se configura y se aprovisiona automáticamente para los usuarios después de que se les asigne una licencia de sistema telefónico. En el caso de los usuarios del sistema telefónico con un buzón de Exchange, tendrá que realizar pasos de configuración adicionales. 

Para obtener más información sobre el buzón de voz de la nube y su configuración, vea los artículos siguientes:

- [Planear el Correo de voz en la nube](set-up-phone-system-voicemail.md)
- [Establecer directivas de buzón de voz en su organización](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identidad de llamadas

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificación de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada. Para obtener información sobre cómo configurar la identificación de llamadas o para cambiar o bloquear la identificación de llamadas, vea [establecer la identificación de llamadas de un usuario](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opciones de conectividad de red telefónica conmutada pública

El sistema telefónico proporciona capacidades completas de PBX para su organización. Sin embargo, para permitir que los usuarios puedan hacer llamadas fuera de su organización, debe conectar el sistema telefónico a la red de telefonía pública conmutada (RTC). Para conectar el sistema telefónico a la RTC, puede elegir una de las siguientes opciones:

- [**Sistema telefónico con plan de llamadas**](#phone-system-with-calling-plan). Una solución todo en la nube con Microsoft como su operador PSTN.

- [**Sistema telefónico con su propia portadora RTC mediante el**](#phone-system-with-own-pstn-carrier-with-direct-routing) enrutamiento directo para conectar el entorno local con los equipos.

También puede elegir una combinación de opciones, que le permite diseñar una solución para un entorno complejo o administrar una migración en varios pasos (más información sobre la migración más adelante).

### <a name="phone-system-with-calling-plan"></a>Sistema telefónico con plan de llamadas 

Como se describió anteriormente en este artículo, el sistema telefónico con plan de llamadas es la solución de voz todo en la nube de Microsoft para los usuarios de Teams. Esta es la opción más sencilla que conecta el sistema telefónico de Microsoft con la red de telefonía pública conmutada (RTC) para permitir llamadas a teléfonos fijos y móviles de todo el mundo. Con esta opción, Microsoft proporciona la funcionalidad de central de conmutación (PBX) para su organización y actúa como su operador PSTN, tal y como se muestra en el siguiente diagrama:

![El diagrama 4 muestra el sistema telefónico con operadores automáticos, colas de llamadas, identificación de llamadas, etc. y Microsoft como la portadora RTC](media/voice-solution-microsoft-complete.png)

Si responde afirmativamente a lo siguiente, el sistema telefónico con el plan de llamadas es la solución adecuada para usted:

- El plan de llamadas está disponible en tu región.
- No es necesario que conserve su operador PSTN actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Con esta opción: 

- Usted recibe Microsoft Phone System con planes de llamadas nacionales e internacionales añadidos que permiten llamar a teléfonos de todo el mundo (según el nivel de servicio al que se les concede la licencia).

- No es necesario implementar ni mantener una implementación local porque el plan de &mdash; llamadas funciona fuera de Microsoft 365 u Office 365.

- Nota: si es necesario, puede elegir conectar un controlador de borde de sesión (SBC) compatible a través del enrutamiento directo para la interoperabilidad con sistemas PBX de terceros, dispositivos analógicos y otros equipos de telefonía de terceros admitidos por SBC.

Esta opción requiere una conexión ininterrumpida a Microsoft 365 u Office 365.

Para obtener más información sobre la planificación de llamadas, consulte los siguientes artículos:

- [¿Qué plan de llamada es adecuado para usted?](calling-plan-landing-page.md)
- [Cómo comprar un plan de llamadas](calling-plans-for-office-365.md)
- [Países y regiones donde el Plan de llamadas está disponible](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Configurar plan de llamadas](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema telefónico con su propio operador PSTN con enrutamiento directo

Esta opción conecta Microsoft Phone System a la red de telefonía mediante enrutamiento directo, como se muestra en el siguiente diagrama: 

![El diagrama 5 muestra el sistema telefónico con enrutamiento directo](media/voice-solution-with-direct-routing.png)

Si responde afirmativamente a las siguientes preguntas, el sistema telefónico con enrutamiento directo es la solución adecuada para usted:

- Quiere usar Teams con el sistema telefónico.
- Debes conservar tu operador de telefonía RTC actual.
- Desea combinar el enrutamiento, con algunas llamadas que pasan por un plan de llamadas, algunas a través de su transportista.
- Necesita interoperar con PBX o equipos de terceros, como localizadores de overhead de Estados Unidos, dispositivos analógicos, etc.

Con esta opción:

- Puede conectar su propio SBC compatible con Microsoft Phone System sin necesidad de software local adicional.

- Puede usar prácticamente cualquier operador de telefonía con Microsoft Phone System.

- Puede elegir configurar y administrar esta opción, o bien su transportista o socio puede configurarlo y administrarlo (pregunte si su transportista o socio proporciona esta opción).

- Puede configurar la interoperabilidad entre su equipo de telefonía &mdash; , como un PBX de terceros, dispositivos analógicos &mdash; y un sistema telefónico de Microsoft.


Esta opción requiere lo siguiente:

- Conexión ininterrumpida a Microsoft 365 u Office 365.

- Implementar y mantener una SBC compatible.

- Un contrato con un proveedor de terceros.
  (A menos que se implemente como una opción para proporcionar conexión a PBX de terceros, dispositivos analógicos u otros equipos de telefonía para usuarios que están en el sistema telefónico con el plan de llamadas).

Para obtener más información sobre el enrutamiento directo, consulte los artículos siguientes:

- [Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)
- [Planear el enrutamiento directo](direct-routing-plan.md)
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Administrar directivas de enrutamiento de voz para usarlas con enrutamiento directo](manage-voice-routing-policies.md)
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Números de teléfono de Microsoft

Microsoft tiene dos tipos de números telefónicos disponibles: números de *suscriptor* (usuario), que se pueden asignar a los usuarios de su organización, y números de *servicio* , disponibles como números de servicio de pago y gratuitos. Los números de servicio tienen una capacidad de llamadas simultáneas superior a la de los abonados y se pueden asignar a servicios como audioconferencias, operadores automáticos o colas de llamadas.

Tendrá que decidir:

- ¿Qué ubicaciones de usuario necesitan números de teléfono nuevos de Microsoft?
- ¿Qué tipo de número de teléfono (suscriptor o servicio) necesito? 
- ¿Cómo Porto números de teléfono existentes a teams?

Para obtener más información sobre cómo administrar números de teléfono de su organización, como obtener números nuevos o transferir números de salida, consulte los artículos siguientes:

- [Administrar los números de teléfono de la organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Diferentes tipos de números de teléfono usados para el plan de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md)
- [Transferir números de teléfono a Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Planes de marcado y enrutamiento de llamadas

Un plan de marcado es un conjunto de reglas de normalización que convierten los números de teléfono marcados en un formato alternativo (por lo general, formato E. 164) para la autorización de llamadas y el enrutamiento de llamadas.

Tendrá que decidir lo siguiente: 

- ¿Mi organización necesita un plan de marcado personalizado?
- ¿Qué usuarios requieren un plan de marcado personalizado?
- ¿Qué plan de marcado de inquilino se debe asignar a cada usuario?

Para obtener más información, vea los artículos siguientes: 

- [¿Qué son los planes de marcado?](what-are-dial-plans.md)
- [Planear planes de marcado de inquilino](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Crear y administrar planes de marcado](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Llamadas de emergencia

La configuración de las llamadas de emergencia difiere según la opción de conectividad RTC: Plan de llamadas de Microsoft o enrutamiento directo. Llamadas de emergencia dinámicas para el plan de llamadas de Microsoft y el enrutamiento directo de sistema telefónico proporcionan la capacidad de configurar y enrutar llamadas de emergencia y de notificar al personal de seguridad en función de la ubicación actual del cliente de Teams. Para obtener más información sobre los conceptos y la terminología de las llamadas de emergencia y sobre cómo configurar las llamadas de emergencia dinámicas, consulte los artículos siguientes:

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
- [Caso práctico de Contoso: llamadas de emergencia](voice-case-study-emergency-calling.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, ha implementado llamadas de emergencia para su organización.

## <a name="location-based-routing-for-direct-routing"></a>Enrutamiento de Location-Based para enrutamiento directo

En algunos países y regiones, no es ilegal eludir el proveedor de la red telefónica conmutada (RTC) para reducir los gastos de llamadas de larga distancia. Location-Based enrutamiento para enrutamiento directo le permite restringir el omisión de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. Para obtener más información sobre cómo planear y configurar Location-Based Routing (LBR), consulte los artículos siguientes:

- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Caso práctico de Contoso: enrutamiento de Location-Based](voice-case-study-location-based-routing.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementada Location-Based el enrutamiento de su organización.

## <a name="network-topology-for-voice-features"></a>Topología de red para características de voz

Si va a implementar las llamadas de emergencia dinámicas o el enrutamiento de Location-Based para el enrutamiento directo, debe configurar las opciones de red para su uso con estas características en Microsoft Teams. Para obtener información sobre cómo configurar las opciones de red para regiones de red, sitios de red, subredes de red y direcciones IP de confianza, consulte los artículos siguientes:

- [Configuración de red de las características de voz en la nube en Microsoft Teams: conceptos y terminología](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube en Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrar su solución de voz existente a teams

En el caso de una organización que está actualizando a Teams, el último objetivo es mover todos los usuarios al modo TeamsOnly. El uso del sistema telefónico con Teams solo se admite cuando el usuario está en modo TeamsOnly. Si necesita información básica sobre la actualización a Teams, empiece aquí:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Acerca del marco de actualización](upgrade-framework.md)
- [Actualizar de Skype empresarial a teams: para administradores de ti](upgrade-to-teams-on-prem-overview.md)

Al migrar la solución de voz, hay cuatro escenarios posibles de llamadas al pasar al modo TeamsOnly:

- [**Un usuario de Skype empresarial online con un plan de llamadas de Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Después de la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft.

- **[Un usuario de Skype empresarial online con funcionalidad de voz local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) a través de Skype empresarial local o Cloud Connector Edition**. La actualización del usuario a teams debe coordinarse con la migración del usuario al enrutamiento directo para garantizar que el usuario de TeamsOnly tiene la funcionalidad de RTC.

- **[Un usuario de Skype empresarial local con telefonía IP empresarial](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), que se va a migrar a en línea y mantener la conectividad RTC local**. Migrar este usuario a teams requiere mover la cuenta de Skype empresarial local del usuario a la nube y coordinar ese movimiento con la migración del usuario al enrutamiento directo. 

- **[Un usuario de Skype empresarial local con telefonía IP empresarial](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), que se va a migrar a en línea y usar un plan de llamadas de Microsoft**.  Migrar este usuario a teams requiere mover la cuenta de Skype empresarial local del usuario a la nube y coordinar el movimiento con una o A una) el puerto del número de ese usuario a un plan de llamadas de Microsoft o B asignar un nuevo número de suscriptor de las regiones disponibles.

Para obtener más información sobre cómo implementar la migración de voz para cada uno de estos escenarios &mdash; , incluida información sobre Cuándo es necesario configurar la conectividad híbrida y cómo migrar usuarios con funcionalidad de voz local para el enrutamiento directo, &mdash; consulte los artículos siguientes:

- [Consideraciones sobre RTC al actualizar a teams: para administradores de ti](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Caso práctico de migración de voz de Contoso](voice-case-study-overview.md)<br>
  El caso práctico describe cómo una corporación multinacional ficticia, Contoso, ha implementado una solución de voz de Teams para su organización. Contiene los artículos siguientes:

  - [Plan de actualización de Teams](voice-case-study-migration-plan.md)
  - [Opciones de conectividad RTC y sistema telefónico](voice-case-study-phone-system.md)
  - [Implementación de enrutamiento basada en la ubicación](voice-case-study-location-based-routing.md)
  - [Llamadas de emergencia](voice-case-study-emergency-calling.md)
  - [Operadores automáticos y las colas de llamadas](voice-case-study-call-queues.md)
  - [Audioconferencia](voice-case-study-audio-conferencing.md)












