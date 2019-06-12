---
title: 'Lync Server 2013: Requisitos previos de software para la telefonía IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a0868-102">Requisitos previos de software para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0868-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0868-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a0868-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a0868-104">Compruebe que la infraestructura en la que desea implementar Enterprise Voice cumpla los siguientes requisitos previos de software:</span><span class="sxs-lookup"><span data-stu-id="a0868-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="a0868-105">Lync Server 2013 Standard Edition o Enterprise Edition está instalado y en funcionamiento en su red.</span><span class="sxs-lookup"><span data-stu-id="a0868-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="a0868-106">Todos los servidores perimetrales se implementan y funcionan en la red perimetral, incluidos los servidores perimetrales que ejecutan el servicio perimetral de acceso, el servicio perimetral a/V, el servicio perimetral de conferencias web y un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="a0868-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="a0868-107">Se necesita Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 para integrar la mensajería unificada de Exchange con Lync Server y ofrecer notificaciones enriquecidas e información de registro de llamadas al Puntos de conexión de Lync.</span><span class="sxs-lookup"><span data-stu-id="a0868-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="a0868-108">Uno o más usuarios se han creado y habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0868-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="a0868-109">Los clientes y dispositivos de Lync se han implementado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0868-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="a0868-110">El generador de topología se instala en un servidor de su red.</span><span class="sxs-lookup"><span data-stu-id="a0868-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="a0868-111">Pasos siguientes: comprobar la seguridad y los requisitos previos de configuración</span><span class="sxs-lookup"><span data-stu-id="a0868-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="a0868-112">Después de comprobar los requisitos previos de software de telefonía IP empresarial, puede usar la documentación para continuar con la preparación de la implementación de telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="a0868-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="a0868-113">Comprobar la seguridad, la configuración de usuario y el hardware perquisites, como se describe en [seguridad y configuración requisitos previos para telefonía IP empresarial en Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="a0868-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="a0868-114">Instale el servidor de mediación, como se describe en [instalar los archivos de Media Server en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero *solo* si desea implementar un servidor o grupo de mediación independiente, ya que los servidores de mediación están instalados como parte del grupo de servidores front-end o Proceso de implementación de servidor Standard Edition cuando se colocan.</span><span class="sxs-lookup"><span data-stu-id="a0868-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="a0868-115">Configure conexiones troncales para proporcionar conectividad RTC para los usuarios, como se describe en [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="a0868-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

