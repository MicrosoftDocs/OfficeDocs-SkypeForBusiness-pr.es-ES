---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se podrían leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874790"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="9315f-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="9315f-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="9315f-104">tblSkippedAffiliations contiene las afiliaciones que no se podrían leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="9315f-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="9315f-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="9315f-105">**Columns**</span></span>

|<span data-ttu-id="9315f-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9315f-106">**Column**</span></span>|<span data-ttu-id="9315f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9315f-107">**Type**</span></span>|<span data-ttu-id="9315f-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9315f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9315f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9315f-109">prinID</span></span>  <br/> |<span data-ttu-id="9315f-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="9315f-110">int, not null</span></span>  <br/> |<span data-ttu-id="9315f-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9315f-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9315f-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="9315f-112">affDescription</span></span>  <br/> |<span data-ttu-id="9315f-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="9315f-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="9315f-114">Una cadena que identifica la afiliación.</span><span class="sxs-lookup"><span data-stu-id="9315f-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="9315f-115">El formato es: guid: _{0}_ uri: _{1}_> identificador:_{2}_</span><span class="sxs-lookup"><span data-stu-id="9315f-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="9315f-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="9315f-116">updatedBy</span></span>  <br/> |<span data-ttu-id="9315f-117">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="9315f-117">int, not null</span></span>  <br/> |<span data-ttu-id="9315f-118">Identificador de la entidad de seguridad que actualizó esta fila.</span><span class="sxs-lookup"><span data-stu-id="9315f-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="9315f-119">Siempre es 1 (los usuarios del sistema) debido a que la sincronización de Active Directory es el único origen para estas entradas.</span><span class="sxs-lookup"><span data-stu-id="9315f-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="9315f-120">**Claves**</span><span class="sxs-lookup"><span data-stu-id="9315f-120">**Keys**</span></span>

|<span data-ttu-id="9315f-121">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="9315f-121">**Column(s)**</span></span>|<span data-ttu-id="9315f-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9315f-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9315f-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="9315f-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="9315f-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9315f-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9315f-125">prinID</span><span class="sxs-lookup"><span data-stu-id="9315f-125">prinID</span></span>  <br/> |<span data-ttu-id="9315f-126">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="9315f-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

