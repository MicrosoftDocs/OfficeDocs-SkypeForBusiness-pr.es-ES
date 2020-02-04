---
title: 'Lync Server 2013: SQL Ubicación de datos y de archivos de registro de SQL Server'
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
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="65ac2-102">Ubicación de datos y de archivos de registro de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65ac2-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65ac2-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="65ac2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="65ac2-104">Durante la planeación y la implementación de Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 para su grupo front-end de Lync Server 2013, una consideración importante es la colocación de los datos y los archivos de registro en discos duros físicos para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="65ac2-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="65ac2-105">La configuración de disco recomendada es implementar un conjunto de RAID 1 + 0 con 6 ejes.</span><span class="sxs-lookup"><span data-stu-id="65ac2-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="65ac2-106">Colocar todos los archivos de base de datos y de registro usados por el grupo de servidores front-end y los roles y servicios de servidor asociados (es decir, servidor de archivado y supervisión, servicio de grupo de respuesta de Lync Server, servicio de estacionamiento de llamadas de Lync Server) en el conjunto de unidades RAID con el servidor de Lync. El Asistente para la implementación generará una configuración que se ha probado para un buen rendimiento.</span><span class="sxs-lookup"><span data-stu-id="65ac2-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="65ac2-107">Los archivos de base de datos y su responsabilidad se detallan en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="65ac2-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65ac2-108">Si las directivas y la configuración de SQL Server requieren una instalación más especializada, la base de datos y los archivos de registro se pueden instalar en cualquier ubicación predefinida mediante el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65ac2-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="65ac2-109">Para obtener más información, vea <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalación de bases de datos con el shell de administración de Lync Server en Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="65ac2-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="65ac2-110">Archivos de datos y de registro para el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="65ac2-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65ac2-111">Archivos de base de datos de almacenamiento de administración central</span><span class="sxs-lookup"><span data-stu-id="65ac2-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="65ac2-112">Archivo de datos o propósito de registro</span><span class="sxs-lookup"><span data-stu-id="65ac2-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-114">Archivo de registro de transacciones para el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="65ac2-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-115">XDS. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-116">Mantiene la configuración de la topología actual de Lync Server 2013, definida y publicada por el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="65ac2-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-117">Lis. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-118">Archivo de datos del servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="65ac2-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-119">Lis. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-120">Registro de transacciones del archivo de datos del servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="65ac2-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="65ac2-121">Archivos de datos y de registro para usuarios, conferencias y libretas de direcciones</span><span class="sxs-lookup"><span data-stu-id="65ac2-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65ac2-122">Archivos de base de datos básicos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65ac2-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="65ac2-123">Archivo de datos o propósito de registro</span><span class="sxs-lookup"><span data-stu-id="65ac2-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-124">RTC. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-125">Datos de usuario persistentes (por ejemplo, listas de control de acceso (ACL), contactos, conferencias programadas)</span><span class="sxs-lookup"><span data-stu-id="65ac2-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-127">Registro de transacciones de datos de RTC</span><span class="sxs-lookup"><span data-stu-id="65ac2-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-128">RTCDyn. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-129">Mantiene datos de usuario transitorios (datos de presencia en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="65ac2-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-131">Registro de transacciones de datos de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="65ac2-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-132">Rtcab. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-133">La base de datos de la libreta de direcciones de las comunicaciones en tiempo real (RTC) es el repositorio de SQL Server donde se almacena la información del servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="65ac2-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-134">Rtcab. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-135">Registro de transacciones para el servicio de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="65ac2-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="65ac2-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="65ac2-137">Hospeda el directorio de conferencia</span><span class="sxs-lookup"><span data-stu-id="65ac2-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-138">Rtcxds. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-139">Mantiene la copia de seguridad de los datos de usuario</span><span class="sxs-lookup"><span data-stu-id="65ac2-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-141">Registro de transacciones de datos de Rtcxds</span><span class="sxs-lookup"><span data-stu-id="65ac2-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="65ac2-142">Archivos de datos y registro para el deestacionamiento de llamada y el grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="65ac2-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65ac2-143">Base de datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="65ac2-143">Application database</span></span></th>
<th><span data-ttu-id="65ac2-144">Archivo de datos o propósito de registro</span><span class="sxs-lookup"><span data-stu-id="65ac2-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-145">Cpsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-146">Base de datos de información dinámica para la aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="65ac2-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-148">Registro de transacciones para el archivo de datos de aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="65ac2-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-149">Rgsconfig. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-150">Archivo de datos del servicio de grupo de respuesta de Lync Server para la configuración de los servicios</span><span class="sxs-lookup"><span data-stu-id="65ac2-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-152">Archivo de registro de transacciones para la configuración de la aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="65ac2-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-153">Rgsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-154">Archivo de datos de servicio de grupo de respuesta para operaciones en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="65ac2-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-156">Registro de transacciones para el archivo de datos de tiempo de ejecución del servicio de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="65ac2-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="65ac2-157">Archivos de datos y registro para el servidor de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="65ac2-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65ac2-158">Archivar y supervisar archivos de base de datos</span><span class="sxs-lookup"><span data-stu-id="65ac2-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="65ac2-159">Archivo de datos o propósito de registro</span><span class="sxs-lookup"><span data-stu-id="65ac2-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-160">LcsCdr. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-161">Almacén de datos para el proceso de grabación de detalles de llamadas (CDR) del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="65ac2-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-163">Registro de transacciones para datos de grabación de detalles de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="65ac2-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-164">QoEMetrics. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-165">Calidad de la experiencia archivo de datos almacenado desde el servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="65ac2-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-167">Registro de transacciones para supervisar datos</span><span class="sxs-lookup"><span data-stu-id="65ac2-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ac2-168">Lcslog. MDF</span><span class="sxs-lookup"><span data-stu-id="65ac2-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-169">Archivo de datos para la retención de mensajes instantáneos y de conferencia en un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="65ac2-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ac2-170">Lcslog. ldf</span><span class="sxs-lookup"><span data-stu-id="65ac2-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="65ac2-171">Registro de transacciones para archivar datos</span><span class="sxs-lookup"><span data-stu-id="65ac2-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="65ac2-172">En este tema, se hacen referencias al disco y al conjunto de RAID.</span><span class="sxs-lookup"><span data-stu-id="65ac2-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="65ac2-173">Tenga en cuenta que en la configuración de los recursos de SQL Server, hacer referencia a un disco significa un único dispositivo de hardware.</span><span class="sxs-lookup"><span data-stu-id="65ac2-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="65ac2-174">Una unidad de disco duro con dos particiones, una con archivos de registro y otra partición que contiene archivos de datos, no es la misma que dos discos, cada uno dedicado a archivos de datos o de registro.</span><span class="sxs-lookup"><span data-stu-id="65ac2-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="65ac2-175">En referencia a los conjuntos de RAID, hay varias tecnologías de RAID distintas de diferentes proveedores.</span><span class="sxs-lookup"><span data-stu-id="65ac2-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="65ac2-176">Además, con la proliferación de redes de área de almacenamiento (SAN), los conjuntos RAID dedicados a un solo sistema son más separables.</span><span class="sxs-lookup"><span data-stu-id="65ac2-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="65ac2-177">Debe consultar a su proveedor de RAID o SAN para determinar cuál es la mejor configuración para su diseño de disco al configurar el rendimiento de SQL Server con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65ac2-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="65ac2-178">Tenga en cuenta también que no todas las unidades de disco se crean por igual; Algunos tienen mejor rendimiento que otros.</span><span class="sxs-lookup"><span data-stu-id="65ac2-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="65ac2-179">Incluso las unidades del mismo fabricante pueden variar en rendimiento debido a la velocidad de giro, el tamaño de la caché de hardware y otros factores.</span><span class="sxs-lookup"><span data-stu-id="65ac2-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

