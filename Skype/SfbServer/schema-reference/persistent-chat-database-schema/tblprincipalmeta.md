---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene las entidades de identidad que deben actualizarse desde los servicios de dominio de Active Directory.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813578"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="b6d27-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="b6d27-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="b6d27-104">tblPrincipalMeta contiene las entidades de identidad que deben actualizarse desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b6d27-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="b6d27-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b6d27-105">**Columns**</span></span>

|<span data-ttu-id="b6d27-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b6d27-106">**Column**</span></span>|<span data-ttu-id="b6d27-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b6d27-107">**Type**</span></span>|<span data-ttu-id="b6d27-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b6d27-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6d27-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b6d27-109">prinID</span></span>  <br/> |<span data-ttu-id="b6d27-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="b6d27-110">int, not null</span></span>  <br/> |<span data-ttu-id="b6d27-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="b6d27-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b6d27-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="b6d27-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="b6d27-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="b6d27-113">bit, not null</span></span>  <br/> |<span data-ttu-id="b6d27-114">True si es necesario actualizar las afiliaciones principales.</span><span class="sxs-lookup"><span data-stu-id="b6d27-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="b6d27-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="b6d27-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="b6d27-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="b6d27-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b6d27-117">True si es necesario actualizar los atributos de principal.</span><span class="sxs-lookup"><span data-stu-id="b6d27-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="b6d27-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="b6d27-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="b6d27-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="b6d27-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b6d27-120">True si el principal se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="b6d27-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="b6d27-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="b6d27-121">tryCount</span></span>  <br/> |<span data-ttu-id="b6d27-122">int</span><span class="sxs-lookup"><span data-stu-id="b6d27-122">int</span></span>  <br/> |<span data-ttu-id="b6d27-123">Número de intentos de actualizar el principal de AD DS que se ha producido hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="b6d27-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="b6d27-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="b6d27-124">lastTry</span></span>  <br/> |<span data-ttu-id="b6d27-125">datetime</span><span class="sxs-lookup"><span data-stu-id="b6d27-125">datetime</span></span>  <br/> |<span data-ttu-id="b6d27-126">Marca de tiempo del último intento de actualizar la entidad de la identidad.</span><span class="sxs-lookup"><span data-stu-id="b6d27-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="b6d27-127">Puede ser null si aún no se ha intentado ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="b6d27-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="b6d27-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="b6d27-128">nextTry</span></span>  <br/> |<span data-ttu-id="b6d27-129">datetime</span><span class="sxs-lookup"><span data-stu-id="b6d27-129">datetime</span></span>  <br/> |<span data-ttu-id="b6d27-130">Marca de tiempo de la siguiente actualización programada.</span><span class="sxs-lookup"><span data-stu-id="b6d27-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="b6d27-131">Puede ser null si no se ha programado ninguna actualización adicional.</span><span class="sxs-lookup"><span data-stu-id="b6d27-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="b6d27-132">**Sus**</span><span class="sxs-lookup"><span data-stu-id="b6d27-132">**Keys**</span></span>

|<span data-ttu-id="b6d27-133">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b6d27-133">**Column**</span></span>|<span data-ttu-id="b6d27-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b6d27-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6d27-135">prinID</span><span class="sxs-lookup"><span data-stu-id="b6d27-135">prinID</span></span>  <br/> |<span data-ttu-id="b6d27-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b6d27-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b6d27-137">prinID</span><span class="sxs-lookup"><span data-stu-id="b6d27-137">prinID</span></span>  <br/> |<span data-ttu-id="b6d27-138">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="b6d27-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

