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
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="ceae9-103">Ver información sobre troncos SIP individuales en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ceae9-103">View information about individual SIP trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ceae9-104">**Resumen:** Obtenga información sobre cómo ver información acerca de troncos SIP en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ceae9-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ceae9-105">Troncos SIP se utilizan para conectar Skype para Business Server voz a través de la red de teléfono IP con la red telefónica pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="ceae9-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ceae9-106">En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal.</span><span class="sxs-lookup"><span data-stu-id="ceae9-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="ceae9-107">Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos.</span><span class="sxs-lookup"><span data-stu-id="ceae9-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="ceae9-108">Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.</span><span class="sxs-lookup"><span data-stu-id="ceae9-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="ceae9-109">En Skype para Business Server, sin embargo, varios troncos ahora se pueden asignar a una única puerta de enlace de RTC; Esto significa que las puertas de enlace y troncos ya no son el mismos.</span><span class="sxs-lookup"><span data-stu-id="ceae9-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="ceae9-110">A su vez, eso significa que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) nueva con el fin de ver información sobre un tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="ceae9-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="ceae9-111">Para ver información sobre todos los enlaces troncales SIP</span><span class="sxs-lookup"><span data-stu-id="ceae9-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="ceae9-112">El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:</span><span class="sxs-lookup"><span data-stu-id="ceae9-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="ceae9-113">Para ver información sobre un enlace troncal SIP específico</span><span class="sxs-lookup"><span data-stu-id="ceae9-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="ceae9-114">Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="ceae9-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="ceae9-115">Ver información sobre todos los troncos SIP asignados a un grupo</span><span class="sxs-lookup"><span data-stu-id="ceae9-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="ceae9-116">En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ceae9-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```