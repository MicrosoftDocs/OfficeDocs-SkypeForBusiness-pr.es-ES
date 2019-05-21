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
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene ámbitos asignados a los nodos.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295198"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="15c71-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="15c71-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="15c71-104">tblScopePrincipal contiene ámbitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="15c71-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="15c71-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="15c71-105">**Columns**</span></span>

|<span data-ttu-id="15c71-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="15c71-106">**Column**</span></span>|<span data-ttu-id="15c71-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="15c71-107">**Type**</span></span>|<span data-ttu-id="15c71-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="15c71-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15c71-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="15c71-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="15c71-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="15c71-110">int, not null</span></span>  <br/> |<span data-ttu-id="15c71-111">IDENTIFICADOR de nodo al que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="15c71-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="15c71-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="15c71-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="15c71-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="15c71-113">int, not null</span></span>  <br/> |<span data-ttu-id="15c71-114">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="15c71-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="15c71-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="15c71-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="15c71-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="15c71-116">bit, not null</span></span>  <br/> |<span data-ttu-id="15c71-117">Verdadero si el tipo de ámbito es denegar; False si la opción permitir.</span><span class="sxs-lookup"><span data-stu-id="15c71-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="15c71-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="15c71-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="15c71-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="15c71-119">int, not null</span></span>  <br/> |<span data-ttu-id="15c71-120">IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="15c71-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="15c71-121">**Sus**</span><span class="sxs-lookup"><span data-stu-id="15c71-121">**Keys**</span></span>

|<span data-ttu-id="15c71-122">**Columna**</span><span class="sxs-lookup"><span data-stu-id="15c71-122">**Column**</span></span>|<span data-ttu-id="15c71-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="15c71-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="15c71-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="15c71-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="15c71-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="15c71-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="15c71-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="15c71-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="15c71-127">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="15c71-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="15c71-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="15c71-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="15c71-129">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="15c71-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

