---
title: Componentes necesarios para la telefonía IP empresarial en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes de voz empresarial de Skype empresarial Server.
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277009"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necesarios para la telefonía IP empresarial en Skype empresarial Server
 
Un resumen de los componentes de voz empresarial de Skype empresarial Server.
  
Para implementar la telefonía IP empresarial, los siguientes componentes son necesarios en su topología. 
  
- Uno o varios servidores de mediación, que traducen las señales y, en algunas configuraciones, medios entre su servidor interno de Skype para empresas, la infraestructura de telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un protocolo de inicio de sesión (SIP) troncal. Los servidores de mediación son el componente más importante de su implementación de telefonía IP empresarial. Para obtener más información, consulte [componente de servidor de mediación en Skype empresarial Server](mediation-server.md).
    
    Los servidores de mediación se pueden colocar con servidores de aplicaciones para el usuario o instalarse como servidores independientes.
    
- Componentes de conectividad con RTC, que pueden incluir troncos SIP o puertas de enlace RTC. Para obtener más información, consulte [componentes de conectividad RTC en Skype empresarial Server](pstn-connectivity.md).
    
- Servidores perimetrales, que permite el uso de características de telefonía IP por parte de los usuarios cuando están fuera del firewall de la organización. 
    
    El servicio perimetral de acceso proporciona señalización SIP para llamadas de Skype empresarial que están fuera del firewall de la organización. El servicio perimetral A/V permite el paso de los medios a través de NAT y firewalls. Un autor de llamada que use un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo dependerá del servicio perimetral A/V para las llamadas individuales y de conferencia.
    
    El servicio de autenticación A/V se combina con el servicio perimetral A/V y le proporciona servicios de autenticación. Los usuarios externos que intenten conectarse al servicio perimetral A/V necesitarán un token de autenticación proporcionado por el servicio de autenticación A/V para que sus llamadas se acepten.
    
- Además, algunos componentes de Enterprise Voice se ejecutan en servidores front-end. Para obtener más información acerca de estos componentes, consulte [componentes de VoIP del servidor front-end para Skype empresarial Server](front-end-server-voip.md) .
    

