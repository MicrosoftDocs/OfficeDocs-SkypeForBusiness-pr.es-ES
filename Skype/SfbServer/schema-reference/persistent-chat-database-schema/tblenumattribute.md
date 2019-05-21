---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla codificada que contiene los atributos de visibilidad y comportamiento que se usan en la tabla de nodos.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295422"
---
# <a name="tblenumattribute"></a><span data-ttu-id="0a7ca-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="0a7ca-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="0a7ca-104">tblEnumAttribute es una tabla codificada que contiene los atributos de visibilidad y comportamiento que se usan en la tabla de nodos.</span><span class="sxs-lookup"><span data-stu-id="0a7ca-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="0a7ca-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-105">**Columns**</span></span>

|<span data-ttu-id="0a7ca-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-106">**Column**</span></span>|<span data-ttu-id="0a7ca-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-107">**Type**</span></span>|<span data-ttu-id="0a7ca-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a7ca-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="0a7ca-109">attributeID</span></span>  <br/> |<span data-ttu-id="0a7ca-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="0a7ca-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="0a7ca-111">IDENTIFICADOR del atributo.</span><span class="sxs-lookup"><span data-stu-id="0a7ca-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="0a7ca-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="0a7ca-112">attributeName</span></span>  <br/> |<span data-ttu-id="0a7ca-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="0a7ca-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="0a7ca-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="0a7ca-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="0a7ca-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-115">**Key**</span></span>

|<span data-ttu-id="0a7ca-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-116">**Column**</span></span>|<span data-ttu-id="0a7ca-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a7ca-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="0a7ca-118">attributeID</span></span>  <br/> |<span data-ttu-id="0a7ca-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="0a7ca-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="0a7ca-120">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-120">**Table Values**</span></span>

|<span data-ttu-id="0a7ca-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-121">**attributeID**</span></span>|<span data-ttu-id="0a7ca-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="0a7ca-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a7ca-123">1</span><span class="sxs-lookup"><span data-stu-id="0a7ca-123">1</span></span>  <br/> |<span data-ttu-id="0a7ca-124">Visión.</span><span class="sxs-lookup"><span data-stu-id="0a7ca-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="0a7ca-125">2</span><span class="sxs-lookup"><span data-stu-id="0a7ca-125">2</span></span>  <br/> |<span data-ttu-id="0a7ca-126">Problema.</span><span class="sxs-lookup"><span data-stu-id="0a7ca-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0a7ca-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a7ca-127">See also</span></span>

[<span data-ttu-id="0a7ca-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="0a7ca-128">tblNode</span></span>](tblnode.md)
