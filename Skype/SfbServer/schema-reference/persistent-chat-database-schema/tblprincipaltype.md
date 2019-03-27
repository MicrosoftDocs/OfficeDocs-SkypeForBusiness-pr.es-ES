---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal.
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887442"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="985c9-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="985c9-103">tblPrincipalType</span></span>
 
<span data-ttu-id="985c9-104">tblPrincipalType contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="985c9-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="985c9-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="985c9-105">**Columns**</span></span>

|<span data-ttu-id="985c9-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="985c9-106">**Column**</span></span>|<span data-ttu-id="985c9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="985c9-107">**Type**</span></span>|<span data-ttu-id="985c9-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="985c9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="985c9-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="985c9-109">ptypeID</span></span>  <br/> |<span data-ttu-id="985c9-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="985c9-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="985c9-111">Identificador del tipo de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="985c9-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="985c9-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="985c9-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="985c9-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="985c9-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="985c9-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="985c9-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="985c9-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="985c9-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="985c9-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="985c9-116">bit, not null</span></span>  <br/> |<span data-ttu-id="985c9-117">Es True si el tipo corresponde a las entidades de seguridad que se usan para fines internos.</span><span class="sxs-lookup"><span data-stu-id="985c9-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="985c9-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="985c9-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="985c9-119">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="985c9-119">bit, not null</span></span>  <br/> |<span data-ttu-id="985c9-120">Es True si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="985c9-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="985c9-121">**Clave**</span><span class="sxs-lookup"><span data-stu-id="985c9-121">**Key**</span></span>

|<span data-ttu-id="985c9-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="985c9-122">**Column**</span></span>|<span data-ttu-id="985c9-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="985c9-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="985c9-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="985c9-124">ptypeID</span></span>  <br/> |<span data-ttu-id="985c9-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="985c9-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="985c9-126">**Valores de la entidad de seguridad**</span><span class="sxs-lookup"><span data-stu-id="985c9-126">**Principal Values**</span></span>

|<span data-ttu-id="985c9-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="985c9-127">**ID**</span></span>|<span data-ttu-id="985c9-128">**Rol**</span><span class="sxs-lookup"><span data-stu-id="985c9-128">**Role**</span></span>|<span data-ttu-id="985c9-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="985c9-129">**Description**</span></span>|<span data-ttu-id="985c9-130">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="985c9-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="985c9-131">1</span><span class="sxs-lookup"><span data-stu-id="985c9-131">1</span></span>  <br/> |<span data-ttu-id="985c9-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="985c9-132">Any</span></span>  <br/> |<span data-ttu-id="985c9-133">Entidad de seguridad genérico con ningún tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="985c9-133">Generic principal with no known type.</span></span> <span data-ttu-id="985c9-134">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="985c9-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="985c9-135">2</span><span class="sxs-lookup"><span data-stu-id="985c9-135">2</span></span>  <br/> |<span data-ttu-id="985c9-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="985c9-136">AnyUser</span></span>  <br/> |<span data-ttu-id="985c9-137">Entidad de seguridad genérico de tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="985c9-137">Generic principal of user type.</span></span> <span data-ttu-id="985c9-138">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="985c9-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="985c9-139">Sí</span><span class="sxs-lookup"><span data-stu-id="985c9-139">Yes</span></span>  <br/> |
|<span data-ttu-id="985c9-140">3</span><span class="sxs-lookup"><span data-stu-id="985c9-140">3</span></span>  <br/> |<span data-ttu-id="985c9-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="985c9-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="985c9-142">Entidad de seguridad genérico con semántica de grupo.</span><span class="sxs-lookup"><span data-stu-id="985c9-142">Generic principal with group semantic.</span></span> <span data-ttu-id="985c9-143">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="985c9-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="985c9-144">4</span><span class="sxs-lookup"><span data-stu-id="985c9-144">4</span></span>  <br/> |<span data-ttu-id="985c9-145">Usuario del sistema</span><span class="sxs-lookup"><span data-stu-id="985c9-145">SystemUser</span></span>  <br/> |<span data-ttu-id="985c9-146">Entidad de seguridad utilizada internamente por el servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="985c9-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="985c9-147">5</span><span class="sxs-lookup"><span data-stu-id="985c9-147">5</span></span>  <br/> |<span data-ttu-id="985c9-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="985c9-148">User</span></span>  <br/> |<span data-ttu-id="985c9-149">Usuario habitual.</span><span class="sxs-lookup"><span data-stu-id="985c9-149">Regular user.</span></span>  <br/> |<span data-ttu-id="985c9-150">Sí</span><span class="sxs-lookup"><span data-stu-id="985c9-150">Yes</span></span>  <br/> |
|<span data-ttu-id="985c9-151">8</span><span class="sxs-lookup"><span data-stu-id="985c9-151">8</span></span>  <br/> |<span data-ttu-id="985c9-152">CONTROLADOR DE DOMINIO</span><span class="sxs-lookup"><span data-stu-id="985c9-152">DC</span></span>  <br/> |<span data-ttu-id="985c9-153">Controlador de dominio de servicios de dominio de Active Directory activo.</span><span class="sxs-lookup"><span data-stu-id="985c9-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="985c9-154">9</span><span class="sxs-lookup"><span data-stu-id="985c9-154">9</span></span>  <br/> |<span data-ttu-id="985c9-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="985c9-155">Group</span></span>  <br/> |<span data-ttu-id="985c9-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="985c9-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="985c9-157">10</span><span class="sxs-lookup"><span data-stu-id="985c9-157">10</span></span>  <br/> |<span data-ttu-id="985c9-158">Carpeta</span><span class="sxs-lookup"><span data-stu-id="985c9-158">Folder</span></span>  <br/> |<span data-ttu-id="985c9-159">Contenedor de Active Directory o la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="985c9-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="985c9-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="985c9-160">See also</span></span>

[<span data-ttu-id="985c9-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="985c9-161">tblPrincipal</span></span>](tblprincipal.md)
