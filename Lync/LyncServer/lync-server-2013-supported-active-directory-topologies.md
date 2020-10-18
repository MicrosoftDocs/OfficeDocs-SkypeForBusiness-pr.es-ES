---
title: 'Lync Server 2013: topologías admitidas de Active Directory'
description: 'Lync Server 2013: topologías admitidas de Active Directory.'
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
ms.openlocfilehash: 9ce820a36cb033933b423e01deb5a3049ed3ea2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575316"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="06caa-103">Topologías de Active Directory admitidas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06caa-103">Supported Active Directory topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06caa-104">_**Última modificación del tema:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="06caa-104">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="06caa-105">Lync Server 2013 admite las mismas topologías de servicios de dominio de Active Directory que Microsoft Lync Server 2010 y Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="06caa-105">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="06caa-106">Se admiten las siguientes topologías:</span><span class="sxs-lookup"><span data-stu-id="06caa-106">The following topologies are supported:</span></span>

  - <span data-ttu-id="06caa-107">Un solo bosque con un solo dominio</span><span class="sxs-lookup"><span data-stu-id="06caa-107">Single forest with single domain</span></span>

  - <span data-ttu-id="06caa-108">Un solo bosque con un solo árbol y varios dominios</span><span class="sxs-lookup"><span data-stu-id="06caa-108">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="06caa-109">Un solo bosque con varios árboles y espacios de nombres separados</span><span class="sxs-lookup"><span data-stu-id="06caa-109">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="06caa-110">Varios bosques en una topología de bosque central</span><span class="sxs-lookup"><span data-stu-id="06caa-110">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="06caa-111">Varios bosques en una topología de bosque de recursos</span><span class="sxs-lookup"><span data-stu-id="06caa-111">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="06caa-112">Varios bosques en una topología de bosque de recursos de Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06caa-112">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="06caa-113">En la siguiente figura se identifican los iconos utilizados en las ilustraciones de esta sección.</span><span class="sxs-lookup"><span data-stu-id="06caa-113">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="06caa-114">**Leyenda de las ilustraciones de topología**</span><span class="sxs-lookup"><span data-stu-id="06caa-114">**Key to topology illustrations**</span></span>

<span data-ttu-id="06caa-115">![Leyenda de las ilustraciones de topología](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Leyenda de las ilustraciones de topología")</span><span class="sxs-lookup"><span data-stu-id="06caa-115">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="06caa-116">Un solo bosque, un solo dominio</span><span class="sxs-lookup"><span data-stu-id="06caa-116">Single Forest, Single Domain</span></span>

<span data-ttu-id="06caa-117">La topología de Active Directory más sencilla compatible con Lync Server, un bosque de dominio único, es una topología común.</span><span class="sxs-lookup"><span data-stu-id="06caa-117">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="06caa-118">En la siguiente figura se muestra una implementación de Lync Server en una topología de Active Directory de un solo dominio.</span><span class="sxs-lookup"><span data-stu-id="06caa-118">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="06caa-119">**Topología de dominio único**</span><span class="sxs-lookup"><span data-stu-id="06caa-119">**Single domain topology**</span></span>

<span data-ttu-id="06caa-120">![Topología de dominio único](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topología de dominio único")</span><span class="sxs-lookup"><span data-stu-id="06caa-120">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="06caa-121">Un solo bosque, varios dominios</span><span class="sxs-lookup"><span data-stu-id="06caa-121">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="06caa-122">Otra topología de Active Directory compatible con Lync Server es un único bosque que consta de un dominio raíz y uno o más dominios secundarios.</span><span class="sxs-lookup"><span data-stu-id="06caa-122">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="06caa-123">En este tipo de topología de Active Directory, el dominio donde se crean los usuarios puede ser diferente del dominio en el que se va a implementar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06caa-123">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="06caa-124">Sin embargo, si implementa un grupo de servidores front-end, deberá implementar todos los servidores front-end del grupo en un dominio único.</span><span class="sxs-lookup"><span data-stu-id="06caa-124">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="06caa-125">Lync Server Support for Windows universal Administrator Groups permite la administración entre dominios.</span><span class="sxs-lookup"><span data-stu-id="06caa-125">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="06caa-126">En la siguiente figura se muestra una implementación en un solo bosque con varios dominios.</span><span class="sxs-lookup"><span data-stu-id="06caa-126">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="06caa-127">En esta figura, un icono de usuario muestra el dominio en el que está hospedada la cuenta de usuario y la flecha apunta al dominio donde reside el grupo de servidores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06caa-127">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="06caa-128">Entre las cuentas de usuario se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="06caa-128">User accounts include the following:</span></span>

  - <span data-ttu-id="06caa-129">Cuentas de usuario dentro del mismo dominio que el grupo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="06caa-129">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="06caa-130">Cuentas de usuario en un dominio diferente del grupo de servidores de Lync Server</span><span class="sxs-lookup"><span data-stu-id="06caa-130">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="06caa-131">Cuentas de usuario en un dominio secundario del dominio con el grupo de servidores de Lync Server</span><span class="sxs-lookup"><span data-stu-id="06caa-131">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="06caa-132">**Un solo bosque con varios dominios**</span><span class="sxs-lookup"><span data-stu-id="06caa-132">**Single forest with multiple domains**</span></span>

<span data-ttu-id="06caa-133">![Un solo bosque con varios dominios](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Un solo bosque con varios dominios")</span><span class="sxs-lookup"><span data-stu-id="06caa-133">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="06caa-134">Un solo bosque, varios árboles</span><span class="sxs-lookup"><span data-stu-id="06caa-134">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="06caa-135">La topología de un solo bosque y varios árboles se compone de dos o más dominios que definen estructuras de árbol independientes y espacios de nombres de Active Directory independientes.</span><span class="sxs-lookup"><span data-stu-id="06caa-135">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="06caa-136">En la figura siguiente se muestra un solo bosque con varios árboles.</span><span class="sxs-lookup"><span data-stu-id="06caa-136">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="06caa-137">En esta figura, un icono de usuario muestra el dominio en el que se hospeda la cuenta de usuario, una línea sólida a un grupo de Lync Server que reside en el mismo dominio o en otro diferente, y una línea discontinua apunta a un grupo de Lync Server que reside en un árbol diferente.</span><span class="sxs-lookup"><span data-stu-id="06caa-137">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="06caa-138">Entre las cuentas de usuario se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="06caa-138">User accounts include the following:</span></span>

  - <span data-ttu-id="06caa-139">Cuentas de usuario dentro del mismo dominio que el grupo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="06caa-139">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="06caa-140">Cuentas de usuario en un dominio diferente de (pero el mismo árbol que) el grupo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="06caa-140">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="06caa-141">Cuentas de usuario en un árbol diferente del grupo de Lync Server</span><span class="sxs-lookup"><span data-stu-id="06caa-141">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="06caa-142">**Un solo bosque con varios árboles**</span><span class="sxs-lookup"><span data-stu-id="06caa-142">**Single forest with multiple trees**</span></span>

<span data-ttu-id="06caa-143">![Un solo bosque con varios árboles](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Un solo bosque con varios árboles")</span><span class="sxs-lookup"><span data-stu-id="06caa-143">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="06caa-144">Varios bosques, bosque central</span><span class="sxs-lookup"><span data-stu-id="06caa-144">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="06caa-145">Lync Server admite varios bosques que están configurados en una topología de bosque central.</span><span class="sxs-lookup"><span data-stu-id="06caa-145">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="06caa-146">Las topologías de bosque central utilizan objetos de contacto en el bosque central para representar a los usuarios en los otros bosques.</span><span class="sxs-lookup"><span data-stu-id="06caa-146">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="06caa-147">El bosque central también hospeda las cuentas de usuario de cualquier usuario de este bosque.</span><span class="sxs-lookup"><span data-stu-id="06caa-147">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="06caa-148">Un producto de sincronización de directorios, como, por ejemplo, Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario en la organización: cuando se crea una nueva cuenta de usuario en uno de los bosques o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza el contacto correspondiente en el bosque central.</span><span class="sxs-lookup"><span data-stu-id="06caa-148">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="06caa-149">Un bosque central tiene las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="06caa-149">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="06caa-150">Los servidores que ejecutan Lync Server están centralizados dentro de un solo bosque.</span><span class="sxs-lookup"><span data-stu-id="06caa-150">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="06caa-151">Los usuarios pueden buscar otros usuarios y comunicarse con ellos en cualquier bosque.</span><span class="sxs-lookup"><span data-stu-id="06caa-151">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="06caa-152">Los usuarios pueden ver la presencia de otros usuarios en cualquier bosque.</span><span class="sxs-lookup"><span data-stu-id="06caa-152">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="06caa-153">El producto de sincronización de directorios automatiza la adición y la eliminación de los objetos de contacto en el bosque central cuando se crean y se quitan cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="06caa-153">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="06caa-154">En la siguiente figura se muestra una topología de bosque central.</span><span class="sxs-lookup"><span data-stu-id="06caa-154">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="06caa-155">En esta figura, hay relaciones de confianza bidireccionales entre el dominio que hospeda Lync Server, que se encuentra en el bosque central, y cada dominio solo de usuario, que se encuentra en un bosque independiente.</span><span class="sxs-lookup"><span data-stu-id="06caa-155">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="06caa-156">No es necesario extender el esquema de los bosques de usuarios independientes.</span><span class="sxs-lookup"><span data-stu-id="06caa-156">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="06caa-157">**Topología de bosque central**</span><span class="sxs-lookup"><span data-stu-id="06caa-157">**Central forest topology**</span></span>

<span data-ttu-id="06caa-158">![Topología de bosque central](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topología de bosque central")</span><span class="sxs-lookup"><span data-stu-id="06caa-158">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="06caa-159">Varios bosques, bosque de recursos</span><span class="sxs-lookup"><span data-stu-id="06caa-159">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="06caa-160">En una topología de bosque de recursos, un bosque está dedicado a ejecutar aplicaciones de servidor, como Microsoft Exchange Server y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06caa-160">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="06caa-161">El bosque de recursos hospeda las aplicaciones de servidor y una representación sincronizada del objeto de usuario activo, pero no contiene cuentas de usuario habilitadas para inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="06caa-161">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="06caa-162">El bosque de recursos actúa como un entorno de servicios compartidos para los otros bosques donde residen los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="06caa-162">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="06caa-163">Los bosques de usuarios tienen una relación de confianza de nivel de bosque con el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="06caa-163">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="06caa-164">Al implementar Lync Server en este tipo de topología, se crea un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios.</span><span class="sxs-lookup"><span data-stu-id="06caa-164">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="06caa-165">Si Microsoft Exchange ya está implementado en el bosque de recursos, es posible que ya existan cuentas de usuario deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="06caa-165">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="06caa-166">Un producto de sincronización de directorios, como MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="06caa-166">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="06caa-167">Cuando se crea una nueva cuenta de usuario en uno de los bosques de usuarios o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza la representación de usuario correspondiente en el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="06caa-167">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="06caa-168">Esta topología se puede usar para proporcionar una infraestructura compartida para servicios en organizaciones que administran varios bosques o para separar la administración de objetos de Active Directory de otra administración.</span><span class="sxs-lookup"><span data-stu-id="06caa-168">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="06caa-169">Las empresas que necesitan aislar la administración de Active Directory por motivos de seguridad suelen elegir esta topología.</span><span class="sxs-lookup"><span data-stu-id="06caa-169">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="06caa-170">Esta topología ofrece la ventaja de limitar la necesidad de extender el esquema de Active Directory a un único bosque (es decir, el bosque de recursos).</span><span class="sxs-lookup"><span data-stu-id="06caa-170">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="06caa-171">El siguiente diagrama ilustra una topología de bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="06caa-171">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="06caa-172">**Topología de bosque de recursos**</span><span class="sxs-lookup"><span data-stu-id="06caa-172">**Resource forest topology**</span></span>

<span data-ttu-id="06caa-173">![Topología de bosque de recursos de Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topología de bosque de recursos de Active Directory")</span><span class="sxs-lookup"><span data-stu-id="06caa-173">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="06caa-174">Varios bosques en una topología de bosque de recursos de Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="06caa-174">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="06caa-175">En esta topología, uno o más bosques se encuentran en local y se dedican a hospedar cuentas de usuario de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06caa-175">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="06caa-176">El bosque de recursos se encuentra fuera de la organización y lo mantiene un proveedor de hospedaje de terceros.</span><span class="sxs-lookup"><span data-stu-id="06caa-176">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="06caa-177">El bosque de recursos contiene solo la implementación de Lync Server y una replicación sincronizada de las cuentas de usuario desde el bosque o las cuentas de usuario locales.</span><span class="sxs-lookup"><span data-stu-id="06caa-177">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="06caa-178">No contiene cuentas de usuario habilitadas para inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="06caa-178">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="06caa-179">Exchange se implementa en los bosques de cuentas de usuario locales integrados junto con Exchange Online (híbrido), o los servicios de correo electrónico para las cuentas de usuario locales se proporcionan exclusivamente por parte de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="06caa-179">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="06caa-180">El bosque de recursos actúa como un entorno de servicios compartidos para el bosque o los bosques de Active Directory locales donde residen los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="06caa-180">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="06caa-181">Los bosques de cuentas de usuario tienen una relación de confianza de nivel de bosque unidireccional con el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="06caa-181">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="06caa-182">Al implementar Lync Server en este tipo de topología, se crea un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios.</span><span class="sxs-lookup"><span data-stu-id="06caa-182">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="06caa-183">Un producto de sincronización de directorios, como MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="06caa-183">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="06caa-184">Cuando se crea una nueva cuenta de usuario en uno de los bosques de usuarios o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza la representación de usuario correspondiente en el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="06caa-184">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="06caa-185">Para obtener más información acerca de la configuración de una implementación de varios bosques, vea [Deploying Lync in a multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="06caa-185">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

