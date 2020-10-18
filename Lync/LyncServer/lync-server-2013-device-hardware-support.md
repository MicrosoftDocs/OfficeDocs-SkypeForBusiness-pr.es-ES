---
title: Soporte de hardware para dispositivos de Lync Server 2013
description: 'Lync Server 2013: compatibilidad con hardware de dispositivos.'
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
ms.openlocfilehash: cd03936d35fbc3a639a3ba4596a4357e8e379719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575666"
---
# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="afcfd-103">Compatibilidad de hardware de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afcfd-103">Device hardware support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afcfd-104">_**Última modificación del tema:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="afcfd-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="afcfd-105">Las configuraciones de hardware específicas deben estar en su ubicación antes de implementar los teléfonos IP y los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="afcfd-105">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="afcfd-106">Los teléfonos IP que ejecutan Lync Phone Edition admiten la detección de niveles de vínculo Protocol-Media la detección de extremos (LLDP-MED) y la alimentación a través de Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="afcfd-106">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="afcfd-107">Para usar el protocolo LLDP-MED, el conmutador debe admitir IEEE802.1AB y ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="afcfd-107"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="afcfd-108">Para usar PoE, el conmutador debe admitir PoE802.3AF o 802.3at.</span><span class="sxs-lookup"><span data-stu-id="afcfd-108">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="afcfd-109">Para habilitar LLDP-MED, el administrador debe habilitar LLDP mediante la ventana de la consola del conmutador y establecer la directiva de red LLDP-MED con el Id. de VLAN de voz correcto.</span><span class="sxs-lookup"><span data-stu-id="afcfd-109">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="afcfd-110">Además, si la implementación incluye dispositivos analógicos, debe configurar la puerta de enlace analógica para que use Lync Server, y la puerta de enlace debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="afcfd-110">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="afcfd-111">Un adaptador de teléfono analógico (ATA)</span><span class="sxs-lookup"><span data-stu-id="afcfd-111">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="afcfd-112">Una puerta de enlace analógica de RTC</span><span class="sxs-lookup"><span data-stu-id="afcfd-112">A PSTN analog gateway</span></span>

  - <span data-ttu-id="afcfd-113">Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace analógica de RTC</span><span class="sxs-lookup"><span data-stu-id="afcfd-113">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="afcfd-114">Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace RTC que se comunique con un ATA</span><span class="sxs-lookup"><span data-stu-id="afcfd-114">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="afcfd-115">Para obtener información sobre cómo configurar una puerta de enlace analógica, vea "planeación para implementar dispositivos analógicos" en [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) la biblioteca de TechNet de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afcfd-115">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="afcfd-116">(Los dispositivos analógicos funcionan del mismo modo en Lync Server 2013 que en Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="afcfd-116">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="afcfd-117">Puede configurar el conmutador para Enhanced 9-1-1 (E9-1-1), si el conmutador lo admite.</span><span class="sxs-lookup"><span data-stu-id="afcfd-117">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

