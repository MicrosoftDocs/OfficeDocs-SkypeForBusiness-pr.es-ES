---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias de la entidad principal.
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831600"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="9dd66-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="9dd66-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="9dd66-104">tblPrincipalMembers contiene pertenencias de la entidad principal.</span><span class="sxs-lookup"><span data-stu-id="9dd66-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="9dd66-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9dd66-105">**Columns**</span></span>

|<span data-ttu-id="9dd66-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9dd66-106">**Column**</span></span>|<span data-ttu-id="9dd66-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9dd66-107">**Type**</span></span>|<span data-ttu-id="9dd66-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9dd66-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9dd66-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9dd66-109">prinID</span></span>  <br/> |<span data-ttu-id="9dd66-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="9dd66-110">int, not null</span></span>  <br/> |<span data-ttu-id="9dd66-111">Id. de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="9dd66-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9dd66-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="9dd66-112">memberADPath</span></span>  <br/> |<span data-ttu-id="9dd66-113">nvarchar (384), no NULL</span><span class="sxs-lookup"><span data-stu-id="9dd66-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="9dd66-p101">Nombre distintivo de un miembro. Un miembro no tiene por qué ser una entidad principal (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="9dd66-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="9dd66-116">**Keys**</span><span class="sxs-lookup"><span data-stu-id="9dd66-116">**Keys**</span></span>

|<span data-ttu-id="9dd66-117">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9dd66-117">**Column**</span></span>|<span data-ttu-id="9dd66-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9dd66-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="9dd66-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9dd66-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9dd66-120">prinID</span><span class="sxs-lookup"><span data-stu-id="9dd66-120">prinID</span></span>  <br/> |<span data-ttu-id="9dd66-121">Clave externa con búsqueda en tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="9dd66-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

