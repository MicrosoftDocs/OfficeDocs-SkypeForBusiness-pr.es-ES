---
title: 'Lync Server 2013: permisos de implementación para SQL Server'
description: 'Lync Server 2013: permisos de implementación para SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575726"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="ba9b8-103">Permisos de implementación para SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba9b8-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba9b8-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ba9b8-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ba9b8-105">Microsoft SQL Server 2012 tiene requisitos específicos al instalar e implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="ba9b8-106">Como Windows y SQL Server definen su seguridad de manera diferente, al iniciar sesión como administrador en el dominio de Active Directory no se conceden permisos implícitamente para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="ba9b8-107">También debe ser miembro de la entidad sysadmin del servidor basado en SQL Server que se está configurando:</span><span class="sxs-lookup"><span data-stu-id="ba9b8-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="ba9b8-108">Permisos necesarios para la instalación de Lync Server y base de datos</span><span class="sxs-lookup"><span data-stu-id="ba9b8-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="ba9b8-109">Las siguientes opciones detallan tres permisos y asociaciones de pertenencia a grupos para la instalación de archivos de Lync Server 2013 y bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="ba9b8-110">Seleccione el escenario que mejor cumpla los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="ba9b8-111">Permisos y asociaciones de pertenencia a grupo</span><span class="sxs-lookup"><span data-stu-id="ba9b8-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba9b8-112">Rol de SQL Server o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba9b8-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="ba9b8-113">Pertenencia a grupo y permisos de SQL Server típicos del rol</span><span class="sxs-lookup"><span data-stu-id="ba9b8-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="ba9b8-114">Función: permisos típicos de Lync Server 2013 y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="ba9b8-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="ba9b8-115">Resultado de permisos</span><span class="sxs-lookup"><span data-stu-id="ba9b8-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba9b8-116">Administrador de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba9b8-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-117">Debe haber obtenido la pertenencia al grupo de seguridad de SQL Server sysadmins y ser miembro del grupo de administradores local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba9b8-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-118">Debe ser miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-119">Lync Server 2013 el administrador tiene los permisos adecuados para instalar las bases de datos de Lync Server 2013 y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9b8-120">Administrador de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba9b8-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-121">Miembro del grupo sysadmin de SQL Server (o equivalente) y miembro del grupo de administradores local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba9b8-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-122">Debe ser miembro del grupo RTCUniversalServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="ba9b8-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-123">El administrador de SQL Server tiene los permisos adecuados para instalar las bases de datos de Lync Server 2013 y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9b8-124">Ambos administradores comparten tareas de instalación</span><span class="sxs-lookup"><span data-stu-id="ba9b8-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-125">Un administrador de SQL Server es miembro del grupo sysadmins (o equivalente) y miembro del grupo de administradores local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba9b8-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-126">El administrador de Lync Server 2013 es miembro de RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba9b8-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba9b8-127">El administrador de Lync Server 2013 puede instalar Lync Server 2013, pero no puede instalar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="ba9b8-128">El administrador de SQL Server usa el shell de administración de Lync Server y los cmdlets de Windows PowerShell proporcionados por el administrador de Lync Server 2013 para instalar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="ba9b8-129">El shell de administración de Lync Server 2013 que usa el administrador de SQL Server está instalado en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="ba9b8-130">Esto elimina la necesidad de instalar las herramientas administrativas de Lync Server 2013 en el servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

