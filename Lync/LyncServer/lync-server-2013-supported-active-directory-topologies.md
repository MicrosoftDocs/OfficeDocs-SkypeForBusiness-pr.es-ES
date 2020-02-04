---
title: 'Lync Server 2013: Topologías admitidas de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e4aca368f6ea7d5b31a1cfe74273dfbd42a6594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="6c9bc-102">Topologías admitidas de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c9bc-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c9bc-103">_**Última modificación del tema:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="6c9bc-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="6c9bc-104">Lync Server 2013 admite las mismas topologías de servicios de dominio de Active Directory que Microsoft Lync Server 2010 y Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6c9bc-105">Se admiten las siguientes topologías:</span><span class="sxs-lookup"><span data-stu-id="6c9bc-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="6c9bc-106">Un solo bosque con un solo dominio</span><span class="sxs-lookup"><span data-stu-id="6c9bc-106">Single forest with single domain</span></span>

  - <span data-ttu-id="6c9bc-107">Un solo bosque con un solo árbol y varios dominios</span><span class="sxs-lookup"><span data-stu-id="6c9bc-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="6c9bc-108">Un solo bosque con varios árboles y espacios de nombres separados</span><span class="sxs-lookup"><span data-stu-id="6c9bc-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="6c9bc-109">Varios bosques en una topología de bosque central</span><span class="sxs-lookup"><span data-stu-id="6c9bc-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="6c9bc-110">Varios bosques en una topología de bosque de recursos</span><span class="sxs-lookup"><span data-stu-id="6c9bc-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="6c9bc-111">Varios bosques en una topología de bosque de recursos de Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6c9bc-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="6c9bc-112">En la siguiente ilustración se identifican los iconos que se usan en las ilustraciones de esta sección.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="6c9bc-113">**Ilustraciones de la clave de la topología**</span><span class="sxs-lookup"><span data-stu-id="6c9bc-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="6c9bc-114">![Ilustraciones de la clave de la topología](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Ilustraciones de la clave de la topología")</span><span class="sxs-lookup"><span data-stu-id="6c9bc-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="6c9bc-115">Bosque único, dominio único</span><span class="sxs-lookup"><span data-stu-id="6c9bc-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="6c9bc-116">La topología de Active Directory más sencilla admitida por Lync Server, un solo bosque de dominio, es una topología común.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="6c9bc-117">En la siguiente ilustración se muestra una implementación de Lync Server en una topología de Active Directory de dominio único.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="6c9bc-118">**Topología de dominio único**</span><span class="sxs-lookup"><span data-stu-id="6c9bc-118">**Single domain topology**</span></span>

<span data-ttu-id="6c9bc-119">![Topología de dominio único](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topología de dominio único")</span><span class="sxs-lookup"><span data-stu-id="6c9bc-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="6c9bc-120">Un único bosque, varios dominios</span><span class="sxs-lookup"><span data-stu-id="6c9bc-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="6c9bc-121">Otra topología de Active Directory admitida por Lync Server es un único bosque que consta de un dominio raíz y uno o más dominios secundarios.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="6c9bc-122">En este tipo de topología de Active Directory, el dominio donde se crean los usuarios puede ser diferente del dominio en el que se implementa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="6c9bc-123">Sin embargo, si implementa un grupo de servidores front-end, debe implementar todos los servidores front-end del grupo en un solo dominio.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="6c9bc-124">La compatibilidad de Lync Server con los grupos de administradores universales de Windows permite la administración de dominios interrelacionados.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="6c9bc-125">En la siguiente ilustración se muestra una implementación en un solo bosque con varios dominios.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="6c9bc-126">En esta ilustración, un icono de usuario muestra el dominio en el que se ha alojado la cuenta de usuario y la flecha apunta al dominio donde reside el grupo de servidores de Lync.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="6c9bc-127">Entre las cuentas de usuario se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c9bc-127">User accounts include the following:</span></span>

  - <span data-ttu-id="6c9bc-128">Cuentas de usuario dentro del mismo dominio que el grupo de servidores de Lync</span><span class="sxs-lookup"><span data-stu-id="6c9bc-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="6c9bc-129">Cuentas de usuario en un dominio diferente del grupo de servidores de Lync</span><span class="sxs-lookup"><span data-stu-id="6c9bc-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="6c9bc-130">Cuentas de usuario en un dominio secundario del dominio con el grupo de servidores de Lync</span><span class="sxs-lookup"><span data-stu-id="6c9bc-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="6c9bc-131">**Bosque único con varios dominios**</span><span class="sxs-lookup"><span data-stu-id="6c9bc-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="6c9bc-132">![Bosque único con varios dominios](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Bosque único con varios dominios")</span><span class="sxs-lookup"><span data-stu-id="6c9bc-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="6c9bc-133">Un solo bosque, varios árboles</span><span class="sxs-lookup"><span data-stu-id="6c9bc-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="6c9bc-134">Una topología de bosques de varios árboles consta de dos o más dominios que definen estructuras de árbol independientes y espacios de nombres de Active Directory independientes.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="6c9bc-135">En la ilustración siguiente se muestra un bosque único con varios árboles.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="6c9bc-136">En esta ilustración, un icono de usuario muestra el dominio en el que se ha alojado la cuenta de usuario, una línea sólida de un grupo de Lync Server que reside en el mismo dominio o en otro diferente, y una línea discontinua que apunta al grupo de Lync Server que reside en un árbol diferente.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="6c9bc-137">Entre las cuentas de usuario se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c9bc-137">User accounts include the following:</span></span>

  - <span data-ttu-id="6c9bc-138">Cuentas de usuario dentro del mismo dominio que el grupo de servidores de Lync</span><span class="sxs-lookup"><span data-stu-id="6c9bc-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="6c9bc-139">Cuentas de usuario en un dominio diferente de (pero el mismo árbol que) el grupo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6c9bc-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="6c9bc-140">Cuentas de usuario en un árbol diferente del grupo de servidores de Lync</span><span class="sxs-lookup"><span data-stu-id="6c9bc-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="6c9bc-141">**Bosque único con varios árboles**</span><span class="sxs-lookup"><span data-stu-id="6c9bc-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="6c9bc-142">![Bosque único con varios árboles](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Bosque único con varios árboles")</span><span class="sxs-lookup"><span data-stu-id="6c9bc-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="6c9bc-143">Varios bosques, bosque central</span><span class="sxs-lookup"><span data-stu-id="6c9bc-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="6c9bc-144">Lync Server admite varios bosques que están configurados en una topología de bosque central.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="6c9bc-145">Las topologías de bosque central usan objetos de contacto en el bosque central para representar a los usuarios de otros bosques.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="6c9bc-146">El bosque central también hospeda cuentas de usuario para los usuarios de este bosque.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="6c9bc-147">Un producto de sincronización de directorios, como Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario en la organización: cuando se crea una nueva cuenta de usuario en uno de los bosques o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza el contacto correspondiente en el bosque central.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="6c9bc-148">Un bosque central tiene las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="6c9bc-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="6c9bc-149">Los servidores que ejecutan Lync Server están centralizados en un solo bosque.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="6c9bc-150">Los usuarios pueden buscar y comunicarse con otros usuarios en cualquier bosque.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="6c9bc-151">Los usuarios pueden ver la presencia de otros usuarios en cualquier bosque.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="6c9bc-152">El producto de sincronización de directorios automatiza la adición y la eliminación de objetos de contacto en el bosque central a medida que se crean o quitan cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="6c9bc-153">En la siguiente ilustración se muestra una topología de bosque central.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="6c9bc-154">En esta ilustración, hay relaciones de confianza bidireccionales entre el dominio que hospeda Lync Server, que está en el bosque central y cada dominio de solo usuario, que se encuentra en un bosque independiente.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="6c9bc-155">No es necesario extender el esquema de los bosques de usuario independientes.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="6c9bc-156">**Topología de bosque central**</span><span class="sxs-lookup"><span data-stu-id="6c9bc-156">**Central forest topology**</span></span>

<span data-ttu-id="6c9bc-157">![Topología de bosque central](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topología de bosque central")</span><span class="sxs-lookup"><span data-stu-id="6c9bc-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="6c9bc-158">Varios bosques, bosque de recursos</span><span class="sxs-lookup"><span data-stu-id="6c9bc-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="6c9bc-159">En una topología de bosque de recursos, un bosque está dedicado a ejecutar aplicaciones de servidor, como Microsoft Exchange Server y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="6c9bc-160">El bosque de recursos hospeda las aplicaciones de servidor y una representación sincronizada del objeto de usuario activo, pero no contiene cuentas de usuario habilitadas para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="6c9bc-161">El bosque de recursos actúa como un entorno de servicios compartidos para los otros bosques donde residen los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="6c9bc-162">Los bosques de usuario tienen una relación de confianza de nivel de bosque con el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="6c9bc-163">Al implementar Lync Server en este tipo de topología, se crea un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario de los bosques de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="6c9bc-164">Si Microsoft Exchange ya está implementado en el bosque de recursos, es posible que ya existan cuentas de usuario deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="6c9bc-165">Un producto de sincronización de directorios, como MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="6c9bc-166">Cuando se crea una nueva cuenta de usuario en uno de los bosques de usuario o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza la representación de usuario correspondiente en el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="6c9bc-167">Esta topología se puede usar para proporcionar una infraestructura compartida para servicios en organizaciones que administran varios bosques o para separar la administración de objetos de Active Directory de otra administración.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="6c9bc-168">Las empresas que necesiten aislar la administración de Active Directory por razones de seguridad suelen elegir esta topología.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="6c9bc-169">Esta topología ofrece la ventaja de limitar la necesidad de ampliar el esquema de Active Directory a un solo bosque (es decir, el bosque de recursos).</span><span class="sxs-lookup"><span data-stu-id="6c9bc-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="6c9bc-170">En el siguiente diagrama se muestra una topología de bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="6c9bc-171">**Topología de bosque de recursos**</span><span class="sxs-lookup"><span data-stu-id="6c9bc-171">**Resource forest topology**</span></span>

<span data-ttu-id="6c9bc-172">![Topología de bosque de recursos de Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topología de bosque de recursos de Active Directory")</span><span class="sxs-lookup"><span data-stu-id="6c9bc-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="6c9bc-173">Varios bosques en una topología de bosque de recursos de Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6c9bc-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="6c9bc-174">En esta topología, uno o más bosques se encuentran en local y se dedican a hospedar cuentas de usuario de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="6c9bc-175">El bosque de recursos se encuentra fuera local y lo mantiene un proveedor de hospedaje de terceros.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="6c9bc-176">El bosque de recursos contiene solo la implementación de Lync Server y una replicación sincronizada de las cuentas de usuario de los bosques de las cuentas de usuario locales.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="6c9bc-177">No contiene cuentas de usuario habilitadas para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="6c9bc-178">Exchange se implementa en los bosques de la cuenta de usuario local integrados junto con Exchange Online (híbrido) o los servicios de correo electrónico para las cuentas de usuario locales se proporcionan exclusivamente por parte de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="6c9bc-179">El bosque de recursos actúa como un entorno de servicios compartidos para los bosques de Active Directory locales donde residen los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="6c9bc-180">Los bosques de cuentas de usuario tienen una relación de confianza de nivel de bosque unidireccional con el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="6c9bc-181">Al implementar Lync Server en este tipo de topología, se crea un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario de los bosques de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="6c9bc-182">Un producto de sincronización de directorios, como MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="6c9bc-183">Cuando se crea una nueva cuenta de usuario en uno de los bosques de usuario o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza la representación de usuario correspondiente en el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="6c9bc-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="6c9bc-184">Para obtener más información acerca de la configuración de una implementación de varios bosques, consulte [implementar Lync en una arquitectura de varios bosques (asociado hospedado de Lync con Exchange híbrido)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="6c9bc-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

