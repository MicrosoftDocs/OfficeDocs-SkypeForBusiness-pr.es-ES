---
title: 'Lync Server 2013: Compatibilidad con hardware de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="ac3cc-102">Compatibilidad con hardware de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac3cc-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac3cc-103">_**Última modificación del tema:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="ac3cc-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="ac3cc-104">Las configuraciones de hardware específicas deben estar vigentes antes de implementar los teléfonos IP y los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="ac3cc-105">Teléfonos IP que ejecutan Lync Phone Edition compatibilidad con el protocolo de descubrimiento de nivel de vínculo: detección de puntos de conexión de medios (LLDP-MED) y alimentación a través de Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="ac3cc-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="ac3cc-106">Para aprovechar LLDP-MED, el switch debe ser compatible con IEEE 802.1 AB y ANSI/and-1057.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="ac3cc-107">Para aprovechar las ventajas de PoE, el conmutador debe ser compatible con PoE 802.3 AF o 802.3 en.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="ac3cc-108">Para habilitar LLDP-MED, el administrador debe habilitar LLDP mediante la ventana cambiar consola y configurar la Directiva de red LLDP-MED con la identificación de voz VLAN correcta.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="ac3cc-109">Además, si su implementación incluye dispositivos analógicos, debe configurar la puerta de enlace analógica para usar Lync Server, y la puerta de enlace debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac3cc-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="ac3cc-110">Un adaptador de teléfono analógico (ATA)</span><span class="sxs-lookup"><span data-stu-id="ac3cc-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="ac3cc-111">Una puerta de enlace analógica RTC</span><span class="sxs-lookup"><span data-stu-id="ac3cc-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="ac3cc-112">Un dispositivo de sucursal con la que se incluye una puerta de enlace analógica RTC</span><span class="sxs-lookup"><span data-stu-id="ac3cc-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="ac3cc-113">Un dispositivo de sucursal con la que se incluye una puerta de enlace RTC que se comunica con un ATA</span><span class="sxs-lookup"><span data-stu-id="ac3cc-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="ac3cc-114">Para obtener información sobre cómo configurar una puerta de enlace analógica, consulte "planear la implementación de [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) dispositivos analógicos" en la biblioteca de TechNet de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="ac3cc-115">(Los dispositivos analógicos funcionan de la misma manera en Lync Server 2013 que en Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="ac3cc-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ac3cc-116">Puede configurar el modificador para una 9-1-1 mejorada (E9-1-1), si el modificador lo admite.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

