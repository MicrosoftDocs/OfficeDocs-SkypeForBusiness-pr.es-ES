---
title: Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes Telefonía IP empresarial en Skype Empresarial Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825830"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server
 
Un resumen de los componentes Telefonía IP empresarial en Skype Empresarial Server.
  
Para implementar Telefonía IP empresarial, se requieren los siguientes componentes en la topología. 
  
- Uno o más servidores de mediación, que traducen señalización y, en algunas configuraciones, medios entre su Skype Empresarial Server interno, una infraestructura de Telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco sip (Protocolo de inicio de sesión). Los servidores de mediación son el componente más fundamental en la implementación Telefonía IP empresarial cliente. Para obtener más información, vea el componente [del servidor de mediación en Skype Empresarial Server.](mediation-server.md)
    
    Los servidores de mediación pueden instalarse con servidores front-end o instalarse como servidores independientes.
    
- Componentes de conectividad RTC, que pueden incluir troncos SIP o puertas de enlace RTC. Para obtener más información, vea [componentes de conectividad rtc en Skype Empresarial Server.](pstn-connectivity.md)
    
- Servidores perimetrales, lo que permite el uso de Telefonía IP empresarial por parte de los usuarios cuando están fuera del firewall de la organización. 
    
    El servicio perimetral de acceso proporciona señalización SIP para llamadas de usuarios de Skype Empresarial que están fuera del firewall de su organización. El servicio perimetral A/V permite el cruce de medios de NAT y firewalls. Un llamador que usa un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo depende del servicio perimetral A/V para llamadas individuales y de conferencia.
    
    El servicio de autenticación A/V se incluye con el servicio perimetral A/V y proporciona servicios de autenticación para el servicio perimetral A/V. Los usuarios externos que intentan conectarse al servicio perimetral A/V requieren un token de autenticación proporcionado por el servicio de autenticación A/V antes de que puedan pasar las llamadas.
    
- Además, algunos componentes Telefonía IP empresarial se ejecutan en servidores front-end. Para obtener más información sobre estos componentes, consulte [Componentes VoIP del servidor front-end para Skype Empresarial Server](front-end-server-voip.md)
    

