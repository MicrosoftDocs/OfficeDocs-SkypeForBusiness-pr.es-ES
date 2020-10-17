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
ms.openlocfilehash: b79fdbaceff06155389d101570b23d6143b9bbcc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536757"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="4ebad-102">Realización y supervisión de copias de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ebad-102">Performing and monitoring backups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ebad-103">_**Última modificación del tema:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="4ebad-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="4ebad-104">Las prioridades empresariales deben impulsar la especificación de los requisitos de copia de seguridad y restauración de su organización.</span><span class="sxs-lookup"><span data-stu-id="4ebad-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="4ebad-105">La realización de copias de seguridad de los servidores y los datos es la primera línea de defensa en la planeación de un desastre.</span><span class="sxs-lookup"><span data-stu-id="4ebad-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="4ebad-106">Los equipos que ejecutan los servicios o roles de servidor de Lync Server 2013 deben tener una copia de la topología actual, las opciones de configuración actuales y las directivas actuales para que puedan funcionar en su rol designado.</span><span class="sxs-lookup"><span data-stu-id="4ebad-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="4ebad-107">Lync Server es responsable de garantizar que esta información se pase a todos los equipos que la necesiten.</span><span class="sxs-lookup"><span data-stu-id="4ebad-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="4ebad-108">Los cmdlets **Export-CsConfiguration** y **Import-CsConfiguration** se usan para realizar copias de seguridad y restaurar la topología, las opciones de configuración y las directivas de Lync Server durante una actualización del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="4ebad-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="4ebad-109">Los cmdlets **Export-CsConfiguration** permiten exportar datos a un. Archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="4ebad-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="4ebad-110">A continuación, puede usar el cmdlet **Import-CsConfiguration** para leerlo. Archivo ZIP y restaurar la topología, las opciones de configuración y las directivas en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="4ebad-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="4ebad-111">A continuación, los servicios de replicación de Lync Server replicarán la información restaurada en otros equipos que ejecutan servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ebad-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="4ebad-112">La capacidad de exportar e importar datos de configuración también se usa durante la configuración inicial de los equipos que se encuentran en la red perimetral (por ejemplo, servidores perimetrales).</span><span class="sxs-lookup"><span data-stu-id="4ebad-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="4ebad-113">Al configurar un equipo en la red perimetral, primero debe realizar una replicación manual con los cmdlets CsConfiguration: debe exportar los datos de configuración mediante **Export-CsConfiguration** y, a continuación, copiar el. Archivo ZIP en el equipo en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="4ebad-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="4ebad-114">Luego, puede usar **Import-CsConfiguration** y el parámetro LocalStore para importar los datos.</span><span class="sxs-lookup"><span data-stu-id="4ebad-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="4ebad-115">Solo tiene que hacerlo una vez.</span><span class="sxs-lookup"><span data-stu-id="4ebad-115">You only have to do this one time.</span></span> <span data-ttu-id="4ebad-116">A continuación, la replicación se producirá automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4ebad-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="4ebad-117">Quién puede iniciar este cmdlet: de forma predeterminada, los miembros de los grupos siguientes están autorizados a ejecutar el cmdlet **Export-CsConfiguration** localmente: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4ebad-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="4ebad-118">Para devolver una lista de todos los roles RBAC a los que se asigna este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4ebad-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="4ebad-119">Se debe realizar una copia de seguridad de todas las bases de datos back-end de SQL 2012 según los [procedimientos recomendados de SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).</span><span class="sxs-lookup"><span data-stu-id="4ebad-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](https://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="4ebad-120">Las pruebas periódicas del plan de recuperación ante desastres para la infraestructura de Lync Server 2013 deben realizarse en un entorno de laboratorio que imite el entorno de producción lo más fielmente posible.</span><span class="sxs-lookup"><span data-stu-id="4ebad-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="4ebad-121">Consulte las tareas mensuales para obtener más información acerca de las pruebas de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="4ebad-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="4ebad-122">Tenga en cuenta que la frecuencia de copia de seguridad se puede ajustar, en función de los objetivos de punto de restauración y punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="4ebad-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="4ebad-123">Como procedimiento recomendado, realice instantáneas regulares y periódicas durante todo el día.</span><span class="sxs-lookup"><span data-stu-id="4ebad-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="4ebad-124">Por lo general, debe realizar copias de seguridad completas cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="4ebad-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4ebad-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ebad-125">See Also</span></span>


[<span data-ttu-id="4ebad-126">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4ebad-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="4ebad-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4ebad-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="4ebad-128">Procedimientos recomendados de SQL</span><span class="sxs-lookup"><span data-stu-id="4ebad-128">SQL best practices</span></span>](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

