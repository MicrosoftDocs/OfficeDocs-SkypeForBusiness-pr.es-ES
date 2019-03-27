---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: la tabla tblScopePrincipal contiene ámbitos asignados a nodos.
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885627"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="643a9-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="643a9-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="643a9-104">la tabla tblScopePrincipal contiene ámbitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="643a9-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="643a9-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="643a9-105">**Columns**</span></span>

|<span data-ttu-id="643a9-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="643a9-106">**Column**</span></span>|<span data-ttu-id="643a9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="643a9-107">**Type**</span></span>|<span data-ttu-id="643a9-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="643a9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="643a9-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="643a9-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="643a9-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="643a9-110">int, not null</span></span>  <br/> |<span data-ttu-id="643a9-111">Identificador de nodo que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="643a9-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="643a9-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="643a9-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="643a9-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="643a9-113">int, not null</span></span>  <br/> |<span data-ttu-id="643a9-114">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="643a9-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="643a9-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="643a9-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="643a9-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="643a9-116">bit, not null</span></span>  <br/> |<span data-ttu-id="643a9-117">Es True si el tipo de ámbito es Denegar; False si es permitir.</span><span class="sxs-lookup"><span data-stu-id="643a9-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="643a9-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="643a9-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="643a9-119">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="643a9-119">int, not null</span></span>  <br/> |<span data-ttu-id="643a9-120">Identificador de la entidad de seguridad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="643a9-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="643a9-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="643a9-121">**Keys**</span></span>

|<span data-ttu-id="643a9-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="643a9-122">**Column**</span></span>|<span data-ttu-id="643a9-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="643a9-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="643a9-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="643a9-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="643a9-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="643a9-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="643a9-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="643a9-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="643a9-127">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="643a9-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="643a9-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="643a9-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="643a9-129">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="643a9-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

