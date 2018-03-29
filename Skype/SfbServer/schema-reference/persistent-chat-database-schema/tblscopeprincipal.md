---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene ámbitos asignados a los nodos.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="bbd13-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="bbd13-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="bbd13-104">tblScopePrincipal contiene ámbitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="bbd13-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="bbd13-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="bbd13-105">**Columns**</span></span>

|<span data-ttu-id="bbd13-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="bbd13-106">**Column**</span></span>|<span data-ttu-id="bbd13-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bbd13-107">**Type**</span></span>|<span data-ttu-id="bbd13-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bbd13-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bbd13-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="bbd13-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="bbd13-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="bbd13-110">int, not null</span></span>  <br/> |<span data-ttu-id="bbd13-111">Identificador de nodo al que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="bbd13-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="bbd13-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="bbd13-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="bbd13-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="bbd13-113">int, not null</span></span>  <br/> |<span data-ttu-id="bbd13-114">Id. principal</span><span class="sxs-lookup"><span data-stu-id="bbd13-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="bbd13-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="bbd13-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="bbd13-116">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="bbd13-116">bit, not null</span></span>  <br/> |<span data-ttu-id="bbd13-117">True si el tipo de ámbito es Denegar; False si se permite.</span><span class="sxs-lookup"><span data-stu-id="bbd13-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="bbd13-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="bbd13-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="bbd13-119">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="bbd13-119">int, not null</span></span>  <br/> |<span data-ttu-id="bbd13-120">Identificador de la entidad de seguridad que se actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="bbd13-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="bbd13-121">**Claves**</span><span class="sxs-lookup"><span data-stu-id="bbd13-121">**Keys**</span></span>

|<span data-ttu-id="bbd13-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="bbd13-122">**Column**</span></span>|<span data-ttu-id="bbd13-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bbd13-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bbd13-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="bbd13-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="bbd13-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="bbd13-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bbd13-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="bbd13-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="bbd13-127">Clave externa con la búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="bbd13-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="bbd13-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="bbd13-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="bbd13-129">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="bbd13-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

