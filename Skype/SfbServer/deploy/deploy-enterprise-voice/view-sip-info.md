---
title: Ver información sobre los troncos SIP individuales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumen: Aprenda a ver información sobre los troncos SIP en Skype empresarial Server.'
ms.openlocfilehash: f67fe998408b9c99311f1a86c35e08200de99431
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766933"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Ver información sobre los troncos SIP individuales en Skype empresarial Server
 
**Resumen:** Aprenda a ver información sobre los troncos SIP en Skype empresarial Server.
  
Los troncos SIP se usan para conectar la red telefónica de voz a través de IP de Skype empresarial Server con la red de telefonía pública conmutada (RTC). En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal. Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos. Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.
  
Sin embargo, en Skype empresarial Server, ahora se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos ya no están en el mismo. A su vez, esto significa que los administradores deben usar el nuevo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para ver información sobre un tronco SIP individual.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Para ver información sobre todos los enlaces troncales SIP

- El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Para ver información sobre un enlace troncal SIP específico

- Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Ver información sobre todos los troncos SIP asignados a un grupo

- En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
