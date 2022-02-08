---
title: Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 2fbc5aa6a7ece34db0d0ae9360d4be7c8b6f2a8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390052"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server
 
Un resumen de los componentes Telefonía IP empresarial en Skype Empresarial Server.
  
Para implementar Telefonía IP empresarial, se necesitan los siguientes componentes en la topología. 
  
- Uno o varios servidores de mediación, que traducen señalización y, en algunas configuraciones, medios entre su Skype Empresarial Server interno, una infraestructura Telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco del Protocolo de inicio de sesión (SIP). Los servidores de mediación son el componente más importante en la Telefonía IP empresarial implementación. Para obtener más información, vea [Mediation Server component in Skype Empresarial Server](mediation-server.md).
    
    Los servidores de mediación se pueden asociar con servidores front-end o instalarse como servidores independientes.
    
- Componentes de conectividad RTC, que pueden incluir troncos SIP o puertas de enlace RTC. Para obtener más información, vea [Componentes de conectividad RTC en Skype Empresarial Server](pstn-connectivity.md).
    
- Servidores perimetrales, que permite el uso de Telefonía IP empresarial características por parte de los usuarios cuando están fuera del firewall de la organización. 
    
    El servicio perimetral de acceso proporciona señalización SIP para las llamadas Skype Empresarial usuarios que están fuera del firewall de la organización. El servicio perimetral A/V permite el recorrido multimedia de NAT y firewalls. Un llamador que usa un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo se basa en el servicio perimetral A/V para llamadas individuales y de conferencia.
    
    El servicio de autenticación A/V está asociado con el servicio perimetral A/V y proporciona servicios de autenticación para el servicio perimetral A/V. Los usuarios externos que intentan conectarse al servicio perimetral A/V requieren un token de autenticación proporcionado por el servicio de autenticación A/V antes de que puedan realizarse las llamadas.
    
- Además, algunos componentes Telefonía IP empresarial se ejecutan en servidores front-end. Para obtener más información acerca de estos componentes, vea [Componentes VoIP del servidor front-end para obtener Skype Empresarial Server](front-end-server-voip.md)
    

