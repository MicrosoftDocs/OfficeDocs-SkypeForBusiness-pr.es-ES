---
title: 'Lync Server 2013: ubicación de los archivos de registro y datos de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc1ae5f876986f6387ce4b1038f89115b746de49
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="2da74-102">Ubicación de los archivos de registro y datos de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2da74-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2da74-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2da74-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2da74-104">Durante la planeación y la implementación de Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 para el grupo de servidores front-end de Lync Server 2013, una consideración importante es la colocación de los datos y los archivos de registro en discos duros físicos para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2da74-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="2da74-105">La configuración de disco recomendada es implementar un conjunto de RAID 1 + 0 con 6 ejes.</span><span class="sxs-lookup"><span data-stu-id="2da74-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="2da74-106">Colocar todos los archivos de base de datos y registro que usan el grupo de servidores front-end y los roles y servicios asociados del servidor (es decir, el servidor de archivado y supervisión, el servicio de grupo de respuesta de Lync Server, el servicio de estacionamiento de llamadas de Lync Server) en el conjunto de unidades RAID mediante Lync Server. El Asistente para la implementación dará como resultado una configuración que se ha probado para obtener un buen rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2da74-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="2da74-107">En la siguiente tabla se detallan los archivos de base de datos y las funciones de las que son responsables.</span><span class="sxs-lookup"><span data-stu-id="2da74-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2da74-108">Si las directivas y las configuraciones de SQL Server requieren una instalación más especializada, los archivos de registro y de base de datos se pueden instalar en cualquier ubicación predefinida mediante el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2da74-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="2da74-109">Consulte <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalación de bases de datos mediante el shell de administración de Lync Server en Lync server 2013</A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2da74-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="2da74-110">Archivos de registro y de datos para el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="2da74-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2da74-111">Archivos de base de datos de almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="2da74-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="2da74-112">Finalidad del registro o archivo de datos</span><span class="sxs-lookup"><span data-stu-id="2da74-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2da74-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-114">Archivo de registro de transacciones para el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="2da74-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-115">XDS. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-116">Mantiene la configuración de la topología actual de Lync Server 2013, tal y como se ha definido y publicado por el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="2da74-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-117">Lis. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-118">Archivo de datos del servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="2da74-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-119">Lis. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-120">Registro de transacciones para el archivo de datos del servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="2da74-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="2da74-121">Archivos de registro y de datos para el usuario, las conferencias y la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="2da74-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2da74-122">Principales archivos de base de datos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2da74-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="2da74-123">Finalidad del registro o archivo de datos</span><span class="sxs-lookup"><span data-stu-id="2da74-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2da74-124">RTC. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-125">Datos de usuario persistentes (por ejemplo, listas de control de acceso (ACL), contactos, conferencias programadas)</span><span class="sxs-lookup"><span data-stu-id="2da74-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-127">Registro de transacciones para datos RTC</span><span class="sxs-lookup"><span data-stu-id="2da74-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-128">RTCDyn. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-129">Mantiene datos de usuario transitorios (datos de tiempo de ejecución de presencia)</span><span class="sxs-lookup"><span data-stu-id="2da74-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-131">Registro de transacciones para datos de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="2da74-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-132">Rtcab. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-133">La base de datos de la libreta de direcciones de las comunicaciones en tiempo real (RTC) es el repositorio de SQL Server cuando se almacena la información del servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="2da74-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-134">Rtcab. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-135">Registro de transacciones para el servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="2da74-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="2da74-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="2da74-137">Hospeda el directorio de conferencia</span><span class="sxs-lookup"><span data-stu-id="2da74-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-138">Rtcxds. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-139">Mantiene la copia de seguridad de los datos de usuario</span><span class="sxs-lookup"><span data-stu-id="2da74-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-141">Registro de transacciones para datos de Rtcxds</span><span class="sxs-lookup"><span data-stu-id="2da74-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="2da74-142">Archivos de registro y de datos para el estacionamiento de llamadas y el grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="2da74-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2da74-143">Base de datos de aplicación</span><span class="sxs-lookup"><span data-stu-id="2da74-143">Application database</span></span></th>
<th><span data-ttu-id="2da74-144">Finalidad del registro o archivo de datos</span><span class="sxs-lookup"><span data-stu-id="2da74-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2da74-145">Cpsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-146">Base de datos de información dinámica para la aplicación estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="2da74-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-148">Registro de transacciones para el archivo de datos de aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="2da74-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-149">Rgsconfig. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-150">Archivo de datos del servicio de grupo de respuesta de Lync Server para la configuración de los servicios</span><span class="sxs-lookup"><span data-stu-id="2da74-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-152">Archivo de registro de transacciones para la configuración de la aplicación del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="2da74-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-153">Rgsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-154">Archivo de datos del servicio de grupo de respuesta para operaciones en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2da74-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-156">Registro de transacciones para el archivo de datos en tiempo de ejecución del servicio de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="2da74-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="2da74-157">Archivos de registro y de datos para el servidor de supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="2da74-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2da74-158">Archivos de la base de datos de supervisión y archivado</span><span class="sxs-lookup"><span data-stu-id="2da74-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="2da74-159">Finalidad del registro o archivo de datos</span><span class="sxs-lookup"><span data-stu-id="2da74-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2da74-160">LcsCdr. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-161">Almacén de datos para el proceso de registro de detalles de llamadas (CDR) del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="2da74-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-163">Registro de transacciones para datos de registro de detalles de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="2da74-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-164">QoEMetrics. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-165">Archivo de datos de calidad de la experiencia almacenado desde el servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="2da74-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-167">Registro de transacciones para datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="2da74-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2da74-168">Lcslog. MDF</span><span class="sxs-lookup"><span data-stu-id="2da74-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="2da74-169">Archivo de datos para la retención de los datos de mensajería instantánea y de conferencias en un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="2da74-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2da74-170">Lcslog. ldf</span><span class="sxs-lookup"><span data-stu-id="2da74-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="2da74-171">Registro de transacciones para datos de archivado</span><span class="sxs-lookup"><span data-stu-id="2da74-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2da74-p103">En este tema, se hacen referencias al disco y al conjunto de discos RAID. Tenga en cuenta que en la configuración de recursos de SQL Server, un disco hace referencia a un único dispositivo de hardware. Una unidad de disco duro con dos particiones, una que contiene archivos de registro y otra que contiene archivos de datos, no es lo mismo que dos discos, cada uno de ellos dedicados a archivos de registro o de datos.</span><span class="sxs-lookup"><span data-stu-id="2da74-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="2da74-175">En referencia a conjuntos de discos RAID, existen varias tecnologías RAID diferentes de varios proveedores.</span><span class="sxs-lookup"><span data-stu-id="2da74-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="2da74-176">Y, con la proliferación de redes de área de almacenamiento (SAN), los conjuntos de discos RAID dedicados a un único sistema son cada vez menos habituales.</span><span class="sxs-lookup"><span data-stu-id="2da74-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="2da74-177">Debe consultar a su proveedor de RAID o SAN para determinar cuál es la mejor configuración para su diseño de disco al configurar el rendimiento de SQL Server con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2da74-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="2da74-178">Además, tenga en cuenta que no todas las unidades de disco se crean del mismo modo; unas rinden mejor que otras.</span><span class="sxs-lookup"><span data-stu-id="2da74-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="2da74-179">Incluso las unidades del mismo fabricante pueden variar su rendimiento debido a la velocidad de rotación, el tamaño de la memoria caché en el hardware y otros factores.</span><span class="sxs-lookup"><span data-stu-id="2da74-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

