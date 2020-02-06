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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias principales.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813948"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="f8794-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="f8794-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="f8794-104">tblPrincipalMembers contiene pertenencias principales.</span><span class="sxs-lookup"><span data-stu-id="f8794-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="f8794-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="f8794-105">**Columns**</span></span>

|<span data-ttu-id="f8794-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f8794-106">**Column**</span></span>|<span data-ttu-id="f8794-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f8794-107">**Type**</span></span>|<span data-ttu-id="f8794-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f8794-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f8794-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f8794-109">prinID</span></span>  <br/> |<span data-ttu-id="f8794-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f8794-110">int, not null</span></span>  <br/> |<span data-ttu-id="f8794-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="f8794-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f8794-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="f8794-112">memberADPath</span></span>  <br/> |<span data-ttu-id="f8794-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="f8794-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="f8794-114">Nombre distintivo de un miembro.</span><span class="sxs-lookup"><span data-stu-id="f8794-114">Distinguished name of a member.</span></span> <span data-ttu-id="f8794-115">Un miembro no tiene que ser un principal (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="f8794-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="f8794-116">**Sus**</span><span class="sxs-lookup"><span data-stu-id="f8794-116">**Keys**</span></span>

|<span data-ttu-id="f8794-117">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f8794-117">**Column**</span></span>|<span data-ttu-id="f8794-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f8794-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f8794-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="f8794-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="f8794-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f8794-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f8794-121">prinID</span><span class="sxs-lookup"><span data-stu-id="f8794-121">prinID</span></span>  <br/> |<span data-ttu-id="f8794-122">Clave externa con la búsqueda en tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="f8794-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

