---
title: Planee la solución de voz en Microsoft Teams
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
description: Obtenga más información sobre las Microsoft Teams de voz en la nube y las decisiones de implementación que tome para su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92b28a00e1737b533c17cf3f1f670bc23561620d
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689798"
---
# <a name="plan-your-teams-voice-solution"></a>Planear su Teams de voz 

Este artículo le ayuda a decidir qué solución de voz de Microsoft es la adecuada para su organización. Una vez que lo haya decidido, el artículo proporciona una hoja de ruta al contenido que le permitirá implementar la solución elegida.

> [!NOTE]
> Para obtener instrucciones sobre la planeación de una solución de voz Teams como parte de su plan general para actualizar Teams a Teams desde Skype Empresarial Server, vea Consideraciones rtc para actualizar Teams a Skype Empresarial [local.](upgrade-to-teams-on-prem-pstn-considerations.md)

Es posible que desee la solución más &mdash; sencilla Sistema telefónico con Plan de llamadas. Esta es la solución todo en la nube de Microsoft que proporciona funcionalidades de Exchange de sucursal privada (PBX) y llamadas a la red telefónica conmutada (RTC), como se muestra en el siguiente diagrama. Con esta solución, Microsoft es su operador RTC.

![Diagrama 1 muestra Sistema telefónico con plan de llamadas](media/voice-solutions-simple.png)

Si responde sí a lo siguiente, Sistema telefónico con Plan de llamadas es la solución adecuada para usted:

- Plan de llamadas está disponible en su región.
- No es necesario conservar el operador RTC actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Sin embargo, es posible que su situación sea más compleja. Por ejemplo, es posible que tenga oficinas en ubicaciones en las que el Plan de llamadas no esté disponible. También es posible que necesite una solución combinada compatible con una implementación compleja y multinacionales, con requisitos diferentes para ubicaciones geográficas diferentes. Microsoft admite una combinación de soluciones: 

- Sistema telefónico con plan de llamadas
- Sistema telefónico con su propio operador RTC con operador Conectar (disponible actualmente solo en **versión preliminar pública)**
- Sistema telefónico con su propio operador RTC con enrutamiento directo
- Una solución combinada que usa Sistema telefónico con plan de llamadas, Sistema telefónico con Conectar operador y/o Sistema telefónico con enrutamiento directo


## <a name="what-do-you-need-to-read"></a>¿Qué necesita leer?

**Necesario para todos.** Algunas de las secciones de este artículo pertenecen a todas las organizaciones. Por ejemplo, todos los usuarios deben leer Sistema telefónico y comprender las opciones para conectarse a la red telefónica conmutada (RTC). 


| Obligatorio para todos | Descripción |
| :------------|:-------|
| [**Sistema telefónico**](#phone-system) | Tecnología de Microsoft para habilitar el control de llamadas y las capacidades de Exchange de sucursales privadas (PBX) en la nube Microsoft 365 con Microsoft Teams. |
| [**Opciones de conectividad de red telefónica conmutada (RTC)**](#public-switched-telephone-network-connectivity-options) | Una opción entre usar Microsoft como operador de telefonía o conectar su propio operador de telefonía a Microsoft Teams mediante enrutamiento directo u operador Conectar. Combinadas Sistema telefónico, las opciones de conectividad RTC permiten a los usuarios realizar llamadas telefónicas en todo el mundo.|

**Según sus requisitos.** Algunas de las secciones de este artículo son pertinentes en función de la implementación y los requisitos existentes. Por ejemplo, Location-Based enrutamiento directo solo es necesario para los clientes de Enrutamiento directo en ubicaciones geográficas que no permiten la omisión de peaje.

Considere cuál de estas configuraciones adicionales puede necesitar:

![El diagrama 2 muestra componentes de voz adicionales, como Teléfono de Microsoft, Planes de marcado y enrutamiento de llamadas, y así sucesivamente.](media/voice-consider-additional-components.png)

| Según sus requisitos | Descripción |
| :------------|:-------|
| [**Teléfono de Microsoft**](#phone-numbers-from-microsoft) | Cómo obtener y administrar números de teléfono de Microsoft y cómo transferir números existentes a Microsoft. Lea esto si necesita obtener números de teléfono para Microsoft Calling Plan, transferir números existentes, obtener números de servicio, y así sucesivamente. |
| [**Planes de marcado y enrutamiento de llamadas**](#dial-plans-and-call-routing) | Cómo configurar y administrar planes de marcado que traducen los números de teléfono marcados a un formato alternativo (normalmente formato E.164) para la autorización de llamadas y el enrutamiento de llamadas. Lea esto si necesita comprender qué son los planes de marcado y si necesita especificar planes de marcado para su organización.|
| [**Llamadas de emergencia**](#emergency-calling) | Cómo administrar y configurar las llamadas de emergencia &mdash; en función de la opción de conectividad RTC. Lea esta sección si usa microsoft calling plan o enrutamiento directo y necesita comprender cómo administrar las llamadas de emergencia para su organización. |
| [**Enrutamiento basado en la ubicación para enrutamiento directo**](#location-based-routing-for-direct-routing) |Cómo usar el Location-Based de pago (LBR) para restringir la omisión de peaje para Microsoft Teams usuarios en función de su ubicación geográfica. Lea esta sección si su organización usa enrutamiento directo en una ubicación que no permite la omisión de peaje.
| [**Topología de red para características de voz en la nube**](#network-topology-for-voice-features) | Si su organización está implementando Location-Based Enrutamiento (LBR) para enrutamiento directo o llamadas de emergencia dinámicas, debe configurar la configuración de red para usarla con estas características en Microsoft Teams. Lea esta sección si está implementando LBR para enrutamiento directo o si está implementando llamadas de emergencia dinámicas con Plan de llamadas o Enrutamiento directo. |
| [**Migrar la solución de voz existente**](#migrate-your-existing-voice-solution-to-teams) | Qué debe pensar al migrar la solución de voz a Teams.  Lea esta sección si va a migrar desde una solución de voz existente a Teams. 



> [!Important]
> Este artículo se centra en las soluciones de voz con Microsoft Teams. Aunque las soluciones con Skype Empresarial Online siguen estando disponibles (como se describe en las soluciones de telefonía de [Microsoft),](/SkypeForBusiness/hybrid/msft-telephony-solutions)es importante comprender que Skype Empresarial Online se retirará el 31 de julio de 2021.  Después de esa fecha, el Skype Empresarial online ya no será accesible. Además, la conectividad RTC entre su entorno local ya sea a través de Skype Empresarial Server o Cloud Connector Edition y &mdash; Skype Empresarial Online ya no será &mdash; compatible. En este artículo se Teams soluciones de voz y cómo puede conectar su red de telefonía local, si es necesario, a Teams mediante enrutamiento directo u operador Conectar.


## <a name="phone-system"></a>Sistema telefónico

Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de Exchange de sucursales privadas (PBX) en la nube Microsoft 365 o Office 365 con Microsoft Teams.

Sistema telefónico funciona con Teams o Skype Empresarial clientes y dispositivos certificados. Sistema telefónico permite reemplazar el sistema PBX existente con un conjunto de características directamente entregado desde Microsoft 365 o Office 365. 

Las llamadas entre usuarios de su organización se controlan internamente dentro de Sistema telefónico y nunca van a la Red telefónica conmutada (RTC). Esto se aplica a las llamadas entre usuarios de su organización ubicados en diferentes áreas geográficas, lo que elimina los costos de larga distancia en estas llamadas internas.

En este artículo se presentan las Sistema telefónico características y funcionalidades clave y las decisiones de implementación que debe tener en cuenta:

- [Operadores automáticos y las colas de llamadas](#auto-attendants-and-call-queues)
- [Correo de voz en la nube](#cloud-voicemail)
- [Identidad de llamada](#calling-identity)

![El diagrama 3 muestra Teléfono con operadores automáticos y consultas de llamadas, correo de voz en la nube e identidad de llamadas](media/phone-system-contains.png)

Para obtener información sobre todas Sistema telefónico características y cómo configurar Sistema telefónico, vea los siguientes artículos:

- [Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)
- [Configurar Sistema telefónico en su organización](setting-up-your-phone-system.md)<br>
  Describe cómo comprar y asignar Sistema telefónico, administrar números de teléfono y configurar créditos de comunicación para números gratuitos. 

Para obtener información sobre la administración de dispositivos compatibles, vea Administrar los dispositivos en [Microsoft Teams](devices/device-management.md) y [Teams Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Operadores automáticos y colas de llamadas

Los operadores automáticos le permiten configurar opciones de menú para enrutar llamadas en función de la entrada de la persona que llama. Las colas de llamadas son áreas de espera para las personas que llaman. Usados juntos, los operadores automáticos y las colas de llamadas pueden enrutar fácilmente a los autores de llamadas a la persona o el departamento adecuados de su organización.

Para obtener información sobre operadores automáticos y colas de llamadas, vea los artículos siguientes:

- [Planear Teams operadores automáticos y colas de llamadas](plan-auto-attendant-call-queue.md)
- [Configurar un operador automático](create-a-phone-system-auto-attendant.md)
- [Crear una cola de llamada](create-a-phone-system-call-queue.md) 
- [Caso práctico de Contoso: Operadores automáticos y colas de llamadas](voice-case-study-call-queues.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó operadores automáticos y colas de llamadas para su solución de voz.

### <a name="cloud-voicemail"></a>Correo de voz en la nube

Correo de voz en la nube, con tecnología de los servicios de Correo de voz de Azure, admite los depósitos de correo de voz solo Exchange buzones. No es compatible con sistemas de correo electrónico de terceros. 

El correo de voz en la nube cuenta con la opción de transcripción del correo de voz, la cual está activada de forma predeterminada para todos los usuarios de la organización. Es posible que las necesidades empresariales requieran deshabilitar la transcripción del correo de voz para usuarios específicos o para todos los usuarios de la organización.

Para los usuarios solo en línea, Correo de voz en la nube se configura y aprovisiona automáticamente para los usuarios después de que se les asigne una Sistema telefónico licencia. Para Sistema telefónico usuarios con un buzón Exchange, deberá realizar pasos de configuración adicionales. 

Para obtener más información sobre Correo de voz en la nube y su configuración, vea los siguientes artículos:

- [Configurar el Correo de voz en la nube](set-up-phone-system-voicemail.md)
- [Establecer directivas de correo de voz en su organización](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada. Para obtener información sobre cómo configurar el identificador de llamada o para cambiar o bloquear el identificador de llamada, vea Establecer el identificador de llamada [para un usuario.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opciones de conectividad de red telefónica conmutada pública

Sistema telefónico proporciona funcionalidades de PBX completas para su organización. Sin embargo, para permitir a los usuarios realizar llamadas fuera de su organización, debe conectarse Sistema telefónico a la red telefónica conmutada (RTC). Para conectar Sistema telefónico a la RTC, puede elegir una de las siguientes opciones:

- [**Sistema telefónico con Plan de llamadas**](#phone-system-with-calling-plan). Una solución todo en la nube con Microsoft como operador rtc.

- [**Sistema telefónico con su propio operador RTC**](#phone-system-with-own-pstn-carrier-with-direct-routing) mediante enrutamiento directo para conectar su entorno local a Teams.

- [**Sistema telefónico con su propio**](operator-connect-plan.md)operador RTC mediante operador Conectar , que actualmente solo está disponible en **versión preliminar pública.**  Con Operador Conectar, si el operador existente es un participante en el programa operador de Microsoft Conectar, pueden administrar el servicio para llevar llamadas RTC a Teams. Para obtener información sobre las ventajas y requisitos de Operador Conectar y para obtener una lista de operadores que participan en este programa, vea [Plan operador Conectar](operator-connect-plan.md).

También puede elegir una combinación de opciones, que le permite diseñar una solución para un entorno complejo o administrar una migración de varios pasos (más información sobre la migración más adelante).

### <a name="phone-system-with-calling-plan"></a>Sistema telefónico con plan de llamadas 

Como se describe anteriormente en este artículo, Sistema telefónico con plan de llamadas es la solución de voz todo en la nube de Microsoft para Teams usuarios. Esta es la opción más sencilla que conecta Teléfono Microsoft System a la red telefónica conmutada (RTC) pública para habilitar las llamadas a fijos y teléfonos móviles de todo el mundo. Con esta opción, Microsoft proporciona funcionalidad de Exchange (PBX) privadas para su organización y actúa como operador RTC, como se muestra en el siguiente diagrama:

![El diagrama 4 muestra Sistema telefónico operadores automáticos, colas de llamadas, identificador de llamada y mucho más, y Microsoft como operador RTC](media/voice-solution-microsoft-complete.png)

Si responde sí a lo siguiente, Sistema telefónico con Plan de llamadas es la solución adecuada para usted:

- Plan de llamadas está disponible en su región.
- No es necesario conservar el operador RTC actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Con esta opción: 

- Obtiene un Teléfono Microsoft con planes de llamadas nacionales o internacionales agregados que permiten llamar a teléfonos de todo el mundo (dependiendo del nivel de servicio que se esté autorizando).

- No requiere la implementación o el mantenimiento de una implementación local porque el plan de llamadas funciona Microsoft 365 &mdash; o Office 365.

- Nota: Si es necesario, puede elegir conectar un controlador de borde de sesión (SBC) compatible a través del enrutamiento directo para la interoperabilidad con PBX de terceros, dispositivos analógicos y otros equipos de telefonía de terceros compatibles con el SBC.

Esta opción requiere una conexión sin interrupciones a Microsoft 365 o Office 365.

Para obtener más información sobre el plan de llamadas, vea los artículos siguientes:

- [¿Qué plan de llamada es adecuado para usted?](calling-plan-landing-page.md)
- [Cómo comprar un plan de llamadas](calling-plans-for-office-365.md)
- [Países y regiones donde el Plan de llamadas está disponible](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurar plan de llamadas](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema telefónico con un operador RTC propio con enrutamiento directo

Esta opción conecta Teléfono Microsoft sistema a su red de telefonía mediante enrutamiento directo, como se muestra en el siguiente diagrama: 

![Diagrama 5 muestra Sistema telefónico con enrutamiento directo](media/voice-solution-with-direct-routing.png)

Si responde sí a las siguientes preguntas, Sistema telefónico enrutamiento directo es la solución adecuada para usted:

- Desea usar Teams con Sistema telefónico.
- Debe conservar el operador RTC actual.
- Desea mezclar el enrutamiento, con algunas llamadas pasando por el Plan de llamadas, otras a través de su operador.
- Necesita interoperar con PBX y/o equipos de terceros, como los paginadores generales, dispositivos analógicos, entre otros.

Con esta opción:

- Conecta su propio SBC compatible con Teléfono Microsoft system sin necesidad de software local adicional.

- Puede usar prácticamente cualquier operador de telefonía con Teléfono Microsoft System.

- Puede configurar y administrar esta opción, o puede configurarla y administrarla su operador o partner (pregunte si su operador o partner proporciona esta opción).

- Puede configurar la interoperabilidad entre los equipos de telefonía, como pbx de terceros y &mdash; dispositivos analógicos &mdash; y Teléfono Microsoft sistema.


Esta opción requiere lo siguiente:

- Conexión ininterrumpida a Microsoft 365 o Office 365.

- Implementar y mantener un SBC compatible.

- Un contrato con un operador de terceros.
  (A menos que se implemente como una opción para proporcionar conexión a PBX de terceros, dispositivos analógicos u otro equipo de telefonía para los usuarios que están en Sistema telefónico con plan de llamadas).

Para obtener más información sobre enrutamiento directo, vea los artículos siguientes:

- [Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)
- [Planear el enrutamiento directo](direct-routing-plan.md)
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Administrar directivas de enrutamiento de voz para su uso con Enrutamiento directo](manage-voice-routing-policies.md)
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Teléfono de Microsoft

Microsoft tiene dos tipos de números de teléfono *disponibles:* números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización, y números de servicio, disponibles como números de servicio gratuitos y de pago.  Los números de servicio tienen mayor capacidad de llamada simultánea que los números de suscriptor y se pueden asignar a servicios como Audioconferencia, Operadores automáticos o Colas de llamadas.

Tendrá que decidir lo siguiente:

- ¿Qué ubicaciones de usuario necesitan nuevos números de teléfono de Microsoft?
- ¿Qué tipo de número de teléfono (suscriptor o servicio) necesito? 
- ¿Cómo puedo portabilidad de números de teléfono existentes a Teams?

Para obtener más información sobre cómo administrar números de teléfono en su organización, como obtener números nuevos o transferir números de salida, vea los siguientes artículos:

- [Administrar los números de teléfono de la organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Diferentes tipos de números de teléfono usados para el plan de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md)
- [Transferir números de teléfono a Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Planes de marcado y enrutamiento de llamadas

Un plan de marcado es un conjunto de reglas de normalización que traducen los números de teléfono marcados a un formato alternativo (normalmente formato E.164) para la autorización de llamadas y el enrutamiento de llamadas.

Tendrá que decidir lo siguiente: 

- ¿Mi organización necesita un plan de marcado personalizado?
- ¿Qué usuarios requieren un plan de marcado personalizado?
- ¿Qué plan de marcado de inquilino se debe asignar a cada usuario?

Para obtener más información, vea los artículos siguientes: 

- [¿Qué son los planes de marcado?](what-are-dial-plans.md)
- [Planear planes de marcado de inquilinos](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Crear y administrar planes de marcado](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Llamadas de emergencia

La forma en que configura las llamadas de emergencia varía en función de la opción de conectividad RTC: Plan de llamadas de Microsoft o Enrutamiento directo. Las llamadas de emergencia dinámicas para Microsoft Calling Plan y Sistema telefónico Direct Routing ofrecen la capacidad de configurar y enrutar llamadas de emergencia y notificar al personal de seguridad en función de la ubicación actual del Teams cliente. Para obtener más información sobre conceptos y terminología de llamadas de emergencia y cómo configurar llamadas de emergencia dinámicas, vea los siguientes artículos:

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
- [Caso práctico de Contoso: Llamadas de emergencia](voice-case-study-emergency-calling.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó llamadas de emergencia para su organización.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based enrutamiento directo

En algunos países y regiones, es ilegal omitir el proveedor de red telefónica conmutada (RTC) para reducir los costos de llamadas de larga distancia. Location-Based enrutamiento directo le permite restringir la omisión de peaje para Microsoft Teams usuarios en función de su ubicación geográfica. Para obtener más información sobre cómo planear y configurar Location-Based enrutamiento (LBR), vea los siguientes artículos:

- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Caso práctico de Contoso: Location-Based enrutamiento](voice-case-study-location-based-routing.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó Location-Based enrutamiento para su organización.

## <a name="network-topology-for-voice-features"></a>Topología de red para características de voz

Si va a implementar llamadas de emergencia dinámicas o Location-Based enrutamiento directo, debe configurar la configuración de red para usarla con estas características en Microsoft Teams. Para obtener información sobre cómo configurar la configuración de red para regiones de red, sitios de red, subredes de red y direcciones IP de confianza, vea los siguientes artículos:

- [Configuración de red para las características de voz en la nube Microsoft Teams: conceptos y terminología](cloud-voice-network-settings.md)
- [Administre la topología de red para las características de voz en la nube en Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrar la solución de voz existente a Teams

Para una organización que está actualizando a Teams, el objetivo final es mover todos los usuarios al modo TeamsOnly. El Sistema telefónico con Teams solo es compatible cuando el usuario está en modo TeamsOnly. Si necesita información básica sobre cómo actualizar a Teams, empiece aquí:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Acerca del marco de actualización](upgrade-framework.md)
- [Estrategias de actualización para administradores de TI](upgrade-to-teams-on-prem-implement.md)

Al migrar la solución de voz, hay cuatro posibles escenarios de llamadas al pasar al modo TeamsOnly:

- [**Un usuario en Skype Empresarial online, con un plan de llamadas de Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Tras la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft.

- **[Un usuario en Skype Empresarial Online,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** con funcionalidad de voz local a través Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.

- **[Un usuario de Skype Empresarial local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** con Telefonía IP empresarial , que se trasladará a internet y mantendrá la conectividad RTC local. Migrar este usuario Teams requiere mover la cuenta de Skype Empresarial local del usuario Skype Empresarial la nube y coordinar ese movimiento con la migración del usuario a Enrutamiento directo. 

- **[Un usuario de Skype Empresarial local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** con Telefonía IP empresarial , que se trasladará a internet y usará un plan de Microsoft Calling.  Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local del usuario Skype Empresarial la nube y coordinar que se muevan con cualquiera de las dos A) el puerto del número de teléfono de ese usuario a un Plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor de las regiones disponibles.

Para obtener más información sobre cómo implementar la migración de voz para cada uno de estos escenarios, incluida información sobre cuándo necesita configurar la conectividad híbrida y cómo migrar usuarios con funcionalidad de voz local a Enrutamiento directo, vea los siguientes &mdash; &mdash; artículos:

- [Consideraciones RTC al actualizar a Teams para administradores de TI](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Caso práctico de migración de voz de Contoso](voice-case-study-overview.md)<br>
  El caso práctico describe cómo una corporación multinacional ficticia, Contoso, implementó una solución de voz Teams para su organización. Contiene los siguientes artículos:

  - [Teams plan de actualización](voice-case-study-migration-plan.md)
  - [Sistema telefónico y las opciones de conectividad RTC](voice-case-study-phone-system.md)
  - [Implementación de enrutamiento basado en ubicación](voice-case-study-location-based-routing.md)
  - [Llamadas de emergencia](voice-case-study-emergency-calling.md)
  - [Operadores automáticos y las colas de llamadas](voice-case-study-call-queues.md)
  - [Audioconferencia](voice-case-study-audio-conferencing.md)