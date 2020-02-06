---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene ámbitos asignados a los nodos.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812448"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="a2ac0-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="a2ac0-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="a2ac0-104">tblScopePrincipal contiene ámbitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="a2ac0-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="a2ac0-105">**Columns**</span></span>

|<span data-ttu-id="a2ac0-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a2ac0-106">**Column**</span></span>|<span data-ttu-id="a2ac0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a2ac0-107">**Type**</span></span>|<span data-ttu-id="a2ac0-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a2ac0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2ac0-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a2ac0-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="a2ac0-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="a2ac0-110">int, not null</span></span>  <br/> |<span data-ttu-id="a2ac0-111">IDENTIFICADOR de nodo al que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="a2ac0-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a2ac0-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="a2ac0-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="a2ac0-113">int, not null</span></span>  <br/> |<span data-ttu-id="a2ac0-114">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a2ac0-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="a2ac0-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="a2ac0-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="a2ac0-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a2ac0-117">Verdadero si el tipo de ámbito es denegar; False si la opción permitir.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="a2ac0-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a2ac0-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="a2ac0-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="a2ac0-119">int, not null</span></span>  <br/> |<span data-ttu-id="a2ac0-120">IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="a2ac0-121">**Sus**</span><span class="sxs-lookup"><span data-stu-id="a2ac0-121">**Keys**</span></span>

|<span data-ttu-id="a2ac0-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a2ac0-122">**Column**</span></span>|<span data-ttu-id="a2ac0-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a2ac0-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2ac0-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="a2ac0-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="a2ac0-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a2ac0-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a2ac0-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="a2ac0-127">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="a2ac0-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a2ac0-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="a2ac0-129">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="a2ac0-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

