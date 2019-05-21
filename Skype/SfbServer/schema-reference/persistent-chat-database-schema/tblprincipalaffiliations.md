---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295317"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="98b57-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="98b57-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="98b57-104">tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="98b57-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="98b57-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="98b57-105">**Columns**</span></span>

|<span data-ttu-id="98b57-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="98b57-106">**Column**</span></span>|<span data-ttu-id="98b57-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="98b57-107">**Type**</span></span>|<span data-ttu-id="98b57-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="98b57-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98b57-109">principalID</span><span class="sxs-lookup"><span data-stu-id="98b57-109">principalID</span></span>  <br/> |<span data-ttu-id="98b57-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="98b57-110">int, not null</span></span>  <br/> |<span data-ttu-id="98b57-111">IDENTIFICADOR de la entidad de identidad afiliada.</span><span class="sxs-lookup"><span data-stu-id="98b57-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="98b57-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="98b57-112">affiliationID</span></span>  <br/> |<span data-ttu-id="98b57-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="98b57-113">int, not null</span></span>  <br/> |<span data-ttu-id="98b57-114">IDENTIFICADOR de la identidad que representa la afiliación.</span><span class="sxs-lookup"><span data-stu-id="98b57-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="98b57-115">Cada principal (excepto los tipos de usuario del sistema) tiene también una afiliación propia.</span><span class="sxs-lookup"><span data-stu-id="98b57-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="98b57-116">clasificación</span><span class="sxs-lookup"><span data-stu-id="98b57-116">index</span></span>  <br/> |<span data-ttu-id="98b57-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="98b57-117">int, not null</span></span>  <br/> |<span data-ttu-id="98b57-118">Clasificación.</span><span class="sxs-lookup"><span data-stu-id="98b57-118">Index.</span></span> <span data-ttu-id="98b57-119">El valor de las afiliaciones automáticas es de-1 y para las otras afiliaciones que aumenta secuencialmente de 1 en cada \<PrincipalID, affiliationId\> bucket.</span><span class="sxs-lookup"><span data-stu-id="98b57-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="98b57-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="98b57-120">updatedBy</span></span>  <br/> |<span data-ttu-id="98b57-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="98b57-121">int, not null</span></span>  <br/> |<span data-ttu-id="98b57-122">Principal que realizó la actualización más reciente.</span><span class="sxs-lookup"><span data-stu-id="98b57-122">Principal that did the latest update.</span></span> <span data-ttu-id="98b57-123">Esto suele ser 1, que significa sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98b57-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="98b57-124">**Sus**</span><span class="sxs-lookup"><span data-stu-id="98b57-124">**Keys**</span></span>

|<span data-ttu-id="98b57-125">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="98b57-125">**Columns**</span></span>|<span data-ttu-id="98b57-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="98b57-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98b57-127">\<principalID, Indice, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="98b57-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="98b57-128">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="98b57-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="98b57-129">principalID</span><span class="sxs-lookup"><span data-stu-id="98b57-129">principalID</span></span>  <br/> |<span data-ttu-id="98b57-130">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="98b57-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="98b57-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="98b57-131">affiliationID</span></span>  <br/> |<span data-ttu-id="98b57-132">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="98b57-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

