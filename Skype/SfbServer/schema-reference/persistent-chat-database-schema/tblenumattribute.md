---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809720"
---
# <a name="tblenumattribute"></a><span data-ttu-id="df7a2-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="df7a2-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="df7a2-104">tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="df7a2-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="df7a2-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="df7a2-105">**Columns**</span></span>

|<span data-ttu-id="df7a2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="df7a2-106">**Column**</span></span>|<span data-ttu-id="df7a2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="df7a2-107">**Type**</span></span>|<span data-ttu-id="df7a2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="df7a2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="df7a2-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="df7a2-109">attributeID</span></span>  <br/> |<span data-ttu-id="df7a2-110">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="df7a2-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="df7a2-111">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="df7a2-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="df7a2-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="df7a2-112">attributeName</span></span>  <br/> |<span data-ttu-id="df7a2-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="df7a2-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="df7a2-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="df7a2-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="df7a2-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="df7a2-115">**Key**</span></span>

|<span data-ttu-id="df7a2-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="df7a2-116">**Column**</span></span>|<span data-ttu-id="df7a2-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="df7a2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df7a2-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="df7a2-118">attributeID</span></span>  <br/> |<span data-ttu-id="df7a2-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="df7a2-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="df7a2-120">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="df7a2-120">**Table Values**</span></span>

|<span data-ttu-id="df7a2-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="df7a2-121">**attributeID**</span></span>|<span data-ttu-id="df7a2-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="df7a2-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df7a2-123">1 </span><span class="sxs-lookup"><span data-stu-id="df7a2-123">1</span></span>  <br/> |<span data-ttu-id="df7a2-124">Visibilidad.</span><span class="sxs-lookup"><span data-stu-id="df7a2-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="df7a2-125">2 </span><span class="sxs-lookup"><span data-stu-id="df7a2-125">2</span></span>  <br/> |<span data-ttu-id="df7a2-126">Comportamiento.</span><span class="sxs-lookup"><span data-stu-id="df7a2-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="df7a2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="df7a2-127">See also</span></span>

[<span data-ttu-id="df7a2-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="df7a2-128">tblNode</span></span>](tblnode.md)
