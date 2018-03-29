---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene a las identidades que tienen que actualizarse desde los servicios de dominio de Active Directory.
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="fbbf1-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="fbbf1-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="fbbf1-104">tblPrincipalMeta contiene a las identidades que tienen que actualizarse desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="fbbf1-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="fbbf1-105">**Columns**</span></span>

|<span data-ttu-id="fbbf1-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fbbf1-106">**Column**</span></span>|<span data-ttu-id="fbbf1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fbbf1-107">**Type**</span></span>|<span data-ttu-id="fbbf1-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fbbf1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fbbf1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fbbf1-109">prinID</span></span>  <br/> |<span data-ttu-id="fbbf1-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="fbbf1-110">int, not null</span></span>  <br/> |<span data-ttu-id="fbbf1-111">Id. principal</span><span class="sxs-lookup"><span data-stu-id="fbbf1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fbbf1-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="fbbf1-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="fbbf1-113">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="fbbf1-113">bit, not null</span></span>  <br/> |<span data-ttu-id="fbbf1-114">Afiliaciones True si principal tienen que actualizarse.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="fbbf1-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="fbbf1-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="fbbf1-116">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="fbbf1-116">bit, not null</span></span>  <br/> |<span data-ttu-id="fbbf1-117">True si principales atributos deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="fbbf1-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="fbbf1-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="fbbf1-119">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="fbbf1-119">bit, not null</span></span>  <br/> |<span data-ttu-id="fbbf1-120">True si se ha eliminado la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="fbbf1-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="fbbf1-121">tryCount</span></span>  <br/> |<span data-ttu-id="fbbf1-122">int</span><span class="sxs-lookup"><span data-stu-id="fbbf1-122">int</span></span>  <br/> |<span data-ttu-id="fbbf1-123">Número de intentos de actualización de la entidad de seguridad de AD DS que ha ocurrido hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="fbbf1-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="fbbf1-124">lastTry</span></span>  <br/> |<span data-ttu-id="fbbf1-125">datetime</span><span class="sxs-lookup"><span data-stu-id="fbbf1-125">datetime</span></span>  <br/> |<span data-ttu-id="fbbf1-126">Marca de tiempo desde el último intento de actualizar al principal.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="fbbf1-127">Puede ser null si no ha habido intentos de ninguna actualización todavía.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="fbbf1-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="fbbf1-128">nextTry</span></span>  <br/> |<span data-ttu-id="fbbf1-129">datetime</span><span class="sxs-lookup"><span data-stu-id="fbbf1-129">datetime</span></span>  <br/> |<span data-ttu-id="fbbf1-130">Marca de tiempo para la siguiente actualización programada.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="fbbf1-131">Puede ser null si no se ha programado la actualización.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="fbbf1-132">**Claves**</span><span class="sxs-lookup"><span data-stu-id="fbbf1-132">**Keys**</span></span>

|<span data-ttu-id="fbbf1-133">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fbbf1-133">**Column**</span></span>|<span data-ttu-id="fbbf1-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fbbf1-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fbbf1-135">prinID</span><span class="sxs-lookup"><span data-stu-id="fbbf1-135">prinID</span></span>  <br/> |<span data-ttu-id="fbbf1-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fbbf1-137">prinID</span><span class="sxs-lookup"><span data-stu-id="fbbf1-137">prinID</span></span>  <br/> |<span data-ttu-id="fbbf1-138">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="fbbf1-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

