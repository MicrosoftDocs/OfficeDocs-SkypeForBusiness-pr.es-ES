---
title: tblSkippedAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se puede leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="2e2ef-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="2e2ef-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="2e2ef-104">tblSkippedAffiliations contiene las afiliaciones que no se puede leer (generalmente debido a errores de acceso a los servicios de dominio de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="2e2ef-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="2e2ef-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="2e2ef-105">**Columns**</span></span>

|<span data-ttu-id="2e2ef-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2e2ef-106">**Column**</span></span>|<span data-ttu-id="2e2ef-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2e2ef-107">**Type**</span></span>|<span data-ttu-id="2e2ef-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2e2ef-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e2ef-109">prinID</span><span class="sxs-lookup"><span data-stu-id="2e2ef-109">prinID</span></span>  <br/> |<span data-ttu-id="2e2ef-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="2e2ef-110">int, not null</span></span>  <br/> |<span data-ttu-id="2e2ef-111">Id. principal</span><span class="sxs-lookup"><span data-stu-id="2e2ef-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="2e2ef-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="2e2ef-112">affDescription</span></span>  <br/> |<span data-ttu-id="2e2ef-113">nvarchar (256), no nulo</span><span class="sxs-lookup"><span data-stu-id="2e2ef-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2e2ef-114">Cadena que identifica la afiliación.</span><span class="sxs-lookup"><span data-stu-id="2e2ef-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="2e2ef-115">El formato es: guid: uri de _{0}_ : _{1}_> id: _{2}_</span><span class="sxs-lookup"><span data-stu-id="2e2ef-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="2e2ef-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="2e2ef-116">updatedBy</span></span>  <br/> |<span data-ttu-id="2e2ef-117">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="2e2ef-117">int, not null</span></span>  <br/> |<span data-ttu-id="2e2ef-118">Identificador de la entidad de seguridad que actualiza esta fila.</span><span class="sxs-lookup"><span data-stu-id="2e2ef-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="2e2ef-119">Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es la única fuente de estas entradas.</span><span class="sxs-lookup"><span data-stu-id="2e2ef-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="2e2ef-120">**Claves**</span><span class="sxs-lookup"><span data-stu-id="2e2ef-120">**Keys**</span></span>

|<span data-ttu-id="2e2ef-121">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="2e2ef-121">**Column(s)**</span></span>|<span data-ttu-id="2e2ef-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2e2ef-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e2ef-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="2e2ef-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="2e2ef-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="2e2ef-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2e2ef-125">prinID</span><span class="sxs-lookup"><span data-stu-id="2e2ef-125">prinID</span></span>  <br/> |<span data-ttu-id="2e2ef-126">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="2e2ef-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

