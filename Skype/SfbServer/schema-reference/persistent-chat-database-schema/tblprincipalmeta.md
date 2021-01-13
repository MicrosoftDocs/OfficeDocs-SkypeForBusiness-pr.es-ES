---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene las entidades de seguridad que deben actualizarse desde los Servicios de dominio de Active Directory.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831550"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="cbdc4-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="cbdc4-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="cbdc4-104">tblPrincipalMeta contiene las entidades de seguridad que deben actualizarse desde los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="cbdc4-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="cbdc4-105">**Columns**</span></span>

|<span data-ttu-id="cbdc4-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="cbdc4-106">**Column**</span></span>|<span data-ttu-id="cbdc4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cbdc4-107">**Type**</span></span>|<span data-ttu-id="cbdc4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cbdc4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cbdc4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="cbdc4-109">prinID</span></span>  <br/> |<span data-ttu-id="cbdc4-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="cbdc4-110">int, not null</span></span>  <br/> |<span data-ttu-id="cbdc4-111">Identificador de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="cbdc4-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="cbdc4-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="cbdc4-113">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="cbdc4-113">bit, not null</span></span>  <br/> |<span data-ttu-id="cbdc4-114">True si hay que actualizar las afiliaciones de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="cbdc4-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="cbdc4-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="cbdc4-116">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="cbdc4-116">bit, not null</span></span>  <br/> |<span data-ttu-id="cbdc4-117">True si hay que actualizar los atributos de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="cbdc4-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="cbdc4-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="cbdc4-119">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="cbdc4-119">bit, not null</span></span>  <br/> |<span data-ttu-id="cbdc4-120">True si la entidad de seguridad se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="cbdc4-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="cbdc4-121">tryCount</span></span>  <br/> |<span data-ttu-id="cbdc4-122">entero</span><span class="sxs-lookup"><span data-stu-id="cbdc4-122">int</span></span>  <br/> |<span data-ttu-id="cbdc4-123">Número de intentos realizados hasta la fecha para actualizar la entidad de seguridad de AD DS.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="cbdc4-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="cbdc4-124">lastTry</span></span>  <br/> |<span data-ttu-id="cbdc4-125">datetime</span><span class="sxs-lookup"><span data-stu-id="cbdc4-125">datetime</span></span>  <br/> |<span data-ttu-id="cbdc4-p101">Marca de tiempo del último intento por actualizar la entidad de seguridad. Puede ser null si aún no se ha realizado ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="cbdc4-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="cbdc4-128">nextTry</span></span>  <br/> |<span data-ttu-id="cbdc4-129">datetime</span><span class="sxs-lookup"><span data-stu-id="cbdc4-129">datetime</span></span>  <br/> |<span data-ttu-id="cbdc4-p102">Marca de tiempo de la siguiente actualización programada. Puede ser NULL si no se han programado más actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="cbdc4-132">**Keys**</span><span class="sxs-lookup"><span data-stu-id="cbdc4-132">**Keys**</span></span>

|<span data-ttu-id="cbdc4-133">**Columna**</span><span class="sxs-lookup"><span data-stu-id="cbdc4-133">**Column**</span></span>|<span data-ttu-id="cbdc4-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cbdc4-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cbdc4-135">prinID</span><span class="sxs-lookup"><span data-stu-id="cbdc4-135">prinID</span></span>  <br/> |<span data-ttu-id="cbdc4-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="cbdc4-137">prinID</span><span class="sxs-lookup"><span data-stu-id="cbdc4-137">prinID</span></span>  <br/> |<span data-ttu-id="cbdc4-138">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

