---
title: tblEnumValue
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
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505079"
---
# <a name="tblenumvalue"></a><span data-ttu-id="4c245-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="4c245-103">tblEnumValue</span></span>
 
<span data-ttu-id="4c245-104">tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="4c245-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="4c245-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="4c245-105">**Columns**</span></span>

|<span data-ttu-id="4c245-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4c245-106">**Column**</span></span>|<span data-ttu-id="4c245-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4c245-107">**Type**</span></span>|<span data-ttu-id="4c245-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4c245-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c245-109">valueID</span><span class="sxs-lookup"><span data-stu-id="4c245-109">valueID</span></span>  <br/> |<span data-ttu-id="4c245-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="4c245-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="4c245-111">Identificador del valor.</span><span class="sxs-lookup"><span data-stu-id="4c245-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="4c245-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="4c245-112">attributeID</span></span>  <br/> |<span data-ttu-id="4c245-113">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="4c245-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="4c245-114">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="4c245-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="4c245-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="4c245-115">attributeValue</span></span>  <br/> |<span data-ttu-id="4c245-116">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="4c245-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="4c245-117">Nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="4c245-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="4c245-118">**Claves**</span><span class="sxs-lookup"><span data-stu-id="4c245-118">**Keys**</span></span>

|<span data-ttu-id="4c245-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4c245-119">**Column**</span></span>|<span data-ttu-id="4c245-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4c245-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c245-121">valueID</span><span class="sxs-lookup"><span data-stu-id="4c245-121">valueID</span></span>  <br/> |<span data-ttu-id="4c245-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="4c245-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4c245-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="4c245-123">attributeID</span></span>  <br/> |<span data-ttu-id="4c245-124">Clave externa con búsqueda en la tabla tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="4c245-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="4c245-125">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="4c245-125">**Table Values**</span></span>

|<span data-ttu-id="4c245-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="4c245-126">**valueID**</span></span>|<span data-ttu-id="4c245-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="4c245-127">**attributeID**</span></span>|<span data-ttu-id="4c245-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="4c245-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c245-129">2</span><span class="sxs-lookup"><span data-stu-id="4c245-129">2</span></span>  <br/> |<span data-ttu-id="4c245-130">1</span><span class="sxs-lookup"><span data-stu-id="4c245-130">1</span></span>  <br/> |<span data-ttu-id="4c245-131">private</span><span class="sxs-lookup"><span data-stu-id="4c245-131">private</span></span>  <br/> |
|<span data-ttu-id="4c245-132">3</span><span class="sxs-lookup"><span data-stu-id="4c245-132">3</span></span>  <br/> |<span data-ttu-id="4c245-133">1</span><span class="sxs-lookup"><span data-stu-id="4c245-133">1</span></span>  <br/> |<span data-ttu-id="4c245-134">ámbito</span><span class="sxs-lookup"><span data-stu-id="4c245-134">scope</span></span>  <br/> |
|<span data-ttu-id="4c245-135">4</span><span class="sxs-lookup"><span data-stu-id="4c245-135">4</span></span>  <br/> |<span data-ttu-id="4c245-136">2</span><span class="sxs-lookup"><span data-stu-id="4c245-136">2</span></span>  <br/> |<span data-ttu-id="4c245-137">normal</span><span class="sxs-lookup"><span data-stu-id="4c245-137">normal</span></span>  <br/> |
|<span data-ttu-id="4c245-138">5</span><span class="sxs-lookup"><span data-stu-id="4c245-138">5</span></span>  <br/> |<span data-ttu-id="4c245-139">2</span><span class="sxs-lookup"><span data-stu-id="4c245-139">2</span></span>  <br/> |<span data-ttu-id="4c245-140">auditorio</span><span class="sxs-lookup"><span data-stu-id="4c245-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="4c245-141">6</span><span class="sxs-lookup"><span data-stu-id="4c245-141">6</span></span>  <br/> |<span data-ttu-id="4c245-142">1</span><span class="sxs-lookup"><span data-stu-id="4c245-142">1</span></span>  <br/> |<span data-ttu-id="4c245-143">Abra</span><span class="sxs-lookup"><span data-stu-id="4c245-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4c245-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c245-144">See also</span></span>

[<span data-ttu-id="4c245-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="4c245-145">tblNode</span></span>](tblnode.md)