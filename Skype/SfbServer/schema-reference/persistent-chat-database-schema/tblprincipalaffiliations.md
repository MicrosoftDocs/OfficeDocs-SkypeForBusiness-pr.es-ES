---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="08035-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="08035-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="08035-104">tblPrincipalAffiliations contiene las afiliaciones principales que describen pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="08035-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="08035-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="08035-105">**Columns**</span></span>

|<span data-ttu-id="08035-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="08035-106">**Column**</span></span>|<span data-ttu-id="08035-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="08035-107">**Type**</span></span>|<span data-ttu-id="08035-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="08035-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08035-109">principalID</span><span class="sxs-lookup"><span data-stu-id="08035-109">principalID</span></span>  <br/> |<span data-ttu-id="08035-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="08035-110">int, not null</span></span>  <br/> |<span data-ttu-id="08035-111">Identificador de la entidad de seguridad asociada.</span><span class="sxs-lookup"><span data-stu-id="08035-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="08035-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="08035-112">affiliationID</span></span>  <br/> |<span data-ttu-id="08035-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="08035-113">int, not null</span></span>  <br/> |<span data-ttu-id="08035-114">Identificador de la entidad de seguridad que representa la afiliación.</span><span class="sxs-lookup"><span data-stu-id="08035-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="08035-115">Cada entidad de seguridad (excepto el sistema de tipos usuario) tiene también una afiliación por cuenta propia.</span><span class="sxs-lookup"><span data-stu-id="08035-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="08035-116">índice</span><span class="sxs-lookup"><span data-stu-id="08035-116">index</span></span>  <br/> |<span data-ttu-id="08035-117">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="08035-117">int, not null</span></span>  <br/> |<span data-ttu-id="08035-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="08035-118">Index.</span></span> <span data-ttu-id="08035-119">El valor de afiliaciones automática es -1 y para las demás afiliaciones aumenta secuencialmente desde 1 dentro de cada \<principalID, affiliationId\> bote.</span><span class="sxs-lookup"><span data-stu-id="08035-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="08035-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="08035-120">updatedBy</span></span>  <br/> |<span data-ttu-id="08035-121">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="08035-121">int, not null</span></span>  <br/> |<span data-ttu-id="08035-122">Entidad de seguridad que hizo la última actualización.</span><span class="sxs-lookup"><span data-stu-id="08035-122">Principal that did the latest update.</span></span> <span data-ttu-id="08035-123">Suele ser 1, que significa la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="08035-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="08035-124">**Claves**</span><span class="sxs-lookup"><span data-stu-id="08035-124">**Keys**</span></span>

|<span data-ttu-id="08035-125">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="08035-125">**Columns**</span></span>|<span data-ttu-id="08035-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="08035-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08035-127">\<principalID, índice, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="08035-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="08035-128">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="08035-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="08035-129">principalID</span><span class="sxs-lookup"><span data-stu-id="08035-129">principalID</span></span>  <br/> |<span data-ttu-id="08035-130">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="08035-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="08035-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="08035-131">affiliationID</span></span>  <br/> |<span data-ttu-id="08035-132">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="08035-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

