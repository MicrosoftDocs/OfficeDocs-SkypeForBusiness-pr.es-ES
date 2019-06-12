---
title: 'Lync Server 2013: ver información sobre los troncos SIP individuales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c7d29c7318c8fb6d1cd08775853eb46b1c898d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="c8ae6-102">Ver información sobre los troncos SIP individuales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8ae6-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8ae6-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c8ae6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c8ae6-104">Los troncos SIP se usan para conectar Lync Server 2013 voz a través de una red telefónica IP con la red de telefonía pública conmutada.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="c8ae6-105">En la versión anterior del producto, los enlaces troncales se usaban para enrutar las llamadas salientes de un servidor de mediación a una puerta de enlace RTC, y cada puerta de enlace estaba limitada a un único enlace troncal.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="c8ae6-106">Como resultado, la puerta de enlace RTC y el enlace troncal SIP eran básicamente idénticos.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="c8ae6-107">Para los administradores, eso significaba que podían ver información sobre un enlace troncal SIP individual al ver información sobre la puerta de enlace RTC asociada.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="c8ae6-108">En Lync Server 2013, sin embargo, ahora se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos ya no están en el mismo.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="c8ae6-109">A su vez, esto significa que los administradores deben usar el nuevo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="c8ae6-110">El cmdlet Get-CsTrunk se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8ae6-111">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="c8ae6-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="c8ae6-112">Para ver información sobre todos los enlaces troncales SIP</span><span class="sxs-lookup"><span data-stu-id="c8ae6-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="c8ae6-113">El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:</span><span class="sxs-lookup"><span data-stu-id="c8ae6-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="c8ae6-114">Para ver información sobre un enlace troncal SIP específico</span><span class="sxs-lookup"><span data-stu-id="c8ae6-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="c8ae6-115">Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="c8ae6-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="c8ae6-116">Ver información de todos los troncos SIP asignados a un grupo</span><span class="sxs-lookup"><span data-stu-id="c8ae6-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="c8ae6-117">En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="c8ae6-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

