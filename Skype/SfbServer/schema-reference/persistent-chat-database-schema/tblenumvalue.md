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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla de nodos.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814608"
---
# <a name="tblenumvalue"></a><span data-ttu-id="d5fe1-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="d5fe1-103">tblEnumValue</span></span>
 
<span data-ttu-id="d5fe1-104">tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla de nodos.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="d5fe1-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-105">**Columns**</span></span>

|<span data-ttu-id="d5fe1-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-106">**Column**</span></span>|<span data-ttu-id="d5fe1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-107">**Type**</span></span>|<span data-ttu-id="d5fe1-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5fe1-109">valueID</span><span class="sxs-lookup"><span data-stu-id="d5fe1-109">valueID</span></span>  <br/> |<span data-ttu-id="d5fe1-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="d5fe1-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d5fe1-111">IDENTIFICADOR del valor.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="d5fe1-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="d5fe1-112">attributeID</span></span>  <br/> |<span data-ttu-id="d5fe1-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="d5fe1-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="d5fe1-114">IDENTIFICADOR del atributo.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="d5fe1-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="d5fe1-115">attributeValue</span></span>  <br/> |<span data-ttu-id="d5fe1-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="d5fe1-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d5fe1-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="d5fe1-118">**Sus**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-118">**Keys**</span></span>

|<span data-ttu-id="d5fe1-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-119">**Column**</span></span>|<span data-ttu-id="d5fe1-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5fe1-121">valueID</span><span class="sxs-lookup"><span data-stu-id="d5fe1-121">valueID</span></span>  <br/> |<span data-ttu-id="d5fe1-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d5fe1-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="d5fe1-123">attributeID</span></span>  <br/> |<span data-ttu-id="d5fe1-124">Clave externa con la búsqueda en la tabla tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="d5fe1-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="d5fe1-125">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-125">**Table Values**</span></span>

|<span data-ttu-id="d5fe1-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-126">**valueID**</span></span>|<span data-ttu-id="d5fe1-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-127">**attributeID**</span></span>|<span data-ttu-id="d5fe1-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="d5fe1-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5fe1-129">1</span><span class="sxs-lookup"><span data-stu-id="d5fe1-129">2</span></span>  <br/> |<span data-ttu-id="d5fe1-130">1</span><span class="sxs-lookup"><span data-stu-id="d5fe1-130">1</span></span>  <br/> |<span data-ttu-id="d5fe1-131">private</span><span class="sxs-lookup"><span data-stu-id="d5fe1-131">private</span></span>  <br/> |
|<span data-ttu-id="d5fe1-132">3</span><span class="sxs-lookup"><span data-stu-id="d5fe1-132">3</span></span>  <br/> |<span data-ttu-id="d5fe1-133">1</span><span class="sxs-lookup"><span data-stu-id="d5fe1-133">1</span></span>  <br/> |<span data-ttu-id="d5fe1-134">ID</span><span class="sxs-lookup"><span data-stu-id="d5fe1-134">scope</span></span>  <br/> |
|<span data-ttu-id="d5fe1-135">4</span><span class="sxs-lookup"><span data-stu-id="d5fe1-135">4</span></span>  <br/> |<span data-ttu-id="d5fe1-136">1</span><span class="sxs-lookup"><span data-stu-id="d5fe1-136">2</span></span>  <br/> |<span data-ttu-id="d5fe1-137">normal</span><span class="sxs-lookup"><span data-stu-id="d5fe1-137">normal</span></span>  <br/> |
|<span data-ttu-id="d5fe1-138">5</span><span class="sxs-lookup"><span data-stu-id="d5fe1-138">5</span></span>  <br/> |<span data-ttu-id="d5fe1-139">1</span><span class="sxs-lookup"><span data-stu-id="d5fe1-139">2</span></span>  <br/> |<span data-ttu-id="d5fe1-140">Audi</span><span class="sxs-lookup"><span data-stu-id="d5fe1-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="d5fe1-141">6</span><span class="sxs-lookup"><span data-stu-id="d5fe1-141">6</span></span>  <br/> |<span data-ttu-id="d5fe1-142">1</span><span class="sxs-lookup"><span data-stu-id="d5fe1-142">1</span></span>  <br/> |<span data-ttu-id="d5fe1-143">volver</span><span class="sxs-lookup"><span data-stu-id="d5fe1-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d5fe1-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5fe1-144">See also</span></span>

[<span data-ttu-id="d5fe1-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="d5fe1-145">tblNode</span></span>](tblnode.md)
