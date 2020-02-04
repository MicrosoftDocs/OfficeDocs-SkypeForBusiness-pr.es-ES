---
title: 'Lync Server 2013: realización y supervisión de copias de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="69a59-102">Realizar y supervisar copias de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69a59-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69a59-103">_**Última modificación del tema:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="69a59-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="69a59-104">Las prioridades empresariales deben impulsar la especificación de los requisitos de copia de seguridad y restauración de su organización.</span><span class="sxs-lookup"><span data-stu-id="69a59-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="69a59-105">La realización de copias de seguridad de los datos y los servidores es la primera línea de defensa en el planeamiento de un desastre.</span><span class="sxs-lookup"><span data-stu-id="69a59-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="69a59-106">Los equipos que ejecutan los servicios de Lync Server 2013 o los roles de servidor deben tener una copia de la topología actual, de las opciones de configuración actuales y de las directivas actuales antes de que puedan funcionar con su función designada.</span><span class="sxs-lookup"><span data-stu-id="69a59-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="69a59-107">Lync Server es responsable de asegurarse de que esta información se transmita a todos los equipos que la necesiten.</span><span class="sxs-lookup"><span data-stu-id="69a59-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="69a59-108">Los cmdlets **Export-CsConfiguration** y **Import-CsConfiguration** se usan para realizar copias de seguridad y restaurar la topología, las opciones de configuración y las directivas de Lync Server durante una actualización de almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="69a59-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="69a59-109">Los cmdlets **Export-CsConfiguration** permiten exportar datos a un. Archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="69a59-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="69a59-110">Puede usar el cmdlet **Import-CsConfiguration** para leerlo. Archivo ZIP y restaurar la topología, los parámetros de configuración y las directivas en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="69a59-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="69a59-111">Después, los servicios de replicación de Lync Server replicarán la información restaurada en otros equipos que ejecuten servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69a59-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="69a59-112">La capacidad de exportar e importar datos de configuración también se usa durante la configuración inicial de los equipos que se encuentran en la red perimetral (por ejemplo, los servidores perimetrales).</span><span class="sxs-lookup"><span data-stu-id="69a59-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="69a59-113">Al configurar un equipo en la red perimetral, primero debe realizar una replicación manual con los cmdlets de CsConfiguration: debe exportar los datos de configuración con **Export-CsConfiguration** y, a continuación, copie el archivo. Archivo ZIP en el equipo de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="69a59-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="69a59-114">Después de ese, puede usar **Import-CsConfiguration** y el parámetro LocalStore para importar los datos.</span><span class="sxs-lookup"><span data-stu-id="69a59-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="69a59-115">Solo tienes que hacerlo una vez.</span><span class="sxs-lookup"><span data-stu-id="69a59-115">You only have to do this one time.</span></span> <span data-ttu-id="69a59-116">Después de eso, la replicación se realizará de forma automática.</span><span class="sxs-lookup"><span data-stu-id="69a59-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="69a59-117">¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet **Export-CsConfiguration** de forma local: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="69a59-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="69a59-118">Para devolver una lista de todos los roles de RBAC, este cmdlet se asigna a (incluidos los roles de RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="69a59-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="69a59-119">Se debe realizar una copia de seguridad de todas las bases de datos back-end de SQL 2012 según las recomendaciones de [SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).</span><span class="sxs-lookup"><span data-stu-id="69a59-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="69a59-120">Las pruebas periódicas del plan de recuperación ante desastres para su infraestructura de Lync Server 2013 deberían realizarse en un entorno de laboratorio que imite el entorno de producción de la mejor manera posible.</span><span class="sxs-lookup"><span data-stu-id="69a59-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="69a59-121">Para obtener más información sobre las pruebas de recuperación ante desastres, consulte las tareas mensuales.</span><span class="sxs-lookup"><span data-stu-id="69a59-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="69a59-122">Tenga en cuenta que la frecuencia de la copia de seguridad se puede ajustar en función de su punto de restauración y sus objetivos de punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="69a59-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="69a59-123">Como práctica recomendada, realice instantáneas periódicas y periódicas durante todo el día.</span><span class="sxs-lookup"><span data-stu-id="69a59-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="69a59-124">Por lo general, deberías realizar copias de seguridad completas cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="69a59-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="69a59-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="69a59-125">See Also</span></span>


[<span data-ttu-id="69a59-126">Importar-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="69a59-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="69a59-127">Exportar-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="69a59-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="69a59-128">Procedimientos recomendados de SQL</span><span class="sxs-lookup"><span data-stu-id="69a59-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

