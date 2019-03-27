---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881172"
---
# <a name="tblenumvalue"></a><span data-ttu-id="071f2-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="071f2-103">tblEnumValue</span></span>
 
<span data-ttu-id="071f2-104">tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="071f2-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="071f2-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="071f2-105">**Columns**</span></span>

|<span data-ttu-id="071f2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="071f2-106">**Column**</span></span>|<span data-ttu-id="071f2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="071f2-107">**Type**</span></span>|<span data-ttu-id="071f2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="071f2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="071f2-109">valueID</span><span class="sxs-lookup"><span data-stu-id="071f2-109">valueID</span></span>  <br/> |<span data-ttu-id="071f2-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="071f2-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="071f2-111">Identificador del valor.</span><span class="sxs-lookup"><span data-stu-id="071f2-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="071f2-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="071f2-112">attributeID</span></span>  <br/> |<span data-ttu-id="071f2-113">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="071f2-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="071f2-114">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="071f2-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="071f2-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="071f2-115">attributeValue</span></span>  <br/> |<span data-ttu-id="071f2-116">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="071f2-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="071f2-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="071f2-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="071f2-118">**Claves**</span><span class="sxs-lookup"><span data-stu-id="071f2-118">**Keys**</span></span>

|<span data-ttu-id="071f2-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="071f2-119">**Column**</span></span>|<span data-ttu-id="071f2-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="071f2-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="071f2-121">valueID</span><span class="sxs-lookup"><span data-stu-id="071f2-121">valueID</span></span>  <br/> |<span data-ttu-id="071f2-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="071f2-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="071f2-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="071f2-123">attributeID</span></span>  <br/> |<span data-ttu-id="071f2-124">Clave externa con búsqueda en la tabla tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="071f2-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="071f2-125">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="071f2-125">**Table Values**</span></span>

|<span data-ttu-id="071f2-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="071f2-126">**valueID**</span></span>|<span data-ttu-id="071f2-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="071f2-127">**attributeID**</span></span>|<span data-ttu-id="071f2-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="071f2-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="071f2-129">2</span><span class="sxs-lookup"><span data-stu-id="071f2-129">2</span></span>  <br/> |<span data-ttu-id="071f2-130">1</span><span class="sxs-lookup"><span data-stu-id="071f2-130">1</span></span>  <br/> |<span data-ttu-id="071f2-131">private</span><span class="sxs-lookup"><span data-stu-id="071f2-131">private</span></span>  <br/> |
|<span data-ttu-id="071f2-132">3</span><span class="sxs-lookup"><span data-stu-id="071f2-132">3</span></span>  <br/> |<span data-ttu-id="071f2-133">1</span><span class="sxs-lookup"><span data-stu-id="071f2-133">1</span></span>  <br/> |<span data-ttu-id="071f2-134">ámbito</span><span class="sxs-lookup"><span data-stu-id="071f2-134">scope</span></span>  <br/> |
|<span data-ttu-id="071f2-135">4</span><span class="sxs-lookup"><span data-stu-id="071f2-135">4</span></span>  <br/> |<span data-ttu-id="071f2-136">2</span><span class="sxs-lookup"><span data-stu-id="071f2-136">2</span></span>  <br/> |<span data-ttu-id="071f2-137">normal</span><span class="sxs-lookup"><span data-stu-id="071f2-137">normal</span></span>  <br/> |
|<span data-ttu-id="071f2-138">5</span><span class="sxs-lookup"><span data-stu-id="071f2-138">5</span></span>  <br/> |<span data-ttu-id="071f2-139">2</span><span class="sxs-lookup"><span data-stu-id="071f2-139">2</span></span>  <br/> |<span data-ttu-id="071f2-140">auditorio</span><span class="sxs-lookup"><span data-stu-id="071f2-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="071f2-141">6</span><span class="sxs-lookup"><span data-stu-id="071f2-141">6</span></span>  <br/> |<span data-ttu-id="071f2-142">1</span><span class="sxs-lookup"><span data-stu-id="071f2-142">1</span></span>  <br/> |<span data-ttu-id="071f2-143">Abra</span><span class="sxs-lookup"><span data-stu-id="071f2-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="071f2-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="071f2-144">See also</span></span>

[<span data-ttu-id="071f2-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="071f2-145">tblNode</span></span>](tblnode.md)
