---
title: 'Lync Server 2013: requisitos de pertenencia a grupos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c1a79d39a70c21e353799a43c76599cc7af2b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="c444b-102">Requisitos de pertenencia a grupo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c444b-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c444b-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c444b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c444b-104">La siguiente tabla resume el grupo o los grupos a los que debe pertenecer una persona para instalar, administrar y solucionar correctamente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c444b-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c444b-105">Lync Server 2013 ejecutable</span><span class="sxs-lookup"><span data-stu-id="c444b-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="c444b-106">Pertenencia a grupos necesaria</span><span class="sxs-lookup"><span data-stu-id="c444b-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c444b-107"><strong>Setup. exe</strong> : ejecutable que inicia la instalación de las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c444b-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="c444b-108">Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c444b-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="c444b-109">Miembro del grupo usuarios del dominio para leer la información de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c444b-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="c444b-110">Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine.</span><span class="sxs-lookup"><span data-stu-id="c444b-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="c444b-111">También puede delegar permisos de configuración a usuarios o grupos a los que no desee conceder pertenencia en el grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="c444b-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="c444b-112">Para obtener más información, consulte <A href="lync-server-2013-granting-setup-permissions.md">concediendo Setup Permissions in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c444b-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c444b-113"><strong>Deploy.exe</strong>: llamado por setup.exe, deploy.exe realiza la implementación de los componentes del software para los roles del servidor.</span><span class="sxs-lookup"><span data-stu-id="c444b-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="c444b-114">Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c444b-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="c444b-115">Miembro del grupo Usuarios de dominio para leer la información en los AD DS.</span><span class="sxs-lookup"><span data-stu-id="c444b-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="c444b-116">Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine.</span><span class="sxs-lookup"><span data-stu-id="c444b-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="c444b-117">Es necesario pertenecer al grupo RtcUniversalReadOnlyAdmins para leer el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="c444b-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c444b-118">Si ejecuta el sistema operativo Windows Vista o Windows 7, el control de cuentas de usuario (UAC) le pedirá que continúe con la instalación.</span><span class="sxs-lookup"><span data-stu-id="c444b-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="c444b-119">Si ha iniciado sesión con una cuenta de usuario estándar, necesitará que alguien que sea miembro del grupo Administradores locales le proporcione las credenciales cuando se le solicite una cuenta con permisos para instalar el software.</span><span class="sxs-lookup"><span data-stu-id="c444b-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c444b-120"><strong>Bootstrapper.exe</strong>: llamado por setup.exe, bootstrapper.exe realiza la implementación y la configuración de los roles del servidor.</span><span class="sxs-lookup"><span data-stu-id="c444b-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="c444b-p105">Miembro del grupo Administradores locales en el equipo desde el que se ejecuta el ejecutable. Miembro del grupo RTCUniversalServerAdmins con permiso para ejecutar el archivo Bootstrapper.exe. Miembro del grupo Usuarios de dominio para leer la información en los AD DS. Este nivel de permiso es necesario porque la instalación automática de los paquetes MSI necesarios en el equipo local requiere privilegios que permitan la lectura de los recursos de equipos locales protegidos y la escritura en estos, como directorios Archivos de programa, y un registro protegido como el subárbol Local Machine.</span><span class="sxs-lookup"><span data-stu-id="c444b-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c444b-125"><strong>TopologyBuilder</strong> : interfaz de usuario guiada por asistente para crear, ver, ajustar y validar topologías de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c444b-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="c444b-126">Miembro del grupo de administradores locales en el equipo desde el que se ejecuta el archivo ejecutable para ver la topología.</span><span class="sxs-lookup"><span data-stu-id="c444b-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="c444b-127">Miembro del grupo RTCUniversalServerAdmins para cambiar los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="c444b-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="c444b-128">Miembro del grupo RTCUniversalServerAdmins y el grupo administradores de dominio, o miembro del grupo RTCUniversalServerAdmins (solo si se han concedido al grupo permisos para delegar la instalación), para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="c444b-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="c444b-129">Para obtener más información sobre cómo delegar permisos de instalación para permitir que los miembros del grupo RTCUniversalServerAdmins publiquen la topología sin ser miembros del grupo administradores de dominio, consulte <a href="lync-server-2013-granting-setup-permissions.md">concediendo Setup Permissions in Lync Server 2013</a> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c444b-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c444b-130"><strong>AdminUIHost</strong> – interfaz gráfica de usuario basada en web para la administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c444b-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="c444b-131">Miembro del grupo CsAdministrator o miembro de otra función de control de acceso basado en roles (RBAC) donde se asigna la tarea administrativa específica.</span><span class="sxs-lookup"><span data-stu-id="c444b-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="c444b-132">Lync Server 2013 el panel de control implementa los cambios de configuración mediante la ejecución de los cmdlets del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c444b-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="c444b-133">Para obtener una lista de las funciones predefinidas y permitir que se ejecuten los miembros de cmdlets, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="c444b-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c444b-134"><strong>PowerShell. exe con el módulo Lync Server 2013 cargado</strong> : herramienta administrativa de línea de comandos con cmdlets específicos para la administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c444b-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="c444b-135">Miembro del grupo CsAdministrator o miembro de otra función de RBAC donde se asignó el cmdlet específico.</span><span class="sxs-lookup"><span data-stu-id="c444b-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="c444b-136">Para obtener una lista de las funciones predefinidas y permitir que se ejecuten los miembros de cmdlets, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="c444b-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="c444b-137">O bien, miembro de uno o más de los siguientes grupos, según el cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c444b-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="c444b-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c444b-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="c444b-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c444b-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="c444b-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="c444b-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

