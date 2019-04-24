---
title: Componentes necesarios para Enterprise Voice en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes de Enterprise Voice de Skype para Business Server.
ms.openlocfilehash: 870110c702c36660652fb08cff702453573349a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206988"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necesarios para Enterprise Voice en Skype para Business Server
 
Un resumen de los componentes de Enterprise Voice de Skype para Business Server.
  
Para implementar Enterprise Voice, se requieren los siguientes componentes en su topología. 
  
- Uno o varios servidores de mediación, que traduce señalización y, en algunas configuraciones, medios entre su Skype interno para Business Server, la infraestructura de Enterprise Voice y una puerta de enlace de telefónica conmutada (RTC) o un protocolo de inicio de sesión Tronco (SIP). Los servidores de mediación son el componente más importante en la implementación de Enterprise Voice. Para obtener más información, vea [componentes de servidor de mediación en Skype para Business Server](mediation-server.md).
    
    Los servidores de mediación se pueden combinar con los servidores Front-End o instalados como servidores independientes.
    
- Componentes de conectividad con RTC, que pueden incluir troncos SIP o puertas de enlace RTC. Para obtener más información, vea [componentes de conectividad de RTC en Skype para Business Server](pstn-connectivity.md).
    
- Los servidores perimetrales, lo que permite que el uso de las características de Enterprise Voice por los usuarios cuando se encuentran fuera del firewall de la organización. 
    
    El servicio de servidor perimetral de acceso proporciona la señalización SIP para las llamadas de Skype para usuarios profesionales que están fuera del firewall de la organización. El servicio perimetral A/V permite el paso de los medios a través de NAT y firewalls. Un autor de llamada que use un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo dependerá del servicio perimetral A/V para las llamadas individuales y de conferencia.
    
    El servicio de autenticación A/V se combina con el servicio perimetral A/V y le proporciona servicios de autenticación. Los usuarios externos que intenten conectarse al servicio perimetral A/V necesitarán un token de autenticación proporcionado por el servicio de autenticación A/V para que sus llamadas se acepten.
    
- Además, algunos componentes de Enterprise Voice se ejecutan en servidores Front-End. Para obtener información detallada acerca de estos componentes, vea [componentes de Front-End Server VoIP para Skype para Business Server](front-end-server-voip.md)
    

