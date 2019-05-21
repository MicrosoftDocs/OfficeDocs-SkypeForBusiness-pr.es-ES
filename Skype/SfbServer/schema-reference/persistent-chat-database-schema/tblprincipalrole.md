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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene los roles explícitos asignados a los nodos.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295240"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="00699-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="00699-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="00699-104">tblPrincipalRole contiene los roles explícitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="00699-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="00699-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="00699-105">**Columns**</span></span>

|<span data-ttu-id="00699-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="00699-106">**Column**</span></span>|<span data-ttu-id="00699-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="00699-107">**Type**</span></span>|<span data-ttu-id="00699-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="00699-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00699-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="00699-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="00699-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="00699-110">int, not null</span></span>  <br/> |<span data-ttu-id="00699-111">IDENTIFICADOR de nodo al que se aplica el rol.</span><span class="sxs-lookup"><span data-stu-id="00699-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="00699-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="00699-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="00699-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="00699-113">int, not null</span></span>  <br/> |<span data-ttu-id="00699-114">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="00699-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="00699-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="00699-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="00699-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="00699-116">int, not null</span></span>  <br/> |<span data-ttu-id="00699-117">IDENTIFICADOR de tipo de rol (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="00699-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="00699-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="00699-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="00699-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="00699-119">int, not null</span></span>  <br/> |<span data-ttu-id="00699-120">IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="00699-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="00699-121">**Sus**</span><span class="sxs-lookup"><span data-stu-id="00699-121">**Keys**</span></span>

|<span data-ttu-id="00699-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="00699-122">**Column**</span></span>|<span data-ttu-id="00699-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="00699-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00699-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="00699-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="00699-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="00699-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="00699-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="00699-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="00699-127">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="00699-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="00699-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="00699-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="00699-129">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="00699-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="00699-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="00699-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="00699-131">Clave externa con la búsqueda en la tabla tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="00699-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

