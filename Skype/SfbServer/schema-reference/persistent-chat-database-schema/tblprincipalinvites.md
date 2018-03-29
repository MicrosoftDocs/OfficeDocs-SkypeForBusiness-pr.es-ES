---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene las invitaciones para todos los usuarios configurados para todos los nodos con auto invite en.
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="b40cb-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="b40cb-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="b40cb-104">tblPrincipalInvites contiene las invitaciones para todos los usuarios configurados para todos los nodos con auto invite en.</span><span class="sxs-lookup"><span data-stu-id="b40cb-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="b40cb-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b40cb-105">**Columns**</span></span>

|<span data-ttu-id="b40cb-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b40cb-106">**Column**</span></span>|<span data-ttu-id="b40cb-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b40cb-107">**Type**</span></span>|<span data-ttu-id="b40cb-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b40cb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b40cb-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b40cb-109">prinID</span></span>  <br/> |<span data-ttu-id="b40cb-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="b40cb-110">int, not null</span></span>  <br/> |<span data-ttu-id="b40cb-111">Id. principal</span><span class="sxs-lookup"><span data-stu-id="b40cb-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b40cb-112">invID</span><span class="sxs-lookup"><span data-stu-id="b40cb-112">invID</span></span>  <br/> |<span data-ttu-id="b40cb-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="b40cb-113">int, not null</span></span>  <br/> |<span data-ttu-id="b40cb-114">Número secuencial único (por ID. principal) generado a partir de la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="b40cb-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="b40cb-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="b40cb-115">nodeID</span></span>  <br/> |<span data-ttu-id="b40cb-116">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="b40cb-116">int, not null</span></span>  <br/> |<span data-ttu-id="b40cb-117">Identificador de nodo (sólo sala de charlas).</span><span class="sxs-lookup"><span data-stu-id="b40cb-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="b40cb-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="b40cb-118">createdOn</span></span>  <br/> |<span data-ttu-id="b40cb-119">fecha y hora, no nulo</span><span class="sxs-lookup"><span data-stu-id="b40cb-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="b40cb-120">Hora de creación.</span><span class="sxs-lookup"><span data-stu-id="b40cb-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="b40cb-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="b40cb-121">**Keys**</span></span>

|<span data-ttu-id="b40cb-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b40cb-122">**Column**</span></span>|<span data-ttu-id="b40cb-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b40cb-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b40cb-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="b40cb-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="b40cb-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b40cb-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b40cb-126">prinID</span><span class="sxs-lookup"><span data-stu-id="b40cb-126">prinID</span></span>  <br/> |<span data-ttu-id="b40cb-127">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b40cb-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="b40cb-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="b40cb-128">nodeID</span></span>  <br/> |<span data-ttu-id="b40cb-129">Clave externa con la búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="b40cb-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

