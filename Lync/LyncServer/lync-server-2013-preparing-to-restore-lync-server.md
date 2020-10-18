---
title: 'Lync Server 2013: preparación para restaurar Lync Server'
description: 'Lync Server 2013: preparación para restaurar Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1875a691cfb70a6a824ab19bfde3dee4d699e48a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579956"
---
# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="f0511-103">Preparación de la restauración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0511-103">Preparing to restore Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0511-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f0511-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f0511-105">Antes de empezar a restaurar los servidores y las bases de datos tras un error, es necesario tener claro lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0511-105">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="f0511-106">Qué se debe restaurar.</span><span class="sxs-lookup"><span data-stu-id="f0511-106">What needs to be restored.</span></span>

  - <span data-ttu-id="f0511-107">El hardware, el software, los datos y las herramientas que necesita para la restauración.</span><span class="sxs-lookup"><span data-stu-id="f0511-107">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="f0511-108">Saber qué hay que restaurar</span><span class="sxs-lookup"><span data-stu-id="f0511-108">Determining What to Restore</span></span>

<span data-ttu-id="f0511-109">En este tema se describe cómo restaurar las interrupciones de Lync Server que se producen en el nivel del servidor, del grupo de servidores o del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="f0511-109">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="f0511-110">Si se produce un error en el almacén de administración central, la implementación de Lync Server sigue funcionando, pero no se pueden realizar cambios en la configuración.</span><span class="sxs-lookup"><span data-stu-id="f0511-110">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="f0511-111">Si se produce un error en un servidor back-end o un servidor Standard Edition, el grupo de usuarios deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="f0511-111">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="f0511-112">Si se produce un error en cualquier otro servidor, la magnitud del error depende del rol de servidor que ejecute el servidor y de si el servidor hospeda una o más bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f0511-112">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="f0511-113">Qué restaurar</span><span class="sxs-lookup"><span data-stu-id="f0511-113">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0511-114">Si se produce un error en...</span><span class="sxs-lookup"><span data-stu-id="f0511-114">If this failed</span></span></th>
<th><span data-ttu-id="f0511-115">Consulte esta sección:</span><span class="sxs-lookup"><span data-stu-id="f0511-115">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0511-116">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f0511-116">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="f0511-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurar un servidor Standard Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0511-118">Almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="f0511-118">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="f0511-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauración del servidor que hospeda el almacén de administración central en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0511-120">Back-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f0511-120">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="f0511-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauración de un servidor back-end de Enterprise Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0511-122">Servidor principal reflejado de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f0511-122">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="f0511-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Primary</a></span><span class="sxs-lookup"><span data-stu-id="f0511-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0511-124">Servidor secundario reflejado de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f0511-124">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="f0511-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Mirror</a></span><span class="sxs-lookup"><span data-stu-id="f0511-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0511-126">Cualquier servidor Enterprise Edition que ejecute una función de servidor, como un servidor front-end, un servidor perimetral, un director, un servidor de mediación o un servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f0511-126">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="f0511-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauración de un servidor miembro de Enterprise Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0511-128">Un grupo completo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f0511-128">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="f0511-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauración de un grupo de servidores de Lync Server en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0511-130">Almacén de archivos de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f0511-130">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="f0511-131"><a href="lync-server-2013-restoring-a-file-store.md">Restaurar un almacén de archivos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-131"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0511-132">Una base de datos de supervisión independiente o base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="f0511-132">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="f0511-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauración de datos de supervisión o archivado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0511-134">Una base de datos de chat persistente independiente</span><span class="sxs-lookup"><span data-stu-id="f0511-134">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="f0511-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauración de datos de chat persistente en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0511-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="f0511-136">Recopilar el hardware, el software y las herramientas</span><span class="sxs-lookup"><span data-stu-id="f0511-136">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="f0511-137">Al restaurar un servidor, se debe empezar con un equipo nuevo o limpio.</span><span class="sxs-lookup"><span data-stu-id="f0511-137">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="f0511-138">Además, debe tener el siguiente hardware y software disponibles:</span><span class="sxs-lookup"><span data-stu-id="f0511-138">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="f0511-139">Un servidor nuevo o limpio con el mismo nombre de dominio completo (FQDN) que el servidor con el error.</span><span class="sxs-lookup"><span data-stu-id="f0511-139">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f0511-140">Cuando instale el sistema operativo, asegúrese de no eliminar la cuenta de equipo en servicios de dominio de Active Directory y compruebe que se conservan los permisos de grupo de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="f0511-140">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="f0511-141">Un software de instalación del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f0511-141">Installation software for the operating system.</span></span> <span data-ttu-id="f0511-142">Para instalar el sistema operativo, use las configuraciones y procedimientos de implementación de servidores que se hayan instaurado en la organización.</span><span class="sxs-lookup"><span data-stu-id="f0511-142">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="f0511-143">Debe tener estos procedimientos y requisitos de configuración disponibles al restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f0511-143">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="f0511-144">Software de instalación de SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f0511-144">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="f0511-145">Para instalar un servidor de bases de datos, use la versión de servidor SQL Server que corresponda, además de las configuraciones y procedimientos de implementación de servidores de bases de datos que se hayan instaurado en la organización.</span><span class="sxs-lookup"><span data-stu-id="f0511-145">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="f0511-146">Debe tener estos procedimientos y requisitos de configuración disponibles al restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f0511-146">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0511-147">El Asistente para la implementación de Lync Server instala automáticamente SQL Server 2012 Express en cada servidor Standard Edition y en cualquier otro servidor de Lync Server cuando se instala un almacén de configuración local, a menos que haya preinstalado SQL Server 2012 o SQL Server 2008 R2 en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f0511-147">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="f0511-148">Software para tomar imágenes del sistema.</span><span class="sxs-lookup"><span data-stu-id="f0511-148">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f0511-149">Le recomendamos que tome una copia de imagen del sistema después de instalar el sistema operativo y SQL Server, y antes de iniciar la restauración, para que pueda usar esta imagen como un punto de reversión en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="f0511-149">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="f0511-150">Software de instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0511-150">Lync Server 2013 installation software.</span></span> <span data-ttu-id="f0511-151">El Asistente para la implementación de Lync Server se encuentra en la carpeta o medio de instalación de Lync Server en la \\ instalación de \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="f0511-151">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="f0511-152">Durante la restauración se usan las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="f0511-152">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="f0511-153">Cmdlets del shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f0511-153">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="f0511-154">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="f0511-154">Import-CsUserData</span></span>

  - <span data-ttu-id="f0511-155">Herramientas para restaurar carpetas de Windows</span><span class="sxs-lookup"><span data-stu-id="f0511-155">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="f0511-156">Topology Builder</span><span class="sxs-lookup"><span data-stu-id="f0511-156">Topology Builder</span></span>

  - <span data-ttu-id="f0511-157">Utilidades de bases de datos de SQL Server, como SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0511-157">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="f0511-158">Preparación para restaurar un servidor</span><span class="sxs-lookup"><span data-stu-id="f0511-158">Preparing to Restore a Server</span></span>

<span data-ttu-id="f0511-159">Antes de restaurar el servidor, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="f0511-159">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="f0511-160">Instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f0511-160">Install the operating system.</span></span>

2.  <span data-ttu-id="f0511-161">Si el servidor es un servidor back-end, instale SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f0511-161">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="f0511-162">Restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="f0511-162">Restore or reenroll your certificates.</span></span> <span data-ttu-id="f0511-163">Para obtener más información sobre los certificados, consulte "requisitos de copia de seguridad adicionales" en [requisitos de copia de seguridad y restauración en Lync Server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="f0511-163">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="f0511-164">Tome una imagen del sistema antes de iniciar la restauración para usarla como punto de retroceso, en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="f0511-164">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0511-165">El Asistente para la implementación de Lync Server y los cmdlets descritos en los procedimientos de este tema y temas relacionados establecen todas las listas de control de acceso (ACL) necesarias.</span><span class="sxs-lookup"><span data-stu-id="f0511-165">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="f0511-166">Compruebe que el hardware y el software que necesita para los componentes que va a restaurar están disponibles antes de iniciar la restauración.</span><span class="sxs-lookup"><span data-stu-id="f0511-166">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="f0511-167">Tras instalar el sistema operativo y el servidor SQL Server, la mayor parte de los pasos de los siguientes procedimientos de restauración se puede llevar a cabo de forma remota.</span><span class="sxs-lookup"><span data-stu-id="f0511-167">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="f0511-168">Las excepciones se indicarán durante el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0511-168">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="f0511-169">También debe tener el plan de copia de seguridad y restauración de su organización y la información de la última copia de seguridad, como la información de las hojas de cálculo de este documento (para obtener más información, vea [copia de seguridad y restauración de hojas de cálculo para Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="f0511-169">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

