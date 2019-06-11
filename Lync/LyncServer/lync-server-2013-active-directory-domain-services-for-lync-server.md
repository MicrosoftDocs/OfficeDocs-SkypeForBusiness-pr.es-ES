---
title: 'Lync Server 2013: servicios de dominio de Active Directory para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="440d1-102">Servicios de dominio de Active Directory para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="440d1-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="440d1-103">_**Última modificación del tema:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="440d1-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="440d1-104">Los servicios de dominio de Active Directory funcionan como el servicio de directorio para Windows Server 2003, Windows Server 2008, Windows Server 2012 y redes Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="440d1-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="440d1-105">Los servicios de dominio de Active Directory también sirven como la base en la que se creó la infraestructura de seguridad 2013 de Microsoft Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="440d1-106">El propósito de esta sección es describir cómo Lync Server 2013 usa los servicios de dominio de Active Directory para crear un entorno digno de confianza para mensajería instantánea, conferencias web, multimedia y voz.</span><span class="sxs-lookup"><span data-stu-id="440d1-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="440d1-107">Para obtener más información sobre las extensiones de Lync Server a los servicios de dominio de Active Directory y sobre cómo preparar el entorno para los servicios de dominio de Active Directory, vea [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la implementación. documentación.</span><span class="sxs-lookup"><span data-stu-id="440d1-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="440d1-108">Para obtener más información sobre el rol de los servicios de dominio de Active Directory en las redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.</span><span class="sxs-lookup"><span data-stu-id="440d1-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="440d1-109">Lync Server 2013 usa los servicios de dominio de Active Directory para almacenar:</span><span class="sxs-lookup"><span data-stu-id="440d1-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="440d1-110">Configuración global que necesitan todos los servidores que ejecutan Lync Server 2013 en un bosque.</span><span class="sxs-lookup"><span data-stu-id="440d1-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="440d1-111">Información de servicio que identifica los roles de todos los servidores que ejecutan Lync Server 2013 en un bosque.</span><span class="sxs-lookup"><span data-stu-id="440d1-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="440d1-112">Algunas configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="440d1-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="440d1-113">Infraestructura de Active Directory</span><span class="sxs-lookup"><span data-stu-id="440d1-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="440d1-114">Entre los requisitos de infraestructura para Active Directory se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="440d1-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="440d1-115">Requisitos del sistema operativo para los controladores de dominio</span><span class="sxs-lookup"><span data-stu-id="440d1-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="440d1-116">Requisitos del nivel funcional de dominio y bosque</span><span class="sxs-lookup"><span data-stu-id="440d1-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="440d1-117">Requisitos del dominio del catálogo global</span><span class="sxs-lookup"><span data-stu-id="440d1-117">Global catalog domain requirements</span></span>

<span data-ttu-id="440d1-118">Para obtener más información, vea requisitos de la [infraestructura de Active Directory para Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="440d1-119">Preparación de los servicios de dominio de Active Directory</span><span class="sxs-lookup"><span data-stu-id="440d1-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="440d1-120">Se recomienda implementar la configuración global en el contenedor de configuración en lugar del contenedor del sistema.</span><span class="sxs-lookup"><span data-stu-id="440d1-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="440d1-121">Esto no mejora la seguridad, pero puede dar lugar a mejoras de escalabilidad para algunas topologías de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="440d1-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="440d1-122">Si va a migrar desde Microsoft Office Communications Server 2007 y ha usado el contenedor del sistema pero tiene previsto usar el contenedor de configuración, debe mover la configuración en el contenedor del sistema antes de realizar la preparación de la actualización.</span><span class="sxs-lookup"><span data-stu-id="440d1-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="440d1-123">Para migrar la configuración del contenedor del sistema al contenedor configuración, consulte la herramienta de migración configuración global de Office <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>Communications Server 2007 en.</span><span class="sxs-lookup"><span data-stu-id="440d1-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="440d1-124">Al implementar Lync Server 2013, el primer paso es preparar los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="440d1-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="440d1-125">La preparación de los servicios de dominio de Active Directory para Lync Server 2013 consta de los tres pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="440d1-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="440d1-126">**Preparar esquema**.</span><span class="sxs-lookup"><span data-stu-id="440d1-126">**Prepare Schema**.</span></span> <span data-ttu-id="440d1-127">Esta tarea extiende el esquema de los servicios de dominio de Active Directory para incluir clases y atributos específicos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="440d1-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="440d1-128">Para obtener detalles sobre la preparación del esquema, consulte ejecución de la [preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="440d1-129">Para obtener más información, vea [migración de Office Communications server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="440d1-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="440d1-130">**Preparar el bosque**.</span><span class="sxs-lookup"><span data-stu-id="440d1-130">**Prepare Forest**.</span></span> <span data-ttu-id="440d1-131">Esta tarea crea la configuración global y los objetos en el dominio raíz del bosque, junto con el servicio universal y los grupos administrativos que rigen el acceso a estos valores y objetos.</span><span class="sxs-lookup"><span data-stu-id="440d1-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="440d1-132">Para obtener detalles sobre la preparación del bosque, consulte ejecución de la [preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="440d1-133">**Preparar el dominio**.</span><span class="sxs-lookup"><span data-stu-id="440d1-133">**Prepare Domain**.</span></span> <span data-ttu-id="440d1-134">Esta tarea agrega las entradas de control de acceso (ACE) necesarias a grupos universales que conceden permisos para hospedar y administrar los usuarios del dominio.</span><span class="sxs-lookup"><span data-stu-id="440d1-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="440d1-135">Esta tarea debe completarse en todos los dominios en los que desee implementar servidores que ejecuten Lync Server 2013 y cualquier dominio en el que se encuentren los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="440d1-136">Para obtener más información sobre la preparación del dominio, vea [ejecución de la preparación del dominio de Lync Server 2013](lync-server-2013-running-domain-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="440d1-137">Para obtener información general sobre el proceso completo de preparación de Active Directory y los derechos y permisos necesarios para realizar cada paso, vea [requisitos de la infraestructura de Active Directory para Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="440d1-138">Grupos universales</span><span class="sxs-lookup"><span data-stu-id="440d1-138">Universal Groups</span></span>

<span data-ttu-id="440d1-139">Durante la preparación del bosque, Lync Server 2013 crea varios grupos universales dentro de los servicios de dominio de Active Directory que tienen permiso para acceder y administrar la configuración global y los servicios.</span><span class="sxs-lookup"><span data-stu-id="440d1-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="440d1-140">Entre estos grupos universales se incluyen:</span><span class="sxs-lookup"><span data-stu-id="440d1-140">These universal groups include:</span></span>

  - <span data-ttu-id="440d1-141">**Grupos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="440d1-141">**Administrative groups**.</span></span> <span data-ttu-id="440d1-142">Estos grupos definen los roles de administrador fundamentales para una red de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="440d1-143">Durante la preparación del bosque, estos grupos de administradores se agregan a los grupos de infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="440d1-144">**Grupos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="440d1-144">**Service groups**.</span></span> <span data-ttu-id="440d1-145">Estos grupos son cuentas de servicio necesarias para obtener acceso a los distintos servicios proporcionados por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="440d1-146">**Grupos de infraestructura**.</span><span class="sxs-lookup"><span data-stu-id="440d1-146">**Infrastructure groups**.</span></span> <span data-ttu-id="440d1-147">Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="440d1-148">Funcionan como componentes de los grupos administrativos y no deben modificarse ni se deben agregar directamente usuarios a esos grupos.</span><span class="sxs-lookup"><span data-stu-id="440d1-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="440d1-149">Durante la preparación del bosque, se añaden grupos de servicio y administración específicos a los grupos de infraestructura correspondientes.</span><span class="sxs-lookup"><span data-stu-id="440d1-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="440d1-150">Para obtener información sobre los grupos universales específicos que se han creado al preparar AD para Lync Server, así como los grupos de servicio y administración que se agregan a los grupos de infraestructura, consulte [cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en el Documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="440d1-151">Lync Server 2013 admite los grupos universales de Windows Server 2012 para servidores que ejecutan Lync Server 2013, así como sistemas operativos Windows Server 2003 para controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="440d1-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="440d1-152">Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque, y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque.</span><span class="sxs-lookup"><span data-stu-id="440d1-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="440d1-153">La compatibilidad con los grupos universales, junto con la delegación de administrador, simplifica la administración de una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="440d1-154">Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.</span><span class="sxs-lookup"><span data-stu-id="440d1-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="440d1-155">Control de acceso basado en roles</span><span class="sxs-lookup"><span data-stu-id="440d1-155">Role-Based Access Control</span></span>

<span data-ttu-id="440d1-156">Además de crear grupos universales de servicio y administración y añadir grupos de servicio y administración a los grupos universales correspondientes, la preparación del bosque también crea grupos de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="440d1-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="440d1-157">Para obtener detalles sobre los grupos RBAC específicos creados por la preparación del bosque, consulte [cambios hechos por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="440d1-158">Para obtener más información sobre los grupos RBAC, consulte [control de acceso basado en roles (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="440d1-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="440d1-159">Entradas de control de acceso (ACE) y herencia</span><span class="sxs-lookup"><span data-stu-id="440d1-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="440d1-160">La preparación del bosque crea ACE privadas y públicas, y añade ACE en los grupos universales que crea.</span><span class="sxs-lookup"><span data-stu-id="440d1-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="440d1-161">Crea ACE privadas específicas en el contenedor de configuración global usado por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="440d1-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="440d1-162">Este contenedor solo es utilizado por Lync Server y se encuentra en el contenedor configuración o en el contenedor del sistema en el dominio raíz, según dónde se almacene la configuración global.</span><span class="sxs-lookup"><span data-stu-id="440d1-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="440d1-p114">El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="440d1-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="440d1-165">Para obtener detalles sobre las ACE públicas creadas y agregadas por la preparación del bosque y la preparación del dominio, consulte [los cambios realizados por la preparación del bosque en Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) y [los cambios realizados por la preparación del dominio en Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) en la implementación documentación.</span><span class="sxs-lookup"><span data-stu-id="440d1-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="440d1-166">Las organizaciones suelen bloquear los servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="440d1-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="440d1-167">Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="440d1-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="440d1-168">Puede incluir la eliminación de ACE de contenedores y unidades organizativas y la deshabilitación de la herencia de permisos en los objetos User, Contact, InetOrgPerson o Computer.</span><span class="sxs-lookup"><span data-stu-id="440d1-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="440d1-169">En un entorno de Active Directory bloqueado, los permisos deben establecerse manualmente en contenedores y unidades organizativas que los requieran.</span><span class="sxs-lookup"><span data-stu-id="440d1-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="440d1-170">Para obtener más información, vea [preparar servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="440d1-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="440d1-171">Información sobre el servidor</span><span class="sxs-lookup"><span data-stu-id="440d1-171">Server Information</span></span>

<span data-ttu-id="440d1-172">Durante la activación, Lync Server 2013 publica la información del servidor en las tres siguientes ubicaciones de los servicios de dominio de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="440d1-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="440d1-173">Un punto de conexión de servicio (SCP) en cada objeto de equipo de Active Directory correspondiente a un equipo físico en el que está instalado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="440d1-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="440d1-174">Objetos de servidor creados en el contenedor de la clase **msRTCSIP-Pools**.</span><span class="sxs-lookup"><span data-stu-id="440d1-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="440d1-175">Servidores de confianza especificados en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="440d1-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="440d1-176">Puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="440d1-176">Service Connection Points</span></span>

<span data-ttu-id="440d1-177">Cada objeto de Lync Server 2013 de los servicios de dominio de Active Directory tiene un SCP denominado servicios de RTC, que a su vez contiene una serie de atributos que identifican cada equipo y especifican los servicios que proporciona.</span><span class="sxs-lookup"><span data-stu-id="440d1-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="440d1-178">Algunos de los atributos más importantes de SCP son *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* y *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="440d1-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="440d1-179">Las aplicaciones de administración de activos de otro fabricante pueden recuperar la información de servidor de una implementación consultando estos y otros atributos de los SCP.</span><span class="sxs-lookup"><span data-stu-id="440d1-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="440d1-180">Objetos de servidor de Active Directory</span><span class="sxs-lookup"><span data-stu-id="440d1-180">Active Directory Server Objects</span></span>

<span data-ttu-id="440d1-181">Cada rol de servidor de Lync Server 2013 tiene un objeto de Active Directory correspondiente cuyos atributos definen los servicios proporcionados por ese rol.</span><span class="sxs-lookup"><span data-stu-id="440d1-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="440d1-182">Además, cuando se activa un servidor Standard Edition o cuando se crea un grupo de servidores Enterprise Edition, Lync Server 2013 crea un nuevo objeto **msRTCSIP-Pool** en el contenedor de **msRTCSIP-pools** .</span><span class="sxs-lookup"><span data-stu-id="440d1-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="440d1-183">La clase **msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo, junto con la asociación entre los componentes front-end y back-end del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="440d1-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="440d1-184">(Un servidor Standard Edition se considera un grupo lógico cuyos extremos frontal y posterior se colocan en un solo equipo).</span><span class="sxs-lookup"><span data-stu-id="440d1-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="440d1-185">Servidores de confianza</span><span class="sxs-lookup"><span data-stu-id="440d1-185">Trusted Servers</span></span>

<span data-ttu-id="440d1-186">En Lync Server 2013, los servidores de confianza son los que se especifican al ejecutar Topology Builder y publicar su topología.</span><span class="sxs-lookup"><span data-stu-id="440d1-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="440d1-187">La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="440d1-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="440d1-188">Solo los servidores definidos en el almacén de administración central son de confianza.</span><span class="sxs-lookup"><span data-stu-id="440d1-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="440d1-189">En Lync Server 2013, un servidor de confianza es aquel que cumple los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="440d1-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="440d1-190">El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="440d1-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="440d1-191">El servidor presenta un certificado válido de una CA de confianza.</span><span class="sxs-lookup"><span data-stu-id="440d1-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="440d1-192">Para obtener más información, consulte [requisitos de infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="440d1-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="440d1-p120">Si no se cumple alguno de estos criterios, el servidor no se considera de confianza y se rechaza la conexión con dicho servidor. Estos dos requisitos impiden que se produzca un posible ataque, aunque poco probable, en el que un servidor no autorizado intenta adoptar el FQDN de un servidor válido.</span><span class="sxs-lookup"><span data-stu-id="440d1-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="440d1-195">Además, para permitir que las implementaciones de Microsoft Office Communications Server 2007 R2 y Microsoft Office Communications Server 2007 se comuniquen con los servidores de Lync Server 2013, Lync Server 2013 crea contenedores durante la preparación del bosque para almacenar listas de servidores de confianza para versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="440d1-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="440d1-196">La siguiente tabla describe los contenedores creados para habilitar la compatibilidad con implementaciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="440d1-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="440d1-197">Listas de servidores de confianza y sus contenedores de Active Directory para la compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="440d1-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="440d1-198">Listas de servidores de confianza</span><span class="sxs-lookup"><span data-stu-id="440d1-198">Trusted server list</span></span></th>
<th><span data-ttu-id="440d1-199">Contenedor de Active Directory</span><span class="sxs-lookup"><span data-stu-id="440d1-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="440d1-200">Servidores de Standard Edition y servidores front-end del grupo Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="440d1-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="440d1-201">Servicio RTC/Configuración global</span><span class="sxs-lookup"><span data-stu-id="440d1-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="440d1-202">Servidores de conferencia</span><span class="sxs-lookup"><span data-stu-id="440d1-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="440d1-203">Servicio RTC/MCU de confianza</span><span class="sxs-lookup"><span data-stu-id="440d1-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="440d1-204">Servidores de componentes web</span><span class="sxs-lookup"><span data-stu-id="440d1-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="440d1-205">Servicio RTC/Servidores de componentes web de confianza</span><span class="sxs-lookup"><span data-stu-id="440d1-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="440d1-206">Servidores de mediación y servidores de Communicator Web Access, Servidor de aplicaciones, Registrador con QoE, Servicio de conferencia A/V (también servidores SIP de otros fabricantes)</span><span class="sxs-lookup"><span data-stu-id="440d1-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="440d1-207">Servicio RTC/Servicios de confianza</span><span class="sxs-lookup"><span data-stu-id="440d1-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="440d1-208">Servidores proxy</span><span class="sxs-lookup"><span data-stu-id="440d1-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="440d1-209">Lync Server 2013 no admite compatibilidad con versiones anteriores para servidores proxy</span><span class="sxs-lookup"><span data-stu-id="440d1-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="440d1-210">Para admitir servidores de confianza de versiones anteriores, debe ejecutar la herramienta Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="440d1-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="440d1-211">Para obtener más información sobre cómo ejecutar el analizador de [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)procedimientos recomendados, consulte.</span><span class="sxs-lookup"><span data-stu-id="440d1-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

