---
title: Cambios de esquema en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema. Las extensiones del esquema agregan las clases y atributos que se necesitan por Skype para Business Server.
ms.openlocfilehash: 8594ff3a25c7af7ef8c57468a8900d3abbb7f790
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240920"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="6b0c6-104">Cambios de esquema en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6b0c6-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="6b0c6-105">Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="6b0c6-106">Las extensiones del esquema agregan las clases y atributos que se necesitan por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="6b0c6-107">Si va a actualizar desde Lync Server 2013 a Skype para Business Server 2015, no se realizan cambios de esquema y, por tanto, en este artículo no se aplica.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="6b0c6-108">Skype para Business Server requiere varias nuevas clases y atributos y modifica algunos atributos y clases existentes.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="6b0c6-109">Además, mucho información de configuración de Skype para Business Server se almacena en el almacén de Administración Central en lugar de hacerlo en AD DS como en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="6b0c6-110">La siguiente información aún se almacena en AD DS en Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="6b0c6-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="6b0c6-111">**Extensiones de esquema**:</span><span class="sxs-lookup"><span data-stu-id="6b0c6-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="6b0c6-112">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="6b0c6-112">User object extensions</span></span>
    
  - <span data-ttu-id="6b0c6-113">Extensiones para las clases mantener la compatibilidad con versiones anteriores con versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="6b0c6-114">**Datos** (almacenados en Skype para el esquema extendido de Business Server y en las clases de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="6b0c6-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="6b0c6-115">Usuario SIP Uniform Resource Identifier (URI) y otros parámetros de usuario</span><span class="sxs-lookup"><span data-stu-id="6b0c6-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="6b0c6-116">Objetos de contacto para aplicaciones como grupo de respuesta y operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="6b0c6-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="6b0c6-117">Un puntero al almacén de Administración Central</span><span class="sxs-lookup"><span data-stu-id="6b0c6-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="6b0c6-118">Cuenta de autenticación de Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="6b0c6-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="6b0c6-119">En este tema se describe los cambios de esquema de Active Directory requeridos por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="6b0c6-120">No se describen los cambios de esquema que se introdujeron en versiones anteriores de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="6b0c6-121">Para obtener una lista de las clases y sus descripciones, vea [las clases de esquema y descripciones de Skype para Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="6b0c6-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="6b0c6-122">Para obtener una lista de atributos y sus descripciones, vea [atributos de esquema y descripciones de Skype para Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="6b0c6-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="6b0c6-123">Para obtener una lista de las clases con los atributos puede contener, vea [atributos de esquema por clase en Skype para Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="6b0c6-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="6b0c6-124">El prefijo msRTCSIP identifica clases y atributos que son específicos de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="6b0c6-125">Nuevos atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="6b0c6-125">New Active Directory Attributes</span></span>

<span data-ttu-id="6b0c6-126">En la siguiente tabla se describe los atributos de Active Directory que se agregan por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="6b0c6-127">**Atributos agregados por Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="6b0c6-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="6b0c6-128">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="6b0c6-128">**Attribute**</span></span>|<span data-ttu-id="6b0c6-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6b0c6-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b0c6-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6b0c6-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="6b0c6-131">Este atributo de varios valor contiene los identificadores para contener las directivas que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="6b0c6-132">Mantenga las directivas de conservar los elementos del buzón para el usuario para la duración de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="6b0c6-133">Este atributo se comparte con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="6b0c6-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6b0c6-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="6b0c6-135">Este es el SIP enrutamiento de identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="6b0c6-136">Los usuarios en el mismo grupo registrará en el mismo servidor de Front-End.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="6b0c6-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6b0c6-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="6b0c6-138">Este atributo se usa para almacenar el reflejado SQL Server usado por el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="6b0c6-139">Clases de Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="6b0c6-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="6b0c6-140">En la siguiente tabla se describe las clases de Active Directory que se modifican por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b0c6-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="6b0c6-141">**Clases modificadas por Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="6b0c6-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="6b0c6-142">**Clase**</span><span class="sxs-lookup"><span data-stu-id="6b0c6-142">**Class**</span></span>|<span data-ttu-id="6b0c6-143">**CAMBIAR**</span><span class="sxs-lookup"><span data-stu-id="6b0c6-143">**Change**</span></span>|<span data-ttu-id="6b0c6-144">**Clase o atributo**</span><span class="sxs-lookup"><span data-stu-id="6b0c6-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b0c6-145">Usuario</span><span class="sxs-lookup"><span data-stu-id="6b0c6-145">User</span></span>  <br/> |<span data-ttu-id="6b0c6-146">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="6b0c6-146">add: mayContain</span></span>  <br/> <span data-ttu-id="6b0c6-147">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="6b0c6-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="6b0c6-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6b0c6-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="6b0c6-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6b0c6-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="6b0c6-150">Contacto</span><span class="sxs-lookup"><span data-stu-id="6b0c6-150">Contact</span></span>  <br/> |<span data-ttu-id="6b0c6-151">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="6b0c6-151">add: mayContain</span></span>  <br/> <span data-ttu-id="6b0c6-152">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="6b0c6-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="6b0c6-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6b0c6-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="6b0c6-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6b0c6-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="6b0c6-155">Destinatario de correo</span><span class="sxs-lookup"><span data-stu-id="6b0c6-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="6b0c6-156">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="6b0c6-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="6b0c6-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6b0c6-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="6b0c6-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="6b0c6-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="6b0c6-159">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="6b0c6-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="6b0c6-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6b0c6-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

