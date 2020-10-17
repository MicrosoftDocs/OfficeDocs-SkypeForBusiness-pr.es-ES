---
title: 'Lync Server 2013: preparación para restaurar Lync Server'
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
ms.openlocfilehash: 2f31354ee87cdf7df5efdb6c4e2accf3758829c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506837"
---
# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="e8374-102">Preparación de la restauración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8374-102">Preparing to restore Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8374-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e8374-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e8374-104">Antes de empezar a restaurar los servidores y las bases de datos tras un error, es necesario tener claro lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8374-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="e8374-105">Qué se debe restaurar.</span><span class="sxs-lookup"><span data-stu-id="e8374-105">What needs to be restored.</span></span>

  - <span data-ttu-id="e8374-106">El hardware, el software, los datos y las herramientas que necesita para la restauración.</span><span class="sxs-lookup"><span data-stu-id="e8374-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="e8374-107">Saber qué hay que restaurar</span><span class="sxs-lookup"><span data-stu-id="e8374-107">Determining What to Restore</span></span>

<span data-ttu-id="e8374-108">En este tema se describe cómo restaurar las interrupciones de Lync Server que se producen en el nivel del servidor, del grupo de servidores o del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="e8374-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="e8374-109">Si se produce un error en el almacén de administración central, la implementación de Lync Server sigue funcionando, pero no se pueden realizar cambios en la configuración.</span><span class="sxs-lookup"><span data-stu-id="e8374-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="e8374-110">Si se produce un error en un servidor back-end o un servidor Standard Edition, el grupo de usuarios deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="e8374-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="e8374-111">Si se produce un error en cualquier otro servidor, la magnitud del error depende del rol de servidor que ejecute el servidor y de si el servidor hospeda una o más bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e8374-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="e8374-112">Qué restaurar</span><span class="sxs-lookup"><span data-stu-id="e8374-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8374-113">Si se produce un error en...</span><span class="sxs-lookup"><span data-stu-id="e8374-113">If this failed</span></span></th>
<th><span data-ttu-id="e8374-114">Consulte esta sección:</span><span class="sxs-lookup"><span data-stu-id="e8374-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8374-115">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e8374-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="e8374-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurar un servidor Standard Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8374-117">Almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="e8374-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="e8374-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauración del servidor que hospeda el almacén de administración central en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8374-119">Back-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e8374-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="e8374-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauración de un servidor back-end de Enterprise Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8374-121">Servidor principal reflejado de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e8374-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="e8374-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Primary</a></span><span class="sxs-lookup"><span data-stu-id="e8374-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8374-123">Servidor secundario reflejado de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e8374-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="e8374-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Mirror</a></span><span class="sxs-lookup"><span data-stu-id="e8374-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8374-125">Cualquier servidor Enterprise Edition que ejecute una función de servidor, como un servidor front-end, un servidor perimetral, un director, un servidor de mediación o un servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e8374-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="e8374-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauración de un servidor miembro de Enterprise Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8374-127">Un grupo completo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8374-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="e8374-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauración de un grupo de servidores de Lync Server en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8374-129">Almacén de archivos de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e8374-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="e8374-130"><a href="lync-server-2013-restoring-a-file-store.md">Restaurar un almacén de archivos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8374-131">Una base de datos de supervisión independiente o base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="e8374-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="e8374-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauración de datos de supervisión o archivado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8374-133">Una base de datos de chat persistente independiente</span><span class="sxs-lookup"><span data-stu-id="e8374-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="e8374-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauración de datos de chat persistente en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8374-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="e8374-135">Recopilar el hardware, el software y las herramientas</span><span class="sxs-lookup"><span data-stu-id="e8374-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="e8374-136">Al restaurar un servidor, se debe empezar con un equipo nuevo o limpio.</span><span class="sxs-lookup"><span data-stu-id="e8374-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="e8374-137">Además, debe tener el siguiente hardware y software disponibles:</span><span class="sxs-lookup"><span data-stu-id="e8374-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="e8374-138">Un servidor nuevo o limpio con el mismo nombre de dominio completo (FQDN) que el servidor con el error.</span><span class="sxs-lookup"><span data-stu-id="e8374-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e8374-139">Cuando instale el sistema operativo, asegúrese de no eliminar la cuenta de equipo en servicios de dominio de Active Directory y compruebe que se conservan los permisos de grupo de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e8374-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="e8374-140">Un software de instalación del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e8374-140">Installation software for the operating system.</span></span> <span data-ttu-id="e8374-141">Para instalar el sistema operativo, use las configuraciones y procedimientos de implementación de servidores que se hayan instaurado en la organización.</span><span class="sxs-lookup"><span data-stu-id="e8374-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="e8374-142">Debe tener estos procedimientos y requisitos de configuración disponibles al restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e8374-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="e8374-143">Software de instalación de SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e8374-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="e8374-144">Para instalar un servidor de bases de datos, use la versión de servidor SQL Server que corresponda, además de las configuraciones y procedimientos de implementación de servidores de bases de datos que se hayan instaurado en la organización.</span><span class="sxs-lookup"><span data-stu-id="e8374-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="e8374-145">Debe tener estos procedimientos y requisitos de configuración disponibles al restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e8374-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8374-146">El Asistente para la implementación de Lync Server instala automáticamente SQL Server 2012 Express en cada servidor Standard Edition y en cualquier otro servidor de Lync Server cuando se instala un almacén de configuración local, a menos que haya preinstalado SQL Server 2012 o SQL Server 2008 R2 en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e8374-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="e8374-147">Software para tomar imágenes del sistema.</span><span class="sxs-lookup"><span data-stu-id="e8374-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e8374-148">Le recomendamos que tome una copia de imagen del sistema después de instalar el sistema operativo y SQL Server, y antes de iniciar la restauración, para que pueda usar esta imagen como un punto de reversión en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="e8374-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="e8374-149">Software de instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8374-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="e8374-150">El Asistente para la implementación de Lync Server se encuentra en la carpeta o medio de instalación de Lync Server en la \\ instalación de \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="e8374-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="e8374-151">Durante la restauración se usan las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="e8374-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="e8374-152">Cmdlets del shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8374-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="e8374-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="e8374-153">Import-CsUserData</span></span>

  - <span data-ttu-id="e8374-154">Herramientas para restaurar carpetas de Windows</span><span class="sxs-lookup"><span data-stu-id="e8374-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="e8374-155">Topology Builder</span><span class="sxs-lookup"><span data-stu-id="e8374-155">Topology Builder</span></span>

  - <span data-ttu-id="e8374-156">Utilidades de bases de datos de SQL Server, como SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e8374-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="e8374-157">Preparación para restaurar un servidor</span><span class="sxs-lookup"><span data-stu-id="e8374-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="e8374-158">Antes de restaurar el servidor, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e8374-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="e8374-159">Instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e8374-159">Install the operating system.</span></span>

2.  <span data-ttu-id="e8374-160">Si el servidor es un servidor back-end, instale SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e8374-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="e8374-161">Restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="e8374-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="e8374-162">Para obtener más información sobre los certificados, consulte "requisitos de copia de seguridad adicionales" en [requisitos de copia de seguridad y restauración en Lync Server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="e8374-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="e8374-163">Tome una imagen del sistema antes de iniciar la restauración para usarla como punto de retroceso, en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="e8374-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8374-164">El Asistente para la implementación de Lync Server y los cmdlets descritos en los procedimientos de este tema y temas relacionados establecen todas las listas de control de acceso (ACL) necesarias.</span><span class="sxs-lookup"><span data-stu-id="e8374-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="e8374-165">Compruebe que el hardware y el software que necesita para los componentes que va a restaurar están disponibles antes de iniciar la restauración.</span><span class="sxs-lookup"><span data-stu-id="e8374-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="e8374-166">Tras instalar el sistema operativo y el servidor SQL Server, la mayor parte de los pasos de los siguientes procedimientos de restauración se puede llevar a cabo de forma remota.</span><span class="sxs-lookup"><span data-stu-id="e8374-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="e8374-167">Las excepciones se indicarán durante el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e8374-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="e8374-168">También debe tener el plan de copia de seguridad y restauración de su organización y la información de la última copia de seguridad, como la información de las hojas de cálculo de este documento (para obtener más información, vea [copia de seguridad y restauración de hojas de cálculo para Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="e8374-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

