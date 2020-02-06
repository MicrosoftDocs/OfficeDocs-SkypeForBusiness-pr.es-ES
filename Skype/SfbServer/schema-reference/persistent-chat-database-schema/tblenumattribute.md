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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla codificada que contiene los atributos de visibilidad y comportamiento que se usan en la tabla de nodos.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814618"
---
# <a name="tblenumattribute"></a><span data-ttu-id="deb4d-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="deb4d-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="deb4d-104">tblEnumAttribute es una tabla codificada que contiene los atributos de visibilidad y comportamiento que se usan en la tabla de nodos.</span><span class="sxs-lookup"><span data-stu-id="deb4d-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="deb4d-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="deb4d-105">**Columns**</span></span>

|<span data-ttu-id="deb4d-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="deb4d-106">**Column**</span></span>|<span data-ttu-id="deb4d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="deb4d-107">**Type**</span></span>|<span data-ttu-id="deb4d-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="deb4d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="deb4d-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="deb4d-109">attributeID</span></span>  <br/> |<span data-ttu-id="deb4d-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="deb4d-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="deb4d-111">IDENTIFICADOR del atributo.</span><span class="sxs-lookup"><span data-stu-id="deb4d-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="deb4d-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="deb4d-112">attributeName</span></span>  <br/> |<span data-ttu-id="deb4d-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="deb4d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="deb4d-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="deb4d-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="deb4d-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="deb4d-115">**Key**</span></span>

|<span data-ttu-id="deb4d-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="deb4d-116">**Column**</span></span>|<span data-ttu-id="deb4d-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="deb4d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="deb4d-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="deb4d-118">attributeID</span></span>  <br/> |<span data-ttu-id="deb4d-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="deb4d-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="deb4d-120">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="deb4d-120">**Table Values**</span></span>

|<span data-ttu-id="deb4d-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="deb4d-121">**attributeID**</span></span>|<span data-ttu-id="deb4d-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="deb4d-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="deb4d-123">1</span><span class="sxs-lookup"><span data-stu-id="deb4d-123">1</span></span>  <br/> |<span data-ttu-id="deb4d-124">Visión.</span><span class="sxs-lookup"><span data-stu-id="deb4d-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="deb4d-125">1</span><span class="sxs-lookup"><span data-stu-id="deb4d-125">2</span></span>  <br/> |<span data-ttu-id="deb4d-126">Problema.</span><span class="sxs-lookup"><span data-stu-id="deb4d-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="deb4d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="deb4d-127">See also</span></span>

[<span data-ttu-id="deb4d-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="deb4d-128">tblNode</span></span>](tblnode.md)
