---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los Servicios de dominio de Active Directory).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831430"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="e67e4-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="e67e4-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="e67e4-104">tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los Servicios de dominio de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="e67e4-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="e67e4-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e67e4-105">**Columns**</span></span>

|<span data-ttu-id="e67e4-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e67e4-106">**Column**</span></span>|<span data-ttu-id="e67e4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e67e4-107">**Type**</span></span>|<span data-ttu-id="e67e4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e67e4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e67e4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e67e4-109">prinID</span></span>  <br/> |<span data-ttu-id="e67e4-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="e67e4-110">int, not null</span></span>  <br/> |<span data-ttu-id="e67e4-111">Id. de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e67e4-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e67e4-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="e67e4-112">affDescription</span></span>  <br/> |<span data-ttu-id="e67e4-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="e67e4-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e67e4-114">Cadena que identifica la afiliación.</span><span class="sxs-lookup"><span data-stu-id="e67e4-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="e67e4-115">El formato es: guid:  _{0}_ uri: _{1}_> id.:  _{2}_</span><span class="sxs-lookup"><span data-stu-id="e67e4-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="e67e4-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e67e4-116">updatedBy</span></span>  <br/> |<span data-ttu-id="e67e4-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="e67e4-117">int, not null</span></span>  <br/> |<span data-ttu-id="e67e4-p101">Identificador de la entidad de seguridad que actualizó esta fila. Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es el único origen de estas entradas.</span><span class="sxs-lookup"><span data-stu-id="e67e4-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="e67e4-120">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e67e4-120">**Keys**</span></span>

|<span data-ttu-id="e67e4-121">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e67e4-121">**Column(s)**</span></span>|<span data-ttu-id="e67e4-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e67e4-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="e67e4-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="e67e4-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e67e4-124">prinID</span><span class="sxs-lookup"><span data-stu-id="e67e4-124">prinID</span></span>  <br/> |<span data-ttu-id="e67e4-125">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e67e4-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

