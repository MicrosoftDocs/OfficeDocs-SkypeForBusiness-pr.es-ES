---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La tabla PrincipalRole contiene roles explícitos asignados a nodos.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831560"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="9891a-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="9891a-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="9891a-104">La tabla PrincipalRole contiene roles explícitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="9891a-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="9891a-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9891a-105">**Columns**</span></span>

|<span data-ttu-id="9891a-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9891a-106">**Column**</span></span>|<span data-ttu-id="9891a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9891a-107">**Type**</span></span>|<span data-ttu-id="9891a-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9891a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9891a-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="9891a-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="9891a-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="9891a-110">int, not null</span></span>  <br/> |<span data-ttu-id="9891a-111">Identificador de nodo al que se aplica el rol.</span><span class="sxs-lookup"><span data-stu-id="9891a-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="9891a-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="9891a-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="9891a-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="9891a-113">int, not null</span></span>  <br/> |<span data-ttu-id="9891a-114">Identificador de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="9891a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9891a-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="9891a-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="9891a-116">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="9891a-116">int, not null</span></span>  <br/> |<span data-ttu-id="9891a-117">Identificador de tipo de función (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="9891a-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="9891a-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="9891a-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="9891a-119">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="9891a-119">int, not null</span></span>  <br/> |<span data-ttu-id="9891a-120">Id. de la entidad que actualizó esta entrada por última vez.</span><span class="sxs-lookup"><span data-stu-id="9891a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="9891a-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="9891a-121">**Keys**</span></span>

|<span data-ttu-id="9891a-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9891a-122">**Column**</span></span>|<span data-ttu-id="9891a-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9891a-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="9891a-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9891a-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9891a-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="9891a-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="9891a-126">Clave externa con búsqueda en la tabla RoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="9891a-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="9891a-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="9891a-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="9891a-128">Clave externa con búsqueda en la tabla Node.nodeID.</span><span class="sxs-lookup"><span data-stu-id="9891a-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="9891a-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="9891a-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="9891a-130">Clave externa con búsqueda en la tabla Principal.prinID.</span><span class="sxs-lookup"><span data-stu-id="9891a-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

