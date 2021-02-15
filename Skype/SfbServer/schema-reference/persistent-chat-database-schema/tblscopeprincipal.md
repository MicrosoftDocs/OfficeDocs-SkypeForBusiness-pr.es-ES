---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: La tabla tblScopePrincipal contiene ámbitos asignados a nodos.
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831520"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="936e5-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="936e5-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="936e5-104">La tabla tblScopePrincipal contiene ámbitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="936e5-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="936e5-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="936e5-105">**Columns**</span></span>

|<span data-ttu-id="936e5-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="936e5-106">**Column**</span></span>|<span data-ttu-id="936e5-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="936e5-107">**Type**</span></span>|<span data-ttu-id="936e5-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="936e5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="936e5-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="936e5-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="936e5-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="936e5-110">int, not null</span></span>  <br/> |<span data-ttu-id="936e5-111">Id. de nodo al que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="936e5-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="936e5-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="936e5-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="936e5-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="936e5-113">int, not null</span></span>  <br/> |<span data-ttu-id="936e5-114">Id. de entidad</span><span class="sxs-lookup"><span data-stu-id="936e5-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="936e5-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="936e5-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="936e5-116">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="936e5-116">bit, not null</span></span>  <br/> |<span data-ttu-id="936e5-117">True si el tipo de ámbito es Denegar; False si es Permitir.</span><span class="sxs-lookup"><span data-stu-id="936e5-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="936e5-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="936e5-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="936e5-119">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="936e5-119">int, not null</span></span>  <br/> |<span data-ttu-id="936e5-120">Id. de la entidad que actualizó esta entrada por última vez.</span><span class="sxs-lookup"><span data-stu-id="936e5-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="936e5-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="936e5-121">**Keys**</span></span>

|<span data-ttu-id="936e5-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="936e5-122">**Column**</span></span>|<span data-ttu-id="936e5-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="936e5-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="936e5-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="936e5-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="936e5-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="936e5-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="936e5-126">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="936e5-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="936e5-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="936e5-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="936e5-128">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="936e5-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

