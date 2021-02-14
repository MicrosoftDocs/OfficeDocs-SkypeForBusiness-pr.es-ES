---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene cambios de Servicios de dominio de Active Directory que aún no se han procesado en los pasos de sincronización de Active Directory posteriores.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821390"
---
# <a name="tbladupdates"></a><span data-ttu-id="9037a-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="9037a-103">tblADUpdates</span></span>
 
<span data-ttu-id="9037a-104">tblADUpdates contiene cambios de Servicios de dominio de Active Directory que aún no se han procesado en los pasos de sincronización de Active Directory posteriores.</span><span class="sxs-lookup"><span data-stu-id="9037a-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="9037a-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9037a-105">**Columns**</span></span>

|<span data-ttu-id="9037a-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9037a-106">**Column**</span></span>|<span data-ttu-id="9037a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9037a-107">**Type**</span></span>|<span data-ttu-id="9037a-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9037a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9037a-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9037a-109">prinGuid</span></span>  <br/> |<span data-ttu-id="9037a-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="9037a-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="9037a-111">GUID principal del objeto que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="9037a-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="9037a-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="9037a-112">prinADPath</span></span>  <br/> |<span data-ttu-id="9037a-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="9037a-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="9037a-114">Nombre distintivo del objeto.</span><span class="sxs-lookup"><span data-stu-id="9037a-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="9037a-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="9037a-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="9037a-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9037a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9037a-117">True si ha cambiado al menos un atributo del objeto.</span><span class="sxs-lookup"><span data-stu-id="9037a-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="9037a-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="9037a-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="9037a-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9037a-119">bit, not null</span></span>  <br/> |<span data-ttu-id="9037a-120">True si ha cambiado la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="9037a-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="9037a-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="9037a-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="9037a-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9037a-122">bit, not null</span></span>  <br/> |<span data-ttu-id="9037a-123">No se usa.</span><span class="sxs-lookup"><span data-stu-id="9037a-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="9037a-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="9037a-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="9037a-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9037a-125">bit, not null</span></span>  <br/> |<span data-ttu-id="9037a-126">True si se ha eliminado el objeto.</span><span class="sxs-lookup"><span data-stu-id="9037a-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="9037a-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="9037a-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="9037a-128">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="9037a-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="9037a-129">Marca de tiempo correspondiente al momento en que se insertó la fila.</span><span class="sxs-lookup"><span data-stu-id="9037a-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

