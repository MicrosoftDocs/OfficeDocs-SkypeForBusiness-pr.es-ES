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
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene tipos de principales para categorizar lo que hay en la tabla tblPrincipal.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295247"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="9ce3e-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="9ce3e-103">tblPrincipalType</span></span>
 
<span data-ttu-id="9ce3e-104">tblPrincipalType contiene tipos de principales para categorizar lo que hay en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="9ce3e-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-105">**Columns**</span></span>

|<span data-ttu-id="9ce3e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-106">**Column**</span></span>|<span data-ttu-id="9ce3e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-107">**Type**</span></span>|<span data-ttu-id="9ce3e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9ce3e-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="9ce3e-109">ptypeID</span></span>  <br/> |<span data-ttu-id="9ce3e-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="9ce3e-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="9ce3e-111">IDENTIFICADOR de tipo de entidad de identidad.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="9ce3e-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="9ce3e-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="9ce3e-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="9ce3e-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="9ce3e-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="9ce3e-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="9ce3e-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="9ce3e-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9ce3e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9ce3e-117">True si el tipo corresponde a las entidades de identidad que se usan para fines internos.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="9ce3e-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="9ce3e-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="9ce3e-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9ce3e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="9ce3e-120">True si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="9ce3e-121">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-121">**Key**</span></span>

|<span data-ttu-id="9ce3e-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-122">**Column**</span></span>|<span data-ttu-id="9ce3e-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9ce3e-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="9ce3e-124">ptypeID</span></span>  <br/> |<span data-ttu-id="9ce3e-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="9ce3e-126">**Valores principales**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-126">**Principal Values**</span></span>

|<span data-ttu-id="9ce3e-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-127">**ID**</span></span>|<span data-ttu-id="9ce3e-128">**Rol**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-128">**Role**</span></span>|<span data-ttu-id="9ce3e-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-129">**Description**</span></span>|<span data-ttu-id="9ce3e-130">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="9ce3e-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ce3e-131">1</span><span class="sxs-lookup"><span data-stu-id="9ce3e-131">1</span></span>  <br/> |<span data-ttu-id="9ce3e-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="9ce3e-132">Any</span></span>  <br/> |<span data-ttu-id="9ce3e-133">Entidad de identidad genérica con un tipo no conocido.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-133">Generic principal with no known type.</span></span> <span data-ttu-id="9ce3e-134">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="9ce3e-135">2</span><span class="sxs-lookup"><span data-stu-id="9ce3e-135">2</span></span>  <br/> |<span data-ttu-id="9ce3e-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="9ce3e-136">AnyUser</span></span>  <br/> |<span data-ttu-id="9ce3e-137">Identidad genérica del tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-137">Generic principal of user type.</span></span> <span data-ttu-id="9ce3e-138">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="9ce3e-139">Sí</span><span class="sxs-lookup"><span data-stu-id="9ce3e-139">Yes</span></span>  <br/> |
|<span data-ttu-id="9ce3e-140">3</span><span class="sxs-lookup"><span data-stu-id="9ce3e-140">3</span></span>  <br/> |<span data-ttu-id="9ce3e-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="9ce3e-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="9ce3e-142">Principal genérico con semántica de grupo.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-142">Generic principal with group semantic.</span></span> <span data-ttu-id="9ce3e-143">No se usa en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="9ce3e-144">4</span><span class="sxs-lookup"><span data-stu-id="9ce3e-144">4</span></span>  <br/> |<span data-ttu-id="9ce3e-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="9ce3e-145">SystemUser</span></span>  <br/> |<span data-ttu-id="9ce3e-146">Principal utilizado internamente por el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="9ce3e-147">5</span><span class="sxs-lookup"><span data-stu-id="9ce3e-147">5</span></span>  <br/> |<span data-ttu-id="9ce3e-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="9ce3e-148">User</span></span>  <br/> |<span data-ttu-id="9ce3e-149">Usuario normal.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-149">Regular user.</span></span>  <br/> |<span data-ttu-id="9ce3e-150">Sí</span><span class="sxs-lookup"><span data-stu-id="9ce3e-150">Yes</span></span>  <br/> |
|<span data-ttu-id="9ce3e-151">4,8</span><span class="sxs-lookup"><span data-stu-id="9ce3e-151">8</span></span>  <br/> |<span data-ttu-id="9ce3e-152">Clona</span><span class="sxs-lookup"><span data-stu-id="9ce3e-152">DC</span></span>  <br/> |<span data-ttu-id="9ce3e-153">Controlador de dominio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="9ce3e-154">99,999</span><span class="sxs-lookup"><span data-stu-id="9ce3e-154">9</span></span>  <br/> |<span data-ttu-id="9ce3e-155">Mesa</span><span class="sxs-lookup"><span data-stu-id="9ce3e-155">Group</span></span>  <br/> |<span data-ttu-id="9ce3e-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="9ce3e-157">base10</span><span class="sxs-lookup"><span data-stu-id="9ce3e-157">10</span></span>  <br/> |<span data-ttu-id="9ce3e-158">Carpetas</span><span class="sxs-lookup"><span data-stu-id="9ce3e-158">Folder</span></span>  <br/> |<span data-ttu-id="9ce3e-159">Contenedor de Active Directory o unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="9ce3e-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="9ce3e-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ce3e-160">See also</span></span>

[<span data-ttu-id="9ce3e-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="9ce3e-161">tblPrincipal</span></span>](tblprincipal.md)
