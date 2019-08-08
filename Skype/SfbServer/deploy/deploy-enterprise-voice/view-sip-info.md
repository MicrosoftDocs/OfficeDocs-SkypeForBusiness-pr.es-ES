---
title: Ver información sobre los troncos SIP individuales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumen: Aprenda a ver información sobre los troncos SIP en Skype empresarial Server.'
ms.openlocfilehash: 3d8ad70428926c26445c6556544a5a363de12f5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239946"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="68af8-103">Ver información sobre los troncos SIP individuales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="68af8-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="68af8-104">**Resumen:** Aprenda a ver información sobre los troncos SIP en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="68af8-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="68af8-105">Los troncos SIP se usan para conectar la red telefónica de voz a través de IP de Skype empresarial Server con la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="68af8-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="68af8-106">En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal.</span><span class="sxs-lookup"><span data-stu-id="68af8-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="68af8-107">Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos.</span><span class="sxs-lookup"><span data-stu-id="68af8-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="68af8-108">Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.</span><span class="sxs-lookup"><span data-stu-id="68af8-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="68af8-109">Sin embargo, en Skype empresarial Server, ahora se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos ya no están en el mismo.</span><span class="sxs-lookup"><span data-stu-id="68af8-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="68af8-110">A su vez, esto significa que los administradores deben usar el nuevo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para ver información sobre un tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="68af8-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="68af8-111">Para ver información sobre todos los enlaces troncales SIP</span><span class="sxs-lookup"><span data-stu-id="68af8-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="68af8-112">El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:</span><span class="sxs-lookup"><span data-stu-id="68af8-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="68af8-113">Para ver información sobre un enlace troncal SIP específico</span><span class="sxs-lookup"><span data-stu-id="68af8-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="68af8-114">Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="68af8-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="68af8-115">Ver información sobre todos los troncos SIP asignados a un grupo</span><span class="sxs-lookup"><span data-stu-id="68af8-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="68af8-116">En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="68af8-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
