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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814188"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="c0f36-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c0f36-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="c0f36-104">tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.</span><span class="sxs-lookup"><span data-stu-id="c0f36-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="c0f36-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="c0f36-105">**Columns**</span></span>

|<span data-ttu-id="c0f36-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c0f36-106">**Column**</span></span>|<span data-ttu-id="c0f36-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c0f36-107">**Type**</span></span>|<span data-ttu-id="c0f36-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c0f36-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0f36-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c0f36-109">prinID</span></span>  <br/> |<span data-ttu-id="c0f36-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="c0f36-110">int, not null</span></span>  <br/> |<span data-ttu-id="c0f36-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="c0f36-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c0f36-112">invID</span><span class="sxs-lookup"><span data-stu-id="c0f36-112">invID</span></span>  <br/> |<span data-ttu-id="c0f36-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="c0f36-113">int, not null</span></span>  <br/> |<span data-ttu-id="c0f36-114">Número secuencial único (por identificador de entidad de identidad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="c0f36-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="c0f36-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="c0f36-115">nodeID</span></span>  <br/> |<span data-ttu-id="c0f36-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="c0f36-116">int, not null</span></span>  <br/> |<span data-ttu-id="c0f36-117">IDENTIFICADOR de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="c0f36-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="c0f36-118">creado</span><span class="sxs-lookup"><span data-stu-id="c0f36-118">createdOn</span></span>  <br/> |<span data-ttu-id="c0f36-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="c0f36-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="c0f36-120">Momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="c0f36-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="c0f36-121">**Sus**</span><span class="sxs-lookup"><span data-stu-id="c0f36-121">**Keys**</span></span>

|<span data-ttu-id="c0f36-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c0f36-122">**Column**</span></span>|<span data-ttu-id="c0f36-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c0f36-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0f36-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="c0f36-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="c0f36-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="c0f36-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c0f36-126">prinID</span><span class="sxs-lookup"><span data-stu-id="c0f36-126">prinID</span></span>  <br/> |<span data-ttu-id="c0f36-127">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="c0f36-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="c0f36-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="c0f36-128">nodeID</span></span>  <br/> |<span data-ttu-id="c0f36-129">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="c0f36-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

