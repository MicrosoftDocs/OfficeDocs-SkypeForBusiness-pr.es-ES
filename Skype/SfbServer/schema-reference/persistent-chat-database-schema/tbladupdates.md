---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Tbladupdate contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado por los pasos posteriores de sincronización de Active Directory.
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929864"
---
# <a name="tbladupdates"></a><span data-ttu-id="d93b2-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="d93b2-103">tblADUpdates</span></span>
 
<span data-ttu-id="d93b2-104">Tbladupdate contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado por los pasos posteriores de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d93b2-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="d93b2-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d93b2-105">**Columns**</span></span>

|<span data-ttu-id="d93b2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d93b2-106">**Column**</span></span>|<span data-ttu-id="d93b2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d93b2-107">**Type**</span></span>|<span data-ttu-id="d93b2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d93b2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d93b2-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d93b2-109">prinGuid</span></span>  <br/> |<span data-ttu-id="d93b2-110">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d93b2-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d93b2-111">Entidad de seguridad el GUID del objeto que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="d93b2-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="d93b2-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="d93b2-112">prinADPath</span></span>  <br/> |<span data-ttu-id="d93b2-113">nvarchar (384), no es nulo</span><span class="sxs-lookup"><span data-stu-id="d93b2-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="d93b2-114">Nombre distintivo del objeto.</span><span class="sxs-lookup"><span data-stu-id="d93b2-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="d93b2-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="d93b2-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="d93b2-116">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d93b2-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d93b2-117">Es True si se ha cambiado al menos un atributo del objeto.</span><span class="sxs-lookup"><span data-stu-id="d93b2-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="d93b2-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="d93b2-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="d93b2-119">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d93b2-119">bit, not null</span></span>  <br/> |<span data-ttu-id="d93b2-120">Es True si ha cambiado la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="d93b2-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="d93b2-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="d93b2-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="d93b2-122">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d93b2-122">bit, not null</span></span>  <br/> |<span data-ttu-id="d93b2-123">No se usa.</span><span class="sxs-lookup"><span data-stu-id="d93b2-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="d93b2-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d93b2-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="d93b2-125">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d93b2-125">bit, not null</span></span>  <br/> |<span data-ttu-id="d93b2-126">True si el objeto se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="d93b2-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="d93b2-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="d93b2-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="d93b2-128">DateTime, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d93b2-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="d93b2-129">Marca de tiempo de cuando se insertó la fila.</span><span class="sxs-lookup"><span data-stu-id="d93b2-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

