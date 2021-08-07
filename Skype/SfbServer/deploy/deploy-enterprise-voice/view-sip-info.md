---
title: Ver información de tronco SIP en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Summary: Learn how to view information about SIP trunks in Skype Empresarial Server.'
ms.openlocfilehash: 2f4cc3a7435577d6c9d635a7dc910873b21f9981
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772801"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>Skype Empresarial Server: ver información sobre troncos SIP individuales 
 
**Resumen:** Obtenga información sobre cómo ver información sobre los troncos SIP en Skype Empresarial Server.
  
Los troncos SIP se usan para conectar Skype Empresarial Server de telefonía IP con la red telefónica conmutada (RTC). En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal. Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos. Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.
  
Sin Skype Empresarial Server, ahora se pueden asignar varios troncos a una única puerta de enlace RTC; esto significa que las puertas de enlace y los troncos ya no son uno y los mismos. A su vez, esto significa que los administradores deben usar el nuevo cmdlet [Get-CsTrunk](/powershell/module/skype/get-cstrunk) para ver información sobre un tronco SIP individual.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Para ver información de todos los troncos SIP

- El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Para ver información de un tronco SIP específico

- Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Ver información de todos los troncos SIP asignados a un grupo

- En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
