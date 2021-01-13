---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla codificada de forma rígida que contiene los valores visibility y behavior de los atributos que se usan en la tabla Node.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816030"
---
# <a name="tblenumvalue"></a><span data-ttu-id="942d7-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="942d7-103">tblEnumValue</span></span>
 
<span data-ttu-id="942d7-104">tblEnumValue es una tabla codificada de forma rígida que contiene los valores visibility y behavior de los atributos que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="942d7-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="942d7-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="942d7-105">**Columns**</span></span>

|<span data-ttu-id="942d7-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="942d7-106">**Column**</span></span>|<span data-ttu-id="942d7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="942d7-107">**Type**</span></span>|<span data-ttu-id="942d7-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="942d7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="942d7-109">valueID</span><span class="sxs-lookup"><span data-stu-id="942d7-109">valueID</span></span>  <br/> |<span data-ttu-id="942d7-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="942d7-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="942d7-111">Identificador del valor.</span><span class="sxs-lookup"><span data-stu-id="942d7-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="942d7-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="942d7-112">attributeID</span></span>  <br/> |<span data-ttu-id="942d7-113">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="942d7-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="942d7-114">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="942d7-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="942d7-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="942d7-115">attributeValue</span></span>  <br/> |<span data-ttu-id="942d7-116">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="942d7-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="942d7-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="942d7-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="942d7-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="942d7-118">**Keys**</span></span>

|<span data-ttu-id="942d7-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="942d7-119">**Column**</span></span>|<span data-ttu-id="942d7-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="942d7-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="942d7-121">valueID</span><span class="sxs-lookup"><span data-stu-id="942d7-121">valueID</span></span>  <br/> |<span data-ttu-id="942d7-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="942d7-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="942d7-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="942d7-123">attributeID</span></span>  <br/> |<span data-ttu-id="942d7-124">Clave externa con búsqueda en la tabla tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="942d7-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="942d7-125">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="942d7-125">**Table Values**</span></span>

|<span data-ttu-id="942d7-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="942d7-126">**valueID**</span></span>|<span data-ttu-id="942d7-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="942d7-127">**attributeID**</span></span>|<span data-ttu-id="942d7-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="942d7-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="942d7-129">2 </span><span class="sxs-lookup"><span data-stu-id="942d7-129">2</span></span>  <br/> |<span data-ttu-id="942d7-130">1 </span><span class="sxs-lookup"><span data-stu-id="942d7-130">1</span></span>  <br/> |<span data-ttu-id="942d7-131">private</span><span class="sxs-lookup"><span data-stu-id="942d7-131">private</span></span>  <br/> |
|<span data-ttu-id="942d7-132">3 </span><span class="sxs-lookup"><span data-stu-id="942d7-132">3</span></span>  <br/> |<span data-ttu-id="942d7-133">1 </span><span class="sxs-lookup"><span data-stu-id="942d7-133">1</span></span>  <br/> |<span data-ttu-id="942d7-134">ámbito</span><span class="sxs-lookup"><span data-stu-id="942d7-134">scope</span></span>  <br/> |
|<span data-ttu-id="942d7-135">4 </span><span class="sxs-lookup"><span data-stu-id="942d7-135">4</span></span>  <br/> |<span data-ttu-id="942d7-136">2 </span><span class="sxs-lookup"><span data-stu-id="942d7-136">2</span></span>  <br/> |<span data-ttu-id="942d7-137">normal</span><span class="sxs-lookup"><span data-stu-id="942d7-137">normal</span></span>  <br/> |
|<span data-ttu-id="942d7-138">5 </span><span class="sxs-lookup"><span data-stu-id="942d7-138">5</span></span>  <br/> |<span data-ttu-id="942d7-139">2 </span><span class="sxs-lookup"><span data-stu-id="942d7-139">2</span></span>  <br/> |<span data-ttu-id="942d7-140">auditorio</span><span class="sxs-lookup"><span data-stu-id="942d7-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="942d7-141">6 </span><span class="sxs-lookup"><span data-stu-id="942d7-141">6</span></span>  <br/> |<span data-ttu-id="942d7-142">1 </span><span class="sxs-lookup"><span data-stu-id="942d7-142">1</span></span>  <br/> |<span data-ttu-id="942d7-143">open</span><span class="sxs-lookup"><span data-stu-id="942d7-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="942d7-144">Ver también</span><span class="sxs-lookup"><span data-stu-id="942d7-144">See also</span></span>

[<span data-ttu-id="942d7-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="942d7-145">tblNode</span></span>](tblnode.md)
