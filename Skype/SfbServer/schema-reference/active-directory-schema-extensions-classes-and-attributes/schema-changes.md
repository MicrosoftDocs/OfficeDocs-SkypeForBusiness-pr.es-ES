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
description: Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory mediante la extensión del esquema. Las extensiones de esquema agregan las clases y atributos requeridos por Skype para Business Server.
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="782ce-104">Cambios de esquema en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="782ce-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="782ce-105">Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory mediante la extensión del esquema.</span><span class="sxs-lookup"><span data-stu-id="782ce-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="782ce-106">Las extensiones de esquema agregan las clases y atributos requeridos por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="782ce-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span> 
  
<span data-ttu-id="782ce-107">Skype para Business Server requiere varias nuevas clases y atributos y modifica algunas clases existentes y los atributos.</span><span class="sxs-lookup"><span data-stu-id="782ce-107">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="782ce-108">Además, mucha información de configuración de Skype para Business Server se almacena en el almacén de Administración Central, en lugar de en AD DS como en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="782ce-108">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="782ce-109">La información siguiente todavía se almacena en AD DS en Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="782ce-109">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="782ce-110">**Extensiones de esquema**:</span><span class="sxs-lookup"><span data-stu-id="782ce-110">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="782ce-111">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="782ce-111">User object extensions</span></span>
    
  - <span data-ttu-id="782ce-112">Extensiones de clases para mantener la compatibilidad con versiones anteriores compatibles de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="782ce-112">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="782ce-113">**Datos** (almacenado en Skype para esquema extendido Business Server y en las clases de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="782ce-113">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="782ce-114">Usuario SIP Uniform Resource Identifier (URI) y otras configuraciones de usuario</span><span class="sxs-lookup"><span data-stu-id="782ce-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="782ce-115">Objetos Contact para aplicaciones como el grupo de respuesta y el operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="782ce-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="782ce-116">Un puntero al almacén de Administración Central</span><span class="sxs-lookup"><span data-stu-id="782ce-116">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="782ce-117">Cuenta de autenticación de Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="782ce-117">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="782ce-118">Este tema describe los cambios de esquema de Active Directory requeridos por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="782ce-118">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="782ce-119">Describe los cambios de esquema que se introdujeron en versiones anteriores de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="782ce-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="782ce-120">Para obtener una lista de las clases y sus descripciones, vea [clases de esquema y descripciones en Skype para Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="782ce-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="782ce-121">Para obtener una lista de atributos y sus descripciones, consulte [descripciones de Skype para Business Server y atributos de esquema](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="782ce-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="782ce-122">Para obtener una lista de clases con los atributos pueden contener, vea [atributos de esquema por clase en Skype para Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="782ce-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="782ce-123">El prefijo msRTCSIP identifica las clases y atributos específicos de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="782ce-123">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="782ce-124">Nuevos atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="782ce-124">New Active Directory Attributes</span></span>

<span data-ttu-id="782ce-125">La tabla siguiente describe los atributos de Active Directory que se agregan por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="782ce-125">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="782ce-126">**Atributos agregados por Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="782ce-126">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="782ce-127">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="782ce-127">**Attribute**</span></span>|<span data-ttu-id="782ce-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="782ce-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="782ce-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="782ce-129">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="782ce-130">Este atributo multivalor contiene identificadores para contener las directivas que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="782ce-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="782ce-131">Mantenga las políticas preservar elementos del buzón del usuario durante el tiempo que dure la suspensión.</span><span class="sxs-lookup"><span data-stu-id="782ce-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="782ce-132">Este atributo se comparte con Exchange de 2013.</span><span class="sxs-lookup"><span data-stu-id="782ce-132">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="782ce-133">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="782ce-133">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="782ce-134">Es el Id. de grupo de enrutamiento de SIP</span><span class="sxs-lookup"><span data-stu-id="782ce-134">This is the SIP routing group ID.</span></span> <span data-ttu-id="782ce-135">Los usuarios del mismo grupo se registran en el mismo servidor de Front-End.</span><span class="sxs-lookup"><span data-stu-id="782ce-135">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="782ce-136">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="782ce-136">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="782ce-137">Este atributo se utiliza para almacenar el servidor reflejado de SQL Server utilizado por el grupo de Front-End.</span><span class="sxs-lookup"><span data-stu-id="782ce-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="782ce-138">Clases de Active Directory modificado</span><span class="sxs-lookup"><span data-stu-id="782ce-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="782ce-139">La tabla siguiente describen las clases de Active Directory que se modifican por Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="782ce-139">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="782ce-140">**Clases modificadas por Skype para Business Server**</span><span class="sxs-lookup"><span data-stu-id="782ce-140">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="782ce-141">**Clase**</span><span class="sxs-lookup"><span data-stu-id="782ce-141">**Class**</span></span>|<span data-ttu-id="782ce-142">**Cambio**</span><span class="sxs-lookup"><span data-stu-id="782ce-142">**Change**</span></span>|<span data-ttu-id="782ce-143">**Clase o atributo**</span><span class="sxs-lookup"><span data-stu-id="782ce-143">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="782ce-144">Usuario</span><span class="sxs-lookup"><span data-stu-id="782ce-144">User</span></span>  <br/> |<span data-ttu-id="782ce-145">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="782ce-145">add: mayContain</span></span>  <br/> <span data-ttu-id="782ce-146">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="782ce-146">add: mayContain</span></span>  <br/> |<span data-ttu-id="782ce-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="782ce-147">ProxyAddresses</span></span>  <br/> <span data-ttu-id="782ce-148">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="782ce-148">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="782ce-149">Contacto</span><span class="sxs-lookup"><span data-stu-id="782ce-149">Contact</span></span>  <br/> |<span data-ttu-id="782ce-150">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="782ce-150">add: mayContain</span></span>  <br/> <span data-ttu-id="782ce-151">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="782ce-151">add: mayContain</span></span>  <br/> |<span data-ttu-id="782ce-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="782ce-152">ProxyAddresses</span></span>  <br/> <span data-ttu-id="782ce-153">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="782ce-153">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="782ce-154">Destinatario de correo</span><span class="sxs-lookup"><span data-stu-id="782ce-154">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="782ce-155">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="782ce-155">add: mayContain</span></span>  <br/> |<span data-ttu-id="782ce-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="782ce-156">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="782ce-157">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="782ce-157">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="782ce-158">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="782ce-158">add: mayContain</span></span>  <br/> |<span data-ttu-id="782ce-159">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="782ce-159">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

