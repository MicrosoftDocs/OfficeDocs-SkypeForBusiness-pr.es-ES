---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene las entidades de seguridad que se deben actualizar desde los servicios de dominio de Active Directory.
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889610"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="58b8e-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="58b8e-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="58b8e-104">tblPrincipalMeta contiene las entidades de seguridad que se deben actualizar desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58b8e-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="58b8e-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="58b8e-105">**Columns**</span></span>

|<span data-ttu-id="58b8e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="58b8e-106">**Column**</span></span>|<span data-ttu-id="58b8e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="58b8e-107">**Type**</span></span>|<span data-ttu-id="58b8e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="58b8e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58b8e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="58b8e-109">prinID</span></span>  <br/> |<span data-ttu-id="58b8e-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="58b8e-110">int, not null</span></span>  <br/> |<span data-ttu-id="58b8e-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="58b8e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="58b8e-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="58b8e-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="58b8e-113">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="58b8e-113">bit, not null</span></span>  <br/> |<span data-ttu-id="58b8e-114">Es True si la entidad de seguridad afiliaciones tienen que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="58b8e-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="58b8e-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="58b8e-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="58b8e-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="58b8e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="58b8e-117">Es True si la entidad de seguridad atributos tienen que actualizar.</span><span class="sxs-lookup"><span data-stu-id="58b8e-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="58b8e-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="58b8e-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="58b8e-119">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="58b8e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="58b8e-120">Es True si se ha eliminado la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="58b8e-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="58b8e-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="58b8e-121">tryCount</span></span>  <br/> |<span data-ttu-id="58b8e-122">int</span><span class="sxs-lookup"><span data-stu-id="58b8e-122">int</span></span>  <br/> |<span data-ttu-id="58b8e-123">Número de intentos de actualización de la entidad de seguridad de AD DS que han sucedido hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="58b8e-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="58b8e-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="58b8e-124">lastTry</span></span>  <br/> |<span data-ttu-id="58b8e-125">datetime</span><span class="sxs-lookup"><span data-stu-id="58b8e-125">datetime</span></span>  <br/> |<span data-ttu-id="58b8e-126">Marca de tiempo del último intento de actualizar la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="58b8e-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="58b8e-127">Puede ser null si no se ha intentado ninguna actualización todavía.</span><span class="sxs-lookup"><span data-stu-id="58b8e-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="58b8e-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="58b8e-128">nextTry</span></span>  <br/> |<span data-ttu-id="58b8e-129">datetime</span><span class="sxs-lookup"><span data-stu-id="58b8e-129">datetime</span></span>  <br/> |<span data-ttu-id="58b8e-130">Marca de tiempo para la próxima actualización programada.</span><span class="sxs-lookup"><span data-stu-id="58b8e-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="58b8e-131">Puede ser null si no se ha programado la actualización.</span><span class="sxs-lookup"><span data-stu-id="58b8e-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="58b8e-132">**Claves**</span><span class="sxs-lookup"><span data-stu-id="58b8e-132">**Keys**</span></span>

|<span data-ttu-id="58b8e-133">**Columna**</span><span class="sxs-lookup"><span data-stu-id="58b8e-133">**Column**</span></span>|<span data-ttu-id="58b8e-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="58b8e-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58b8e-135">prinID</span><span class="sxs-lookup"><span data-stu-id="58b8e-135">prinID</span></span>  <br/> |<span data-ttu-id="58b8e-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="58b8e-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="58b8e-137">prinID</span><span class="sxs-lookup"><span data-stu-id="58b8e-137">prinID</span></span>  <br/> |<span data-ttu-id="58b8e-138">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="58b8e-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

