---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929871"
---
# <a name="tblenumvalue"></a><span data-ttu-id="41b0c-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="41b0c-103">tblEnumValue</span></span>
 
<span data-ttu-id="41b0c-104">tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="41b0c-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="41b0c-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="41b0c-105">**Columns**</span></span>

|<span data-ttu-id="41b0c-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="41b0c-106">**Column**</span></span>|<span data-ttu-id="41b0c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41b0c-107">**Type**</span></span>|<span data-ttu-id="41b0c-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="41b0c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41b0c-109">valueID</span><span class="sxs-lookup"><span data-stu-id="41b0c-109">valueID</span></span>  <br/> |<span data-ttu-id="41b0c-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="41b0c-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="41b0c-111">Identificador del valor.</span><span class="sxs-lookup"><span data-stu-id="41b0c-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="41b0c-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="41b0c-112">attributeID</span></span>  <br/> |<span data-ttu-id="41b0c-113">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="41b0c-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="41b0c-114">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="41b0c-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="41b0c-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="41b0c-115">attributeValue</span></span>  <br/> |<span data-ttu-id="41b0c-116">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="41b0c-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="41b0c-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="41b0c-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="41b0c-118">**Claves**</span><span class="sxs-lookup"><span data-stu-id="41b0c-118">**Keys**</span></span>

|<span data-ttu-id="41b0c-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="41b0c-119">**Column**</span></span>|<span data-ttu-id="41b0c-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="41b0c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41b0c-121">valueID</span><span class="sxs-lookup"><span data-stu-id="41b0c-121">valueID</span></span>  <br/> |<span data-ttu-id="41b0c-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="41b0c-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="41b0c-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="41b0c-123">attributeID</span></span>  <br/> |<span data-ttu-id="41b0c-124">Clave externa con búsqueda en la tabla tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="41b0c-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="41b0c-125">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="41b0c-125">**Table Values**</span></span>

|<span data-ttu-id="41b0c-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="41b0c-126">**valueID**</span></span>|<span data-ttu-id="41b0c-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="41b0c-127">**attributeID**</span></span>|<span data-ttu-id="41b0c-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="41b0c-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41b0c-129">2</span><span class="sxs-lookup"><span data-stu-id="41b0c-129">2</span></span>  <br/> |<span data-ttu-id="41b0c-130">1</span><span class="sxs-lookup"><span data-stu-id="41b0c-130">1</span></span>  <br/> |<span data-ttu-id="41b0c-131">private</span><span class="sxs-lookup"><span data-stu-id="41b0c-131">private</span></span>  <br/> |
|<span data-ttu-id="41b0c-132">3</span><span class="sxs-lookup"><span data-stu-id="41b0c-132">3</span></span>  <br/> |<span data-ttu-id="41b0c-133">1</span><span class="sxs-lookup"><span data-stu-id="41b0c-133">1</span></span>  <br/> |<span data-ttu-id="41b0c-134">ámbito</span><span class="sxs-lookup"><span data-stu-id="41b0c-134">scope</span></span>  <br/> |
|<span data-ttu-id="41b0c-135">4</span><span class="sxs-lookup"><span data-stu-id="41b0c-135">4</span></span>  <br/> |<span data-ttu-id="41b0c-136">2</span><span class="sxs-lookup"><span data-stu-id="41b0c-136">2</span></span>  <br/> |<span data-ttu-id="41b0c-137">normal</span><span class="sxs-lookup"><span data-stu-id="41b0c-137">normal</span></span>  <br/> |
|<span data-ttu-id="41b0c-138">5</span><span class="sxs-lookup"><span data-stu-id="41b0c-138">5</span></span>  <br/> |<span data-ttu-id="41b0c-139">2</span><span class="sxs-lookup"><span data-stu-id="41b0c-139">2</span></span>  <br/> |<span data-ttu-id="41b0c-140">auditorio</span><span class="sxs-lookup"><span data-stu-id="41b0c-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="41b0c-141">6</span><span class="sxs-lookup"><span data-stu-id="41b0c-141">6</span></span>  <br/> |<span data-ttu-id="41b0c-142">1</span><span class="sxs-lookup"><span data-stu-id="41b0c-142">1</span></span>  <br/> |<span data-ttu-id="41b0c-143">Abra</span><span class="sxs-lookup"><span data-stu-id="41b0c-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="41b0c-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="41b0c-144">See also</span></span>

[<span data-ttu-id="41b0c-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="41b0c-145">tblNode</span></span>](tblnode.md)
