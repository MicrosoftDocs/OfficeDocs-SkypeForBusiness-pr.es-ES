---
title: Opciones de conectividad RTC
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
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
description: Obtenga más información sobre Teams de llamadas (conectividad RTC) y las decisiones que tome para su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53b553a83349c3d4fd20a926f29b4c727175c73aba5ba0f5e352cf19a53f9e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285946"
---
# <a name="pstn-connectivity-options"></a>Opciones de conectividad RTC

Microsoft proporciona funcionalidades completas de Exchange de sucursal privada (PBX) para su organización a través de Sistema telefónico. Sin embargo, para permitir a los usuarios realizar llamadas fuera de la organización, debe conectarse Sistema telefónico a la red telefónica conmutada (RTC).

Este artículo se centra en las opciones de conectividad RTC. Para obtener más información acerca de las soluciones de voz de Microsoft, incudiendo en detalles sobre Sistema telefónico características, vea [Plan your Teams voice solution](cloud-voice-landing-page.md).

Para conectar Sistema telefónico a la RTC, puede elegir entre las siguientes opciones:

- [**Plan de llamadas**](#phone-system-with-calling-plan). Una solución todo en la nube con Microsoft como proveedor de RTC.

- [**Operador Conectar**](#phone-system-with-operator-connect), que actualmente solo está disponible en **versión preliminar pública.**  Con Operator Conectar, si el operador existente es un participante en el programa operador de Microsoft Conectar, pueden administrar llamadas RTC y controladores de borde de sesión (SBC). 

- [**Enrutamiento directo**](#phone-system-with-direct-routing), que permite usar su propio operador RTC conectando los controladores de borde de sesión (SBC) a Sistema telefónico.


También puede elegir una combinación de opciones, lo que le permite diseñar una solución para un entorno complejo o administrar una migración de varios pasos.

Ten en cuenta que la opción o las opciones que elijas afectan a la configuración de algunas Sistema telefónico características. Para obtener más información, vea [Consideraciones de configuración](#configuration-considerations) más adelante en este artículo.


## <a name="phone-system-with-calling-plan"></a>Sistema telefónico con plan de llamadas 

Sistema telefónico con plan de llamadas es la solución de voz de Microsoft todo en la nube para Teams usuarios. Esta es la opción más sencilla que se conecta Sistema telefónico a la RTC. Con esta opción, Microsoft actúa como su portador de RTC, como se muestra en el siguiente diagrama:

![El diagrama 1 muestra Sistema telefónico con plan de llamadas](media/voice-solutions-simple.png)

Si responde sí a lo siguiente, Sistema telefónico con plan de llamadas es la solución adecuada para usted:

- El plan de llamadas está disponible en su región.
- No es necesario conservar el operador RTC actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Con esta opción: 

- Obtiene el sistema telefónico de Microsoft con planes de llamadas nacionales o internacionales agregados que permiten llamar a teléfonos en todo el mundo (en función del nivel de servicio que se licencia).

- No es necesario implementar ni mantener una implementación local porque el plan de llamadas funciona &mdash; sin Microsoft 365.

- Nota: Si es necesario, puede elegir conectar un controlador de borde de sesión (SBC) compatible a través del enrutamiento directo para la interoperabilidad con PBX de terceros, dispositivos analógicos y otros equipos de telefonía de terceros compatibles con el SBC.

Esta opción requiere una conexión sin interrupciones a Microsoft 365.

Para obtener más información acerca del plan de llamadas, consulte los artículos siguientes:

- [¿Qué plan de llamada es adecuado para usted?](calling-plan-landing-page.md)
- [Cómo comprar un plan de llamadas](calling-plans-for-office-365.md)
- [Disponibilidad de país y región para plan de llamadas](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurar plan de llamadas](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>Sistema telefónico con operador Conectar

Con Operator Conectar, actualmente en versión preliminar pública, si su operador existente es un participante en el programa operador de Microsoft Conectar, puede administrar el servicio para llevar llamadas RTC a Teams. Su operador administra los servicios de llamadas RTC y los controladores de borde de sesión (SBC), lo que le permite ahorrar en la compra y administración de hardware.

La Conectar operador puede ser la solución adecuada para su organización si:

- Microsoft Calling Plan no está disponible en su ubicación geográfica.
- Su operador preferido es un participante en el programa de Conectar microsoft.
- Desea encontrar un nuevo operador para habilitar las llamadas en Teams.

Para obtener información sobre las ventajas y los requisitos del operador Conectar, y para obtener una lista de los operadores que participan en este programa, vea [Plan Operator Conectar](operator-connect-plan.md). Para obtener información sobre cómo configurar el operador Conectar, vea [Configure Operator Conectar](operator-connect-configure.md).


## <a name="phone-system-with-direct-routing"></a>Sistema telefónico con enrutamiento directo

Esta opción conecta Sistema telefónico a la red de telefonía mediante enrutamiento directo, como se muestra en el siguiente diagrama: 

![El diagrama 5 muestra Sistema telefónico con enrutamiento directo](media/voice-solution-with-direct-routing.png)

El sistema telefónico con Enrutamiento directo podría ser la solución adecuada para usted si responde sí a las siguientes preguntas:

- Quiere usar Teams con el sistema telefónico.
- Debe conservar su operador RTC actual.
- Quiere un enrutamiento mixto, con algunas llamadas que van a través del plan de llamadas y otras a través de su operador.
- Debe interoperar con PBX y/o equipos de terceros, como paginadores de sobrecarga, dispositivos analógicos, entre otros.

Con esta opción:

- Conecte su propio controlador de borde de sesión (SBC) compatible Sistema telefónico sin necesidad de software local adicional.

- Puede usar prácticamente cualquier operador de telefonía con Sistema telefónico.

- Puede elegir configurar y administrar esta opción, o bien puede configurarla y administrarla el operador o asociado (pregunte si su operador o asociado proporciona esta opción).

- Puede configurar la interoperabilidad entre los equipos de telefonía, como una PBX de terceros y &mdash; dispositivos analógicos &mdash; y Sistema telefónico.

Esta opción requiere lo siguiente:

- Conexión sin interrupciones a Microsoft 365.

- Implementar y mantener un SBC compatible.

- Un contrato con un operador tercero. (A menos que se implemente como una opción para ofrecer la conexión a PBX de terceros, dispositivos analógicos u otros equipos de telefonía para los usuarios que tienen Sistema telefónico con Plan de llamadas).

Para obtener más información acerca del enrutamiento directo, vea los siguientes artículos:

- [Planear el enrutamiento directo](direct-routing-plan.md)
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Administrar directivas de enrutamiento de voz para su uso con Enrutamiento directo](manage-voice-routing-policies.md)
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Lista de controladores de borde de sesión certificados para el Enrutamiento directo](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Consideraciones de configuración

La mayoría Sistema telefónico características son las mismas independientemente de la opción de conectividad RTC que elija. Por ejemplo, la configuración de llamadas sin respuesta y reenvío, la transferencia de llamadas, la música personalizada en espera, el estacionamiento de llamadas, la línea compartida y las aplicaciones de voz están disponibles. Para obtener una lista completa de Sistema telefónico características, vea [Here's what you get with Sistema telefónico](here-s-what-you-get-with-phone-system.md).

Sin embargo, existen algunas diferencias en la funcionalidad que afectan a la forma en que se configuran determinadas Sistema telefónico características. Por ejemplo, El enrutamiento directo requiere pasos adicionales para configurar el enrutamiento de llamadas. Como otro ejemplo, El enrutamiento directo proporciona enrutamiento basado en ubicaciones (LBR), de modo que puede restringir la omisión de peaje en determinadas ubicaciones geográficas donde no está permitido. 

En la tabla siguiente se resaltan las diferencias de configuración principales. Las secciones que siguen a la tabla proporcionan vínculos a más información y detalles.

| Opción | Descripción | Teléfono de números | Enrutamiento de llamada | Disponibilidad de llamadas de emergencia |
| :------------| :-------| :-------| :-------| :-------| 
| Planes de llamadas | -Microsoft actúa como operador RTC.<br>-No es necesario comprar ni administrar SBC.| Obtenido a través de Microsoft.| -Administrado por Microsoft. <br> -Admin configura los planes de marcado de usuario para la traducción de números. | -Enabled by Microsoft. <br> -Admin registra direcciones. <br> -Se admiten llamadas dinámicas. |
| Conexión con operador | -Carrier administra la conectividad RTC y los SBC. <br> -No es necesario comprar ni administrar SBC. | -Obtenido a través del operador. <br> - Números asociados con direcciones de emergencia administradas por el operador.  | -Administrado por el operador. <br>-Admin configura los planes de marcado de usuario para la traducción de números. | -Enabled by carrier. <br> -Admin registra direcciones. <br> -Se admiten llamadas dinámicas. |
| Enrutamiento directo | -Requiere SBC certificado comprado a un proveedor externo.<br>-Conectar SBC a Sistema telefónico.<br> -Use el operador RTC existente. | Obtenido a través del operador. | -Requiere una configuración adicional por parte del administrador.<br>-Admin configura los planes de marcado troncal para la traducción de números. <br>-LBR disponible para restringir la omisión de peaje. | -Requiere una configuración adicional por parte del administrador. <br>-Las direcciones registradas no son compatibles. <br>-Dynamic calling supported but requires additional configuration. |
|||||


### <a name="phone-number-management"></a>Teléfono de números

Microsoft tiene dos tipos de números de teléfono disponibles: números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización, y números de servicio, disponibles como números de servicio gratuitos y gratuitos. Los números de servicio tienen mayor capacidad de llamada simultánea que los números de suscriptor y se pueden asignar a servicios como Audioconferencia, Operadores automáticos o Colas de llamadas.

Tendrá que decidir:

- ¿Qué ubicaciones de usuario necesitan nuevos números de teléfono de Microsoft?
- ¿Qué tipo de número de teléfono (suscriptor o servicio) necesito?
- ¿Cómo puedo portabilidad de números de teléfono existentes a Teams?

La forma de adquirir y administrar números de teléfono varía en función de la opción de conectividad RTC.

- Para obtener información acerca de la administración de números de teléfono para el plan de llamadas, vea [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para obtener información acerca de la administración de números de teléfono con operador Conectar, vea Configurar números [de teléfono con operador Conectar](operator-connect-configure.md#set-up-phone-numbers).

- Para obtener información sobre cómo administrar números de teléfono para enrutamiento directo, vea [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).


### <a name="call-routing-and-dial-plans"></a>Planes de marcado y enrutamiento de llamadas

La forma en que se configura el enrutamiento de llamadas varía en función de la opción de conectividad RTC.  

- En el caso de los planes de llamadas, la mayor parte del enrutamiento de llamadas se controla mediante la infraestructura del Plan de llamadas de Microsoft. Configure los planes de marcado de usuario para fines de traducción de números para la autorización de llamadas y el enrutamiento de llamadas. Para obtener más información, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).

- En el caso Conectar operador, la mayoría del enrutamiento de llamadas lo administra el operador.  Configure los planes de marcado de usuario para fines de traducción de números para la autorización de llamadas y el enrutamiento de llamadas. Para obtener más información, vea [¿Qué son los planes de marcado?](what-are-dial-plans.md).

- Para enrutamiento directo, debe configurar el enrutamiento de llamadas especificando las rutas de voz y asignando directivas de enrutamiento de voz a los usuarios. Puede configurar planes de marcado para la traducción de números en el nivel de tronco para garantizar la interoperabilidad con los controladores de borde de sesión (SBC). Para obtener más información, vea [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), Manage voice routing [policies](manage-voice-routing-policies.md) y Translate [phone numbers](direct-routing-translate-numbers.md). 


### <a name="location-based-routing-for-direct-routing"></a>Enrutamiento basado en la ubicación para Enrutamiento directo

En algunos países y regiones, es ilegal omitir el operador RTC para reducir los costos de llamadas de larga distancia. Location-Based routing (LBR) para enrutamiento directo permite restringir la omisión de Teams usuarios en función de su ubicación geográfica. Para obtener más información acerca de cómo planear y configurar LBR, consulte los siguientes artículos:

- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Caso práctico de Contoso: Location-Based enrutamiento](voice-case-study-location-based-routing.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó Location-Based enrutamiento para su organización.


### <a name="emergency-calling"></a>Llamadas de emergencia

La forma en que se configuran las llamadas de emergencia varía en función de la opción de conectividad RTC.

- Para el Plan de llamadas, cada usuario se habilita automáticamente para llamadas de emergencia y es necesario que tenga una dirección de emergencia registrada asociada con su número de teléfono asignado. Se admiten llamadas de emergencia dinámicas (en función de la ubicación del Teams cliente).  

- Para el operador Conectar, cada usuario está habilitado automáticamente para llamadas de emergencia y es necesario que tenga una dirección de emergencia registrada asociada con su número de teléfono asignado, pero solo puede ser establecida por el partner del operador. Se admiten llamadas de emergencia dinámicas (en función de la ubicación del Teams cliente).

- Para enrutamiento directo, debe definir directivas de llamadas de emergencia para los usuarios mediante una directiva de enrutamiento de llamadas de emergencia de Teams (TeamsEmergencyCallRoutingPolicy) para definir los números de emergencia y su destino de enrutamiento asociado. Las ubicaciones de emergencia registradas no son compatibles con los usuarios de enrutamiento directo. Para las llamadas de emergencia dinámicas, se requiere una configuración adicional para enrutar llamadas de emergencia y, posiblemente, para la conectividad de asociados.

Para obtener más información acerca de los conceptos y terminología de llamadas de emergencia y cómo configurar llamadas de emergencia y llamadas de emergencia dinámicas, consulte los artículos siguientes:

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md)
- [Caso práctico de Contoso: llamada de emergencia](voice-case-study-emergency-calling.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó llamadas de emergencia para su organización.


### <a name="network-topology-for-voice-features"></a>Topología de red para características de voz

Si va a implementar llamadas de emergencia dinámicas o enrutamiento Location-Based para enrutamiento directo, debe configurar la configuración de red para su uso con estas características en Microsoft Teams. Para obtener información sobre cómo configurar la configuración de red para regiones de red, sitios de red, subredes de red y direcciones IP de confianza, consulte los artículos siguientes:

- [Configuración de red para las características de voz en la nube Microsoft Teams: conceptos y terminología](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube en Microsoft Teams](manage-your-network-topology.md)



