---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla de codificado que contiene los atributos de visibilidad y el comportamiento que se utilizan en la tabla del nodo.
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a><span data-ttu-id="5f705-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="5f705-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="5f705-104">tblEnumAttribute es una tabla de codificado que contiene los atributos de visibilidad y el comportamiento que se utilizan en la tabla del nodo.</span><span class="sxs-lookup"><span data-stu-id="5f705-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="5f705-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5f705-105">**Columns**</span></span>

|<span data-ttu-id="5f705-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5f705-106">**Column**</span></span>|<span data-ttu-id="5f705-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5f705-107">**Type**</span></span>|<span data-ttu-id="5f705-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5f705-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f705-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="5f705-109">attributeID</span></span>  <br/> |<span data-ttu-id="5f705-110">smallint, no nulo</span><span class="sxs-lookup"><span data-stu-id="5f705-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="5f705-111">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="5f705-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="5f705-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="5f705-112">attributeName</span></span>  <br/> |<span data-ttu-id="5f705-113">nvarchar (256), no nulo</span><span class="sxs-lookup"><span data-stu-id="5f705-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="5f705-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="5f705-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="5f705-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="5f705-115">**Key**</span></span>

|<span data-ttu-id="5f705-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5f705-116">**Column**</span></span>|<span data-ttu-id="5f705-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5f705-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f705-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="5f705-118">attributeID</span></span>  <br/> |<span data-ttu-id="5f705-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5f705-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="5f705-120">**Valores de la tabla**</span><span class="sxs-lookup"><span data-stu-id="5f705-120">**Table Values**</span></span>

|<span data-ttu-id="5f705-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="5f705-121">**attributeID**</span></span>|<span data-ttu-id="5f705-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="5f705-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f705-123">1</span><span class="sxs-lookup"><span data-stu-id="5f705-123">1</span></span>  <br/> |<span data-ttu-id="5f705-124">Visibilidad.</span><span class="sxs-lookup"><span data-stu-id="5f705-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="5f705-125">2</span><span class="sxs-lookup"><span data-stu-id="5f705-125">2</span></span>  <br/> |<span data-ttu-id="5f705-126">Comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5f705-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5f705-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f705-127">See also</span></span>

#### 

[<span data-ttu-id="5f705-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="5f705-128">tblNode</span></span>](tblnode.md)

