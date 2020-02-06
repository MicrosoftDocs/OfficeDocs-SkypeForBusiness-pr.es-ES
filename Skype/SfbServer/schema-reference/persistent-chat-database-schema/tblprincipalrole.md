---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene los roles explícitos asignados a los nodos.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813368"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="5f3d7-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="5f3d7-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="5f3d7-104">tblPrincipalRole contiene los roles explícitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="5f3d7-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5f3d7-105">**Columns**</span></span>

|<span data-ttu-id="5f3d7-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5f3d7-106">**Column**</span></span>|<span data-ttu-id="5f3d7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5f3d7-107">**Type**</span></span>|<span data-ttu-id="5f3d7-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5f3d7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f3d7-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5f3d7-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5f3d7-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f3d7-110">int, not null</span></span>  <br/> |<span data-ttu-id="5f3d7-111">IDENTIFICADOR de nodo al que se aplica el rol.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="5f3d7-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5f3d7-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5f3d7-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f3d7-113">int, not null</span></span>  <br/> |<span data-ttu-id="5f3d7-114">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5f3d7-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5f3d7-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5f3d7-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f3d7-116">int, not null</span></span>  <br/> |<span data-ttu-id="5f3d7-117">IDENTIFICADOR de tipo de rol (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="5f3d7-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="5f3d7-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5f3d7-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="5f3d7-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f3d7-119">int, not null</span></span>  <br/> |<span data-ttu-id="5f3d7-120">IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5f3d7-121">**Sus**</span><span class="sxs-lookup"><span data-stu-id="5f3d7-121">**Keys**</span></span>

|<span data-ttu-id="5f3d7-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5f3d7-122">**Column**</span></span>|<span data-ttu-id="5f3d7-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5f3d7-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f3d7-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="5f3d7-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="5f3d7-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5f3d7-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5f3d7-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5f3d7-127">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5f3d7-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5f3d7-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5f3d7-129">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="5f3d7-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5f3d7-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5f3d7-131">Clave externa con la búsqueda en la tabla tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="5f3d7-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

