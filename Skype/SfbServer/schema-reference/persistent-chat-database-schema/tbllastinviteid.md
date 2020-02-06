---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último identificador de invitación generado (y usado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814578"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="080e1-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="080e1-103">tblLastInviteId</span></span>
 
<span data-ttu-id="080e1-104">tblLastInviteId contiene el último identificador de invitación generado (y usado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="080e1-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="080e1-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="080e1-105">**Columns**</span></span>

|<span data-ttu-id="080e1-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="080e1-106">**Column**</span></span>|<span data-ttu-id="080e1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="080e1-107">**Type**</span></span>|<span data-ttu-id="080e1-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="080e1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="080e1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="080e1-109">prinID</span></span>  <br/> |<span data-ttu-id="080e1-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="080e1-110">int, not null</span></span>  <br/> |<span data-ttu-id="080e1-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="080e1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="080e1-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="080e1-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="080e1-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="080e1-113">int, not null</span></span>  <br/> |<span data-ttu-id="080e1-114">Último ID de invitación usado.</span><span class="sxs-lookup"><span data-stu-id="080e1-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="080e1-115">**Sus**</span><span class="sxs-lookup"><span data-stu-id="080e1-115">**Keys**</span></span>

|<span data-ttu-id="080e1-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="080e1-116">**Column**</span></span>|<span data-ttu-id="080e1-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="080e1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="080e1-118">prinID</span><span class="sxs-lookup"><span data-stu-id="080e1-118">prinID</span></span>  <br/> |<span data-ttu-id="080e1-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="080e1-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="080e1-120">prinID</span><span class="sxs-lookup"><span data-stu-id="080e1-120">prinID</span></span>  <br/> |<span data-ttu-id="080e1-121">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="080e1-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="080e1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="080e1-122">See also</span></span>

[<span data-ttu-id="080e1-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="080e1-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
