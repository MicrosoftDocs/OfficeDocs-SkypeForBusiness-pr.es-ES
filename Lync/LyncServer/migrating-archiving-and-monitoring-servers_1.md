---
title: Migrar servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3abd26386ad26e3b6628d5b9db873bd17373be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="b62ce-102">Migrar servidores de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="b62ce-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b62ce-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b62ce-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b62ce-104">Si ha implementado el servidor de archivado y el servidor de supervisión en Office Communications Server 2007 R2, puede implementar estos servidores en el entorno de Lync Server 2013 después de migrar los grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b62ce-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="b62ce-105">Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo piloto antes de realizar la migración para que la funcionalidad esté disponible durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="b62ce-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="b62ce-106">Si quiere que la funcionalidad de archivado y supervisión durante la migración y la fase de coexistencia, tenga en cuenta las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="b62ce-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="b62ce-107">Los datos de archivado y supervisión no se mueven a la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b62ce-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b62ce-108">Los datos de los que haya hecho una copia de seguridad antes de retirar el entorno heredado serán el historial de actividad en el Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b62ce-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="b62ce-109">La versión de Office Communications Server 2007 R2 del servidor de archivado y del servidor de supervisión solo se puede asociar con un grupo front-end de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b62ce-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="b62ce-110">En Lync Server 2013, el archivado y la supervisión ya no tienen roles de servidor, pero los servicios integrados en el grupo front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b62ce-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="b62ce-111">Durante el tiempo que coexistan las implementaciones heredadas de Lync Server 2013, la versión de Office Communications Server 2007 R2 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en los grupos de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b62ce-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="b62ce-112">La versión de Lync Server 2013 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en los grupos de servidores de Skype empresarial 2013.</span><span class="sxs-lookup"><span data-stu-id="b62ce-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b62ce-113">Durante la fase de migración, cuando aún está usando su servidor perimetral heredado con el nuevo grupo piloto de Lync Server 2013, la versión R2 de Office Communications Server 2007 R2 recopila datos para usuarios alojados en Office Communications Server 2007 Los grupos R2 y la versión 2013 de Lync Server del servidor de archivado recopilan datos para los usuarios alojados en los grupos de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b62ce-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="b62ce-114">Si usa una solución de archivado y supervisión de terceros junto con el servidor de archivado y el servidor de supervisión, hable con su proveedor sobre cuándo y cómo necesita integrar la solución de terceros con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b62ce-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

