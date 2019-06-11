---
title: 'Lync Server 2013: Requisitos para publicar una topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e90604315732d9e9bfe4c45968ff0bcf5fbd2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="969cc-102">Requisitos para publicar una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="969cc-102">Requirements to publish a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="969cc-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="969cc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="969cc-104">En este tema se describen los requisitos de software y de infraestructura específicos de la publicación de una topología, ya sea mediante el creador de topologías o la interfaz de línea de comandos del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="969cc-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="969cc-105">Estos requisitos son adicionales a los requisitos del sistema operativo general, el software y los permisos aplicables a todas las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="969cc-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="969cc-106">Asegúrese de cumplir con todos los requisitos de las herramientas administrativas antes de publicar una topología.</span><span class="sxs-lookup"><span data-stu-id="969cc-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="969cc-107">Debe ejecutar el generador de topología en un equipo que se haya unido al mismo dominio o al bosque de la implementación de Lync Server 2013 que está creando para que los pasos de preparación de los servicios de dominio de Active Directory ya estén completados, lo que le permitirá usar las herramientas administrativas en ese equipo para publicar correctamente su topología.</span><span class="sxs-lookup"><span data-stu-id="969cc-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="969cc-108">Los equipos definidos en la topología deben unirse al dominio, excepto los servidores perimetrales y AD DS.</span><span class="sxs-lookup"><span data-stu-id="969cc-108">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS.</span></span> <span data-ttu-id="969cc-109">Sin embargo, no es necesario que los equipos estén conectados al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="969cc-109">However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="969cc-110">El recurso compartido de archivos para el grupo debe crearse y estar disponible para los usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="969cc-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="969cc-111">Para poder publicar un grupo de servidores front-end Enterprise Edition, el servidor back-end basado en SQL Server debe estar unido al dominio en el que está implementando los servidores, en línea y configurado con las reglas de Firewall apropiadas para que estén disponibles para los usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="969cc-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="969cc-112">Para obtener más información sobre cómo especificar excepciones de firewall, consulte [Understanding Firewall Requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="969cc-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="969cc-113">Para obtener más información sobre cómo configurar SQL Server, consulte [configurar SQL Server para Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="969cc-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="969cc-114">El servidor Standard Edition tiene una base de datos en el que se acepta la configuración publicada.</span><span class="sxs-lookup"><span data-stu-id="969cc-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="969cc-115">Primero debe ejecutar la tarea preparar el programa de instalación del <STRONG>servidor Standard Edition</STRONG> en el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="969cc-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="969cc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="969cc-116">See Also</span></span>


[<span data-ttu-id="969cc-117">Publicar la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="969cc-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="969cc-118">Delegar permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="969cc-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="969cc-119">Requisitos de software para herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="969cc-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="969cc-120">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="969cc-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="969cc-121">Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="969cc-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

