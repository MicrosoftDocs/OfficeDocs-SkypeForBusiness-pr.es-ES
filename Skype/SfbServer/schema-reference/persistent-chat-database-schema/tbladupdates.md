---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814688"
---
# <a name="tbladupdates"></a><span data-ttu-id="03cdd-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="03cdd-103">tblADUpdates</span></span>
 
<span data-ttu-id="03cdd-104">tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03cdd-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="03cdd-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="03cdd-105">**Columns**</span></span>

|<span data-ttu-id="03cdd-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="03cdd-106">**Column**</span></span>|<span data-ttu-id="03cdd-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="03cdd-107">**Type**</span></span>|<span data-ttu-id="03cdd-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="03cdd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03cdd-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="03cdd-109">prinGuid</span></span>  <br/> |<span data-ttu-id="03cdd-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="03cdd-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="03cdd-111">GUID principal del objeto que cambió.</span><span class="sxs-lookup"><span data-stu-id="03cdd-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="03cdd-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="03cdd-112">prinADPath</span></span>  <br/> |<span data-ttu-id="03cdd-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="03cdd-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="03cdd-114">Nombre distintivo del objeto.</span><span class="sxs-lookup"><span data-stu-id="03cdd-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="03cdd-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="03cdd-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="03cdd-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="03cdd-116">bit, not null</span></span>  <br/> |<span data-ttu-id="03cdd-117">True si ha cambiado al menos un atributo del objeto.</span><span class="sxs-lookup"><span data-stu-id="03cdd-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="03cdd-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="03cdd-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="03cdd-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="03cdd-119">bit, not null</span></span>  <br/> |<span data-ttu-id="03cdd-120">True si la pertenencia ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="03cdd-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="03cdd-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="03cdd-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="03cdd-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="03cdd-122">bit, not null</span></span>  <br/> |<span data-ttu-id="03cdd-123">No usado.</span><span class="sxs-lookup"><span data-stu-id="03cdd-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="03cdd-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="03cdd-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="03cdd-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="03cdd-125">bit, not null</span></span>  <br/> |<span data-ttu-id="03cdd-126">True si el objeto se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="03cdd-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="03cdd-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="03cdd-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="03cdd-128">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="03cdd-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="03cdd-129">Marca de tiempo del momento en que se insertó la fila.</span><span class="sxs-lookup"><span data-stu-id="03cdd-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

