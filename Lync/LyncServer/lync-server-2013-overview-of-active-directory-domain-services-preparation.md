---
title: 'Lync Server 2013: información general sobre la preparación de los servicios de dominio de Active Directory'
description: 'Lync Server 2013: información general sobre la preparación de los servicios de dominio de Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566846"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="69232-103">Información general sobre la preparación de los servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69232-103">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69232-104">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="69232-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="69232-105">Para preparar los servicios de dominio de Active Directory para la implementación de Lync Server 2013, debe realizar tres pasos en una secuencia específica.</span><span class="sxs-lookup"><span data-stu-id="69232-105">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="69232-106">En la tabla siguiente se describen los pasos necesarios para preparar AD DS para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-106">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="69232-107">Pasos de preparación de Active Directory</span><span class="sxs-lookup"><span data-stu-id="69232-107">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="69232-108">Paso</span><span class="sxs-lookup"><span data-stu-id="69232-108">Step</span></span></th>
<th><span data-ttu-id="69232-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="69232-109">Description</span></span></th>
<th><span data-ttu-id="69232-110">Dónde se ejecuta</span><span class="sxs-lookup"><span data-stu-id="69232-110">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="69232-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparar el esquema de Active Directory en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="69232-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69232-112">Amplía el esquema de Active Directory agregando nuevas clases y atributos que se usan en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-112">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="69232-113">Ejecutarse una vez para cada bosque de la implementación donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-113">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="69232-114">En el maestro de esquema en el dominio raíz de cada bosque donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-114">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69232-p101">No es necesario realizar este paso en el dominio raíz si tiene permisos en el maestro de esquema, pero debe ser miembro del grupo Administradores de esquema en el dominio raíz y miembro del grupo Administradores de organización en el maestro de esquema. En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.</span><span class="sxs-lookup"><span data-stu-id="69232-p101">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master. In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="69232-118"><a href="lync-server-2013-preparing-the-forest.md">Preparar el bosque para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="69232-118"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69232-119">Crea la configuración global y los grupos universales que se usan en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-119">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="69232-120">Ejecutarse una vez para cada bosque de la implementación donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-120">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="69232-121">En el dominio raíz de cada bosque donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-121">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="69232-122">Para llevar a cabo este paso, debe ser miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="69232-122">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69232-p103">En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.</span><span class="sxs-lookup"><span data-stu-id="69232-p103">In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="69232-125"><a href="lync-server-2013-preparing-domains.md">Preparar dominios para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="69232-125"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69232-126">Agrega permisos a los objetos que van a usar los miembros de grupos universales.</span><span class="sxs-lookup"><span data-stu-id="69232-126">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="69232-127">Ejecútelo una vez por dominio de usuario o dominio de servidor.</span><span class="sxs-lookup"><span data-stu-id="69232-127">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69232-128">Si va a migrar de Lync Server 2010 a Lync Server 2013, es posible que el Asistente para la implementación indique que ya se ha completado la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="69232-128">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="69232-129">No necesita volver a ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="69232-129">You do not need to run domain preparation again.</span></span> <span data-ttu-id="69232-130">No se cambiaron los permisos de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69232-130">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="69232-131">En un servidor miembro en cada dominio donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69232-131">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="69232-132">Para ejecutar este paso, debe ser miembro del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="69232-132">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="69232-133">Lync Server 2013, al igual que Lync Server 2010, almacena gran parte de la información de configuración en el almacén de administración central en lugar de en AD DS como era el caso en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="69232-133">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="69232-134">Sin embargo, la siguiente información se almacena en AD DS:</span><span class="sxs-lookup"><span data-stu-id="69232-134">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="69232-135">**Extensiones de esquema**:</span><span class="sxs-lookup"><span data-stu-id="69232-135">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="69232-136">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="69232-136">User object extensions</span></span>
    
      - <span data-ttu-id="69232-137">Extensiones para las clases de Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="69232-137">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="69232-138">**Datos** (almacenados en el esquema extendido de Lync Server y en las clases de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="69232-138">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="69232-139">Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario</span><span class="sxs-lookup"><span data-stu-id="69232-139">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="69232-140">Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="69232-140">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="69232-141">Una referencia al almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="69232-141">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="69232-142">Cuenta de autenticación Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="69232-142">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="69232-143">En Lync Server 2013, delegue la configuración y la administración mediante la concesión de permisos de instalación al grupo universal RTCUniversalServerAdmins para que los miembros de ese grupo puedan instalar y activar Lync Server 2013 en un servidor local (después de que el servidor se haya agregado a la topología, se haya publicado y habilitado).</span><span class="sxs-lookup"><span data-stu-id="69232-143">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="69232-144">Los usuarios delegados deben ser administradores locales en el equipo en el que se van a instalar y activar Lync Server 2013, pero no es necesario que sean miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="69232-144">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="69232-145">También puede conceder permisos para objetos en unidades organizativas especificadas para que los miembros de los grupos universales creados durante la preparación del bosque puedan tener acceso a esos objetos sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="69232-145">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="69232-146">Para las implementaciones nuevas de Lync Server 2013, la configuración global debe almacenarse en el contenedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="69232-146">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="69232-147">Si su organización está actualizando desde una versión anterior y todavía tiene una configuración global en el contenedor del sistema, el contenedor del sistema todavía es compatible.</span><span class="sxs-lookup"><span data-stu-id="69232-147">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69232-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69232-148">See Also</span></span>


[<span data-ttu-id="69232-149">Preparar el esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69232-149">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="69232-150">Extensiones de esquema, clases y atributos de Active Directory usados por Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69232-150">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="69232-151">Preparar el bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69232-151">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="69232-152">Preparar dominios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69232-152">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

