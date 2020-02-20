---
title: 'Lync Server 2013: requisitos para publicar una topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dac78de6d6cf0f86f0411b8085e6f8172b0f2f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="037b3-102">Requisitos para publicar una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="037b3-102">Requirements to publish a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="037b3-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="037b3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="037b3-104">En este tema se describen los requisitos de infraestructura y software específicos para la publicación de una topología, ya sea mediante el generador de topologías o la interfaz de línea de comandos del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="037b3-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="037b3-105">Estos requisitos son adicionales a los requisitos de sistema operativo, software y permisos generales aplicables a todas las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="037b3-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="037b3-106">Asegúrese de que cumple con todos los requisitos de las herramientas administrativas antes de publicar una topología.</span><span class="sxs-lookup"><span data-stu-id="037b3-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="037b3-107">Debe ejecutar el generador de topologías en un equipo que se haya unido al mismo dominio o al bosque de la implementación de Lync Server 2013 que está creando para que los pasos de preparación de los servicios de dominio de Active Directory ya se hayan completado, lo que le permite usar las herramientas administrativas en que el equipo publique correctamente la topología.</span><span class="sxs-lookup"><span data-stu-id="037b3-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="037b3-p102">Los equipos definidos en la topología deben estar unidos al dominio, excepto los servidores perimetrales y en AD DS. Sin embargo, los equipos no necesitan estar en línea cuando publica la topología.</span><span class="sxs-lookup"><span data-stu-id="037b3-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="037b3-110">El recurso compartido de archivos para el grupo de servidores debe estar creado y disponible para los usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="037b3-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="037b3-111">Para publicar un grupo de servidores front-end Enterprise Edition, el servidor back-end basado en SQL Server debe estar unido al dominio en el que va a implementar los servidores, en línea y configurados con las reglas de Firewall adecuadas para que estén disponibles para los usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="037b3-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="037b3-112">Para obtener información detallada sobre cómo especificar las excepciones de firewall, consulte [Understanding Firewall Requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="037b3-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="037b3-113">Para obtener más información acerca de la configuración de SQL Server, consulte [configurar SQL Server para Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="037b3-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="037b3-114">El servidor Standard Edition tiene una base de datos combinada que aceptará la configuración publicada.</span><span class="sxs-lookup"><span data-stu-id="037b3-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="037b3-115">Primero debe ejecutar la tarea de configuración <STRONG>preparar el primer servidor Standard Edition</STRONG> en el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="037b3-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="037b3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="037b3-116">See Also</span></span>


[<span data-ttu-id="037b3-117">Publicar la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="037b3-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="037b3-118">Delegación de permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="037b3-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="037b3-119">Requisitos de software de herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="037b3-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="037b3-120">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="037b3-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="037b3-121">Permisos y derechos de administrador necesarios para la instalación y administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="037b3-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

