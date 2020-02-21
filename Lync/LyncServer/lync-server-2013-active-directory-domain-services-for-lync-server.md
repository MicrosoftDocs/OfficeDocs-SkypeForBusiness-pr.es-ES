---
title: 'Lync Server 2013: servicios de dominio de Active Directory para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00038dce85a7461be37456d9dee263a71f60c113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="8c829-102">Servicios de dominio de Active Directory para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c829-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c829-103">_**Última modificación del tema:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="8c829-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="8c829-104">Servicios de dominio de Active Directory funciona como el servicio de directorio para Windows Server 2003, Windows Server 2008, Windows Server 2012 y redes de Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="8c829-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="8c829-105">Los servicios de dominio de Active Directory también sirven como base sobre la que se crea la infraestructura de seguridad de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c829-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="8c829-106">La finalidad de esta sección es describir cómo Lync Server 2013 usa los servicios de dominio de Active Directory para crear un entorno confiable para la mensajería instantánea, la conferencia Web, los medios y la voz.</span><span class="sxs-lookup"><span data-stu-id="8c829-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="8c829-107">Para obtener más información sobre las extensiones de Lync Server a los servicios de dominio de Active Directory y sobre cómo preparar el entorno para los servicios de dominio de Active Directory, consulte preparación de los [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="8c829-108">Para obtener más información sobre el rol de los servicios de dominio de Active Directory en las redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.</span><span class="sxs-lookup"><span data-stu-id="8c829-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="8c829-109">Lync Server 2013 usa los servicios de dominio de Active Directory para almacenar:</span><span class="sxs-lookup"><span data-stu-id="8c829-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="8c829-110">La configuración global que requieren todos los servidores que ejecutan Lync Server 2013 en un bosque.</span><span class="sxs-lookup"><span data-stu-id="8c829-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="8c829-111">Información de servicio que identifica los roles de todos los servidores que ejecutan Lync Server 2013 en un bosque.</span><span class="sxs-lookup"><span data-stu-id="8c829-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="8c829-112">Algunas opciones de configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="8c829-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="8c829-113">Infraestructura de Active Directory</span><span class="sxs-lookup"><span data-stu-id="8c829-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="8c829-114">Entre los requisitos de infraestructura para Active Directory se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c829-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="8c829-115">Requisitos del sistema operativo para los controladores de dominio</span><span class="sxs-lookup"><span data-stu-id="8c829-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="8c829-116">Requisitos del nivel funcional de dominio y bosque</span><span class="sxs-lookup"><span data-stu-id="8c829-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="8c829-117">Requisitos del dominio del catálogo global</span><span class="sxs-lookup"><span data-stu-id="8c829-117">Global catalog domain requirements</span></span>

<span data-ttu-id="8c829-118">Para obtener más información, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="8c829-119">Preparación de los servicios de dominio de Active Directory</span><span class="sxs-lookup"><span data-stu-id="8c829-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c829-120">Se recomienda implementar la configuración global en el contenedor de configuración en lugar del contenedor del sistema.</span><span class="sxs-lookup"><span data-stu-id="8c829-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="8c829-121">Esto no mejora la seguridad, pero puede dar como resultado mejoras de escalabilidad para algunas topologías de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c829-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="8c829-122">Si va a migrar desde Microsoft Office Communications Server 2007 y ha usado el contenedor del sistema pero tiene previsto usar el contenedor de configuración, debe mover la configuración del contenedor del sistema antes de realizar los preparativos de actualización.</span><span class="sxs-lookup"><span data-stu-id="8c829-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="8c829-123">Para migrar la configuración del contenedor del sistema al contenedor de configuración, vea Office Communications Server 2007 global Settings <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>Migration Tool en.</span><span class="sxs-lookup"><span data-stu-id="8c829-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="8c829-124">Al implementar Lync Server 2013, el primer paso consiste en preparar los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c829-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="8c829-125">La preparación de los servicios de dominio de Active Directory para Lync Server 2013 consta de los tres pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c829-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="8c829-126">**Preparar el esquema**.</span><span class="sxs-lookup"><span data-stu-id="8c829-126">**Prepare Schema**.</span></span> <span data-ttu-id="8c829-127">Esta tarea amplía el esquema de los servicios de dominio de Active Directory para incluir clases y atributos específicos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c829-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="8c829-128">Para obtener información detallada sobre la preparación del esquema, consulte Running Active Directory Schema Preparation [in Lync Server 2013](lync-server-2013-running-schema-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="8c829-129">Para obtener más información, vea [migración de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8c829-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="8c829-130">**Preparar el bosque**.</span><span class="sxs-lookup"><span data-stu-id="8c829-130">**Prepare Forest**.</span></span> <span data-ttu-id="8c829-131">Esta tarea crea la configuración global y los objetos en el dominio raíz del bosque, junto con los grupos de servicio universal y administrativo que rigen el acceso a estos objetos y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="8c829-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="8c829-132">Para obtener información detallada acerca de la preparación del bosque, consulte [Running Forest Preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="8c829-133">**Prepare el dominio**.</span><span class="sxs-lookup"><span data-stu-id="8c829-133">**Prepare Domain**.</span></span> <span data-ttu-id="8c829-134">Esta tarea agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios del dominio.</span><span class="sxs-lookup"><span data-stu-id="8c829-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="8c829-135">Esta tarea debe completarse en todos los dominios en los que desea implementar servidores que ejecutan Lync Server 2013 y cualquier dominio en el que residen los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c829-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="8c829-136">Para obtener información detallada sobre la preparación del dominio, consulte [Running Domain Preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8c829-137">Para obtener información general sobre el proceso completo para preparar Active Directory y los derechos y permisos necesarios para realizar cada paso, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="8c829-138">Grupos universales</span><span class="sxs-lookup"><span data-stu-id="8c829-138">Universal Groups</span></span>

<span data-ttu-id="8c829-139">Durante la preparación del bosque, Lync Server 2013 crea varios grupos universales dentro de los servicios de dominio de Active Directory que tienen permiso para obtener acceso a los servicios y la configuración global y administrarlos.</span><span class="sxs-lookup"><span data-stu-id="8c829-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="8c829-140">Estos grupos universales incluyen:</span><span class="sxs-lookup"><span data-stu-id="8c829-140">These universal groups include:</span></span>

  - <span data-ttu-id="8c829-141">**Grupos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="8c829-141">**Administrative groups**.</span></span> <span data-ttu-id="8c829-142">Estos grupos definen los roles de administrador fundamentales para una red de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c829-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="8c829-143">Durante la preparación del bosque, estos grupos de administradores se agregan a los grupos de infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c829-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="8c829-144">**Grupos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="8c829-144">**Service groups**.</span></span> <span data-ttu-id="8c829-145">Estos grupos son cuentas de servicio necesarias para tener acceso a varios servicios proporcionados por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c829-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="8c829-146">**Grupos de infraestructura**.</span><span class="sxs-lookup"><span data-stu-id="8c829-146">**Infrastructure groups**.</span></span> <span data-ttu-id="8c829-147">Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c829-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="8c829-148">Funcionan como componentes de los grupos administrativos y no se deben modificar ni agregar usuarios directamente a ellos.</span><span class="sxs-lookup"><span data-stu-id="8c829-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="8c829-149">Durante la preparación del bosque, los grupos de servicio y administración específicos se agregan a los grupos de infraestructura correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8c829-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="8c829-150">Para obtener información detallada sobre los grupos universales específicos que se crearon al preparar AD para Lync Server, así como los grupos de servicio y administración que se agregan a los grupos de infraestructura, vea [los cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c829-151">Lync Server 2013 admite los grupos universales de Windows Server 2012 para servidores que ejecutan Lync Server 2013, así como sistemas operativos Windows Server 2003 para controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="8c829-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="8c829-152">Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque.</span><span class="sxs-lookup"><span data-stu-id="8c829-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="8c829-153">La compatibilidad con grupos universales, combinada con la delegación de administrador, simplifica la administración de una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c829-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="8c829-154">Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.</span><span class="sxs-lookup"><span data-stu-id="8c829-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="8c829-155">Control de acceso basado en roles</span><span class="sxs-lookup"><span data-stu-id="8c829-155">Role-Based Access Control</span></span>

<span data-ttu-id="8c829-156">Además de crear grupos de servicio y administración universales y agregar grupos de servicio y administración a los grupos universales apropiados, la preparación del bosque también crea grupos de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="8c829-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="8c829-157">Para obtener más información sobre los grupos RBAC específicos creados por la preparación del bosque, consulte [Changes by Forest Preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="8c829-158">Para obtener más información acerca de los grupos RBAC, consulte [role-based access control (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="8c829-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="8c829-159">Entradas de control de acceso (ACE) y herencia</span><span class="sxs-lookup"><span data-stu-id="8c829-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="8c829-160">La preparación del bosque crea ACE privadas y públicas, y agrega entradas ACE para los grupos universales que crea.</span><span class="sxs-lookup"><span data-stu-id="8c829-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="8c829-161">Crea ACE privadas específicas en el contenedor de configuración global usado por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c829-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="8c829-162">Este contenedor solo se usa en Lync Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, en función de dónde almacene la configuración global.</span><span class="sxs-lookup"><span data-stu-id="8c829-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="8c829-163">El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio.</span><span class="sxs-lookup"><span data-stu-id="8c829-163">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="8c829-164">La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="8c829-164">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="8c829-165">Para más información sobre las ACE públicas creadas y agregadas por la preparación del bosque y la preparación del dominio, consulte [Changes by Forest Preparation in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) y [cambios realizados por la preparación del dominio en Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8c829-166">Las organizaciones a menudo bloquean los servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8c829-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="8c829-167">Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c829-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="8c829-168">Esto puede incluir la eliminación de ACE de contenedores y unidades organizativas, y la deshabilitación de la herencia de permisos en objetos user, Contact, InetOrgPerson o Computer.</span><span class="sxs-lookup"><span data-stu-id="8c829-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="8c829-169">En un entorno de Active Directory bloqueado, los permisos deben establecerse manualmente en los contenedores y en las unidades organizativas que los requieran.</span><span class="sxs-lookup"><span data-stu-id="8c829-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="8c829-170">Para obtener más información, consulte [preparación de servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="8c829-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="8c829-171">Información del servidor</span><span class="sxs-lookup"><span data-stu-id="8c829-171">Server Information</span></span>

<span data-ttu-id="8c829-172">Durante la activación, Lync Server 2013 publica la información del servidor en las tres ubicaciones siguientes de los servicios de dominio de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="8c829-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="8c829-173">Un punto de conexión de servicio (SCP) en cada objeto de equipo de Active Directory correspondiente a un equipo físico en el que Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="8c829-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="8c829-174">Objetos de servidor creados en el contenedor de la clase **msRTCSIP-pools** .</span><span class="sxs-lookup"><span data-stu-id="8c829-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="8c829-175">Servidores de confianza especificados en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="8c829-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="8c829-176">Puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="8c829-176">Service Connection Points</span></span>

<span data-ttu-id="8c829-177">Cada objeto de Lync Server 2013 en los servicios de dominio de Active Directory tiene un SCP denominado servicios de RTC, que a su vez contiene una serie de atributos que identifican cada equipo y especifican los servicios que proporciona.</span><span class="sxs-lookup"><span data-stu-id="8c829-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="8c829-178">Entre los atributos de SCP más importantes se encuentran *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*y *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="8c829-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="8c829-179">Las aplicaciones de administración de activos de terceros pueden recuperar información del servidor en una implementación consultando estos y otros atributos de SCP.</span><span class="sxs-lookup"><span data-stu-id="8c829-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="8c829-180">Objetos de servidor de Active Directory</span><span class="sxs-lookup"><span data-stu-id="8c829-180">Active Directory Server Objects</span></span>

<span data-ttu-id="8c829-181">Cada rol de servidor de Lync Server 2013 tiene un objeto de Active Directory correspondiente cuyos atributos definen los servicios proporcionados por el rol.</span><span class="sxs-lookup"><span data-stu-id="8c829-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="8c829-182">Además, cuando se activa un servidor Standard Edition o cuando se crea un grupo de servidores Enterprise Edition, Lync Server 2013 crea un nuevo objeto **msRTCSIP-Pool** en el contenedor **msRTCSIP-pools** .</span><span class="sxs-lookup"><span data-stu-id="8c829-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="8c829-183">La clase **msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo, junto con la asociación entre los componentes front-end y back-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="8c829-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="8c829-184">(Un servidor Standard Edition se considera un grupo lógico cuyos extremos delantero y back se combinan en un solo equipo).</span><span class="sxs-lookup"><span data-stu-id="8c829-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="8c829-185">Servidores de confianza</span><span class="sxs-lookup"><span data-stu-id="8c829-185">Trusted Servers</span></span>

<span data-ttu-id="8c829-186">En Lync Server 2013, los servidores de confianza son los que se especifican al ejecutar el generador de topologías y publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="8c829-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="8c829-187">La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="8c829-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="8c829-188">Solo se confía en los servidores definidos en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="8c829-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="8c829-189">En Lync Server 2013, un servidor de confianza es el único que cumple con los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="8c829-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="8c829-190">El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="8c829-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="8c829-191">El servidor presenta un certificado válido de una entidad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="8c829-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="8c829-192">Para obtener más información, consulte [requisitos de infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c829-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="8c829-193">Si falta alguno de estos criterios, el servidor no es de confianza y se rechaza la conexión con él.</span><span class="sxs-lookup"><span data-stu-id="8c829-193">If either of these criteria is missing, the server is not trusted and connection with it is refused.</span></span> <span data-ttu-id="8c829-194">Este doble requisito evita un posible ataque, si no es probable, en el que un servidor malintencionado intenta asumir el FQDN de un servidor válido.</span><span class="sxs-lookup"><span data-stu-id="8c829-194">This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="8c829-195">Además, para habilitar las implementaciones de Microsoft Office Communications Server 2007 R2 y Microsoft Office Communications Server 2007 para comunicarse con los servidores de Lync Server 2013, Lync Server 2013 crea contenedores durante la preparación del bosque para la retención de listas de servidores de confianza para versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="8c829-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="8c829-196">En la tabla siguiente se describen los contenedores creados para habilitar la compatibilidad con las implementaciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="8c829-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="8c829-197">Listas de servidores de confianza y sus contenedores de Active Directory para la compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="8c829-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c829-198">Lista de servidores de confianza</span><span class="sxs-lookup"><span data-stu-id="8c829-198">Trusted server list</span></span></th>
<th><span data-ttu-id="8c829-199">Contenedor de Active Directory</span><span class="sxs-lookup"><span data-stu-id="8c829-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c829-200">Servidores Standard Edition y servidores front-end del grupo de servidores Enterprise</span><span class="sxs-lookup"><span data-stu-id="8c829-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8c829-201">Servicio RTC/configuración global</span><span class="sxs-lookup"><span data-stu-id="8c829-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c829-202">Servidores de conferencia</span><span class="sxs-lookup"><span data-stu-id="8c829-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="8c829-203">Servicio RTC/MCU de confianza</span><span class="sxs-lookup"><span data-stu-id="8c829-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c829-204">Servidores de componentes Web</span><span class="sxs-lookup"><span data-stu-id="8c829-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="8c829-205">Servicio de RTC/confianza</span><span class="sxs-lookup"><span data-stu-id="8c829-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c829-206">Servidores de mediación y servidores de Communicator Web Access, servidor de aplicaciones, registrador con QoE, servicio de conferencia A/V (también servidores SIP de terceros)</span><span class="sxs-lookup"><span data-stu-id="8c829-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="8c829-207">Servicio RTC/servicios de confianza</span><span class="sxs-lookup"><span data-stu-id="8c829-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c829-208">Servidores proxy</span><span class="sxs-lookup"><span data-stu-id="8c829-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="8c829-209">Lync Server 2013 no admite compatibilidad con versiones anteriores para servidores proxy</span><span class="sxs-lookup"><span data-stu-id="8c829-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8c829-210">Para admitir servidores de confianza de versiones anteriores, debe ejecutar la herramienta Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="8c829-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="8c829-211">Para obtener más información sobre cómo ejecutar el analizador de [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633)procedimientos recomendados, consulte.</span><span class="sxs-lookup"><span data-stu-id="8c829-211">For details about running the best practices analyzer, see [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

