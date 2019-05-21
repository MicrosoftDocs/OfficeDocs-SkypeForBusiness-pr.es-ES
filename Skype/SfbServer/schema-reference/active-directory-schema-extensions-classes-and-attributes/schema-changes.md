---
title: Cambios de esquema en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implementar y trabajar con Skype empresarial Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema. Las extensiones de esquema agregan las clases y los atributos que necesita Skype empresarial Server.
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296661"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="336b7-104">Cambios de esquema en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="336b7-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="336b7-105">Antes de implementar y trabajar con Skype empresarial Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema.</span><span class="sxs-lookup"><span data-stu-id="336b7-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="336b7-106">Las extensiones de esquema agregan las clases y los atributos que necesita Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="336b7-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="336b7-107">Si está actualizando desde Lync Server 2013 a Skype empresarial Server 2015, no se realizarán cambios de esquema y, por lo tanto, no se aplicará este artículo.</span><span class="sxs-lookup"><span data-stu-id="336b7-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="336b7-108">Skype empresarial Server requiere varias clases y atributos nuevos y modifica algunas clases y atributos existentes.</span><span class="sxs-lookup"><span data-stu-id="336b7-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="336b7-109">Además, la información de configuración de Skype empresarial Server se almacena en el almacén de administración central, en lugar de en AD DS, como en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="336b7-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="336b7-110">La siguiente información se almacena aún en AD DS en Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="336b7-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="336b7-111">**Extensiones de esquema**:</span><span class="sxs-lookup"><span data-stu-id="336b7-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="336b7-112">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="336b7-112">User object extensions</span></span>
    
  - <span data-ttu-id="336b7-113">Extensiones para las clases para mantener la compatibilidad con versiones anteriores compatibles de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="336b7-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="336b7-114">**Datos** (se almacena en el esquema extendido de Skype empresarial Server y en las clases de esquema existentes):</span><span class="sxs-lookup"><span data-stu-id="336b7-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="336b7-115">Identificador uniforme de recursos (URI) SIP de usuario y otra configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="336b7-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="336b7-116">Objetos de contacto para aplicaciones como el operador de conferencia y el grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="336b7-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="336b7-117">Puntero al almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="336b7-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="336b7-118">Cuenta de autenticación Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="336b7-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="336b7-119">En este tema se describen los cambios de esquema de Active Directory que necesita Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="336b7-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="336b7-120">No se describen los cambios de esquema introducidos por versiones anteriores de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="336b7-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="336b7-121">Para obtener una lista de las clases y sus descripciones, vea [clases de esquema y descripciones de Skype empresarial Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="336b7-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="336b7-122">Para obtener una lista de atributos y sus descripciones, consulte [atributos y descripciones del esquema en Skype empresarial Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="336b7-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="336b7-123">Para obtener una lista de las clases con los atributos que pueden contener, consulte [atributos de esquema por clase en Skype empresarial Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="336b7-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="336b7-124">El prefijo msRTCSIP identifica clases y atributos específicos de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="336b7-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="336b7-125">Nuevos atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="336b7-125">New Active Directory Attributes</span></span>

<span data-ttu-id="336b7-126">En la siguiente tabla se describen los atributos de Active Directory que agrega Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="336b7-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="336b7-127">**Atributos agregados por Skype empresarial Server**</span><span class="sxs-lookup"><span data-stu-id="336b7-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="336b7-128">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="336b7-128">**Attribute**</span></span>|<span data-ttu-id="336b7-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="336b7-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="336b7-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="336b7-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="336b7-131">Este atributo de valor múltiple contiene los identificadores para las directivas de retención que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="336b7-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="336b7-132">Las directivas de retención mantienen los elementos del buzón de correo para el usuario durante el período de espera.</span><span class="sxs-lookup"><span data-stu-id="336b7-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="336b7-133">Este atributo se comparte con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="336b7-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="336b7-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="336b7-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="336b7-135">Este es el identificador de grupo de enrutamiento SIP.</span><span class="sxs-lookup"><span data-stu-id="336b7-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="336b7-136">Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="336b7-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="336b7-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="336b7-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="336b7-138">Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="336b7-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="336b7-139">Clases de Active Directory modificadas</span><span class="sxs-lookup"><span data-stu-id="336b7-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="336b7-140">En la siguiente tabla se describen las clases de Active Directory que modifica Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="336b7-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="336b7-141">**Clases modificadas por Skype empresarial Server**</span><span class="sxs-lookup"><span data-stu-id="336b7-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="336b7-142">**Las**</span><span class="sxs-lookup"><span data-stu-id="336b7-142">**Class**</span></span>|<span data-ttu-id="336b7-143">**Cambio**</span><span class="sxs-lookup"><span data-stu-id="336b7-143">**Change**</span></span>|<span data-ttu-id="336b7-144">**Clase o atributo**</span><span class="sxs-lookup"><span data-stu-id="336b7-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="336b7-145">Usuario</span><span class="sxs-lookup"><span data-stu-id="336b7-145">User</span></span>  <br/> |<span data-ttu-id="336b7-146">Agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="336b7-146">add: mayContain</span></span>  <br/> <span data-ttu-id="336b7-147">Agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="336b7-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="336b7-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="336b7-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="336b7-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="336b7-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="336b7-150">Con</span><span class="sxs-lookup"><span data-stu-id="336b7-150">Contact</span></span>  <br/> |<span data-ttu-id="336b7-151">Agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="336b7-151">add: mayContain</span></span>  <br/> <span data-ttu-id="336b7-152">Agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="336b7-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="336b7-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="336b7-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="336b7-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="336b7-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="336b7-155">Destinatario de correo</span><span class="sxs-lookup"><span data-stu-id="336b7-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="336b7-156">Agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="336b7-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="336b7-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="336b7-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="336b7-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="336b7-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="336b7-159">Agregar: mayContain</span><span class="sxs-lookup"><span data-stu-id="336b7-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="336b7-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="336b7-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

