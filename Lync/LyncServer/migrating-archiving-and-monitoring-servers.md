---
title: Migrar servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572cbee046ed960017a3b60b7ae68c58ec67cf23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="a6059-102">Migrar servidores de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="a6059-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6059-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a6059-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a6059-104">Si ha implementado el servidor de archivado y el servidor de supervisión en el entorno de Lync Server 2010, puede implementar estos servidores en el entorno de Lync Server 2013 después de migrar los grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="a6059-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="a6059-105">Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo de pruebas piloto de Lync Server 2013 antes de la migración para que la funcionalidad esté disponible durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="a6059-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="a6059-106">Si desea mantener la funcionalidad de archivado y supervisión durante el proceso de migración, tenga en cuenta las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="a6059-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="a6059-107">Los datos de archivado y supervisión no se mueven a la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6059-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="a6059-108">Los datos de los que haya hecho una copia de seguridad antes de retirar el entorno heredado serán el historial de actividad en el entorno de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a6059-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="a6059-109">La versión de Lync Server 2010 del servidor de archivado y del servidor de supervisión solo se puede asociar con un grupo front-end de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a6059-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="a6059-110">En Lync Server 2013, el archivado y la supervisión ya no tienen roles de servidor, pero los servicios integrados en el grupo front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6059-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="a6059-111">Durante el tiempo que coexistan las implementaciones heredadas de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en los grupos de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a6059-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="a6059-112">Archivado y supervisión en Lync Server 2013 recopilar datos para los usuarios alojados en los grupos de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6059-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6059-113">Durante la fase de migración, cuando aún está usando su servidor perimetral heredado con el nuevo grupo piloto de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado continúa recopilando datos para los usuarios alojados en los grupos de Lync Server 2010 y archivados en Lync Server 2013 recopila datos para los usuarios alojados en los grupos de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6059-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="a6059-114">Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Lync Server 2013, consulte con su proveedor sobre cuándo y cómo necesita integrar la solución de terceros con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6059-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

