---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias principales.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295289"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="5a9b8-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="5a9b8-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="5a9b8-104">tblPrincipalMembers contiene pertenencias principales.</span><span class="sxs-lookup"><span data-stu-id="5a9b8-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="5a9b8-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5a9b8-105">**Columns**</span></span>

|<span data-ttu-id="5a9b8-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5a9b8-106">**Column**</span></span>|<span data-ttu-id="5a9b8-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5a9b8-107">**Type**</span></span>|<span data-ttu-id="5a9b8-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5a9b8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a9b8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5a9b8-109">prinID</span></span>  <br/> |<span data-ttu-id="5a9b8-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="5a9b8-110">int, not null</span></span>  <br/> |<span data-ttu-id="5a9b8-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="5a9b8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5a9b8-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="5a9b8-112">memberADPath</span></span>  <br/> |<span data-ttu-id="5a9b8-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="5a9b8-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="5a9b8-114">Nombre distintivo de un miembro.</span><span class="sxs-lookup"><span data-stu-id="5a9b8-114">Distinguished name of a member.</span></span> <span data-ttu-id="5a9b8-115">Un miembro no tiene que ser un principal (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="5a9b8-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="5a9b8-116">**Sus**</span><span class="sxs-lookup"><span data-stu-id="5a9b8-116">**Keys**</span></span>

|<span data-ttu-id="5a9b8-117">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5a9b8-117">**Column**</span></span>|<span data-ttu-id="5a9b8-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5a9b8-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5a9b8-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="5a9b8-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="5a9b8-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5a9b8-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5a9b8-121">prinID</span><span class="sxs-lookup"><span data-stu-id="5a9b8-121">prinID</span></span>  <br/> |<span data-ttu-id="5a9b8-122">Clave externa con la búsqueda en tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="5a9b8-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

