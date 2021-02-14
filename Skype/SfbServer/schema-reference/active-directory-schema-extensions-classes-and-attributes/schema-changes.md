---
title: Cambios de esquema en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implementar y operar Skype Empresarial Server, debe preparar los Servicios de dominio de Active Directory ampliando el esquema. Las extensiones de esquema agregan las clases y atributos necesarios para Skype Empresarial Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813580"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="d4443-104">Cambios de esquema en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d4443-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="d4443-105">Antes de implementar y operar Skype Empresarial Server, debe preparar los Servicios de dominio de Active Directory ampliando el esquema.</span><span class="sxs-lookup"><span data-stu-id="d4443-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="d4443-106">Las extensiones de esquema agregan las clases y atributos necesarios para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4443-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="d4443-107">Si va a actualizar de Lync Server 2013 a Skype Empresarial Server 2015, no se realizan cambios de esquema y, por lo tanto, este artículo no es aplicable.</span><span class="sxs-lookup"><span data-stu-id="d4443-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="d4443-108">Skype Empresarial Server requiere varias clases y atributos nuevos y modifica algunas clases y atributos existentes.</span><span class="sxs-lookup"><span data-stu-id="d4443-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="d4443-109">Además, mucha información de configuración para Skype Empresarial Server se almacena en el almacén de administración central en lugar de en AD DS como en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="d4443-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="d4443-110">La siguiente información se sigue almacenando en AD DS en Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="d4443-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="d4443-111">**Extensiones de esquema**:</span><span class="sxs-lookup"><span data-stu-id="d4443-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="d4443-112">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="d4443-112">User object extensions</span></span>
    
  - <span data-ttu-id="d4443-113">Extensiones para las clases para mantener la compatibilidad con versiones anteriores compatibles con versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4443-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="d4443-114">**Datos** (almacenados en el esquema extendido de Skype Empresarial Server y en clases de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="d4443-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="d4443-115">Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario</span><span class="sxs-lookup"><span data-stu-id="d4443-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="d4443-116">Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="d4443-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="d4443-117">Una referencia al almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="d4443-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="d4443-118">Cuenta de autenticación Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="d4443-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="d4443-119">En este tema se describen los cambios de esquema de Active Directory requeridos por Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4443-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="d4443-120">No se describen los cambios de esquema introducidos por versiones anteriores de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="d4443-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="d4443-121">Para obtener una lista de clases y sus descripciones, consulte Clases de esquema [y descripciones en Skype Empresarial Server.](schema-classes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="d4443-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="d4443-122">Para obtener una lista de atributos y sus descripciones, consulte Atributos de esquema [y descripciones en Skype Empresarial Server.](schema-attributes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="d4443-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="d4443-123">Para obtener una lista de clases con los atributos que pueden contener, consulte Atributos de [esquema por clase en Skype Empresarial Server.](schema-attributes-by-class.md)</span><span class="sxs-lookup"><span data-stu-id="d4443-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="d4443-124">El prefijo msRTCSIP identifica clases y atributos específicos de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4443-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="d4443-125">Nuevos atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4443-125">New Active Directory Attributes</span></span>

<span data-ttu-id="d4443-126">En la tabla siguiente se describen los atributos de Active Directory agregados por Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4443-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="d4443-127">**Atributos agregados por Skype Empresarial Server**</span><span class="sxs-lookup"><span data-stu-id="d4443-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="d4443-128">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="d4443-128">**Attribute**</span></span>|<span data-ttu-id="d4443-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d4443-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4443-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d4443-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="d4443-131">Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="d4443-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="d4443-132">Las directivas de retención conservan los elementos del buzón del usuario durante toda la retención.</span><span class="sxs-lookup"><span data-stu-id="d4443-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="d4443-133">Este atributo se comparte con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d4443-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="d4443-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d4443-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="d4443-p106">Este es el identificador de grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d4443-p106">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="d4443-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d4443-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="d4443-138">Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d4443-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="d4443-139">Clases de Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="d4443-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="d4443-140">En la tabla siguiente se describen las clases de Active Directory modificadas por Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4443-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="d4443-141">**Clases modificadas por Skype Empresarial Server**</span><span class="sxs-lookup"><span data-stu-id="d4443-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="d4443-142">**Clase**</span><span class="sxs-lookup"><span data-stu-id="d4443-142">**Class**</span></span>|<span data-ttu-id="d4443-143">**Cambio**</span><span class="sxs-lookup"><span data-stu-id="d4443-143">**Change**</span></span>|<span data-ttu-id="d4443-144">**Clase o atributo**</span><span class="sxs-lookup"><span data-stu-id="d4443-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4443-145">User</span><span class="sxs-lookup"><span data-stu-id="d4443-145">User</span></span>  <br/> |<span data-ttu-id="d4443-146">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="d4443-146">add: mayContain</span></span>  <br/> <span data-ttu-id="d4443-147">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="d4443-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="d4443-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d4443-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="d4443-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d4443-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="d4443-150">Contacto</span><span class="sxs-lookup"><span data-stu-id="d4443-150">Contact</span></span>  <br/> |<span data-ttu-id="d4443-151">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="d4443-151">add: mayContain</span></span>  <br/> <span data-ttu-id="d4443-152">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="d4443-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="d4443-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d4443-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="d4443-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d4443-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="d4443-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="d4443-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="d4443-156">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d4443-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="d4443-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d4443-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="d4443-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="d4443-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="d4443-159">agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="d4443-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="d4443-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d4443-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

