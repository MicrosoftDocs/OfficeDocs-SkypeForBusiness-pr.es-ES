---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene funciones explícitas que se asigna a los nodos.
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a><span data-ttu-id="e42fe-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="e42fe-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="e42fe-104">tblPrincipalRole contiene funciones explícitas que se asigna a los nodos.</span><span class="sxs-lookup"><span data-stu-id="e42fe-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="e42fe-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e42fe-105">**Columns**</span></span>

|<span data-ttu-id="e42fe-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e42fe-106">**Column**</span></span>|<span data-ttu-id="e42fe-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e42fe-107">**Type**</span></span>|<span data-ttu-id="e42fe-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e42fe-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e42fe-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e42fe-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="e42fe-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="e42fe-110">int, not null</span></span>  <br/> |<span data-ttu-id="e42fe-111">Identificador de nodo al que se aplica la función.</span><span class="sxs-lookup"><span data-stu-id="e42fe-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="e42fe-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e42fe-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="e42fe-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="e42fe-113">int, not null</span></span>  <br/> |<span data-ttu-id="e42fe-114">Id. principal</span><span class="sxs-lookup"><span data-stu-id="e42fe-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e42fe-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e42fe-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="e42fe-116">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="e42fe-116">int, not null</span></span>  <br/> |<span data-ttu-id="e42fe-117">Identificador de tipo de papel (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="e42fe-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="e42fe-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e42fe-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="e42fe-119">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="e42fe-119">int, not null</span></span>  <br/> |<span data-ttu-id="e42fe-120">Identificador de la entidad de seguridad que se actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="e42fe-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="e42fe-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="e42fe-121">**Keys**</span></span>

|<span data-ttu-id="e42fe-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e42fe-122">**Column**</span></span>|<span data-ttu-id="e42fe-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e42fe-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e42fe-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="e42fe-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="e42fe-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="e42fe-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e42fe-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e42fe-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="e42fe-127">Clave externa con la búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="e42fe-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="e42fe-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e42fe-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="e42fe-129">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e42fe-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e42fe-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e42fe-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="e42fe-131">Clave externa con la búsqueda en la tabla tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="e42fe-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

