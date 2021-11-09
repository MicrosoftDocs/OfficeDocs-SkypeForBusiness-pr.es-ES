---
title: Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un resumen de los componentes Telefonía IP empresarial en Skype Empresarial Server.
ms.openlocfilehash: 0dcc7578ee427fe6bf37f2bbde48c09ff32d62e7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855427"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server
 
Un resumen de los componentes Telefonía IP empresarial en Skype Empresarial Server.
  
Para implementar Telefonía IP empresarial, se necesitan los siguientes componentes en la topología. 
  
- Uno o varios servidores de mediación, que traducen señalización y, en algunas configuraciones, medios entre su Skype Empresarial Server interno, una infraestructura Telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco del Protocolo de inicio de sesión (SIP). Los servidores de mediación son el componente más importante en la Telefonía IP empresarial implementación. Para obtener más información, vea [Mediation Server component in Skype Empresarial Server](mediation-server.md).
    
    Los servidores de mediación se pueden asociar con servidores front-end o instalarse como servidores independientes.
    
- Componentes de conectividad RTC, que pueden incluir troncos SIP o puertas de enlace RTC. Para obtener más información, [vea Componentes de conectividad RTC en Skype Empresarial Server](pstn-connectivity.md).
    
- Servidores perimetrales, que permite el uso de Telefonía IP empresarial características por parte de los usuarios cuando están fuera del firewall de la organización. 
    
    El servicio perimetral de acceso proporciona señalización SIP para las llamadas Skype Empresarial usuarios que están fuera del firewall de la organización. El servicio perimetral A/V permite el recorrido multimedia de NAT y firewalls. Un llamador que usa un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo se basa en el servicio perimetral A/V para llamadas individuales y de conferencia.
    
    El servicio de autenticación A/V está asociado con el servicio perimetral A/V y proporciona servicios de autenticación para el servicio perimetral A/V. Los usuarios externos que intentan conectarse al servicio perimetral A/V requieren un token de autenticación proporcionado por el servicio de autenticación A/V antes de que puedan realizarse las llamadas.
    
- Además, algunos componentes Telefonía IP empresarial se ejecutan en servidores front-end. Para obtener información detallada acerca de estos componentes, vea Componentes VoIP del [servidor front-end para Skype Empresarial Server](front-end-server-voip.md)
    

