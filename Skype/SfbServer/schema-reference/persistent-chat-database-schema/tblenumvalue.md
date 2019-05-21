---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla de nodos.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295429"
---
# <a name="tblenumvalue"></a><span data-ttu-id="2febc-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="2febc-103">tblEnumValue</span></span>
 
<span data-ttu-id="2febc-104">tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla de nodos.</span><span class="sxs-lookup"><span data-stu-id="2febc-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="2febc-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="2febc-105">**Columns**</span></span>

|<span data-ttu-id="2febc-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2febc-106">**Column**</span></span>|<span data-ttu-id="2febc-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2febc-107">**Type**</span></span>|<span data-ttu-id="2febc-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2febc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2febc-109">valueID</span><span class="sxs-lookup"><span data-stu-id="2febc-109">valueID</span></span>  <br/> |<span data-ttu-id="2febc-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="2febc-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="2febc-111">IDENTIFICADOR del valor.</span><span class="sxs-lookup"><span data-stu-id="2febc-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="2febc-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="2febc-112">attributeID</span></span>  <br/> |<span data-ttu-id="2febc-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="2febc-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="2febc-114">IDENTIFICADOR del atributo.</span><span class="sxs-lookup"><span data-stu-id="2febc-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="2febc-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="2febc-115">attributeValue</span></span>  <br/> |<span data-ttu-id="2febc-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="2febc-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2febc-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="2febc-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="2febc-118">**Sus**</span><span class="sxs-lookup"><span data-stu-id="2febc-118">**Keys**</span></span>

|<span data-ttu-id="2febc-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2febc-119">**Column**</span></span>|<span data-ttu-id="2febc-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2febc-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2febc-121">valueID</span><span class="sxs-lookup"><span data-stu-id="2febc-121">valueID</span></span>  <br/> |<span data-ttu-id="2febc-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="2febc-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2febc-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="2febc-123">attributeID</span></span>  <br/> |<span data-ttu-id="2febc-124">Clave externa con la búsqueda en la tabla tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="2febc-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="2febc-125">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="2febc-125">**Table Values**</span></span>

|<span data-ttu-id="2febc-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="2febc-126">**valueID**</span></span>|<span data-ttu-id="2febc-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="2febc-127">**attributeID**</span></span>|<span data-ttu-id="2febc-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="2febc-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2febc-129">2</span><span class="sxs-lookup"><span data-stu-id="2febc-129">2</span></span>  <br/> |<span data-ttu-id="2febc-130">1</span><span class="sxs-lookup"><span data-stu-id="2febc-130">1</span></span>  <br/> |<span data-ttu-id="2febc-131">private</span><span class="sxs-lookup"><span data-stu-id="2febc-131">private</span></span>  <br/> |
|<span data-ttu-id="2febc-132">3</span><span class="sxs-lookup"><span data-stu-id="2febc-132">3</span></span>  <br/> |<span data-ttu-id="2febc-133">1</span><span class="sxs-lookup"><span data-stu-id="2febc-133">1</span></span>  <br/> |<span data-ttu-id="2febc-134">ID</span><span class="sxs-lookup"><span data-stu-id="2febc-134">scope</span></span>  <br/> |
|<span data-ttu-id="2febc-135">4</span><span class="sxs-lookup"><span data-stu-id="2febc-135">4</span></span>  <br/> |<span data-ttu-id="2febc-136">2</span><span class="sxs-lookup"><span data-stu-id="2febc-136">2</span></span>  <br/> |<span data-ttu-id="2febc-137">normal</span><span class="sxs-lookup"><span data-stu-id="2febc-137">normal</span></span>  <br/> |
|<span data-ttu-id="2febc-138">5</span><span class="sxs-lookup"><span data-stu-id="2febc-138">5</span></span>  <br/> |<span data-ttu-id="2febc-139">2</span><span class="sxs-lookup"><span data-stu-id="2febc-139">2</span></span>  <br/> |<span data-ttu-id="2febc-140">Audi</span><span class="sxs-lookup"><span data-stu-id="2febc-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="2febc-141">6</span><span class="sxs-lookup"><span data-stu-id="2febc-141">6</span></span>  <br/> |<span data-ttu-id="2febc-142">1</span><span class="sxs-lookup"><span data-stu-id="2febc-142">1</span></span>  <br/> |<span data-ttu-id="2febc-143">volver</span><span class="sxs-lookup"><span data-stu-id="2febc-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2febc-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="2febc-144">See also</span></span>

[<span data-ttu-id="2febc-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="2febc-145">tblNode</span></span>](tblnode.md)
