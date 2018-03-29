---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias a principales.
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="7bbcc-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="7bbcc-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="7bbcc-104">tblPrincipalMembers contiene pertenencias a principales.</span><span class="sxs-lookup"><span data-stu-id="7bbcc-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="7bbcc-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="7bbcc-105">**Columns**</span></span>

|<span data-ttu-id="7bbcc-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7bbcc-106">**Column**</span></span>|<span data-ttu-id="7bbcc-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7bbcc-107">**Type**</span></span>|<span data-ttu-id="7bbcc-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7bbcc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7bbcc-109">prinID</span><span class="sxs-lookup"><span data-stu-id="7bbcc-109">prinID</span></span>  <br/> |<span data-ttu-id="7bbcc-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="7bbcc-110">int, not null</span></span>  <br/> |<span data-ttu-id="7bbcc-111">Id. principal</span><span class="sxs-lookup"><span data-stu-id="7bbcc-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="7bbcc-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="7bbcc-112">memberADPath</span></span>  <br/> |<span data-ttu-id="7bbcc-113">nvarchar (384), no nulo</span><span class="sxs-lookup"><span data-stu-id="7bbcc-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="7bbcc-114">Nombre completo de un miembro.</span><span class="sxs-lookup"><span data-stu-id="7bbcc-114">Distinguished name of a member.</span></span> <span data-ttu-id="7bbcc-115">No tiene un miembro sea un principal (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="7bbcc-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="7bbcc-116">**Claves**</span><span class="sxs-lookup"><span data-stu-id="7bbcc-116">**Keys**</span></span>

|<span data-ttu-id="7bbcc-117">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7bbcc-117">**Column**</span></span>|<span data-ttu-id="7bbcc-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7bbcc-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7bbcc-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="7bbcc-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="7bbcc-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="7bbcc-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7bbcc-121">prinID</span><span class="sxs-lookup"><span data-stu-id="7bbcc-121">prinID</span></span>  <br/> |<span data-ttu-id="7bbcc-122">Clave externa con la búsqueda en tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="7bbcc-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

