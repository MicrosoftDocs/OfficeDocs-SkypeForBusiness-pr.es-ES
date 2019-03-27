---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias de la entidad de seguridad.
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874255"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="3204d-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="3204d-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="3204d-104">tblPrincipalMembers contiene pertenencias de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3204d-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="3204d-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="3204d-105">**Columns**</span></span>

|<span data-ttu-id="3204d-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3204d-106">**Column**</span></span>|<span data-ttu-id="3204d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3204d-107">**Type**</span></span>|<span data-ttu-id="3204d-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3204d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3204d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3204d-109">prinID</span></span>  <br/> |<span data-ttu-id="3204d-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="3204d-110">int, not null</span></span>  <br/> |<span data-ttu-id="3204d-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3204d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3204d-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="3204d-112">memberADPath</span></span>  <br/> |<span data-ttu-id="3204d-113">nvarchar (384), no es nulo</span><span class="sxs-lookup"><span data-stu-id="3204d-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="3204d-114">Nombre distintivo (DN) de un miembro.</span><span class="sxs-lookup"><span data-stu-id="3204d-114">Distinguished name of a member.</span></span> <span data-ttu-id="3204d-115">Un miembro no tiene que ser una entidad de seguridad (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="3204d-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="3204d-116">**Claves**</span><span class="sxs-lookup"><span data-stu-id="3204d-116">**Keys**</span></span>

|<span data-ttu-id="3204d-117">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3204d-117">**Column**</span></span>|<span data-ttu-id="3204d-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3204d-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3204d-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="3204d-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="3204d-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="3204d-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3204d-121">prinID</span><span class="sxs-lookup"><span data-stu-id="3204d-121">prinID</span></span>  <br/> |<span data-ttu-id="3204d-122">Clave externa con búsqueda en tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="3204d-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

