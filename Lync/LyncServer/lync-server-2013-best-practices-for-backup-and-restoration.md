---
title: 'Lync Server 2013: procedimientos recomendados para copias de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca14913d063a8691d0477af912e70e72b91143fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535207"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="e75df-102">Procedimientos recomendados para copias de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e75df-102">Best practices for backup and restoration for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e75df-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e75df-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e75df-104">Esta sección incluye dos tipos de procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="e75df-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="e75df-105">Prácticas recomendadas para la copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="e75df-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="e75df-106">Procedimientos recomendados para minimizar el impacto de un desastre.</span><span class="sxs-lookup"><span data-stu-id="e75df-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="e75df-107">Procedimientos recomendados de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="e75df-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="e75df-108">Para facilitar el proceso de copia de seguridad y restauración, aplique los siguientes procedimientos recomendados al realizar una copia de seguridad de los datos o restaurarlos:</span><span class="sxs-lookup"><span data-stu-id="e75df-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="e75df-109">Realice copias de seguridad regularmente y a intervalos apropiados.</span><span class="sxs-lookup"><span data-stu-id="e75df-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="e75df-110">La rutina más sencilla y habitual a la hora de programar copias de seguridad es hacer cada noche copias completas de toda la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e75df-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="e75df-111">A continuación, si la restauración es necesaria, el proceso de restauración solo requiere una copia de seguridad y no se deben perder más datos de un día.</span><span class="sxs-lookup"><span data-stu-id="e75df-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="e75df-112">Si usa cmdlets o el panel de control de Lync Server para realizar cambios en la configuración, use el cmdlet **Export-CsConfiguration** para realizar una copia de seguridad de instantáneas del archivo de configuración de la topología (XDS. MDF) después de realizar los cambios, de modo que no pierda los cambios si necesita restaurar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e75df-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="e75df-113">Tenga en cuenta que se realiza una copia de seguridad de esta configuración en formato XML y se comprime como un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="e75df-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="e75df-114">Asegúrese de que la carpeta compartida que va a usar para hacer copias de seguridad de Lync Server tiene suficiente espacio en disco para contener todos los datos de los que ha realizado una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e75df-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="e75df-115">Programe las copias de seguridad cuando el uso de Lync Server sea normalmente bajo, para mejorar el rendimiento del servidor y la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="e75df-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="e75df-116">Asegúrese de que la ubicación donde se realiza la copia de seguridad de los datos es segura (se recomienda una ubicación remota).</span><span class="sxs-lookup"><span data-stu-id="e75df-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="e75df-117">Conserve los archivos de copia de seguridad donde estarán disponibles, en caso de que necesite restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="e75df-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="e75df-118">Planear y programar pruebas periódicas de los procesos de restauración compatibles con la organización.</span><span class="sxs-lookup"><span data-stu-id="e75df-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="e75df-119">Valide los procesos de copia de seguridad y restauración de antemano para asegurarse de que funcionan como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="e75df-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="e75df-120">Procedimientos recomendados para minimizar el impacto de un desastre</span><span class="sxs-lookup"><span data-stu-id="e75df-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="e75df-121">La mejor estrategia para tratar con interrupciones de servicio desastrosas (causadas por eventos no administrables, como cortes en la alimentación o errores repentinos de hardware) es suponer que se producirán y planear en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="e75df-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="e75df-122">Si los servicios de Lync, con un mínimo de interrupción y interrupción, son fundamentales para el negocio en su organización, debe considerar la posibilidad de implementar grupos emparejados de servidores front-end, como se describe en [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e75df-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="e75df-123">A continuación, si uno de estos grupos de servidores tiene un desastre, un administrador puede cambiar a los usuarios de ese grupo para que los atienda el otro grupo, con un mínimo de tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="e75df-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="e75df-124">Los planes de administración ante desastres que desarrolle como parte de su estrategia de copia de seguridad y restauración deben incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e75df-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="e75df-125">Mantener los medios de software y las actualizaciones de software y firmware, disponibles fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e75df-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="e75df-126">Mantenga registros de hardware y software.</span><span class="sxs-lookup"><span data-stu-id="e75df-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="e75df-127">Realizar copias de seguridad de los datos con regularidad y supervisar la integridad de las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e75df-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="e75df-128">Forme a su personal en recuperación de desastres, documente todos los procedimientos y lleve a cabo simulacros de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="e75df-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="e75df-129">Mantener disponible el hardware de reserva o, si tiene un contrato de nivel de servicio (SLA), contratando a los proveedores de hardware y proveedores los reemplazos de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="e75df-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="e75df-130">Separe la ubicación de sus archivos de registro de transacciones (archivos .ldf) y los archivos de bases de datos (archivos .mdf).</span><span class="sxs-lookup"><span data-stu-id="e75df-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

