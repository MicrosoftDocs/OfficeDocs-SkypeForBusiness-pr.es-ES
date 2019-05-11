---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con invitación automática activada.
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924426"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="5baf5-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="5baf5-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="5baf5-104">tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con invitación automática activada.</span><span class="sxs-lookup"><span data-stu-id="5baf5-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="5baf5-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5baf5-105">**Columns**</span></span>

|<span data-ttu-id="5baf5-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5baf5-106">**Column**</span></span>|<span data-ttu-id="5baf5-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5baf5-107">**Type**</span></span>|<span data-ttu-id="5baf5-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5baf5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5baf5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5baf5-109">prinID</span></span>  <br/> |<span data-ttu-id="5baf5-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5baf5-110">int, not null</span></span>  <br/> |<span data-ttu-id="5baf5-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5baf5-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5baf5-112">invID</span><span class="sxs-lookup"><span data-stu-id="5baf5-112">invID</span></span>  <br/> |<span data-ttu-id="5baf5-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5baf5-113">int, not null</span></span>  <br/> |<span data-ttu-id="5baf5-114">Número secuencial único (por identificador de entidad de seguridad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="5baf5-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="5baf5-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="5baf5-115">nodeID</span></span>  <br/> |<span data-ttu-id="5baf5-116">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5baf5-116">int, not null</span></span>  <br/> |<span data-ttu-id="5baf5-117">Identificador de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="5baf5-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="5baf5-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="5baf5-118">createdOn</span></span>  <br/> |<span data-ttu-id="5baf5-119">DateTime, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5baf5-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="5baf5-120">Hora de creación.</span><span class="sxs-lookup"><span data-stu-id="5baf5-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="5baf5-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="5baf5-121">**Keys**</span></span>

|<span data-ttu-id="5baf5-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5baf5-122">**Column**</span></span>|<span data-ttu-id="5baf5-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5baf5-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5baf5-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="5baf5-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="5baf5-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5baf5-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5baf5-126">prinID</span><span class="sxs-lookup"><span data-stu-id="5baf5-126">prinID</span></span>  <br/> |<span data-ttu-id="5baf5-127">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="5baf5-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="5baf5-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="5baf5-128">nodeID</span></span>  <br/> |<span data-ttu-id="5baf5-129">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="5baf5-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

