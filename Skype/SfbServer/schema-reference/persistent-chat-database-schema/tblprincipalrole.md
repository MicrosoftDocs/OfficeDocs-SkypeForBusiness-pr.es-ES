---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: la tabla PrincipalRole contiene roles explícitos asignados a nodos.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890772"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="24459-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="24459-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="24459-104">la tabla PrincipalRole contiene roles explícitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="24459-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="24459-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="24459-105">**Columns**</span></span>

|<span data-ttu-id="24459-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="24459-106">**Column**</span></span>|<span data-ttu-id="24459-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="24459-107">**Type**</span></span>|<span data-ttu-id="24459-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="24459-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="24459-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="24459-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="24459-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="24459-110">int, not null</span></span>  <br/> |<span data-ttu-id="24459-111">Identificador de nodo que se aplica la función.</span><span class="sxs-lookup"><span data-stu-id="24459-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="24459-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="24459-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="24459-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="24459-113">int, not null</span></span>  <br/> |<span data-ttu-id="24459-114">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="24459-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="24459-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="24459-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="24459-116">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="24459-116">int, not null</span></span>  <br/> |<span data-ttu-id="24459-117">Identificador de tipo de función (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="24459-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="24459-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="24459-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="24459-119">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="24459-119">int, not null</span></span>  <br/> |<span data-ttu-id="24459-120">Identificador de la entidad de seguridad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="24459-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="24459-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="24459-121">**Keys**</span></span>

|<span data-ttu-id="24459-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="24459-122">**Column**</span></span>|<span data-ttu-id="24459-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="24459-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="24459-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="24459-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="24459-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="24459-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="24459-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="24459-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="24459-127">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="24459-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="24459-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="24459-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="24459-129">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="24459-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="24459-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="24459-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="24459-131">Clave externa con búsqueda en la tabla principal.prinid.</span><span class="sxs-lookup"><span data-stu-id="24459-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

