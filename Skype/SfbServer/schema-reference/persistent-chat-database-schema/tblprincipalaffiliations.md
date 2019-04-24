---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: la tabla tblPrincipalAffiliations contiene las afiliaciones principales que describen la pertenencia a grupos en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212505"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="c9e45-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="c9e45-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="c9e45-104">la tabla tblPrincipalAffiliations contiene las afiliaciones principales que describen la pertenencia a grupos en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="c9e45-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="c9e45-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="c9e45-105">**Columns**</span></span>

|<span data-ttu-id="c9e45-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c9e45-106">**Column**</span></span>|<span data-ttu-id="c9e45-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c9e45-107">**Type**</span></span>|<span data-ttu-id="c9e45-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c9e45-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9e45-109">principalID</span><span class="sxs-lookup"><span data-stu-id="c9e45-109">principalID</span></span>  <br/> |<span data-ttu-id="c9e45-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="c9e45-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9e45-111">Identificador de la entidad de seguridad afiliado.</span><span class="sxs-lookup"><span data-stu-id="c9e45-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="c9e45-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="c9e45-112">affiliationID</span></span>  <br/> |<span data-ttu-id="c9e45-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="c9e45-113">int, not null</span></span>  <br/> |<span data-ttu-id="c9e45-114">Identificador de la entidad de seguridad que representa la afiliación.</span><span class="sxs-lookup"><span data-stu-id="c9e45-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="c9e45-115">Cada entidad de seguridad (excepto system-usuario-types) tiene también un afiliación Self.</span><span class="sxs-lookup"><span data-stu-id="c9e45-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="c9e45-116">índice</span><span class="sxs-lookup"><span data-stu-id="c9e45-116">index</span></span>  <br/> |<span data-ttu-id="c9e45-117">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="c9e45-117">int, not null</span></span>  <br/> |<span data-ttu-id="c9e45-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="c9e45-118">Index.</span></span> <span data-ttu-id="c9e45-119">El valor de afiliaciones Self es -1, y para las demás afiliaciones aumenta secuencialmente desde 1 dentro de cada uno de ellos \<principalID, affiliationId\> bucket.</span><span class="sxs-lookup"><span data-stu-id="c9e45-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="c9e45-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="c9e45-120">updatedBy</span></span>  <br/> |<span data-ttu-id="c9e45-121">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="c9e45-121">int, not null</span></span>  <br/> |<span data-ttu-id="c9e45-122">Entidad de seguridad que hizo la actualización más reciente.</span><span class="sxs-lookup"><span data-stu-id="c9e45-122">Principal that did the latest update.</span></span> <span data-ttu-id="c9e45-123">Generalmente es 1, lo que significa que la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c9e45-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="c9e45-124">**Claves**</span><span class="sxs-lookup"><span data-stu-id="c9e45-124">**Keys**</span></span>

|<span data-ttu-id="c9e45-125">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="c9e45-125">**Columns**</span></span>|<span data-ttu-id="c9e45-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c9e45-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9e45-127">\<principalID, index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="c9e45-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="c9e45-128">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="c9e45-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c9e45-129">principalID</span><span class="sxs-lookup"><span data-stu-id="c9e45-129">principalID</span></span>  <br/> |<span data-ttu-id="c9e45-130">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="c9e45-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="c9e45-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="c9e45-131">affiliationID</span></span>  <br/> |<span data-ttu-id="c9e45-132">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="c9e45-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

