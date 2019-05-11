---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal.
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924461"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="6687f-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="6687f-103">tblPrincipalType</span></span>
 
<span data-ttu-id="6687f-104">tblPrincipalType contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6687f-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="6687f-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="6687f-105">**Columns**</span></span>

|<span data-ttu-id="6687f-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6687f-106">**Column**</span></span>|<span data-ttu-id="6687f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6687f-107">**Type**</span></span>|<span data-ttu-id="6687f-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6687f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6687f-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="6687f-109">ptypeID</span></span>  <br/> |<span data-ttu-id="6687f-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="6687f-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="6687f-111">Identificador del tipo de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6687f-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="6687f-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="6687f-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="6687f-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="6687f-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="6687f-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="6687f-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="6687f-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="6687f-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="6687f-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="6687f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6687f-117">Es True si el tipo corresponde a las entidades de seguridad que se usan para fines internos.</span><span class="sxs-lookup"><span data-stu-id="6687f-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="6687f-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="6687f-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="6687f-119">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="6687f-119">bit, not null</span></span>  <br/> |<span data-ttu-id="6687f-120">Es True si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="6687f-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="6687f-121">**Clave**</span><span class="sxs-lookup"><span data-stu-id="6687f-121">**Key**</span></span>

|<span data-ttu-id="6687f-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6687f-122">**Column**</span></span>|<span data-ttu-id="6687f-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6687f-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6687f-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="6687f-124">ptypeID</span></span>  <br/> |<span data-ttu-id="6687f-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="6687f-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="6687f-126">**Valores de la entidad de seguridad**</span><span class="sxs-lookup"><span data-stu-id="6687f-126">**Principal Values**</span></span>

|<span data-ttu-id="6687f-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="6687f-127">**ID**</span></span>|<span data-ttu-id="6687f-128">**Rol**</span><span class="sxs-lookup"><span data-stu-id="6687f-128">**Role**</span></span>|<span data-ttu-id="6687f-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6687f-129">**Description**</span></span>|<span data-ttu-id="6687f-130">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="6687f-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6687f-131">1</span><span class="sxs-lookup"><span data-stu-id="6687f-131">1</span></span>  <br/> |<span data-ttu-id="6687f-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="6687f-132">Any</span></span>  <br/> |<span data-ttu-id="6687f-133">Entidad de seguridad genérico con ningún tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="6687f-133">Generic principal with no known type.</span></span> <span data-ttu-id="6687f-134">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6687f-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="6687f-135">2</span><span class="sxs-lookup"><span data-stu-id="6687f-135">2</span></span>  <br/> |<span data-ttu-id="6687f-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="6687f-136">AnyUser</span></span>  <br/> |<span data-ttu-id="6687f-137">Entidad de seguridad genérico de tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="6687f-137">Generic principal of user type.</span></span> <span data-ttu-id="6687f-138">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6687f-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="6687f-139">Sí</span><span class="sxs-lookup"><span data-stu-id="6687f-139">Yes</span></span>  <br/> |
|<span data-ttu-id="6687f-140">3</span><span class="sxs-lookup"><span data-stu-id="6687f-140">3</span></span>  <br/> |<span data-ttu-id="6687f-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="6687f-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="6687f-142">Entidad de seguridad genérico con semántica de grupo.</span><span class="sxs-lookup"><span data-stu-id="6687f-142">Generic principal with group semantic.</span></span> <span data-ttu-id="6687f-143">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6687f-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="6687f-144">4</span><span class="sxs-lookup"><span data-stu-id="6687f-144">4</span></span>  <br/> |<span data-ttu-id="6687f-145">Usuario del sistema</span><span class="sxs-lookup"><span data-stu-id="6687f-145">SystemUser</span></span>  <br/> |<span data-ttu-id="6687f-146">Entidad de seguridad utilizada internamente por el servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6687f-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="6687f-147">5</span><span class="sxs-lookup"><span data-stu-id="6687f-147">5</span></span>  <br/> |<span data-ttu-id="6687f-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="6687f-148">User</span></span>  <br/> |<span data-ttu-id="6687f-149">Usuario habitual.</span><span class="sxs-lookup"><span data-stu-id="6687f-149">Regular user.</span></span>  <br/> |<span data-ttu-id="6687f-150">Sí</span><span class="sxs-lookup"><span data-stu-id="6687f-150">Yes</span></span>  <br/> |
|<span data-ttu-id="6687f-151">8</span><span class="sxs-lookup"><span data-stu-id="6687f-151">8</span></span>  <br/> |<span data-ttu-id="6687f-152">CONTROLADOR DE DOMINIO</span><span class="sxs-lookup"><span data-stu-id="6687f-152">DC</span></span>  <br/> |<span data-ttu-id="6687f-153">Controlador de dominio de servicios de dominio de Active Directory activo.</span><span class="sxs-lookup"><span data-stu-id="6687f-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="6687f-154">9</span><span class="sxs-lookup"><span data-stu-id="6687f-154">9</span></span>  <br/> |<span data-ttu-id="6687f-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="6687f-155">Group</span></span>  <br/> |<span data-ttu-id="6687f-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6687f-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="6687f-157">10</span><span class="sxs-lookup"><span data-stu-id="6687f-157">10</span></span>  <br/> |<span data-ttu-id="6687f-158">Carpeta</span><span class="sxs-lookup"><span data-stu-id="6687f-158">Folder</span></span>  <br/> |<span data-ttu-id="6687f-159">Contenedor de Active Directory o la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="6687f-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="6687f-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="6687f-160">See also</span></span>

[<span data-ttu-id="6687f-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="6687f-161">tblPrincipal</span></span>](tblprincipal.md)
