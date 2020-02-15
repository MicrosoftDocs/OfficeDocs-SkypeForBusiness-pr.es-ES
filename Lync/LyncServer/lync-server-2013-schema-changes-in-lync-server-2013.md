---
title: 'Lync Server 2013: cambios de esquema en Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789a6a67b1794eee5f01e8672f9aeb1076646ecf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="5c09e-102">Cambios de esquema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c09e-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c09e-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5c09e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5c09e-104">Antes de implementar y usar Lync Server 2013, debe preparar los servicios de dominio de Active Directory extendiendo el esquema.</span><span class="sxs-lookup"><span data-stu-id="5c09e-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="5c09e-105">Las extensiones de esquema agregan las clases y atributos que necesita Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c09e-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="5c09e-106">Lync Server 2013 requiere varias clases y atributos nuevos y modifica algunas clases y atributos existentes.</span><span class="sxs-lookup"><span data-stu-id="5c09e-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="5c09e-107">Además, la información de configuración de Lync Server 2013 se almacena en el almacén de administración central, en lugar de en AD DS como en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5c09e-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="5c09e-108">La siguiente información todavía se almacena en AD DS en Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="5c09e-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="5c09e-109">**Extensiones de esquema**:</span><span class="sxs-lookup"><span data-stu-id="5c09e-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="5c09e-110">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="5c09e-110">User object extensions</span></span>
    
      - <span data-ttu-id="5c09e-111">Extensiones para las clases de Office Communications Server 2007 y Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores compatibles</span><span class="sxs-lookup"><span data-stu-id="5c09e-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="5c09e-112">**Datos** (almacenados en el esquema extendido de Lync Server y en las clases de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="5c09e-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="5c09e-113">Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario</span><span class="sxs-lookup"><span data-stu-id="5c09e-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="5c09e-114">Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="5c09e-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="5c09e-115">Una referencia al almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="5c09e-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="5c09e-116">Cuenta de autenticación Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="5c09e-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="5c09e-117">En este tema se describen los cambios en el esquema de Active Directory que necesita Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c09e-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="5c09e-118">No se describen los cambios de esquema que se introdujeron en versiones anteriores de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="5c09e-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="5c09e-119">Para obtener una lista de las clases y sus descripciones, vea [clases de esquema y descripciones en Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="5c09e-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="5c09e-120">Para obtener una lista de atributos y sus descripciones, consulte [atributos y descripciones del esquema en Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="5c09e-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="5c09e-121">Para obtener una lista de las clases con los atributos que pueden contener, consulte [atributos de esquema por clase en Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="5c09e-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="5c09e-122">El prefijo msRTCSIP identifica clases y atributos que son específicos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5c09e-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="5c09e-123">Nuevos atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="5c09e-123">New Active Directory Attributes</span></span>

<span data-ttu-id="5c09e-124">En la tabla siguiente se describen los atributos de Active Directory que se agregan con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c09e-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="5c09e-125">Atributos agregados por Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c09e-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c09e-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="5c09e-126">Attribute</span></span></th>
<th><span data-ttu-id="5c09e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c09e-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c09e-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5c09e-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="5c09e-129">Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="5c09e-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="5c09e-130">Las directivas de retención conservan los elementos del buzón del usuario durante toda la retención.</span><span class="sxs-lookup"><span data-stu-id="5c09e-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="5c09e-131">Este atributo se comparte con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="5c09e-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c09e-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5c09e-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="5c09e-p105">Este es el identificador de grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5c09e-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c09e-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5c09e-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="5c09e-136">Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="5c09e-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="5c09e-137">Clases de Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="5c09e-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="5c09e-138">En la tabla siguiente se describen las clases de Active Directory que se modifican en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c09e-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="5c09e-139">Clases modificadas por Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c09e-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c09e-140">Class</span><span class="sxs-lookup"><span data-stu-id="5c09e-140">Class</span></span></th>
<th><span data-ttu-id="5c09e-141">Cambio</span><span class="sxs-lookup"><span data-stu-id="5c09e-141">Change</span></span></th>
<th><span data-ttu-id="5c09e-142">Clase o atributo</span><span class="sxs-lookup"><span data-stu-id="5c09e-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c09e-143">Usuario</span><span class="sxs-lookup"><span data-stu-id="5c09e-143">User</span></span></p></td>
<td><p><span data-ttu-id="5c09e-144">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5c09e-144">add: mayContain</span></span></p>
<p><span data-ttu-id="5c09e-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5c09e-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5c09e-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5c09e-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5c09e-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5c09e-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c09e-148">Contacto</span><span class="sxs-lookup"><span data-stu-id="5c09e-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="5c09e-149">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5c09e-149">add: mayContain</span></span></p>
<p><span data-ttu-id="5c09e-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5c09e-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5c09e-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5c09e-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5c09e-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5c09e-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c09e-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="5c09e-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="5c09e-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5c09e-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5c09e-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5c09e-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c09e-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="5c09e-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="5c09e-157">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="5c09e-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5c09e-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5c09e-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

