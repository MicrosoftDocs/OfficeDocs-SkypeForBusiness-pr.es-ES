---
title: Ver información sobre troncos SIP individuales en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumen: Obtenga información sobre cómo ver información acerca de troncos SIP en Skype para Business Server 2015.'
ms.openlocfilehash: fb9990ec4315ffd26f51adaee2414810a053a97f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568245"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a>Ver información sobre troncos SIP individuales en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo ver información acerca de troncos SIP en Skype para Business Server 2015.
  
Troncos SIP se utilizan para conectar Skype para Business Server voz a través de la red de teléfono IP con la red telefónica pública conmutada (RTC). En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal. Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos. Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.
  
En Skype para Business Server, sin embargo, varios troncos ahora se pueden asignar a una única puerta de enlace de RTC; Esto significa que las puertas de enlace y troncos ya no son el mismos. A su vez, eso significa que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) nueva con el fin de ver información sobre un tronco SIP individual.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Para ver información sobre todos los enlaces troncales SIP

- El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Para ver información sobre un enlace troncal SIP específico

- Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Ver información sobre todos los troncos SIP asignados a un grupo

- En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```