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
description: 'Obtenga información sobre las soluciones de telefonía de Microsoft: Sistema telefónico (Central de conmutación privada - PBX) y opciones de conectividad RTC (planes de llamadas y enrutamiento directo).'
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 3f5e4f0cf0cb027ed0c18b98c85b123634687a77
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878544"
---
# <a name="microsoft-telephony-solutions"></a>Soluciones de telefonía de Microsoft

Microsoft admite varias opciones a medida que comienza su viaje a Teams en la nube de Microsoft. Este artículo le ayuda a decidir qué solución de telefonía de Microsoft (Sistema telefónico en la nube o Telefonía IP empresarial local) es adecuada para los usuarios de su organización y cómo se puede conectar su organización a la red telefónica conmutada (RTC).

Debe usar este artículo junto con el diagrama técnico asociado, que proporciona una ayuda visual para tomar la decisión correcta para su organización:

- [Soluciones de telefonía de Microsoft - PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluciones de telefonía de Microsoft: Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opciones de central de conmutación (PBX)

### <a name="phone-system-microsoft-365-or-office-365"></a>Sistema telefónico (Microsoft 365 u Office 365)
  
Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de central de conmutación (PBX) en la nube de Microsoft 365 u Office 365 con Microsoft Teams o Skype Empresarial Online.

Sistema telefónico funciona con clientes y dispositivos certificados de Teams o Skype Empresarial Online. Sistema telefónico le permite reemplazar su sistema PBX existente con un conjunto de características que se entregan directamente desde Microsoft 365 u Office 365 y se integran estrechamente en la experiencia de productividad en la nube de la empresa. Para conectar el sistema telefónico a la red telefónica conmutada (RTC), puede elegir el Plan de llamadas de Microsoft o su propio operador de telefonía.

Para obtener más información, vea [¿Qué es el sistema telefónico en Microsoft 365 u Office 365?](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365)

### <a name="enterprise-voice-skype-for-business-server"></a>Telefonía IP empresarial (Skype Empresarial Server)

Telefonía IP empresarial es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de central de conmutación (PBX) en el Skype Empresarial Server local. Esta opción de Skype Empresarial solo se puede conectar a la red telefónica conmutada mediante su propio operador de telefonía.

Para obtener más información, consulte [Plan for Telefonía IP empresarial in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Conexión a las opciones de red telefónica conmutada (RTC)

Puede elegir conectarse a la red telefónica conmutada (RTC) mediante:

- Usar el plan de llamadas de Microsoft en Microsoft 365 u Office 365 
- Conectar su propio operador de telefonía

### <a name="calling-plan-microsoft-365-or-office-365"></a>Plan de llamadas (Microsoft 365 u Office 365)

Esta opción conecta el sistema telefónico de Microsoft 365 u Office 365 a la red telefónica conmutada (RTC) para habilitar las llamadas a teléfonos fijos y móviles de todo el mundo. Con el plan de llamadas, Microsoft es su operador de RTC.

Para obtener más información, vea [Planes de llamadas para Microsoft 365 u Office 365.](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>Conectar su propio operador de telefonía (Microsoft 365 u Office 365 y Skype Empresarial local)

Esta opción conecta el Sistema telefónico de Microsoft 365 u Office 365 o Telefonía IP empresarial en Skype Empresarial local a su red de telefonía. Esta opción requiere un controlador de borde de sesión (SBC) compatible. En algunos casos, esta opción puede requerir software adicional de Microsoft implementado localmente.

## <a name="which-solution-is-right-for-your-organization"></a>¿Qué solución es adecuada para su organización?

Puede elegir una solución todo en la nube, una solución connect-your-own-carrier o una combinación entre operadores de todo en la nube y de terceros:

- Sistema telefónico con plan de llamadas (todo en la nube)

- Sistema telefónico con operador propio mediante enrutamiento directo

- Sistema telefónico con operador propio a través de Skype Empresarial Server o Cloud Connector Edition

- Telefonía IP empresarial en Skype Empresarial Server con un operador propio

La solución que elija dependerá de sus necesidades actuales y futuras, como:

- Tanto si desea(o es necesario) conservar la funcionalidad proporcionada por la implementación local.
- El cliente que desea implementar para los usuarios.
- Cuál es su plan para mover personas a la nube.
- Si necesita interoperar con PBX de terceros y otros equipos de telefonía.

Tenga en cuenta las siguientes preguntas para determinar la mejor solución para su organización:

- ¿Tiene una implementación existente de Skype Empresarial Server?
- ¿Los usuarios están en Skype Empresarial local, en la nube en Skype Empresarial Online o en ambos? 
- ¿Desea mover usuarios locales a la nube?
- ¿El plan de llamadas RTC de Microsoft está disponible en su región?
- ¿Desea o necesita mantener su operador de telefonía actual?  Por ejemplo, ¿necesita mantener su operador actual debido a un contrato existente?
- ¿Tiene una PBX heredada local existente que desea o necesita conservar?
- ¿Su PBX heredada actual ofrece características únicas que son fundamentales para su empresa?
- ¿Alguno o todos los usuarios requieren características que actualmente no se ofrecen en el Sistema telefónico?

Tenga en cuenta lo siguiente:

- Las cuatro opciones pueden coexistir entre sí en caso de que necesite diseñar una solución para entornos complejos o administrar la migración en varios pasos.
- El sistema telefónico con un operador propio a través de Skype Empresarial Server o Cloud Connector Edition solo se puede implementar con Skype Empresarial Server o Cloud Connector. La coexistencia de Skype Empresarial Server y Cloud Connector no es compatible con una sola empresa.

## <a name="phone-system-with-calling-plan"></a>Sistema telefónico con plan de llamadas


Sistema telefónico con plan de llamadas es una opción de todo en la nube para los usuarios de Teams o Skype Empresarial Online, tal como se muestra en el siguiente diagrama:

![Sistema telefónico con plan de llamadas](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Sistema telefónico de Microsoft con planes de llamadas nacionales o internacionales agregados que permiten realizar llamadas a teléfonos de todo el mundo (según el nivel de servicio al que se concede la licencia). 
- Dado que el plan de llamadas RTC funciona desde Microsoft 365 u Office 365, esta opción no requiere la implementación ni el mantenimiento de ninguna implementación local.
- Los clientes pueden conectar un SBC compatible a través del enrutamiento directo para la interoperabilidad con PBX de terceros, dispositivos analógicos y otros equipos de telefonía de terceros compatibles con el SBC.

| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere conexión ininterrumpida a Microsoft 365 u Office 365 | Sí |
| Disponible en todo el mundo*                            | No  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | No |
| Requiere contrato con un operador de terceros      | No   |
| Requiere la implementación y el mantenimiento de Skype Empresarial Server o Cloud Connector Edition | No |

\*Para obtener más información acerca de los países donde el Plan de llamadas está disponible, vea Disponibilidad de país y región para [Audioconferencia y Planes de llamada.](https://docs.microsoft.com/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)


Si responde afirmativamente a las siguientes preguntas, esta es la solución adecuada para usted:

- El plan de llamadas está disponible en su región.
- No es necesario conservar su operador de RTC actual.
- Desea usar el acceso administrado por Microsoft a la red telefónica conmutada (RTC).
- No desea administrar los controladores de borde de sesión por su cuenta.
- Teams o Skype Empresarial Online tiene todas las características que necesita su organización.

Para obtener más información, vea ¿Qué es el sistema telefónico en [Microsoft 365 y Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) y planes de llamada [para Microsoft 365 u Office 365?](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema telefónico con operador propio mediante enrutamiento directo

Esta opción proporciona a Microsoft Phone System en la nube prácticamente cualquier operador de telefonía para los usuarios de Teams.

![Sistema telefónico con su operador a través del enrutamiento directo](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Conecte su propio SBC compatible con Microsoft Phone System directamente sin necesidad de software local adicional.  
- Use prácticamente cualquier operador de telefonía con El sistema telefónico de Microsoft.
- Puede ser configurado y administrado por los clientes o por su operador o partner (pregunte si su operador o partner ofrece esta opción).
- Configure la interoperabilidad entre el equipo de telefonía (como pbx de terceros y dispositivos analógicos) y el sistema telefónico de Microsoft.

| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere conexión ininterrumpida a Microsoft 365 u Office 365 | Sí |
| Disponible en todo el mundo                            | Sí  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | Sí |
| Requiere contrato con un operador de terceros*      | Sí   |
| Requiere la implementación y el mantenimiento de Skype Empresarial Server o Cloud Connector Edition | No |

\* A menos que se implemente como opción para proporcionar conexión a PBX de terceros, dispositivos analógicos u otros equipos de telefonía para los usuarios que están en el sistema telefónico con planes de llamada.

Si responde afirmativamente a las siguientes preguntas, esta es la solución adecuada para usted:

- Desea usar Teams con sistema telefónico.
- Debe conservar su operador de RTC actual.
- Quiere mezclar el enrutamiento, algunas llamadas se están haciendo a través de Planes de llamadas, otras a través de su operador
- Debe interoperar con PBX de terceros o equipos como paginadores de sobrecarga, dispositivos analógicos
- Teams tiene todas las características que necesita su organización.

Para obtener más información, vea ¿Qué es el sistema telefónico [en Microsoft 365 y Office 365?](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) y [Planear el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan)


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema telefónico con operador propio a través de Skype Empresarial Server o Cloud Connector Edition

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Esta opción proporciona al Sistema telefónico de Microsoft en la nube conectividad a una red de telefonía local para usuarios de Skype Empresarial Online.

![Sistema telefónico con su operador a través de Skype Empresarial Server o Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Conecte su propio SBC compatible con El sistema telefónico de Microsoft a través de Skype Empresarial Server o Skype Empresarial Cloud Connector Edition implementado localmente. 
- Use prácticamente cualquier operador de telefonía con El sistema telefónico de Microsoft. 
- Si ya tiene Skype Empresarial Server local, puede aprovecharlo;  Si no lo hace, puede implementar una versión más ligera: Cloud Connector Edition.


| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere conexión ininterrumpida a Microsoft 365 u Office 365 | Sí |
| Disponible en todo el mundo                            | Sí  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | Sí |
| Requiere contrato con un operador de terceros      | Sí   |
| Requiere la implementación y el mantenimiento de Skype Empresarial Server o Cloud Connector Edition | Sí |



Si responde afirmativamente a las siguientes preguntas, esta es la solución adecuada para usted:

- You want to use Skype for Business Online for your users.
- El plan de llamadas RTC no está disponible en su región.
- Debe conservar su operador de RTC actual.

Para obtener más información, vea ¿Qué es el sistema telefónico en [Microsoft 365 y Office 365,](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) [Skype Empresarial Server 2019](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-server-2019)y [Plan para Skype Empresarial Cloud Connector Edition?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)

Recomendación: Cuando cambien las condiciones empresariales (por ejemplo, ya no necesita conservar su operador de RTC), considere la posibilidad de cambiar a Microsoft Teams con las opciones 1 o 2 para:
- Minimizar los costos de mantenimiento
- Tener acceso a las últimas características publicadas por Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Telefonía IP empresarial en Skype Empresarial Server con un operador propio

Esta opción proporciona Telefonía IP empresarial local con conectividad a una red de telefonía local para los usuarios locales de Skype Empresarial.

![Telefonía IP empresarial en Skype Empresarial Server con un operador propio](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Conecte su propio SBC compatible con el Telefonía IP empresarial en el servidor local de Skype Empresarial.
- Se usa si necesita supervivencia local.
- Use prácticamente cualquier operador de telefonía con El sistema telefónico de Microsoft. 
- Opción más compleja de implementar y mantener.

| Requisitos previos de infraestructura                   | ¿Necesario?|
| :----------------------------------------------------| ---------:|
| Requiere conexión ininterrumpida a Microsoft 365 u Office 365 | No |
| Disponible en todo el mundo                            | Sí  |
| Requiere la implementación y el mantenimiento de un controlador de borde de sesión (SBC) compatible | Sí |
| Requiere contrato con un operador de terceros      | Sí   |
| Requiere la implementación y el mantenimiento de Skype Empresarial Server | Sí |

Para obtener más información, consulte [Plan for Telefonía IP empresarial in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Recomendación: Cuando cambien las condiciones empresariales (por ejemplo, ya no necesita conservar su operador de RTC), considere la posibilidad de cambiar a Microsoft Teams con las opciones 1 o 2 para:
- Minimizar los costos de mantenimiento
- Tener acceso a las últimas características publicadas por Microsoft
