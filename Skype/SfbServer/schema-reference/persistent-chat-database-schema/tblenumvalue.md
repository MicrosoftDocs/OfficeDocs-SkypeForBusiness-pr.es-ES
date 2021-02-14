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
# <a name="tblenumvalue"></a><span data-ttu-id="22b8e-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="22b8e-103">tblEnumValue</span></span>
 
<span data-ttu-id="22b8e-104">tblEnumValue es una tabla codificada de forma rígida que contiene los valores visibility y behavior de los atributos que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="22b8e-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="22b8e-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="22b8e-105">**Columns**</span></span>

|<span data-ttu-id="22b8e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="22b8e-106">**Column**</span></span>|<span data-ttu-id="22b8e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="22b8e-107">**Type**</span></span>|<span data-ttu-id="22b8e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="22b8e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22b8e-109">valueID</span><span class="sxs-lookup"><span data-stu-id="22b8e-109">valueID</span></span>  <br/> |<span data-ttu-id="22b8e-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="22b8e-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="22b8e-111">Identificador del valor.</span><span class="sxs-lookup"><span data-stu-id="22b8e-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="22b8e-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="22b8e-112">attributeID</span></span>  <br/> |<span data-ttu-id="22b8e-113">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="22b8e-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="22b8e-114">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="22b8e-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="22b8e-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="22b8e-115">attributeValue</span></span>  <br/> |<span data-ttu-id="22b8e-116">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="22b8e-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="22b8e-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="22b8e-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="22b8e-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="22b8e-118">**Keys**</span></span>

|<span data-ttu-id="22b8e-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="22b8e-119">**Column**</span></span>|<span data-ttu-id="22b8e-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="22b8e-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22b8e-121">valueID</span><span class="sxs-lookup"><span data-stu-id="22b8e-121">valueID</span></span>  <br/> |<span data-ttu-id="22b8e-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="22b8e-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="22b8e-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="22b8e-123">attributeID</span></span>  <br/> |<span data-ttu-id="22b8e-124">Clave externa con búsqueda en la tabla tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="22b8e-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="22b8e-125">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="22b8e-125">**Table Values**</span></span>

|<span data-ttu-id="22b8e-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="22b8e-126">**valueID**</span></span>|<span data-ttu-id="22b8e-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="22b8e-127">**attributeID**</span></span>|<span data-ttu-id="22b8e-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="22b8e-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22b8e-129">2 </span><span class="sxs-lookup"><span data-stu-id="22b8e-129">2</span></span>  <br/> |<span data-ttu-id="22b8e-130">1 </span><span class="sxs-lookup"><span data-stu-id="22b8e-130">1</span></span>  <br/> |<span data-ttu-id="22b8e-131">private</span><span class="sxs-lookup"><span data-stu-id="22b8e-131">private</span></span>  <br/> |
|<span data-ttu-id="22b8e-132">3 </span><span class="sxs-lookup"><span data-stu-id="22b8e-132">3</span></span>  <br/> |<span data-ttu-id="22b8e-133">1 </span><span class="sxs-lookup"><span data-stu-id="22b8e-133">1</span></span>  <br/> |<span data-ttu-id="22b8e-134">ámbito</span><span class="sxs-lookup"><span data-stu-id="22b8e-134">scope</span></span>  <br/> |
|<span data-ttu-id="22b8e-135">4 </span><span class="sxs-lookup"><span data-stu-id="22b8e-135">4</span></span>  <br/> |<span data-ttu-id="22b8e-136">2 </span><span class="sxs-lookup"><span data-stu-id="22b8e-136">2</span></span>  <br/> |<span data-ttu-id="22b8e-137">normal</span><span class="sxs-lookup"><span data-stu-id="22b8e-137">normal</span></span>  <br/> |
|<span data-ttu-id="22b8e-138">5 </span><span class="sxs-lookup"><span data-stu-id="22b8e-138">5</span></span>  <br/> |<span data-ttu-id="22b8e-139">2 </span><span class="sxs-lookup"><span data-stu-id="22b8e-139">2</span></span>  <br/> |<span data-ttu-id="22b8e-140">auditorio</span><span class="sxs-lookup"><span data-stu-id="22b8e-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="22b8e-141">6 </span><span class="sxs-lookup"><span data-stu-id="22b8e-141">6</span></span>  <br/> |<span data-ttu-id="22b8e-142">1 </span><span class="sxs-lookup"><span data-stu-id="22b8e-142">1</span></span>  <br/> |<span data-ttu-id="22b8e-143">open</span><span class="sxs-lookup"><span data-stu-id="22b8e-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="22b8e-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="22b8e-144">See also</span></span>

[<span data-ttu-id="22b8e-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="22b8e-145">tblNode</span></span>](tblnode.md)
