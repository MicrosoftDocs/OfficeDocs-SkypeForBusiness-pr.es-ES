---
title: 'Lync Server 2013: Permisos de implementación para SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="30495-102">Permisos de implementación para SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30495-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30495-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="30495-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="30495-104">Microsoft SQL Server 2012 tiene requisitos específicos al instalar e implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30495-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="30495-105">Puesto que Windows y SQL Server definen su seguridad de manera diferente, iniciar sesión como administrador en el dominio de Active Directory no concede permisos de forma implícita para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30495-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="30495-106">También debe ser miembro de la entidad sysadmin en el servidor basado en SQL Server que está configurando.</span><span class="sxs-lookup"><span data-stu-id="30495-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="30495-107">Permisos necesarios para la instalación de base de datos y Lync Server</span><span class="sxs-lookup"><span data-stu-id="30495-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="30495-108">Las siguientes opciones detallan tres permisos y asociaciones de pertenencia a grupos para la instalación de archivos de Lync Server 2013 y bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30495-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="30495-109">Elija el escenario que mejor se adapte a los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="30495-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="30495-110">Permisos y asociaciones de pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="30495-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30495-111">Rol de 2013 de SQL Server o Lync Server</span><span class="sxs-lookup"><span data-stu-id="30495-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="30495-112">Rol: permisos típicos de SQL Server y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="30495-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="30495-113">Rol: permisos típicos de Lync Server 2013 y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="30495-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="30495-114">Resultado de los permisos</span><span class="sxs-lookup"><span data-stu-id="30495-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30495-115">Administrador de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="30495-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="30495-116">Se debe conceder la pertenencia a sysadmins del grupo de seguridad de SQL Server y miembro del grupo de administradores local de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30495-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="30495-117">Debe ser miembro del grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="30495-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="30495-118">El administrador de Lync Server 2013 tiene los permisos adecuados para instalar las bases de datos de Lync Server 2013 y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30495-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30495-119">Administrador de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30495-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="30495-120">Miembro del grupo sysadmin de SQL Server (o equivalente) y miembro del grupo de administradores locales de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30495-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="30495-121">Debe ser miembro del grupo RTCUniversalServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="30495-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="30495-122">El administrador de SQL Server tiene los permisos adecuados para instalar las bases de datos de Lync Server 2013 y de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30495-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30495-123">Ambos administradores comparten deberes de instalación</span><span class="sxs-lookup"><span data-stu-id="30495-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="30495-124">El administrador de SQL Server es miembro del grupo sysadmins (o equivalente) y miembro del grupo de administradores locales de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30495-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="30495-125">El administrador de Lync Server 2013 es miembro de RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="30495-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="30495-126">El administrador de Lync Server 2013 puede instalar Lync Server 2013, pero no puede instalar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="30495-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="30495-127">El administrador de SQL Server usa el shell de administración de Lync Server y los cmdlets de Windows PowerShell proporcionados por el administrador de Lync Server 2013 para instalar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="30495-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="30495-128">El shell de administración de Lync Server 2013 que usa el administrador de SQL Server está instalado en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="30495-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="30495-129">Esto elimina la necesidad de instalar las herramientas administrativas de Lync Server 2013 en el servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30495-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

