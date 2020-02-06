---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene tipos de principales para categorizar lo que hay en la tabla tblPrincipal.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812938"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="b4c15-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b4c15-103">tblPrincipalType</span></span>
 
<span data-ttu-id="b4c15-104">tblPrincipalType contiene tipos de principales para categorizar lo que hay en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4c15-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="b4c15-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b4c15-105">**Columns**</span></span>

|<span data-ttu-id="b4c15-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b4c15-106">**Column**</span></span>|<span data-ttu-id="b4c15-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b4c15-107">**Type**</span></span>|<span data-ttu-id="b4c15-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b4c15-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4c15-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b4c15-109">ptypeID</span></span>  <br/> |<span data-ttu-id="b4c15-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b4c15-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b4c15-111">IDENTIFICADOR de tipo de entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="b4c15-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="b4c15-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b4c15-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="b4c15-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="b4c15-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b4c15-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="b4c15-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="b4c15-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b4c15-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="b4c15-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="b4c15-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b4c15-117">True si el tipo corresponde a las entidades de identidad que se usan para fines internos.</span><span class="sxs-lookup"><span data-stu-id="b4c15-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="b4c15-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b4c15-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="b4c15-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="b4c15-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b4c15-120">True si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4c15-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="b4c15-121">**Clave**</span><span class="sxs-lookup"><span data-stu-id="b4c15-121">**Key**</span></span>

|<span data-ttu-id="b4c15-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b4c15-122">**Column**</span></span>|<span data-ttu-id="b4c15-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b4c15-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4c15-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b4c15-124">ptypeID</span></span>  <br/> |<span data-ttu-id="b4c15-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b4c15-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b4c15-126">**Valores principales**</span><span class="sxs-lookup"><span data-stu-id="b4c15-126">**Principal Values**</span></span>

|<span data-ttu-id="b4c15-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="b4c15-127">**ID**</span></span>|<span data-ttu-id="b4c15-128">**Rol**</span><span class="sxs-lookup"><span data-stu-id="b4c15-128">**Role**</span></span>|<span data-ttu-id="b4c15-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b4c15-129">**Description**</span></span>|<span data-ttu-id="b4c15-130">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="b4c15-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4c15-131">1</span><span class="sxs-lookup"><span data-stu-id="b4c15-131">1</span></span>  <br/> |<span data-ttu-id="b4c15-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b4c15-132">Any</span></span>  <br/> |<span data-ttu-id="b4c15-133">Entidad de identidad genérica con un tipo no conocido.</span><span class="sxs-lookup"><span data-stu-id="b4c15-133">Generic principal with no known type.</span></span> <span data-ttu-id="b4c15-134">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4c15-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b4c15-135">1</span><span class="sxs-lookup"><span data-stu-id="b4c15-135">2</span></span>  <br/> |<span data-ttu-id="b4c15-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b4c15-136">AnyUser</span></span>  <br/> |<span data-ttu-id="b4c15-137">Identidad genérica del tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4c15-137">Generic principal of user type.</span></span> <span data-ttu-id="b4c15-138">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4c15-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="b4c15-139">Sí</span><span class="sxs-lookup"><span data-stu-id="b4c15-139">Yes</span></span>  <br/> |
|<span data-ttu-id="b4c15-140">3</span><span class="sxs-lookup"><span data-stu-id="b4c15-140">3</span></span>  <br/> |<span data-ttu-id="b4c15-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b4c15-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="b4c15-142">Principal genérico con semántica de grupo.</span><span class="sxs-lookup"><span data-stu-id="b4c15-142">Generic principal with group semantic.</span></span> <span data-ttu-id="b4c15-143">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="b4c15-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b4c15-144">4</span><span class="sxs-lookup"><span data-stu-id="b4c15-144">4</span></span>  <br/> |<span data-ttu-id="b4c15-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="b4c15-145">SystemUser</span></span>  <br/> |<span data-ttu-id="b4c15-146">Principal utilizado internamente por el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b4c15-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="b4c15-147">5</span><span class="sxs-lookup"><span data-stu-id="b4c15-147">5</span></span>  <br/> |<span data-ttu-id="b4c15-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="b4c15-148">User</span></span>  <br/> |<span data-ttu-id="b4c15-149">Usuario normal.</span><span class="sxs-lookup"><span data-stu-id="b4c15-149">Regular user.</span></span>  <br/> |<span data-ttu-id="b4c15-150">Sí</span><span class="sxs-lookup"><span data-stu-id="b4c15-150">Yes</span></span>  <br/> |
|<span data-ttu-id="b4c15-151">4,8</span><span class="sxs-lookup"><span data-stu-id="b4c15-151">8</span></span>  <br/> |<span data-ttu-id="b4c15-152">Clona</span><span class="sxs-lookup"><span data-stu-id="b4c15-152">DC</span></span>  <br/> |<span data-ttu-id="b4c15-153">Controlador de dominio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4c15-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="b4c15-154">99,999</span><span class="sxs-lookup"><span data-stu-id="b4c15-154">9</span></span>  <br/> |<span data-ttu-id="b4c15-155">Mesa</span><span class="sxs-lookup"><span data-stu-id="b4c15-155">Group</span></span>  <br/> |<span data-ttu-id="b4c15-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4c15-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="b4c15-157">base10</span><span class="sxs-lookup"><span data-stu-id="b4c15-157">10</span></span>  <br/> |<span data-ttu-id="b4c15-158">Carpetas</span><span class="sxs-lookup"><span data-stu-id="b4c15-158">Folder</span></span>  <br/> |<span data-ttu-id="b4c15-159">Contenedor de Active Directory o unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="b4c15-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="b4c15-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4c15-160">See also</span></span>

[<span data-ttu-id="b4c15-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b4c15-161">tblPrincipal</span></span>](tblprincipal.md)
