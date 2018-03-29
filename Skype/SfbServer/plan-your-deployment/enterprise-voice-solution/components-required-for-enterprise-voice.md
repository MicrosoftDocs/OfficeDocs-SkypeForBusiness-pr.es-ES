---
title: Componentes necesarios de la Telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes de Telefonía IP empresarial en Skype para Business Server.
ms.openlocfilehash: 2c5df4c0d580d767693717cf48585ceb0d4c7365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a>Componentes necesarios de la Telefonía IP empresarial en Skype Empresarial Server 2015
 
Un resumen de los componentes de Telefonía IP empresarial en Skype para Business Server.
  
Para implementar la Telefonía IP empresarial, son necesarios los siguientes componentes en su topología. 
  
- Uno o más servidores de mediación, que convierte las señales y, en algunas configuraciones, media entre el interno Skype para Business Server, la infraestructura de Telefonía IP empresarial y una puerta de enlace de telefonía pública conmutada (PSTN) de la red o un protocolo de inicio de sesión Tronco (SIP). Los servidores de mediación son el componente más crucial en la implementación de Telefonía IP empresarial. Para obtener más información, vea [componentes de servidor de mediación en Skype para Business Server 2015](mediation-server.md).
    
    Servidores de mediación pueden ser colocados con servidores frontales o instalados como servidores independientes.
    
- Componentes de conectividad con RTC, que pueden incluir troncos SIP o puertas de enlace RTC. Para obtener más información, vea [componentes de conectividad PSTN en Skype para Business Server 2015](pstn-connectivity.md).
    
- Servidores de borde, que permite el uso de las características de Telefonía IP empresarial por los usuarios cuando se encuentran fuera del cortafuegos de su organización. 
    
    El servicio de servidor perimetral de acceso proporciona la señalización SIP para las llamadas de Skype para usuarios profesionales que se encuentran fuera del cortafuegos de su organización. El servicio perimetral A/V permite el paso de los medios a través de NAT y firewalls. Un autor de llamada que use un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo dependerá del servicio perimetral A/V para las llamadas individuales y de conferencia.
    
    El servicio de autenticación A/V se combina con el servicio perimetral A/V y le proporciona servicios de autenticación. Los usuarios externos que intenten conectarse al servicio perimetral A/V necesitarán un token de autenticación proporcionado por el servicio de autenticación A/V para que sus llamadas se acepten.
    
- Además, algunos componentes de Telefonía IP empresarial se ejecutan en servidores frontales. Para obtener más información acerca de estos componentes, vea [componentes de VoIP de Front End servidor de Skype para Business Server 2015](front-end-server-voip.md)
    

