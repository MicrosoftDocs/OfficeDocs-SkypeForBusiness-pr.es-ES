---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con invitación automática activada.
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876693"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="65da2-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="65da2-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="65da2-104">tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con invitación automática activada.</span><span class="sxs-lookup"><span data-stu-id="65da2-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="65da2-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="65da2-105">**Columns**</span></span>

|<span data-ttu-id="65da2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="65da2-106">**Column**</span></span>|<span data-ttu-id="65da2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="65da2-107">**Type**</span></span>|<span data-ttu-id="65da2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="65da2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="65da2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="65da2-109">prinID</span></span>  <br/> |<span data-ttu-id="65da2-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="65da2-110">int, not null</span></span>  <br/> |<span data-ttu-id="65da2-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="65da2-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="65da2-112">invID</span><span class="sxs-lookup"><span data-stu-id="65da2-112">invID</span></span>  <br/> |<span data-ttu-id="65da2-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="65da2-113">int, not null</span></span>  <br/> |<span data-ttu-id="65da2-114">Número secuencial único (por identificador de entidad de seguridad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="65da2-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="65da2-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="65da2-115">nodeID</span></span>  <br/> |<span data-ttu-id="65da2-116">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="65da2-116">int, not null</span></span>  <br/> |<span data-ttu-id="65da2-117">Identificador de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="65da2-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="65da2-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="65da2-118">createdOn</span></span>  <br/> |<span data-ttu-id="65da2-119">DateTime, no es nulo</span><span class="sxs-lookup"><span data-stu-id="65da2-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="65da2-120">Hora de creación.</span><span class="sxs-lookup"><span data-stu-id="65da2-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="65da2-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="65da2-121">**Keys**</span></span>

|<span data-ttu-id="65da2-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="65da2-122">**Column**</span></span>|<span data-ttu-id="65da2-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="65da2-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65da2-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="65da2-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="65da2-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="65da2-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="65da2-126">prinID</span><span class="sxs-lookup"><span data-stu-id="65da2-126">prinID</span></span>  <br/> |<span data-ttu-id="65da2-127">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="65da2-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="65da2-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="65da2-128">nodeID</span></span>  <br/> |<span data-ttu-id="65da2-129">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="65da2-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

