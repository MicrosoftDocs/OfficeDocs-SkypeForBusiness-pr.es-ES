---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias de la entidad de seguridad.
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904163"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="63fb0-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="63fb0-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="63fb0-104">tblPrincipalMembers contiene pertenencias de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="63fb0-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="63fb0-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="63fb0-105">**Columns**</span></span>

|<span data-ttu-id="63fb0-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="63fb0-106">**Column**</span></span>|<span data-ttu-id="63fb0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="63fb0-107">**Type**</span></span>|<span data-ttu-id="63fb0-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="63fb0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63fb0-109">prinID</span><span class="sxs-lookup"><span data-stu-id="63fb0-109">prinID</span></span>  <br/> |<span data-ttu-id="63fb0-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="63fb0-110">int, not null</span></span>  <br/> |<span data-ttu-id="63fb0-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="63fb0-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="63fb0-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="63fb0-112">memberADPath</span></span>  <br/> |<span data-ttu-id="63fb0-113">nvarchar (384), no es nulo</span><span class="sxs-lookup"><span data-stu-id="63fb0-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="63fb0-114">Nombre distintivo (DN) de un miembro.</span><span class="sxs-lookup"><span data-stu-id="63fb0-114">Distinguished name of a member.</span></span> <span data-ttu-id="63fb0-115">Un miembro no tiene que ser una entidad de seguridad (en la tabla tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="63fb0-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="63fb0-116">**Claves**</span><span class="sxs-lookup"><span data-stu-id="63fb0-116">**Keys**</span></span>

|<span data-ttu-id="63fb0-117">**Columna**</span><span class="sxs-lookup"><span data-stu-id="63fb0-117">**Column**</span></span>|<span data-ttu-id="63fb0-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="63fb0-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63fb0-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="63fb0-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="63fb0-120">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="63fb0-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="63fb0-121">prinID</span><span class="sxs-lookup"><span data-stu-id="63fb0-121">prinID</span></span>  <br/> |<span data-ttu-id="63fb0-122">Clave externa con búsqueda en tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="63fb0-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

