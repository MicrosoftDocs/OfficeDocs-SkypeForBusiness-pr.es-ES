---
title: 'Lync Server 2013: configuración de la configuración del tronco del SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a6b1c8a43258c849de73b10a10bccf8ff537c5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b67eb-102">Probar la configuración del tronco del SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b67eb-102">Test SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b67eb-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b67eb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b67eb-104">Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="b67eb-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="b67eb-105">Estas opciones de configuración especifican:</span><span class="sxs-lookup"><span data-stu-id="b67eb-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="b67eb-106">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="b67eb-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="b67eb-107">Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="b67eb-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="b67eb-108">Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="b67eb-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b67eb-109">Al instalar Microsoft Lync Server 2013, se crea una colección global de parámetros de configuración del tronco del SIP.</span><span class="sxs-lookup"><span data-stu-id="b67eb-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b67eb-110">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="b67eb-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="b67eb-111">Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.</span><span class="sxs-lookup"><span data-stu-id="b67eb-111">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="b67eb-112">Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="b67eb-112">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet.</span></span> <span data-ttu-id="b67eb-113">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b67eb-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b67eb-114">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="b67eb-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="b67eb-115">Para probar las opciones de configuración de troncos SIP</span><span class="sxs-lookup"><span data-stu-id="b67eb-115">To test SIP trunk configuration settings</span></span>

  - <span data-ttu-id="b67eb-116">Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="b67eb-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

