---
title: Soporte de hardware para dispositivos de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b2d730181426d5b23463816d13a6f3b0e502b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="1116f-102">Compatibilidad de hardware de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1116f-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1116f-103">_**Última modificación del tema:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="1116f-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="1116f-104">Las configuraciones de hardware específicas deben estar en su ubicación antes de implementar los teléfonos IP y los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="1116f-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="1116f-105">Los teléfonos IP que ejecutan Lync Phone Edition admiten el protocolo de detección de niveles de vínculos: detección de extremos de medios (LLDP-MED) y Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="1116f-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="1116f-106">Para usar el protocolo LLDP-MED, el conmutador debe admitir IEEE802.1AB y ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="1116f-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="1116f-107">Para usar PoE, el conmutador debe admitir PoE802.3AF o 802.3at.</span><span class="sxs-lookup"><span data-stu-id="1116f-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="1116f-108">Para habilitar LLDP-MED, el administrador debe habilitar LLDP mediante la ventana de la consola del conmutador y establecer la directiva de red LLDP-MED con el Id. de VLAN de voz correcto.</span><span class="sxs-lookup"><span data-stu-id="1116f-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="1116f-109">Además, si la implementación incluye dispositivos analógicos, debe configurar la puerta de enlace analógica para que use Lync Server, y la puerta de enlace debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1116f-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="1116f-110">Un adaptador de teléfono analógico (ATA)</span><span class="sxs-lookup"><span data-stu-id="1116f-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="1116f-111">Una puerta de enlace analógica de RTC</span><span class="sxs-lookup"><span data-stu-id="1116f-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="1116f-112">Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace analógica de RTC</span><span class="sxs-lookup"><span data-stu-id="1116f-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="1116f-113">Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace RTC que se comunique con un ATA</span><span class="sxs-lookup"><span data-stu-id="1116f-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="1116f-114">Para obtener información sobre cómo configurar una puerta [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) de enlace analógica, vea "planeación para implementar dispositivos analógicos" en la biblioteca de TechNet de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1116f-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="1116f-115">(Los dispositivos analógicos funcionan del mismo modo en Lync Server 2013 que en Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="1116f-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1116f-116">Puede configurar el conmutador para Enhanced 9-1-1 (E9-1-1), si el conmutador lo admite.</span><span class="sxs-lookup"><span data-stu-id="1116f-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

