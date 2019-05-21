---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295296"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="d9ce5-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d9ce5-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="d9ce5-104">tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.</span><span class="sxs-lookup"><span data-stu-id="d9ce5-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="d9ce5-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d9ce5-105">**Columns**</span></span>

|<span data-ttu-id="d9ce5-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d9ce5-106">**Column**</span></span>|<span data-ttu-id="d9ce5-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d9ce5-107">**Type**</span></span>|<span data-ttu-id="d9ce5-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d9ce5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d9ce5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d9ce5-109">prinID</span></span>  <br/> |<span data-ttu-id="d9ce5-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="d9ce5-110">int, not null</span></span>  <br/> |<span data-ttu-id="d9ce5-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="d9ce5-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d9ce5-112">invID</span><span class="sxs-lookup"><span data-stu-id="d9ce5-112">invID</span></span>  <br/> |<span data-ttu-id="d9ce5-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="d9ce5-113">int, not null</span></span>  <br/> |<span data-ttu-id="d9ce5-114">Número secuencial único (por identificador de entidad de identidad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="d9ce5-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="d9ce5-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="d9ce5-115">nodeID</span></span>  <br/> |<span data-ttu-id="d9ce5-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="d9ce5-116">int, not null</span></span>  <br/> |<span data-ttu-id="d9ce5-117">IDENTIFICADOR de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="d9ce5-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="d9ce5-118">creado</span><span class="sxs-lookup"><span data-stu-id="d9ce5-118">createdOn</span></span>  <br/> |<span data-ttu-id="d9ce5-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="d9ce5-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="d9ce5-120">Momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="d9ce5-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="d9ce5-121">**Sus**</span><span class="sxs-lookup"><span data-stu-id="d9ce5-121">**Keys**</span></span>

|<span data-ttu-id="d9ce5-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d9ce5-122">**Column**</span></span>|<span data-ttu-id="d9ce5-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d9ce5-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9ce5-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="d9ce5-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="d9ce5-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="d9ce5-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d9ce5-126">prinID</span><span class="sxs-lookup"><span data-stu-id="d9ce5-126">prinID</span></span>  <br/> |<span data-ttu-id="d9ce5-127">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="d9ce5-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="d9ce5-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="d9ce5-128">nodeID</span></span>  <br/> |<span data-ttu-id="d9ce5-129">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="d9ce5-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

