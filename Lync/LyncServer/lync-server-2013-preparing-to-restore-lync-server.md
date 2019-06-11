---
title: 'Lync Server 2013: preparación de la restauración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="08ea3-102">Prepararse para restaurar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08ea3-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08ea3-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="08ea3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="08ea3-104">Antes de empezar a restaurar servidores y bases de datos después de un error, debe determinar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08ea3-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="08ea3-105">Qué se debe restaurar.</span><span class="sxs-lookup"><span data-stu-id="08ea3-105">What needs to be restored.</span></span>

  - <span data-ttu-id="08ea3-106">El hardware, el software, los datos y las herramientas que necesita para la restauración.</span><span class="sxs-lookup"><span data-stu-id="08ea3-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="08ea3-107">Determinar qué restaurar</span><span class="sxs-lookup"><span data-stu-id="08ea3-107">Determining What to Restore</span></span>

<span data-ttu-id="08ea3-108">En este tema se describe cómo restaurar las interrupciones de Lync Server que se producen en el servidor, grupo o nivel de almacenamiento de administración central.</span><span class="sxs-lookup"><span data-stu-id="08ea3-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="08ea3-109">Si se produce un error en el almacén de administración central, la implementación de Lync Server continúa funcionando, pero no puede realizar cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="08ea3-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="08ea3-110">Si se produce un error en un servidor de back-end o un servidor Standard Edition, el grupo de usuarios deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="08ea3-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="08ea3-111">Si se produce un error en cualquier otro servidor, la magnitud del error depende del rol de servidor que se esté ejecutando en el servidor y de si el servidor hospeda una o más bases de datos.</span><span class="sxs-lookup"><span data-stu-id="08ea3-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="08ea3-112">Qué restaurar</span><span class="sxs-lookup"><span data-stu-id="08ea3-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08ea3-113">Si esto no se realizó correctamente</span><span class="sxs-lookup"><span data-stu-id="08ea3-113">If this failed</span></span></th>
<th><span data-ttu-id="08ea3-114">Consulte esta sección:</span><span class="sxs-lookup"><span data-stu-id="08ea3-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ea3-115">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="08ea3-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="08ea3-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurar un servidor Standard Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea3-117">Almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="08ea3-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="08ea3-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restaurar el servidor que hospeda el almacén de administración central en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ea3-119">Back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="08ea3-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="08ea3-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauración de un servidor de servicios de fondo de la edición empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea3-121">Enterprise Edition back end principal servidor principal</span><span class="sxs-lookup"><span data-stu-id="08ea3-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="08ea3-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-principal</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ea3-123">Servidor secundario reflejado de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="08ea3-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="08ea3-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-Mirror</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea3-125">Cualquier servidor Enterprise Edition que ejecute un rol de servidor, como un servidor front end, un servidor EDGE, un director, un servidor de mediación o un servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="08ea3-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="08ea3-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restaurar un servidor miembro de Enterprise Edition en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ea3-127">Todo un grupo de servidores de Lync</span><span class="sxs-lookup"><span data-stu-id="08ea3-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="08ea3-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauración de un grupo de servidores de Lync en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea3-129">Enterprise Edition, almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="08ea3-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="08ea3-130"><a href="lync-server-2013-restoring-a-file-store.md">Restaurar un almacén de archivos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ea3-131">Una base de datos de seguimiento independiente o una base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="08ea3-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="08ea3-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restaurar o archivar datos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea3-133">Una base de datos de chat persistente independiente</span><span class="sxs-lookup"><span data-stu-id="08ea3-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="08ea3-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauración de datos de chat persistente en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="08ea3-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="08ea3-135">Recopilar hardware, software y herramientas</span><span class="sxs-lookup"><span data-stu-id="08ea3-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="08ea3-136">Cuando restaura un servidor, debe empezar con un equipo nuevo o limpio.</span><span class="sxs-lookup"><span data-stu-id="08ea3-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="08ea3-137">Además, debe tener el siguiente hardware y software disponibles:</span><span class="sxs-lookup"><span data-stu-id="08ea3-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="08ea3-138">Un servidor limpio o nuevo con el mismo nombre de dominio completo (FQDN) que el servidor con error.</span><span class="sxs-lookup"><span data-stu-id="08ea3-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08ea3-139">Cuando instale el sistema operativo, asegúrese de no eliminar la cuenta de equipo en servicios de dominio de Active Directory y compruebe que se conservan los permisos de grupo para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="08ea3-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="08ea3-140">Software de instalación para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="08ea3-140">Installation software for the operating system.</span></span> <span data-ttu-id="08ea3-141">Para instalar el sistema operativo, use los procedimientos y las configuraciones de implementación del servidor que haya establecido su organización.</span><span class="sxs-lookup"><span data-stu-id="08ea3-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="08ea3-142">Debe tener estos procedimientos y los requisitos de configuración disponibles al restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="08ea3-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="08ea3-143">Software de instalación para SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="08ea3-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="08ea3-144">Para instalar un servidor de base de datos, use la versión adecuada de SQL Server y los procedimientos y configuraciones de implementación del servidor de base de datos que haya establecido su organización.</span><span class="sxs-lookup"><span data-stu-id="08ea3-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="08ea3-145">Debe tener estos procedimientos y los requisitos de configuración disponibles al restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="08ea3-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08ea3-146">El Asistente para la implementación de Lync Server instala automáticamente SQL Server 2012 Express en cada servidor Standard Edition y en cualquier otro servidor de Lync Server cuando se instala un almacén de configuración local, a menos que tenga SQL Server 2012 preinstalado o SQL Server 2008 R2 en el servidor.</span><span class="sxs-lookup"><span data-stu-id="08ea3-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="08ea3-147">Software para tomar imágenes del sistema.</span><span class="sxs-lookup"><span data-stu-id="08ea3-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="08ea3-148">Le recomendamos que tome una copia de imagen del sistema después de instalar el sistema operativo y SQL Server, y antes de iniciar la restauración para que pueda usar esta imagen como un punto de reversión en caso de que algo falle durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="08ea3-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="08ea3-149">Software de instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08ea3-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="08ea3-150">El Asistente para la implementación de Lync Server se encuentra en la carpeta o los medios \\de\\instalación\\de Lync Server en la instalación AMD64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="08ea3-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="08ea3-151">Durante la restauración, se usan las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="08ea3-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="08ea3-152">Cmdlets del shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="08ea3-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="08ea3-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="08ea3-153">Import-CsUserData</span></span>

  - <span data-ttu-id="08ea3-154">Herramientas para restaurar carpetas de Windows</span><span class="sxs-lookup"><span data-stu-id="08ea3-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="08ea3-155">Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="08ea3-155">Topology Builder</span></span>

  - <span data-ttu-id="08ea3-156">Utilidades de la base de datos de SQL Server, como SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08ea3-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="08ea3-157">Prepararse para restaurar un servidor</span><span class="sxs-lookup"><span data-stu-id="08ea3-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="08ea3-158">Antes de restaurar el servidor, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="08ea3-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="08ea3-159">Instale el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="08ea3-159">Install the operating system.</span></span>

2.  <span data-ttu-id="08ea3-160">Si el servidor es un servidor de servicios de fondo, instale SQL Server 2012 o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="08ea3-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="08ea3-161">Restaure o reinscriba los certificados.</span><span class="sxs-lookup"><span data-stu-id="08ea3-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="08ea3-162">Para obtener más información sobre los certificados, consulte "requisitos de copia de seguridad adicionales" en requisitos de copia de seguridad [y restauración en Lync Server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="08ea3-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="08ea3-163">Tome una imagen del sistema antes de iniciar la restauración para usarla como punto de desinstalación, en caso de que algo falle durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="08ea3-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08ea3-164">El Asistente para la implementación de Lync Server y los cmdlets que se describen en los procedimientos de este tema y temas relacionados, establezca todas las listas de control de acceso (ACL) necesarias.</span><span class="sxs-lookup"><span data-stu-id="08ea3-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="08ea3-165">Antes de comenzar la restauración, compruebe que el hardware y el software que necesita para los componentes que planea restaurar estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="08ea3-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="08ea3-166">Después de instalar el sistema operativo y SQL Server, la mayoría de los pasos de los procedimientos de restauración siguientes se pueden ejecutar de forma remota.</span><span class="sxs-lookup"><span data-stu-id="08ea3-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="08ea3-167">Las excepciones se indican en los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="08ea3-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="08ea3-168">También debe tener el plan de copia de seguridad y restauración de su organización y la información de la última copia de seguridad, como la información de las hojas de cálculo de este documento (para obtener información detallada, vea [copias de seguridad y restauración de hojas de cálculo para Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="08ea3-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

