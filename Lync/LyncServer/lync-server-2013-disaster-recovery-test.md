---
title: 'Lync Server 2013: prueba de recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2d36ec6ad1afb8c41c7c5f614e90e03ce4d9282
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528957"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="1ddc7-102">Prueba de recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ddc7-102">Disaster recovery test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ddc7-103">_**Última modificación del tema:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="1ddc7-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="1ddc7-104">Realice una recuperación del sistema para un servidor de grupo de servidores de Lync Server 2013 para probar el proceso de recuperación ante desastres documentado.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="1ddc7-105">Esta prueba simulará un error de hardware completo para un servidor y ayudará a garantizar que los recursos, los planes y los datos estén disponibles para la recuperación.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="1ddc7-106">Intente girar el foco de la prueba cada mes para que la organización Pruebe el error de un servidor diferente o de otro elemento del equipo cada vez.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="1ddc7-107">Tenga en cuenta que la programación por la que las organizaciones realizan pruebas de recuperación ante desastres variarán.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="1ddc7-108">Es muy importante que las pruebas de recuperación ante desastres no se ignore o sin atender.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="1ddc7-109">Exporte la topología, las directivas y las opciones de configuración de Lync Server 2013 a un archivo.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="1ddc7-110">Entre otras cosas, este archivo puede usarse para restaurar esta información en el almacén de administración central después de una actualización, un error de hardware o algún otro problema ha provocado la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="1ddc7-111">Importe la topología, las directivas y las opciones de configuración de Lync Server 2013 al almacén de administración central o al equipo local, como se muestra en los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="1ddc7-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="1ddc7-112">Para hacer una copia de seguridad de los datos de 2013 de producción de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1ddc7-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="1ddc7-113">Realice una copia de seguridad de las bases de datos RTC y LCSLog mediante el proceso de copia de seguridad estándar de SQL Server para volcar la base de datos en un dispositivo de volcado de archivos o cinta.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="1ddc7-114">Use una aplicación de copia de seguridad de terceros para realizar una copia de seguridad de los datos en archivo o en cinta.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="1ddc7-115">Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="1ddc7-116">Use la copia de seguridad del sistema de archivos o de terceros para hacer copias de seguridad de contenido de reuniones y registros de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="1ddc7-117">Use la herramienta de línea de comandos Export-CsConfiguration para realizar una copia de seguridad de la configuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="1ddc7-118">El primer paso del procedimiento de conmutación por error incluye un movimiento forzoso de los usuarios del grupo de producción al grupo de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="1ddc7-119">Esto será un movimiento forzado porque el grupo de producción no estará disponible para aceptar la reubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="1ddc7-120">El proceso de migración de usuarios de Lync Server 2013 es, en realidad, un cambio en un atributo del objeto de cuenta de usuario además de una actualización de registros en la base de datos SQL de RTC.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="1ddc7-121">Estos datos se pueden restaurar a través de los dos procesos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ddc7-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="1ddc7-122">RTC Database puede restaurarse a partir del dispositivo de volcado de copia de seguridad original desde el SQL Server de producción mediante el proceso de restauración estándar de SQL Server o mediante una utilidad de copia de seguridad y restauración de terceros.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="1ddc7-123">Los datos de contacto de los usuarios se pueden restaurar con la utilidad de DBIMPEXP.exe mediante el archivo XML que se creó a partir de la exportación de SQL Server de producción.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="1ddc7-124">Una vez que se han restaurado estos datos, los usuarios pueden conectarse de forma eficaz al grupo de recuperación ante desastres de Lync Server 2013 y funcionar como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="1ddc7-125">Para permitir que los usuarios se conecten al grupo de recuperación ante desastres Lync Server 2013, será necesario cambiar un registro DNS.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="1ddc7-126">Los clientes harán referencia al grupo de producción Lync Server 2013 mediante la configuración automática y los registros SRV de DNS de:</span><span class="sxs-lookup"><span data-stu-id="1ddc7-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="1ddc7-127">SRV: \_ SIP. \_ MTLS.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-127">SRV: \_sip.\_tls.\<domain\></span></span> <span data-ttu-id="1ddc7-128">/CNAME: SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-128">/CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="1ddc7-129">CNAME: SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-129">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="1ddc7-130">/cvc-pool-1.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-130">/cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="1ddc7-131">Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="1ddc7-131">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="1ddc7-132">CNAME: SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-132">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="1ddc7-133">/DROCSPool.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-133">/DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="1ddc7-134">SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-134">Sip.\<domain\></span></span>

  - <span data-ttu-id="1ddc7-135">Va.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-135">AV.\<domain\></span></span>

  - <span data-ttu-id="1ddc7-136">WebConf.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-136">webconf.\<domain\></span></span>

  - <span data-ttu-id="1ddc7-137">OCSServices.\<domain\></span><span class="sxs-lookup"><span data-stu-id="1ddc7-137">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ddc7-138">Para obtener información detallada acerca de los procedimientos de administración y administración, consulte <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">copia de seguridad y restauración de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1ddc7-138">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ddc7-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ddc7-139">See Also</span></span>


[<span data-ttu-id="1ddc7-140">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ddc7-140">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="1ddc7-141">Cmdlets de copia de seguridad y alta disponibilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ddc7-141">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="1ddc7-142">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="1ddc7-142">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="1ddc7-143">Copia de seguridad y restauración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ddc7-143">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="1ddc7-144">Administración del servicio de copia de seguridad, alta disponibilidad y recuperación ante desastres de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ddc7-144">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

