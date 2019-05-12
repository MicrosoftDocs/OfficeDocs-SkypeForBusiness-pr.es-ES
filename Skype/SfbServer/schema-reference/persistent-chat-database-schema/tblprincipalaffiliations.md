---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: la tabla tblPrincipalAffiliations contiene las afiliaciones principales que describen la pertenencia a grupos en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: fb1bd8eb7291ba001a5c23240c2de70aaff048b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929822"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="474e9-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="474e9-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="474e9-104">la tabla tblPrincipalAffiliations contiene las afiliaciones principales que describen la pertenencia a grupos en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="474e9-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="474e9-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="474e9-105">**Columns**</span></span>

|<span data-ttu-id="474e9-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="474e9-106">**Column**</span></span>|<span data-ttu-id="474e9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="474e9-107">**Type**</span></span>|<span data-ttu-id="474e9-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="474e9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="474e9-109">principalID</span><span class="sxs-lookup"><span data-stu-id="474e9-109">principalID</span></span>  <br/> |<span data-ttu-id="474e9-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="474e9-110">int, not null</span></span>  <br/> |<span data-ttu-id="474e9-111">Identificador de la entidad de seguridad afiliado.</span><span class="sxs-lookup"><span data-stu-id="474e9-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="474e9-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="474e9-112">affiliationID</span></span>  <br/> |<span data-ttu-id="474e9-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="474e9-113">int, not null</span></span>  <br/> |<span data-ttu-id="474e9-114">Identificador de la entidad de seguridad que representa la afiliación.</span><span class="sxs-lookup"><span data-stu-id="474e9-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="474e9-115">Cada entidad de seguridad (excepto system-usuario-types) tiene también un afiliación Self.</span><span class="sxs-lookup"><span data-stu-id="474e9-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="474e9-116">índice</span><span class="sxs-lookup"><span data-stu-id="474e9-116">index</span></span>  <br/> |<span data-ttu-id="474e9-117">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="474e9-117">int, not null</span></span>  <br/> |<span data-ttu-id="474e9-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="474e9-118">Index.</span></span> <span data-ttu-id="474e9-119">El valor de afiliaciones Self es -1, y para las demás afiliaciones aumenta secuencialmente desde 1 dentro de cada uno de ellos \<principalID, affiliationId\> bucket.</span><span class="sxs-lookup"><span data-stu-id="474e9-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="474e9-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="474e9-120">updatedBy</span></span>  <br/> |<span data-ttu-id="474e9-121">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="474e9-121">int, not null</span></span>  <br/> |<span data-ttu-id="474e9-122">Entidad de seguridad que hizo la actualización más reciente.</span><span class="sxs-lookup"><span data-stu-id="474e9-122">Principal that did the latest update.</span></span> <span data-ttu-id="474e9-123">Generalmente es 1, lo que significa que la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="474e9-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="474e9-124">**Claves**</span><span class="sxs-lookup"><span data-stu-id="474e9-124">**Keys**</span></span>

|<span data-ttu-id="474e9-125">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="474e9-125">**Columns**</span></span>|<span data-ttu-id="474e9-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="474e9-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="474e9-127">\<principalID, index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="474e9-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="474e9-128">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="474e9-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="474e9-129">principalID</span><span class="sxs-lookup"><span data-stu-id="474e9-129">principalID</span></span>  <br/> |<span data-ttu-id="474e9-130">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="474e9-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="474e9-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="474e9-131">affiliationID</span></span>  <br/> |<span data-ttu-id="474e9-132">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="474e9-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

