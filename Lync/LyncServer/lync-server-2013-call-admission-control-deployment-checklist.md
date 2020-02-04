---
title: 'Lync Server 2013: lista de comprobación de la implementación de control de admisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="bb7b6-102">Lista de comprobación de la implementación de control de admisión para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb7b6-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb7b6-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="bb7b6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="bb7b6-104">Use la siguiente lista de comprobación para comprobar que ha completado todas las tareas de configuración necesarias para implementar el control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="bb7b6-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="bb7b6-105">Si se implementan uno o varios servidores perimetrales, cada dirección IP de la interfaz externa debe agregarse a la lista de subred en la configuración de red, con una máscara de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="bb7b6-106">También tiene que asociar esta subred (dirección IP) con el identificador de sitio de red de la ubicación geográfica donde implemente el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bb7b6-107">No es necesario que los servidores perimetrales implementen CAC.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="bb7b6-108">Asegúrese de que CAC está habilitado, ya sea mediante el panel de control de Lync Server o mediante la ejecución del cmdlet especificado en [Habilitar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="bb7b6-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="bb7b6-109">Compruebe que el servicio de control de admisión de llamadas esté habilitado en todos los sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="bb7b6-110">Esto se puede hacer a través del generador de topología.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="bb7b6-111">Si aparece una advertencia durante la publicación, *no* la ignore.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="bb7b6-112">Asegúrese de que todas las subredes que se administren en la red de empresa estén configuradas en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="bb7b6-113">También es esencial que cada subred esté asociada a un sitio de red, como se explica en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="bb7b6-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="bb7b6-114">Compruebe que la subred o las direcciones IP de todos los servidores front-end, las aplicaciones de sucursal con funciones de supervivencia, los servidores de conferencia de audio y vídeo (si se encuentran en un grupo de servidores distinto) y los servidores de mediación estén definidos en los parámetros de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="bb7b6-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

