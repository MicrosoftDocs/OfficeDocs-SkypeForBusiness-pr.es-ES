---
title: Soluciones de telefonía de Microsoft
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Describe las soluciones de telefonía de Microsoft.
ms.openlocfilehash: 1ab2feb1a7cc650bc9dbb35d3205a6f9de2de7b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048631"
---
# <a name="microsoft-telephony-solutions"></a>Soluciones de telefonía de Microsoft

Microsoft admite varias opciones a medida que comienza el viaje a Microsoft Teams en la nube de Microsoft. Este artículo le ayudará a decidir qué solución de telefonía de Microsoft (sistema telefónico en la nube o la telefonía IP empresarial local) es la adecuada para los usuarios de su organización y cómo su organización puede conectarse a la red telefónica conmutada (RTC) pública. 

Debe usar este artículo junto con el diagrama técnico asociado, que proporciona una ayuda visual para tomar la decisión correcta para su organización:

- [Soluciones de telefonía de Microsoft-PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluciones de telefonía de Microsoft-Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opciones de central de conmutación (PBX)

### <a name="phone-system-office-365"></a>Sistema telefónico (Office 365)
  
Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de central de conmutación (PBX) en la nube de Office 365 con Microsoft Teams y/o Skype empresarial online. 

Sistema telefónico funciona con los clientes de Microsoft Teams o Skype empresarial online y los dispositivos certificados. El sistema telefónico le permite reemplazar su sistema PBX existente por un conjunto de características que se entregan directamente desde Office 365 y que están estrechamente integradas en la experiencia de productividad en la nube de la compañía. Para conectar el sistema telefónico a la red telefónica conmutada (RTC), puede elegir el plan de llamadas de Microsoft o su propio operador de telefonía.

Para obtener más información, consulte [What is Phone System in Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>Telefonía IP empresarial (Skype empresarial Server)

La telefonía IP empresarial es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de central de conmutación (PBX) en el servidor local de Skype empresarial Server. Esta opción solo se puede conectar a la red telefónica conmutada pública mediante su propio operador de telefonía. 

Para obtener más información, consulte [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Conexión a las opciones de la red telefónica conmutada (RTC)

Puede elegir conectarse a la red telefónica conmutada (RTC) de la siguiente manera:

- Uso del plan de llamadas de Microsoft en Office 365 
- Conexión de su propio operador de telefonía

### <a name="calling-plan-office-365"></a>Plan de llamadas (Office 365)

Esta opción conecta el sistema telefónico de Office 365 de Microsoft con la red telefónica conmutada (RTC) para habilitar las llamadas a teléfonos fijos y móviles en todo el mundo. Con el plan de llamadas, Microsoft es su operador de RTC.

Para obtener más información, consulte [planes de llamada para Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

### <a name="connect-your-own-telephony-carrier-office-365-and-skype-for-business-on-premises"></a>Conectar su propio operador de telefonía (Office 365 y Skype empresarial local)

Esta opción conecta un sistema telefónico en Office 365 o un sistema de telefonía IP empresarial en Skype empresarial local a su red de telefonía. Esta opción requiere un controlador de borde de sesión (SBC) compatible. En algunos casos, es posible que esta opción requiera software de Microsoft adicional implementado localmente.

## <a name="which-solution-is-right-for-your-organization"></a>¿Qué solución es la más adecuada para su organización?

Puede elegir una solución "todo en la nube", una soluci? o de conexión de su propio operador o una combinación entre operadores de la nube y proveedores de terceros:

- Sistema telefónico con plan de llamadas (todo en la nube)

- Sistema telefónico con operador propio a través del enrutamiento directo

- Sistema telefónico con operador propio a través de Skype empresarial Server o Cloud Connector Edition

- Telefonía IP empresarial en Skype empresarial Server con operador propio

La solución que elija dependerá de sus necesidades actuales y futuras, como:

- Si quiere, o si es necesario,-para conservar la funcionalidad proporcionada por su implementación local.
- Qué cliente desea implementar para sus usuarios.
- Qué planea ser el plan para mover personas a la nube.
- Si necesita interoperar con sistemas PBX de terceros y otros equipos de telefonía.

Tenga en cuenta las siguientes preguntas para determinar cuál es la mejor solución para su organización:

- ¿Tiene una implementación existente de Skype empresarial Server?
- ¿Los usuarios están hospedados en Skype empresarial local, en la nube en Skype empresarial online o en ambos? 
- ¿Desea mover los usuarios locales a la nube?
- ¿Está disponible el plan de llamadas RTC de Microsoft en su región?
- ¿Quiere o necesita mantener su operador de telefonía actual?  Por ejemplo, ¿necesita mantener su operador actual debido a un contrato existente?
- ¿Tiene una PBX heredada local existente que desee o deba mantener?
- ¿Su PBX heredada actual ofrece características únicas que son esenciales para su empresa?
- ¿Alguno o todos los usuarios necesitan características que no se ofrecen actualmente en el sistema telefónico?

Tenga en cuenta lo siguiente:

- Las cuatro opciones pueden coexistir entre sí en caso de que necesite diseñar una solución para un entorno complejo o administrar la migración en varios pasos.
- El sistema telefónico con operador propio a través de Skype empresarial Server o Cloud Connector Edition solo se puede implementar con Skype empresarial Server o Cloud Connector. La coexistencia de Skype empresarial Server y Cloud Connector no es compatible con una sola empresa.

## <a name="phone-system-with-calling-plan"></a>Sistema telefónico con plan de llamadas


Sistema telefónico con plan de llamadas es una opción todo en la nube para los usuarios de Microsoft Teams o Skype empresarial online, como se muestra en el siguiente diagrama:

![Sistema telefónico con plan de llamadas](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Microsoft Phone System con planes de llamadas nacionales e internacionales agregados que permiten llamar a teléfonos en todo el mundo (en función del nivel de servicio al que se les concede la licencia). 
- Debido a que el plan de llamadas RTC funciona fuera de la oficina 365, esta opción no requiere la implementación ni el mantenimiento de ninguna implementación local.
- Los clientes pueden conectar un SBC compatible mediante el enrutamiento directo para interoperabilidad con PBX de terceros, dispositivos analógicos y otros equipos de telefonía de terceros admitidos por el SBC.

| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere una conexión ininterrumpida a Office 365 | Sí |
| Disponible en todo el mundo *                            | No  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | No |
| Requiere contrato con un proveedor de terceros      | No   |
| Requiere la implementación y el mantenimiento de Skype empresarial Server o Cloud Connector Edition | No |

\*Para obtener más información acerca de los países en los que está disponible el plan de llamadas, consulte [disponibilidad de países y regiones para audioconferencia y planes de llamada](https://docs.microsoft.com/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).


Si responde afirmativamente a las siguientes preguntas, esta es la solución adecuada para usted:

- El plan de llamadas está disponible en su región.
- No es necesario que conserve su operador de RTC actual.
- Desea usar el acceso administrado por Microsoft a la red telefónica conmutada (RTC).
- No desea administrar los controladores de borde de sesión por su cuenta.
- Teams o Skype empresarial online tiene todas las características que necesita su organización.

Para obtener más información, consulte [What is Phone System in Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) y [planes de llamadas para Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema telefónico con operador propio a través del enrutamiento directo

Esta opción proporciona el sistema telefónico de Microsoft en la nube con prácticamente cualquier operador de telefonía para los usuarios de Teams.

![Sistema telefónico con el transportista a través del enrutamiento directo](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Conecte su propio SBC compatible a Microsoft Phone System directamente, sin necesidad de software local adicional.  
- Use virtualmente cualquier operador de telefonía con Microsoft Phone System.
- La pueden configurar y administrar los clientes o el proveedor o el Partner (pregunte si su proveedor o su socio proporcionan esta opción).
- Configure la interoperabilidad entre el equipo de telefonía, como un PBX de terceros y dispositivos analógicos, y el sistema telefónico de Microsoft.

| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere una conexión ininterrumpida a Office 365 | Sí |
| Disponible en todo el mundo                            | Sí  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | Sí |
| Requiere contrato con un proveedor de terceros *      | Sí   |
| Requiere la implementación y el mantenimiento de Skype empresarial Server o Cloud Connector Edition | No |

\*A menos que se implemente como una opción para proporcionar conexión a un PBX de terceros, dispositivos analógicos u otros equipos de telefonía para los usuarios de sistema telefónico con planes de llamada.

Si responde afirmativamente a las siguientes preguntas, esta es la solución adecuada para usted:

- Desea usar Teams con el sistema telefónico.
- Necesita mantener su operador de RTC actual.
- Desea mezclar el enrutamiento, algunas llamadas se realizarán a través de planes de llamada, algunos a través de su operador
- Debe interoperar con PBX de terceros o con equipamientos como por ejemplo, los dispositivos analógicos y buscapersonas
- Microsoft Teams tiene todas las características que requiere su organización.

Para obtener más información, consulte [What is Phone System in Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) y [plan Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema telefónico con operador propio a través de Skype empresarial Server o Cloud Connector Edition

Esta opción proporciona el sistema telefónico de Microsoft en la nube con conectividad a una red de telefonía local para los usuarios de Skype empresarial online.

![Sistema telefónico con su operador a través de Skype empresarial Server o Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Conecte su propio SBC compatible con Microsoft Phone System a través de Skype empresarial Server o Skype empresarial Cloud Connector Edition implementado localmente. 
- Use virtualmente cualquier operador de telefonía con Microsoft Phone System. 
- Si ya tiene Skype empresarial Server local, puede aprovecharlo;  Si no lo hace, puede implementar una versión más ligera: Cloud Connector Edition.


| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere una conexión ininterrumpida a Office 365 | Sí |
| Disponible en todo el mundo                            | Sí  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | Sí |
| Requiere contrato con un proveedor de terceros      | Sí   |
| Requiere la implementación y el mantenimiento de Skype empresarial Server o Cloud Connector Edition | Sí |



Si responde afirmativamente a las siguientes preguntas, esta es la solución adecuada para usted:

- Desea usar Skype empresarial online para los usuarios.
- El plan de llamadas RTC no está disponible en su región.
- Necesita mantener su operador de RTC actual.

Para obtener más información, consulte [What is Phone System in Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365), [Skype for Business Server 2019](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-server-2019)y [Plan for Skype for Business Cloud Connector Edition](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Recomendación: cuando cambien las condiciones empresariales (por ejemplo, ya no necesita mantener su operador de RTC), considere la posibilidad de migrar a Microsoft Teams con las opciones 1 o 2 para:
- Minimizar los costos de mantenimiento
- Tener acceso a las características más recientes que publica Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Telefonía IP empresarial en Skype empresarial Server con operador propio

Esta opción proporciona la telefonía IP empresarial local con conectividad a una red de telefonía local para usuarios locales de Skype empresarial.

![Telefonía IP empresarial en Skype empresarial Server con operador propio](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Conecte su propio SBC compatible con el sistema de telefonía IP empresarial en el servidor local de Skype empresarial.
- Use si necesita la supervivencia local.
- Use virtualmente cualquier operador de telefonía con Microsoft Phone System. 
- Opción más compleja de implementar y mantener.

| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere una conexión ininterrumpida a Office 365 | No |
| Disponible en todo el mundo                            | Sí  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | Sí |
| Requiere contrato con un proveedor de terceros      | Sí   |
| Requiere la implementación y el mantenimiento de Skype empresarial Server | Sí |

Para obtener más información, consulte [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Recomendación: cuando cambien las condiciones empresariales (por ejemplo, ya no necesita mantener su operador de RTC), considere la posibilidad de migrar a Microsoft Teams con las opciones 1 o 2 para:
- Minimizar los costos de mantenimiento
- Tener acceso a las características más recientes que publica Microsoft











  
