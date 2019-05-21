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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295562"
---
# <a name="tbladupdates"></a><span data-ttu-id="d0389-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="d0389-103">tblADUpdates</span></span>
 
<span data-ttu-id="d0389-104">tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d0389-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="d0389-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d0389-105">**Columns**</span></span>

|<span data-ttu-id="d0389-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d0389-106">**Column**</span></span>|<span data-ttu-id="d0389-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d0389-107">**Type**</span></span>|<span data-ttu-id="d0389-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d0389-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0389-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d0389-109">prinGuid</span></span>  <br/> |<span data-ttu-id="d0389-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="d0389-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d0389-111">GUID principal del objeto que cambió.</span><span class="sxs-lookup"><span data-stu-id="d0389-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="d0389-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="d0389-112">prinADPath</span></span>  <br/> |<span data-ttu-id="d0389-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="d0389-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="d0389-114">Nombre distintivo del objeto.</span><span class="sxs-lookup"><span data-stu-id="d0389-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="d0389-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="d0389-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="d0389-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0389-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d0389-117">True si ha cambiado al menos un atributo del objeto.</span><span class="sxs-lookup"><span data-stu-id="d0389-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="d0389-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="d0389-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="d0389-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0389-119">bit, not null</span></span>  <br/> |<span data-ttu-id="d0389-120">True si la pertenencia ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="d0389-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="d0389-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="d0389-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="d0389-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0389-122">bit, not null</span></span>  <br/> |<span data-ttu-id="d0389-123">No usado.</span><span class="sxs-lookup"><span data-stu-id="d0389-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="d0389-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d0389-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="d0389-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0389-125">bit, not null</span></span>  <br/> |<span data-ttu-id="d0389-126">True si el objeto se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="d0389-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="d0389-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="d0389-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="d0389-128">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="d0389-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="d0389-129">Marca de tiempo del momento en que se insertó la fila.</span><span class="sxs-lookup"><span data-stu-id="d0389-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

