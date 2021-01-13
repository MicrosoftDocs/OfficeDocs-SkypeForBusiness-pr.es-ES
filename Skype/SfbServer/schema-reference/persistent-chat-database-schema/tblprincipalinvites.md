---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: La tabla tblPrincipalInvites contiene invitaciones para todos los usuarios y para todos los nodos con la opción de invitación automática activada.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815860"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="453db-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="453db-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="453db-104">La tabla tblPrincipalInvites contiene invitaciones para todos los usuarios y para todos los nodos con la opción de invitación automática activada.</span><span class="sxs-lookup"><span data-stu-id="453db-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="453db-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="453db-105">**Columns**</span></span>

|<span data-ttu-id="453db-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="453db-106">**Column**</span></span>|<span data-ttu-id="453db-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="453db-107">**Type**</span></span>|<span data-ttu-id="453db-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="453db-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="453db-109">prinID</span><span class="sxs-lookup"><span data-stu-id="453db-109">prinID</span></span>  <br/> |<span data-ttu-id="453db-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="453db-110">int, not null</span></span>  <br/> |<span data-ttu-id="453db-111">Id. de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="453db-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="453db-112">invID</span><span class="sxs-lookup"><span data-stu-id="453db-112">invID</span></span>  <br/> |<span data-ttu-id="453db-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="453db-113">int, not null</span></span>  <br/> |<span data-ttu-id="453db-114">Número secuencial único (por identificador de la entidad de seguridad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="453db-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="453db-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="453db-115">nodeID</span></span>  <br/> |<span data-ttu-id="453db-116">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="453db-116">int, not null</span></span>  <br/> |<span data-ttu-id="453db-117">Identificador de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="453db-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="453db-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="453db-118">createdOn</span></span>  <br/> |<span data-ttu-id="453db-119">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="453db-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="453db-120">Momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="453db-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="453db-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="453db-121">**Keys**</span></span>

|<span data-ttu-id="453db-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="453db-122">**Column**</span></span>|<span data-ttu-id="453db-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="453db-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="453db-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="453db-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="453db-125">prinID</span><span class="sxs-lookup"><span data-stu-id="453db-125">prinID</span></span>  <br/> |<span data-ttu-id="453db-126">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="453db-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="453db-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="453db-127">nodeID</span></span>  <br/> |<span data-ttu-id="453db-128">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="453db-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

