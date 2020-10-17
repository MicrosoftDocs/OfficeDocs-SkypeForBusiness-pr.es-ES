---
title: Migrar servidores de archivado y supervisión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba32bf2b35a0d2e8b0048ebb9c62aac09cb6eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527417"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="9dd25-102">Migrar servidores de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="9dd25-102">Migrating Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dd25-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9dd25-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9dd25-104">Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno de Lync Server 2010, puede implementar estos servidores en su entorno de Lync Server 2013 después de migrar los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="9dd25-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="9dd25-105">Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar el archivado y la supervisión al grupo piloto de Lync Server 2013 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="9dd25-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="9dd25-106">Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9dd25-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="9dd25-107">Los datos de archivado y supervisión no se mueven a la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dd25-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="9dd25-108">Los datos de los que realice una copia de seguridad antes de retirar el entorno heredado serán su historial de actividades en el entorno de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9dd25-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="9dd25-109">La versión 2010 de Lync Server del servidor de archivado y el servidor de supervisión solo pueden asociarse con un grupo de servidores front-end de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9dd25-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="9dd25-110">En Lync Server 2013, el archivado y la supervisión ya no tienen roles de servidor, sino que están integrados en el grupo de servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dd25-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="9dd25-111">Durante el tiempo que coexisten las implementaciones heredadas de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios hospedados en los grupos de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9dd25-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="9dd25-112">Archivado y supervisión en Lync Server 2013 recopilar datos para los usuarios alojados en los grupos de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dd25-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9dd25-113">Durante la fase de migración, cuando sigue usando el servidor perimetral heredado con el nuevo grupo piloto de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado continúa recopilando datos para los usuarios hospedados en los grupos de servidores de Lync Server 2010 y el archivado en Lync Server 2013 recopila datos para los usuarios hospedados en los grupos de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dd25-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="9dd25-114">Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Lync Server 2013, consulte al proveedor Cuándo y cómo debe integrar la solución de terceros con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dd25-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

