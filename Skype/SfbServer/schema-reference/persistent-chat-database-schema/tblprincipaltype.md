---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831540"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="13c5d-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="13c5d-103">tblPrincipalType</span></span>
 
<span data-ttu-id="13c5d-104">tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="13c5d-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="13c5d-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="13c5d-105">**Columns**</span></span>

|<span data-ttu-id="13c5d-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="13c5d-106">**Column**</span></span>|<span data-ttu-id="13c5d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="13c5d-107">**Type**</span></span>|<span data-ttu-id="13c5d-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13c5d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13c5d-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="13c5d-109">ptypeID</span></span>  <br/> |<span data-ttu-id="13c5d-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="13c5d-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="13c5d-111">Id. del tipo de entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="13c5d-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="13c5d-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="13c5d-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="13c5d-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="13c5d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="13c5d-114">Descripción del tipo.</span><span class="sxs-lookup"><span data-stu-id="13c5d-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="13c5d-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="13c5d-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="13c5d-116">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="13c5d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="13c5d-117">Verdadero si el tipo corresponde a las entidades de seguridad utilizadas para fines internos.</span><span class="sxs-lookup"><span data-stu-id="13c5d-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="13c5d-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="13c5d-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="13c5d-119">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="13c5d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="13c5d-120">Verdadero si el tipo es un tipo de usuario.</span><span class="sxs-lookup"><span data-stu-id="13c5d-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="13c5d-121">**Clave**</span><span class="sxs-lookup"><span data-stu-id="13c5d-121">**Key**</span></span>

|<span data-ttu-id="13c5d-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="13c5d-122">**Column**</span></span>|<span data-ttu-id="13c5d-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13c5d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13c5d-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="13c5d-124">ptypeID</span></span>  <br/> |<span data-ttu-id="13c5d-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="13c5d-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="13c5d-126">**Valores de las entidades de seguridad**</span><span class="sxs-lookup"><span data-stu-id="13c5d-126">**Principal Values**</span></span>

|<span data-ttu-id="13c5d-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="13c5d-127">**ID**</span></span>|<span data-ttu-id="13c5d-128">**Rol**</span><span class="sxs-lookup"><span data-stu-id="13c5d-128">**Role**</span></span>|<span data-ttu-id="13c5d-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13c5d-129">**Description**</span></span>|<span data-ttu-id="13c5d-130">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="13c5d-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13c5d-131">1 </span><span class="sxs-lookup"><span data-stu-id="13c5d-131">1</span></span>  <br/> |<span data-ttu-id="13c5d-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="13c5d-132">Any</span></span>  <br/> |<span data-ttu-id="13c5d-p101">Entidad de seguridad genérica sin tipo conocido. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="13c5d-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="13c5d-135">2 </span><span class="sxs-lookup"><span data-stu-id="13c5d-135">2</span></span>  <br/> |<span data-ttu-id="13c5d-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="13c5d-136">AnyUser</span></span>  <br/> |<span data-ttu-id="13c5d-p102">Entidad de seguridad genérica de tipo de usuario. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="13c5d-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="13c5d-139">Sí</span><span class="sxs-lookup"><span data-stu-id="13c5d-139">Yes</span></span>  <br/> |
|<span data-ttu-id="13c5d-140">3 </span><span class="sxs-lookup"><span data-stu-id="13c5d-140">3</span></span>  <br/> |<span data-ttu-id="13c5d-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="13c5d-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="13c5d-p103">Entidad de seguridad genérica con semántica de grupo. No se utiliza en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="13c5d-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="13c5d-144">4 </span><span class="sxs-lookup"><span data-stu-id="13c5d-144">4</span></span>  <br/> |<span data-ttu-id="13c5d-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="13c5d-145">SystemUser</span></span>  <br/> |<span data-ttu-id="13c5d-146">Entidad de seguridad usada internamente por el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="13c5d-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="13c5d-147">5 </span><span class="sxs-lookup"><span data-stu-id="13c5d-147">5</span></span>  <br/> |<span data-ttu-id="13c5d-148">Usuario</span><span class="sxs-lookup"><span data-stu-id="13c5d-148">User</span></span>  <br/> |<span data-ttu-id="13c5d-149">Usuario habitual.</span><span class="sxs-lookup"><span data-stu-id="13c5d-149">Regular user.</span></span>  <br/> |<span data-ttu-id="13c5d-150">Sí</span><span class="sxs-lookup"><span data-stu-id="13c5d-150">Yes</span></span>  <br/> |
|<span data-ttu-id="13c5d-151">8 </span><span class="sxs-lookup"><span data-stu-id="13c5d-151">8</span></span>  <br/> |<span data-ttu-id="13c5d-152">DC</span><span class="sxs-lookup"><span data-stu-id="13c5d-152">DC</span></span>  <br/> |<span data-ttu-id="13c5d-153">Controlador de dominio de Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="13c5d-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="13c5d-154">9 </span><span class="sxs-lookup"><span data-stu-id="13c5d-154">9</span></span>  <br/> |<span data-ttu-id="13c5d-155">Group</span><span class="sxs-lookup"><span data-stu-id="13c5d-155">Group</span></span>  <br/> |<span data-ttu-id="13c5d-156">Grupo de seguridad de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="13c5d-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="13c5d-157">10 </span><span class="sxs-lookup"><span data-stu-id="13c5d-157">10</span></span>  <br/> |<span data-ttu-id="13c5d-158">Folder</span><span class="sxs-lookup"><span data-stu-id="13c5d-158">Folder</span></span>  <br/> |<span data-ttu-id="13c5d-159">Unidad organizativa o contenedor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="13c5d-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="13c5d-160">Ver también</span><span class="sxs-lookup"><span data-stu-id="13c5d-160">See also</span></span>

[<span data-ttu-id="13c5d-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="13c5d-161">tblPrincipal</span></span>](tblprincipal.md)
