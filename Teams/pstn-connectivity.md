---
title: Opciones de conectividad con RTC
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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Obtenga más información sobre las opciones de llamadas de Teams (conectividad RTC) y las decisiones que tome para su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f547528f39e92be1660f670cad44c66726fe3ef2
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999645"
---
# <a name="pstn-connectivity-options"></a>Opciones de conectividad con RTC

Microsoft proporciona funcionalidades completas de la central de intercambio privado (PBX) para su organización a través del sistema telefónico. Sin embargo, para permitir que los usuarios realicen llamadas fuera de su organización, debe conectar el sistema telefónico a la red telefónica conmutada (RTC).

Este artículo se centra en las opciones de conectividad de RTC. Para obtener más información sobre las soluciones de voz de Microsoft, incluidos los detalles sobre las características de Sistema telefónico, consulte [Planear la solución de voz de Teams](cloud-voice-landing-page.md).

Para conectar El sistema telefónico a la RTC, puede elegir entre las siguientes opciones:

- [**Plan de llamadas**](#phone-system-with-calling-plan). Una solución todo en la nube con Microsoft como su operador de RTC.

- [**Operador Conectar**](#phone-system-with-operator-connect). Con Operador Connect, si su operador actual participa en el programa Microsoft Operator Connect, puede administrar las llamadas RTC y los controladores de borde de sesión (SCS).

- [**Operador de conexión móvil**](#phone-system-with-operator-connect-mobile). Con Operador de conexión móvil, el número de teléfono habilitado para SIM de un usuario también es su número de teléfono de Teams. Si su operador actual participa en el programa microsoft Operador de conexión móvil, puede administrar el servicio para llevar las llamadas RTC a Teams.  **Operador de conexión móvil es una versión preliminar pública.**

- [**Enrutamiento directo**](#phone-system-with-direct-routing), que le permite usar su propio operador RTC conectando los controladores de borde de sesión (SBC) con el sistema telefónico.

También puede elegir una combinación de opciones, lo que le permite diseñar una solución para un entorno complejo o administrar una migración de varios pasos.

Las opciones que elijas afectan a la forma en que se configuran algunas características del sistema telefónico. Para obtener más información, vea [Consideraciones de configuración](#configuration-considerations) más adelante en este artículo.

## <a name="phone-system-with-calling-plan"></a>Sistema telefónico con plan de llamadas

Sistema telefónico con plan de llamadas es la solución de voz todo en la nube de Microsoft para los usuarios de Teams. Esta solución es la opción más sencilla que conecta El sistema telefónico a la RTC. Con esta opción, Microsoft actúa como su operador de RTC, como se muestra en el siguiente diagrama:

![El diagrama 1 muestra el sistema telefónico con plan de llamadas.](media/voice-solutions-simple.png)

Si responde sí a lo siguiente, sistema telefónico con plan de llamadas es la solución adecuada para usted:

- Plan de llamadas está disponible en su región.
- No es necesario que conserve su operador DE RTC actual.
- Desea usar el acceso administrado por Microsoft a la RTC.

Con esta opción:

- Obtiene Sistema telefónico con planes de llamadas nacionales o internacionales agregados que permiten llamar a teléfonos de todo el mundo (en función del nivel de servicio que se tenga licencia).

- No requiere la implementación o el mantenimiento de una implementación&mdash;local porque el plan de llamadas funciona con Microsoft 365.

- Nota: Puede conectar un controlador de borde de sesión compatible (SBC) a través del enrutamiento directo para interoperabilidad con PBX de terceros, dispositivos analógicos y otros equipos de telefonía compatibles con el SBC.

Esta opción requiere una conexión ininterrumpida a Microsoft 365.

Para obtener más información sobre el plan de llamadas, vea los siguientes artículos:

- [¿Qué plan de llamada es adecuado para usted?](calling-plan-landing-page.md)
- [Cómo comprar un plan de llamadas](calling-plans-for-office-365.md)
- [Países y regiones donde el Plan de llamadas está disponible](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurar el plan de llamadas](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>Sistema telefónico con operador Conectar

Con Operador Connect, si su operador actual participa en el programa Microsoft Operator Connect, puede administrar el servicio para llevar las llamadas RTC a Teams. Su operador administra los servicios de llamadas RTC y los controladores de borde de sesión (SCS), lo que le permite ahorrar en la compra y administración de hardware.

Operator Connect podría ser la solución adecuada para su organización si:

- El plan de llamadas de Microsoft no está disponible en su ubicación geográfica.
- Su operador preferido es un participante en el programa Microsoft Operator Connect.
- Desea buscar un nuevo operador para habilitar las llamadas en Teams.

Para obtener información sobre las ventajas y requisitos de Operator Connect, así como para obtener una lista de los operadores que participan en este programa, consulte [Planificar Operador Connect](operator-connect-plan.md). Para obtener información sobre cómo configurar Operator Connect, consulta [Configurar Operator Connect](operator-connect-configure.md).

## <a name="phone-system-with-operator-connect-mobile"></a>Sistema telefónico con Operador de conexión móvil

**Operador de conexión móvil es una versión preliminar pública.**

Si su operador actual participa en el programa microsoft Operador de conexión móvil, puede administrar el servicio para llevar las llamadas RTC a Teams. Con Operador de conexión móvil, el número de teléfono habilitado para SIM de un usuario también es su número de teléfono de Teams.  Los usuarios pueden usar un solo número de teléfono en Microsoft Teams, tanto en el servicio móvil como en el escritorio.  

Puede considerar una combinación de servicios. Por ejemplo, puede elegir Operador de conexión móvil para las organizaciones de ventas y de campo que requieren soporte técnico móvil, pero otra solución para su organización del centro de llamadas in situ que se base en teléfonos de escritorio. 

Operador de conexión móvil puede ser la solución adecuada para su organización si:

- Desea usar un número de teléfono móvil principal habilitado para SIM propiedad de la empresa para Teams Phone como una solución de número único.
- Su operador preferido es un participante en el programa microsoft Operador de conexión móvil.
- Desea buscar un nuevo operador para habilitar las llamadas en Teams.

Para obtener información sobre los beneficios y requisitos de Operador de conexión móvil, y para obtener vínculos a operadores que participan en este programa, consulte [Planear Operador de conexión móvil](operator-connect-mobile-plan.md). Para obtener información sobre cómo configurar Operador de conexión móvil, vea [Configurar Operador de conexión móvil](operator-connect-mobile-configure.md).

## <a name="phone-system-with-direct-routing"></a>Sistema telefónico con enrutamiento directo

Esta opción conecta El sistema telefónico a su red de telefonía mediante enrutamiento directo, como se muestra en el siguiente diagrama: 

![El diagrama 5 muestra el sistema telefónico con enrutamiento directo.](media/voice-solution-with-direct-routing.png)

Si respondes sí a las siguientes preguntas, sistema telefónico con enrutamiento directo es la solución adecuada para ti:

- Desea usar Teams con Sistema telefónico.
- Debe conservar su operador de RTC actual.
- Desea mezclar el enrutamiento, con algunas llamadas que pasan por Plan de llamadas, algunas a través de su operador.
- Debe interoperar con PBX de terceros o con equipos como re páges superior, dispositivos analógicos, etc.

Con esta opción:

- Conecta tu propio controlador de borde de sesión compatible (SBC) al sistema telefónico sin necesidad de software local adicional.

- Puede usar prácticamente cualquier operador de telefonía con Sistema telefónico.

- Puede configurar y administrar esta opción, o bien la puede configurar y administrar su operador o partner (pregunte si su operador o partner proporciona esta opción).

- Puede configurar la interoperabilidad entre su equipo&mdash;de telefonía, como PBX de terceros, dispositivos&mdash;analógicos y sistema telefónico.

Esta opción requiere lo siguiente:

- Conexión sin interrupciones a Microsoft 365.

- Implementar y mantener un SBC compatible.

- Un contrato con un transportista de terceros.
  (A menos que se implemente como opción para proporcionar conexión a PBX de terceros, dispositivos analógicos u otro equipo de telefonía para los usuarios que se encuentran en El sistema telefónico con plan de llamadas).

Para obtener más información sobre el enrutamiento directo, vea los artículos siguientes:

- [Planear el enrutamiento directo](direct-routing-plan.md)
- [Configurar el enrutamiento directo](direct-routing-configure.md)
- [Administrar directivas de enrutamiento de voz para usarlas con enrutamiento directo](manage-voice-routing-policies.md)
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Lista de controladores de borde de sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>Consideraciones de configuración

La mayoría de las características del sistema telefónico son las mismas independientemente de la opción de conectividad con RTC que elija. Por ejemplo, la configuración de llamadas no respondidas y de desvío, la transferencia de llamadas, la música personalizada en espera, el parque de llamadas, la línea compartida y las aplicaciones de voz están disponibles. Para obtener una lista completa de las características del sistema telefónico, consulta [Esto es lo que obtienes con Sistema telefónico](here-s-what-you-get-with-phone-system.md).

Sin embargo, hay algunas diferencias en la funcionalidad que afectan a la forma de configurar determinadas características del sistema telefónico. Por ejemplo, enrutamiento directo requiere pasos adicionales para configurar el enrutamiento de llamadas. Como otro ejemplo, Enrutamiento directo proporciona enrutamiento basado en ubicación (LBR). LBR le permite restringir la omisión de peaje en determinadas ubicaciones geográficas donde no está permitido. 

En la tabla siguiente se resaltan las diferencias de configuración principales. Las secciones que siguen a la tabla proporcionan vínculos a más información y detalles.

| Opción | Descripción | Administración de números de teléfono | Enrutamiento de llamada | Disponibilidad de llamadas de emergencia |
| :------------| :-------| :-------| :-------| :-------| 
| Planes de llamadas | -Microsoft actúa como operador de RTC.<br>-No es necesario comprar ni administrar SBCs.| Obtenido a través de Microsoft.| - Administrado por Microsoft. <br> -Administración configura los planes de marcado del usuario para la traducción de números. | -Habilitado por Microsoft. <br> -Administración registra direcciones. <br> -Llamadas dinámicas admitidas. |
| Operator Connect | -Carrier administra la conectividad RTC y los SBA. <br> -No es necesario comprar ni administrar SBCs. | -Obtenido a través del transportista. <br> - Números asociados a direcciones de emergencia administradas por el transportista. | -Administrado por el transportista. <br>-Administración configura los planes de marcado del usuario para la traducción de números. | -Habilitado por el operador. <br> -Administración registra direcciones. <br> -Llamadas dinámicas admitidas. |
| Operador de conexión móvil | -Carrier administra SIM-Enabled número móvil, conectividad CON RTC y SBCs. <br> -No es necesario comprar ni administrar SBCs. | -Obtenido a través del transportista. <br> -Números asociados a direcciones de emergencia administradas por el operador. | -Administrado por el transportista. <br> Administración configura los planes de marcado del usuario para la traducción de números. |- Habilitado por el operador. <br> - Administración registra direcciones. <br> - Llamadas dinámicas admitidas. <br> - Operador compatible Llamadas de emergencia con marcador nativo. |
| Enrutamiento directo | -Requiere SBC certificado comprado a un proveedor de terceros.<br>-Conecta tu SBC al sistema telefónico.<br> -Use su operador DE RTC existente. | Obtenido a través del transportista. | -Requiere configuración adicional por parte del administrador.<br>-Administración configura los planes de marcado troncal para la traducción de números. <br>-LBR disponible para restringir la omisión de pago. | -Requiere configuración adicional por parte del administrador. <br>-Direcciones registradas no admitidas. <br>-Llamada dinámica compatible, pero requiere configuración adicional. |


### <a name="phone-number-management"></a>Administración de números de teléfono

Microsoft tiene dos tipos de números de teléfono disponibles: números de suscriptor (usuarios), que se pueden asignar a usuarios de su organización, y números de servicio, disponibles como números de servicio de pago y gratuitos. Los números de servicio tienen una mayor capacidad de llamadas simultáneas que los números de suscriptor y se pueden asignar a servicios como Audioconferencia, Operadores automáticos o Colas de llamadas.

Tendrás que decidir lo siguiente:

- ¿Qué ubicaciones de usuario necesitan números de teléfono nuevos de Microsoft?
- ¿Qué tipo de número de teléfono (suscriptor o servicio) necesito?
- Cómo transferir los números de teléfono existentes a Teams?

La forma de adquirir y administrar números de teléfono varía según la opción de conectividad con RTC.

- Para obtener información sobre la administración de números de teléfono para el plan de llamadas, vea [Administrar números de teléfono para planes de llamadas](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para obtener información sobre la administración de números de teléfono con Operador de conexión, consulta [Configurar números de teléfono con Operador conectar](operator-connect-configure.md#set-up-phone-numbers).

- Para obtener información sobre cómo administrar números de teléfono con Operador de conexión móvil, vea [Configurar números de teléfono con Operador de conexión móvil](operator-connect-mobile-configure.md#set-up-phone-numbers).

- Para obtener información sobre la administración de números de teléfono para enrutamiento directo, vea [Configurar el número de teléfono y habilitar la voz empresarial](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).

### <a name="call-routing-and-dial-plans"></a>Enrutamiento de llamadas y planes de marcado

La forma de configurar el enrutamiento de llamadas varía según la opción de conectividad con RTC.  

- Para los planes de llamadas, la mayor parte del enrutamiento de llamadas se controla mediante la infraestructura del plan de llamadas de Microsoft. Los planes de marcado de usuario se configuran para la traducción de números para la autorización de llamadas y el enrutamiento de llamadas. Para obtener más información, consulte [¿Qué son los planes de marcado?](what-are-dial-plans.md).

- Para los Operador de conexión móvil y La conexión de operadores, la mayor parte del enrutamiento de llamadas lo administra el operador. Los planes de marcado de usuario se configuran para la traducción de números para la autorización de llamadas y el enrutamiento de llamadas. Para obtener más información, consulte [¿Qué son los planes de marcado?](what-are-dial-plans.md).

- Para el enrutamiento directo, debe configurar el enrutamiento de llamadas especificando las rutas de voz y asignando directivas de enrutamiento de voz a los usuarios. Puede configurar planes de marcado para la traducción de números en el nivel troncal para garantizar la interoperabilidad con los controladores de borde de sesión (SFC). Para obtener más información, vea [Configurar el enrutamiento de voz para enrutamiento directo](direct-routing-voice-routing.md), [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md) y [Traducir números de teléfono](direct-routing-translate-numbers.md). 

### <a name="location-based-routing-for-direct-routing"></a>enrutamiento Location-Based para enrutamiento directo

En algunos países y regiones, es ilegal omitir el operador RTC para reducir los costos de llamadas de larga distancia. Location-Based Enrutamiento (LBR) para enrutamiento directo le permite restringir la omisión de pago para los usuarios de Teams en función de su ubicación geográfica. Para obtener más información sobre cómo planear y configurar LBR, vea los siguientes artículos:

- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Caso práctico de Contoso: enrutamiento Location-Based](voice-case-study-location-based-routing.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó Location-Based Enrutamiento para su organización.

### <a name="emergency-calling"></a>Llamadas de emergencia

La forma de configurar las llamadas de emergencia varía según la opción de conectividad con RTC.

- Para el plan de llamadas, cada usuario se habilita automáticamente para las llamadas de emergencia. Este usuario debe tener una dirección de emergencia registrada asociada a su número de teléfono asignado. Se admite llamadas de emergencia dinámicas (en función de la ubicación del cliente de Teams). Para obtener más información, vea [Consideraciones para planes de llamadas](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

- Para Operator Connect, cada usuario se habilita automáticamente para las llamadas de emergencia. Se requiere que el usuario tenga una dirección de emergencia registrada asociada a su número de teléfono asignado. Se admite llamadas de emergencia dinámicas (en función de la ubicación del cliente de Teams). Para obtener más información, consulta [Consideraciones sobre la conexión de operadores](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect). 

- Por Operador de conexión móvil, cada usuario se habilita automáticamente para las llamadas de emergencia. Las llamadas de emergencia se redirigen automáticamente al Operador de conexión móvil operador para un número determinado. Se admite llamadas de emergencia dinámicas (en función de la ubicación del cliente de Teams). Para obtener más información, vea [Consideraciones para Operador de conexión móvil](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect-mobile). 

- Para el enrutamiento directo, debe definir directivas de llamadas de emergencia para los usuarios mediante una directiva de enrutamiento de llamadas de emergencia de Teams (TeamsEmergencyCallRoutingPolicy). La directiva definirá los números de emergencia y su destino de enrutamiento asociado. Las ubicaciones de emergencia registradas no son compatibles con los usuarios de enrutamiento directo. Para las llamadas de emergencia dinámicas, es necesaria una configuración adicional para enrutar llamadas de emergencia y posiblemente para la conectividad de socios. Para obtener más información, vea [Consideraciones para el enrutamiento directo](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).

#### <a name="for-more-information"></a>Más información

Para obtener más información sobre conceptos y terminología de llamadas de emergencia, y cómo configurar las llamadas de emergencia y las llamadas de emergencia dinámicas, vea los artículos siguientes:

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planear y configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md)
- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md)
- [Caso práctico de Contoso: Llamadas de emergencia](voice-case-study-emergency-calling.md)<br>
  Describe cómo una corporación multinacional ficticia, Contoso, implementó llamadas de emergencia para su organización.

### <a name="network-topology-for-voice-features"></a>Topología de red para características de voz

Si va a implementar llamadas de emergencia dinámicas o Location-Based Enrutamiento para enrutamiento directo, debe configurar las opciones de red para estas características en Microsoft Teams. Para obtener información sobre cómo configurar la configuración de red para regiones de red, sitios de red, subredes de red y direcciones IP de confianza, vea los artículos siguientes:

- [Configuración de red para las características de voz en la nube en Microsoft Teams: conceptos y terminología](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube en Microsoft Teams](manage-your-network-topology.md)
