---
title: tblPrincipalType
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
ms.openlocfilehash: d5c710e1301344c853ef39aeff3b57f62c630c95
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505128"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="480fa-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="480fa-103">tblPrincipalType</span></span>
 
<span data-ttu-id="480fa-104">tblPrincipalType contiene los tipos de entidad de seguridad para clasificar lo que aparece en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="480fa-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="480fa-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="480fa-105">**Columns**</span></span>

|<span data-ttu-id="480fa-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="480fa-106">**Column**</span></span>|<span data-ttu-id="480fa-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="480fa-107">**Type**</span></span>|<span data-ttu-id="480fa-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="480fa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="480fa-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="480fa-109">ptypeID</span></span>  <br/> |<span data-ttu-id="480fa-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="480fa-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="480fa-111">Identificador del tipo de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="480fa-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="480fa-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="480fa-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="480fa-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="480fa-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="480fa-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="480fa-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="480fa-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="480fa-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="480fa-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="480fa-116">bit, not null</span></span>  <br/> |<span data-ttu-id="480fa-117">Es True si el tipo corresponde a las entidades de seguridad que se usan para fines internos.</span><span class="sxs-lookup"><span data-stu-id="480fa-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="480fa-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="480fa-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="480fa-119">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="480fa-119">bit, not null</span></span>  <br/> |<span data-ttu-id="480fa-120">Es True si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="480fa-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="480fa-121">**Clave**</span><span class="sxs-lookup"><span data-stu-id="480fa-121">**Key**</span></span>

|<span data-ttu-id="480fa-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="480fa-122">**Column**</span></span>|<span data-ttu-id="480fa-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="480fa-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="480fa-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="480fa-124">ptypeID</span></span>  <br/> |<span data-ttu-id="480fa-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="480fa-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="480fa-126">**Valores de la entidad de seguridad**</span><span class="sxs-lookup"><span data-stu-id="480fa-126">**Principal Values**</span></span>

|<span data-ttu-id="480fa-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="480fa-127">**ID**</span></span>|<span data-ttu-id="480fa-128">**Rol**</span><span class="sxs-lookup"><span data-stu-id="480fa-128">**Role**</span></span>|<span data-ttu-id="480fa-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="480fa-129">**Description**</span></span>|<span data-ttu-id="480fa-130">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="480fa-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="480fa-131">1</span><span class="sxs-lookup"><span data-stu-id="480fa-131">1</span></span>  <br/> |<span data-ttu-id="480fa-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="480fa-132">Any</span></span>  <br/> |<span data-ttu-id="480fa-133">Entidad de seguridad genérico con ningún tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="480fa-133">Generic principal with no known type.</span></span> <span data-ttu-id="480fa-134">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="480fa-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="480fa-135">2</span><span class="sxs-lookup"><span data-stu-id="480fa-135">2</span></span>  <br/> |<span data-ttu-id="480fa-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="480fa-136">AnyUser</span></span>  <br/> |<span data-ttu-id="480fa-137">Entidad de seguridad genérico de tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="480fa-137">Generic principal of user type.</span></span> <span data-ttu-id="480fa-138">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="480fa-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="480fa-139">Sí</span><span class="sxs-lookup"><span data-stu-id="480fa-139">Yes</span></span>  <br/> |
|<span data-ttu-id="480fa-140">3</span><span class="sxs-lookup"><span data-stu-id="480fa-140">3</span></span>  <br/> |<span data-ttu-id="480fa-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="480fa-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="480fa-142">Entidad de seguridad genérico con semántica de grupo.</span><span class="sxs-lookup"><span data-stu-id="480fa-142">Generic principal with group semantic.</span></span> <span data-ttu-id="480fa-143">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="480fa-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="480fa-144">4</span><span class="sxs-lookup"><span data-stu-id="480fa-144">4</span></span>  <br/> |<span data-ttu-id="480fa-145">Usuario del sistema</span><span class="sxs-lookup"><span data-stu-id="480fa-145">SystemUser</span></span>  <br/> |<span data-ttu-id="480fa-146">Entidad de seguridad utilizada internamente por el servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="480fa-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="480fa-147">5</span><span class="sxs-lookup"><span data-stu-id="480fa-147">5</span></span>  <br/> |<span data-ttu-id="480fa-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="480fa-148">User</span></span>  <br/> |<span data-ttu-id="480fa-149">Usuario habitual.</span><span class="sxs-lookup"><span data-stu-id="480fa-149">Regular user.</span></span>  <br/> |<span data-ttu-id="480fa-150">Sí</span><span class="sxs-lookup"><span data-stu-id="480fa-150">Yes</span></span>  <br/> |
|<span data-ttu-id="480fa-151">8</span><span class="sxs-lookup"><span data-stu-id="480fa-151">8</span></span>  <br/> |<span data-ttu-id="480fa-152">CONTROLADOR DE DOMINIO</span><span class="sxs-lookup"><span data-stu-id="480fa-152">DC</span></span>  <br/> |<span data-ttu-id="480fa-153">Controlador de dominio de servicios de dominio de Active Directory activo.</span><span class="sxs-lookup"><span data-stu-id="480fa-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="480fa-154">9</span><span class="sxs-lookup"><span data-stu-id="480fa-154">9</span></span>  <br/> |<span data-ttu-id="480fa-155">Grupo</span><span class="sxs-lookup"><span data-stu-id="480fa-155">Group</span></span>  <br/> |<span data-ttu-id="480fa-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="480fa-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="480fa-157"> 10</span><span class="sxs-lookup"><span data-stu-id="480fa-157">10</span></span>  <br/> |<span data-ttu-id="480fa-158">Carpeta</span><span class="sxs-lookup"><span data-stu-id="480fa-158">Folder</span></span>  <br/> |<span data-ttu-id="480fa-159">Contenedor de Active Directory o la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="480fa-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="480fa-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="480fa-160">See also</span></span>

[<span data-ttu-id="480fa-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="480fa-161">tblPrincipal</span></span>](tblprincipal.md)