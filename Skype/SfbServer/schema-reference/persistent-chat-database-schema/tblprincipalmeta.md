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
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene las entidades de identidad que deben actualizarse desde los servicios de dominio de Active Directory.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295261"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="a7e84-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="a7e84-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="a7e84-104">tblPrincipalMeta contiene las entidades de identidad que deben actualizarse desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7e84-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="a7e84-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="a7e84-105">**Columns**</span></span>

|<span data-ttu-id="a7e84-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a7e84-106">**Column**</span></span>|<span data-ttu-id="a7e84-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a7e84-107">**Type**</span></span>|<span data-ttu-id="a7e84-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a7e84-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7e84-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a7e84-109">prinID</span></span>  <br/> |<span data-ttu-id="a7e84-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="a7e84-110">int, not null</span></span>  <br/> |<span data-ttu-id="a7e84-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="a7e84-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a7e84-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="a7e84-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="a7e84-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="a7e84-113">bit, not null</span></span>  <br/> |<span data-ttu-id="a7e84-114">True si es necesario actualizar las afiliaciones principales.</span><span class="sxs-lookup"><span data-stu-id="a7e84-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="a7e84-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="a7e84-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="a7e84-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="a7e84-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a7e84-117">True si es necesario actualizar los atributos de principal.</span><span class="sxs-lookup"><span data-stu-id="a7e84-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="a7e84-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a7e84-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="a7e84-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="a7e84-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a7e84-120">True si el principal se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="a7e84-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="a7e84-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="a7e84-121">tryCount</span></span>  <br/> |<span data-ttu-id="a7e84-122">int</span><span class="sxs-lookup"><span data-stu-id="a7e84-122">int</span></span>  <br/> |<span data-ttu-id="a7e84-123">Número de intentos de actualizar el principal de AD DS que se ha producido hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="a7e84-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="a7e84-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="a7e84-124">lastTry</span></span>  <br/> |<span data-ttu-id="a7e84-125">datetime</span><span class="sxs-lookup"><span data-stu-id="a7e84-125">datetime</span></span>  <br/> |<span data-ttu-id="a7e84-126">Marca de tiempo del último intento de actualizar la entidad de la identidad.</span><span class="sxs-lookup"><span data-stu-id="a7e84-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="a7e84-127">Puede ser null si aún no se ha intentado ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="a7e84-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="a7e84-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="a7e84-128">nextTry</span></span>  <br/> |<span data-ttu-id="a7e84-129">datetime</span><span class="sxs-lookup"><span data-stu-id="a7e84-129">datetime</span></span>  <br/> |<span data-ttu-id="a7e84-130">Marca de tiempo de la siguiente actualización programada.</span><span class="sxs-lookup"><span data-stu-id="a7e84-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="a7e84-131">Puede ser null si no se ha programado ninguna actualización adicional.</span><span class="sxs-lookup"><span data-stu-id="a7e84-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="a7e84-132">**Sus**</span><span class="sxs-lookup"><span data-stu-id="a7e84-132">**Keys**</span></span>

|<span data-ttu-id="a7e84-133">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a7e84-133">**Column**</span></span>|<span data-ttu-id="a7e84-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a7e84-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7e84-135">prinID</span><span class="sxs-lookup"><span data-stu-id="a7e84-135">prinID</span></span>  <br/> |<span data-ttu-id="a7e84-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="a7e84-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a7e84-137">prinID</span><span class="sxs-lookup"><span data-stu-id="a7e84-137">prinID</span></span>  <br/> |<span data-ttu-id="a7e84-138">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="a7e84-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

