---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: la tabla tblScopePrincipal contiene ámbitos asignados a nodos.
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924930"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="7188a-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="7188a-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="7188a-104">la tabla tblScopePrincipal contiene ámbitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="7188a-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="7188a-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="7188a-105">**Columns**</span></span>

|<span data-ttu-id="7188a-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7188a-106">**Column**</span></span>|<span data-ttu-id="7188a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7188a-107">**Type**</span></span>|<span data-ttu-id="7188a-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7188a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7188a-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="7188a-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="7188a-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7188a-110">int, not null</span></span>  <br/> |<span data-ttu-id="7188a-111">Identificador de nodo que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="7188a-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="7188a-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="7188a-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="7188a-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7188a-113">int, not null</span></span>  <br/> |<span data-ttu-id="7188a-114">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7188a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="7188a-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="7188a-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="7188a-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7188a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="7188a-117">Es True si el tipo de ámbito es Denegar; False si es permitir.</span><span class="sxs-lookup"><span data-stu-id="7188a-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="7188a-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="7188a-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="7188a-119">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7188a-119">int, not null</span></span>  <br/> |<span data-ttu-id="7188a-120">Identificador de la entidad de seguridad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="7188a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="7188a-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="7188a-121">**Keys**</span></span>

|<span data-ttu-id="7188a-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7188a-122">**Column**</span></span>|<span data-ttu-id="7188a-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7188a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7188a-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="7188a-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="7188a-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="7188a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7188a-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="7188a-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="7188a-127">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="7188a-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="7188a-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="7188a-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="7188a-129">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="7188a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

