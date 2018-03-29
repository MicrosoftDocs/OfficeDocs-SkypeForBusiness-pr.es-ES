---
title: Ver información sobre troncos SIP individuales en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumen: Conozca cómo ver información acerca de los troncos SIP en Skype para Business Server 2015.'
ms.openlocfilehash: c307d4e9b18b7ff5fda8d8d0deaa4eb88ba5b6b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a>Ver información sobre troncos SIP individuales en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a ver información sobre los troncos SIP en Skype para Business Server 2015.
  
Los troncos SIP se utilizan para conectar Skype para voz de Business Server sobre la red de teléfono IP con la red telefónica pública conmutada (PSTN). En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal. Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos. Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.
  
En Skype para Business Server, sin embargo, varios troncos pueden ahora asignarse a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos ya no son el mismo. A su vez, eso significa que los administradores deben utilizar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) nueva con el fin de ver información sobre un tronco SIP individual.
  
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


