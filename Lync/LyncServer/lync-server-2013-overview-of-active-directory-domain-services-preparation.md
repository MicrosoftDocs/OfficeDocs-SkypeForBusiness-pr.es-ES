---
title: 'Lync Server 2013: información general sobre la preparación de los servicios de dominio de Active Directory'
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
ms.openlocfilehash: 3085caf0b118b20bf52a4ff82a14b399d1ee6594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="38642-102">Información general sobre la preparación de los servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38642-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38642-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="38642-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="38642-104">Para preparar los servicios de dominio de Active Directory para la implementación de Lync Server 2013, debe realizar tres pasos en una secuencia específica.</span><span class="sxs-lookup"><span data-stu-id="38642-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="38642-105">En la tabla siguiente se describen los pasos necesarios para preparar AD DS para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="38642-106">Pasos de preparación de Active Directory</span><span class="sxs-lookup"><span data-stu-id="38642-106">Active Directory Preparation Steps</span></span>

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
<th><span data-ttu-id="38642-107">Paso</span><span class="sxs-lookup"><span data-stu-id="38642-107">Step</span></span></th>
<th><span data-ttu-id="38642-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="38642-108">Description</span></span></th>
<th><span data-ttu-id="38642-109">Dónde se ejecuta</span><span class="sxs-lookup"><span data-stu-id="38642-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="38642-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparar el esquema de Active Directory en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38642-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38642-111">Amplía el esquema de Active Directory agregando nuevas clases y atributos que se usan en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="38642-112">Ejecutarse una vez para cada bosque de la implementación donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="38642-113">En el maestro de esquema en el dominio raíz de cada bosque donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="38642-p101">No es necesario realizar este paso en el dominio raíz si tiene permisos en el maestro de esquema, pero debe ser miembro del grupo Administradores de esquema en el dominio raíz y miembro del grupo Administradores de organización en el maestro de esquema. En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.</span><span class="sxs-lookup"><span data-stu-id="38642-p101">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master. In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="38642-117"><a href="lync-server-2013-preparing-the-forest.md">Preparar el bosque para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38642-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38642-118">Crea la configuración global y los grupos universales que se usan en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="38642-119">Ejecutarse una vez para cada bosque de la implementación donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="38642-120">En el dominio raíz de cada bosque donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="38642-121">Para llevar a cabo este paso, debe ser miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="38642-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="38642-p103">En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.</span><span class="sxs-lookup"><span data-stu-id="38642-p103">In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="38642-124"><a href="lync-server-2013-preparing-domains.md">Preparar dominios para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="38642-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="38642-125">Agrega permisos a los objetos que van a usar los miembros de grupos universales.</span><span class="sxs-lookup"><span data-stu-id="38642-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="38642-126">Ejecútelo una vez por dominio de usuario o dominio de servidor.</span><span class="sxs-lookup"><span data-stu-id="38642-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="38642-127">Si va a migrar de Lync Server 2010 a Lync Server 2013, es posible que el Asistente para la implementación indique que ya se ha completado la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="38642-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="38642-128">No necesita volver a ejecutar la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="38642-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="38642-129">No se cambiaron los permisos de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38642-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="38642-130">En un servidor miembro en cada dominio donde se implementará Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38642-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="38642-131">Para ejecutar este paso, debe ser miembro del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="38642-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="38642-132">Lync Server 2013, al igual que Lync Server 2010, almacena gran parte de la información de configuración en el almacén de administración central en lugar de en AD DS como era el caso en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="38642-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="38642-133">Sin embargo, la siguiente información se almacena en AD DS:</span><span class="sxs-lookup"><span data-stu-id="38642-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="38642-134">**Extensiones de esquema**:</span><span class="sxs-lookup"><span data-stu-id="38642-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="38642-135">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="38642-135">User object extensions</span></span>
    
      - <span data-ttu-id="38642-136">Extensiones para las clases de Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="38642-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="38642-137">**Datos** (almacenados en el esquema extendido de Lync Server y en las clases de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="38642-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="38642-138">Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario</span><span class="sxs-lookup"><span data-stu-id="38642-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="38642-139">Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="38642-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="38642-140">Una referencia al almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="38642-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="38642-141">Cuenta de autenticación Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="38642-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="38642-142">En Lync Server 2013, delegue la configuración y la administración mediante la concesión de permisos de instalación al grupo universal RTCUniversalServerAdmins para que los miembros de ese grupo puedan instalar y activar Lync Server 2013 en un servidor local (después de que el servidor se haya agregado al topología, publicada y habilitada).</span><span class="sxs-lookup"><span data-stu-id="38642-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="38642-143">Los usuarios delegados deben ser administradores locales en el equipo en el que se van a instalar y activar Lync Server 2013, pero no es necesario que sean miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="38642-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="38642-144">También puede conceder permisos para objetos en unidades organizativas especificadas para que los miembros de los grupos universales creados durante la preparación del bosque puedan tener acceso a esos objetos sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="38642-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="38642-145">Para las implementaciones nuevas de Lync Server 2013, la configuración global debe almacenarse en el contenedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="38642-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="38642-146">Si su organización está actualizando desde una versión anterior y todavía tiene una configuración global en el contenedor del sistema, el contenedor del sistema todavía es compatible.</span><span class="sxs-lookup"><span data-stu-id="38642-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38642-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="38642-147">See Also</span></span>


[<span data-ttu-id="38642-148">Preparar el esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38642-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="38642-149">Extensiones de esquema, clases y atributos de Active Directory usados por Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38642-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="38642-150">Preparar el bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38642-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="38642-151">Preparar dominios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38642-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

