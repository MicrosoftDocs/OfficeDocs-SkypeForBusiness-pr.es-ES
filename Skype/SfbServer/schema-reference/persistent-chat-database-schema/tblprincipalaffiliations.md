---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815870"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="95753-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="95753-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="95753-104">tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="95753-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="95753-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="95753-105">**Columns**</span></span>

|<span data-ttu-id="95753-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="95753-106">**Column**</span></span>|<span data-ttu-id="95753-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="95753-107">**Type**</span></span>|<span data-ttu-id="95753-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="95753-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95753-109">principalID</span><span class="sxs-lookup"><span data-stu-id="95753-109">principalID</span></span>  <br/> |<span data-ttu-id="95753-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="95753-110">int, not null</span></span>  <br/> |<span data-ttu-id="95753-111">Id. de la entidad de seguridad afiliada.</span><span class="sxs-lookup"><span data-stu-id="95753-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="95753-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="95753-112">affiliationID</span></span>  <br/> |<span data-ttu-id="95753-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="95753-113">int, not null</span></span>  <br/> |<span data-ttu-id="95753-p101">Id. de la entidad de seguridad que representa la afiliación. Todas las entidades de seguridad (excepto system-user-types) tienen también una afiliación propia.</span><span class="sxs-lookup"><span data-stu-id="95753-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="95753-116">index</span><span class="sxs-lookup"><span data-stu-id="95753-116">index</span></span>  <br/> |<span data-ttu-id="95753-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="95753-117">int, not null</span></span>  <br/> |<span data-ttu-id="95753-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="95753-118">Index.</span></span> <span data-ttu-id="95753-119">El valor de las afiliaciones automáticas es -1 y para las demás afiliaciones aumenta secuencialmente de 1 dentro de cada \<principalID, affiliationId\> depósito.</span><span class="sxs-lookup"><span data-stu-id="95753-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="95753-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="95753-120">updatedBy</span></span>  <br/> |<span data-ttu-id="95753-121">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="95753-121">int, not null</span></span>  <br/> |<span data-ttu-id="95753-p103">Entidad de seguridad que realizó la actualización más reciente. Suele ser 1, lo que significa sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="95753-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="95753-124">**Keys**</span><span class="sxs-lookup"><span data-stu-id="95753-124">**Keys**</span></span>

|<span data-ttu-id="95753-125">**Columns**</span><span class="sxs-lookup"><span data-stu-id="95753-125">**Columns**</span></span>|<span data-ttu-id="95753-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="95753-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="95753-127">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="95753-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="95753-128">principalID</span><span class="sxs-lookup"><span data-stu-id="95753-128">principalID</span></span>  <br/> |<span data-ttu-id="95753-129">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="95753-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="95753-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="95753-130">affiliationID</span></span>  <br/> |<span data-ttu-id="95753-131">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="95753-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

