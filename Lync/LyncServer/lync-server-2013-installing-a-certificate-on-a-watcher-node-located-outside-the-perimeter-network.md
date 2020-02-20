---
title: 'Lync Server 2013: instalar un certificado en un nodo de monitor ubicado fuera de la red perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4704cc5284b6923967e530492edf2a07054a2a19
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="a31b7-102">Instalar un certificado en un nodo de monitor ubicado fuera de la red perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a31b7-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a31b7-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a31b7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a31b7-104">Los agentes de System Center Operations Manager que se ejecutan en una red perimetral (como un servidor perimetral de Lync Server), fuera de la empresa (como un nodo de monitor de transacciones sintéticas externo) o en un límite de confianza de los servicios de dominio de Active Directory, podrían requerir la configuración de un servidor de puerta de enlace de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a31b7-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="a31b7-105">Este rol de servidor permite que los agentes que no tienen una relación de confianza con el servidor de administración raíz inicien alertas.</span><span class="sxs-lookup"><span data-stu-id="a31b7-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="a31b7-106">Para obtener más información, vea "administrar servidores de puerta de enlace en Operations Manager 2007" en la biblioteca [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703)de TechNet de System Center Operations Manager en.</span><span class="sxs-lookup"><span data-stu-id="a31b7-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="a31b7-107">Si implementa un agente en una de estas ubicaciones, también tendrá que solicitar y configurar un certificado que permita al nodo de monitor enviar alertas a System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a31b7-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="a31b7-108">Para simplificar este proceso, el equipo de Operations Manager creó una serie de utilidades para que pueda solicitar e instalar el tipo correcto de certificado en la PC nodo de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a31b7-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="a31b7-109">Para obtener más información y para descargar estas utilidades, consulte el artículo del blog "obtención de certificados para agentes no Unidos a un dominio fácilmente con el asistente [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421)para generación de certificados" en.</span><span class="sxs-lookup"><span data-stu-id="a31b7-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

