---
title: 'Lync Server 2013: requisitos previos de software para la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4b0b2e2708abbf3b92223474ec0804c1d11ac8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="9ffc3-102">Requisitos previos de software para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ffc3-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ffc3-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9ffc3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9ffc3-104">Compruebe que la infraestructura en la que tiene pensado implementar la Telefonía IP empresarial satisface el siguiente software necesario como requisito previo:</span><span class="sxs-lookup"><span data-stu-id="9ffc3-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="9ffc3-105">Lync Server 2013 Standard Edition o Enterprise Edition está instalado y en funcionamiento en la red.</span><span class="sxs-lookup"><span data-stu-id="9ffc3-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="9ffc3-106">Todos los servidores perimetrales se implementan y funcionan en la red perimetral, incluidos los servidores perimetrales que ejecutan el servicio perimetral de acceso, el servicio perimetral A/V, el servicio perimetral de conferencia web y un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="9ffc3-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="9ffc3-107">Se requiere Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 para integrar la mensajería unificada de Exchange con Lync Server y proporcionar notificaciones enriquecidas e información del registro de llamadas al Puntos de conexión de Lync.</span><span class="sxs-lookup"><span data-stu-id="9ffc3-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="9ffc3-108">Se han creado uno o más usuarios y están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ffc3-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="9ffc3-109">Los clientes y dispositivos de Lync se han implementado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ffc3-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="9ffc3-110">El generador de topologías está instalado en un servidor de la red.</span><span class="sxs-lookup"><span data-stu-id="9ffc3-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="9ffc3-111">Pasos siguientes: Comprobar los requisitos previos de configuración y seguridad</span><span class="sxs-lookup"><span data-stu-id="9ffc3-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="9ffc3-112">Tras comprobar los requisitos previos de software de la Telefonía IP empresarial, puede usar la documentación para seguir con la preparación de la implementación de Telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="9ffc3-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="9ffc3-113">Compruebe la seguridad, la configuración de usuario y la perquisites de hardware, como se describe en [Security and Configuration Prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="9ffc3-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="9ffc3-114">Instale el servidor de mediación, tal y como se describe en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero *solo* si desea implementar un servidor o grupo de servidores de mediación independiente, ya que los servidores de mediación se instalan como parte del grupo de servidores front-end o del proceso de implementación de servidor Standard Edition al combinarse.</span><span class="sxs-lookup"><span data-stu-id="9ffc3-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="9ffc3-115">Configure las conexiones troncales para proporcionar conectividad con RTC a los usuarios, como se describe en [Configuring troncos in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="9ffc3-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

