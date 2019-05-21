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
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último identificador de invitación generado (y usado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295359"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="6d407-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="6d407-103">tblLastInviteId</span></span>
 
<span data-ttu-id="6d407-104">tblLastInviteId contiene el último identificador de invitación generado (y usado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="6d407-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="6d407-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="6d407-105">**Columns**</span></span>

|<span data-ttu-id="6d407-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6d407-106">**Column**</span></span>|<span data-ttu-id="6d407-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6d407-107">**Type**</span></span>|<span data-ttu-id="6d407-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6d407-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d407-109">prinID</span><span class="sxs-lookup"><span data-stu-id="6d407-109">prinID</span></span>  <br/> |<span data-ttu-id="6d407-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="6d407-110">int, not null</span></span>  <br/> |<span data-ttu-id="6d407-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="6d407-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6d407-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="6d407-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="6d407-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="6d407-113">int, not null</span></span>  <br/> |<span data-ttu-id="6d407-114">Último ID de invitación usado.</span><span class="sxs-lookup"><span data-stu-id="6d407-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="6d407-115">**Sus**</span><span class="sxs-lookup"><span data-stu-id="6d407-115">**Keys**</span></span>

|<span data-ttu-id="6d407-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6d407-116">**Column**</span></span>|<span data-ttu-id="6d407-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6d407-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d407-118">prinID</span><span class="sxs-lookup"><span data-stu-id="6d407-118">prinID</span></span>  <br/> |<span data-ttu-id="6d407-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="6d407-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6d407-120">prinID</span><span class="sxs-lookup"><span data-stu-id="6d407-120">prinID</span></span>  <br/> |<span data-ttu-id="6d407-121">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="6d407-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6d407-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d407-122">See also</span></span>

[<span data-ttu-id="6d407-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="6d407-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
