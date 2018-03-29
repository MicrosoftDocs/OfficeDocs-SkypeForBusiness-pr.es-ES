---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado los pasos posteriores de sincronización de Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a><span data-ttu-id="e4f8e-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="e4f8e-103">tblADUpdates</span></span>
 
<span data-ttu-id="e4f8e-104">tblADUpdates contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado los pasos posteriores de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="e4f8e-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e4f8e-105">**Columns**</span></span>

|<span data-ttu-id="e4f8e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e4f8e-106">**Column**</span></span>|<span data-ttu-id="e4f8e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e4f8e-107">**Type**</span></span>|<span data-ttu-id="e4f8e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e4f8e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4f8e-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e4f8e-109">prinGuid</span></span>  <br/> |<span data-ttu-id="e4f8e-110">GUID, no nulo</span><span class="sxs-lookup"><span data-stu-id="e4f8e-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="e4f8e-111">Principal el GUID del objeto que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="e4f8e-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="e4f8e-112">prinADPath</span></span>  <br/> |<span data-ttu-id="e4f8e-113">nvarchar (384), no nulo</span><span class="sxs-lookup"><span data-stu-id="e4f8e-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="e4f8e-114">Nombre distintivo del objeto.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="e4f8e-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="e4f8e-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="e4f8e-116">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="e4f8e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="e4f8e-117">True si al menos un atributo del objeto modificado.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="e4f8e-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="e4f8e-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="e4f8e-119">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="e4f8e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="e4f8e-120">True si cambia la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="e4f8e-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="e4f8e-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="e4f8e-122">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="e4f8e-122">bit, not null</span></span>  <br/> |<span data-ttu-id="e4f8e-123">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="e4f8e-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="e4f8e-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="e4f8e-125">bits, no nulo</span><span class="sxs-lookup"><span data-stu-id="e4f8e-125">bit, not null</span></span>  <br/> |<span data-ttu-id="e4f8e-126">True si el objeto se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="e4f8e-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="e4f8e-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="e4f8e-128">fecha y hora, no nulo</span><span class="sxs-lookup"><span data-stu-id="e4f8e-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="e4f8e-129">Marca de hora de cuando se insertó la fila.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

