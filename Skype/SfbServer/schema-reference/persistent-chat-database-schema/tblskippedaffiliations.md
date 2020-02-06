---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los servicios de dominio de Active Directory).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812018"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="adab4-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="adab4-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="adab4-104">tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los servicios de dominio de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="adab4-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="adab4-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="adab4-105">**Columns**</span></span>

|<span data-ttu-id="adab4-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="adab4-106">**Column**</span></span>|<span data-ttu-id="adab4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="adab4-107">**Type**</span></span>|<span data-ttu-id="adab4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="adab4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="adab4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="adab4-109">prinID</span></span>  <br/> |<span data-ttu-id="adab4-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="adab4-110">int, not null</span></span>  <br/> |<span data-ttu-id="adab4-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="adab4-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="adab4-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="adab4-112">affDescription</span></span>  <br/> |<span data-ttu-id="adab4-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="adab4-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="adab4-114">Una cadena que identifica la afiliación.</span><span class="sxs-lookup"><span data-stu-id="adab4-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="adab4-115">El formato es: GUID: _{0}_ uri: _{1}_> ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="adab4-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="adab4-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="adab4-116">updatedBy</span></span>  <br/> |<span data-ttu-id="adab4-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="adab4-117">int, not null</span></span>  <br/> |<span data-ttu-id="adab4-118">IDENTIFICADOR de la entidad de identidad que actualizó esta fila.</span><span class="sxs-lookup"><span data-stu-id="adab4-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="adab4-119">Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es el único origen de estas entradas.</span><span class="sxs-lookup"><span data-stu-id="adab4-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="adab4-120">**Sus**</span><span class="sxs-lookup"><span data-stu-id="adab4-120">**Keys**</span></span>

|<span data-ttu-id="adab4-121">**Columna (s)**</span><span class="sxs-lookup"><span data-stu-id="adab4-121">**Column(s)**</span></span>|<span data-ttu-id="adab4-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="adab4-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="adab4-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="adab4-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="adab4-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="adab4-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="adab4-125">prinID</span><span class="sxs-lookup"><span data-stu-id="adab4-125">prinID</span></span>  <br/> |<span data-ttu-id="adab4-126">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="adab4-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

