---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929906"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="fe862-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="fe862-103">tblLastInviteId</span></span>
 
<span data-ttu-id="fe862-104">tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="fe862-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="fe862-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="fe862-105">**Columns**</span></span>

|<span data-ttu-id="fe862-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fe862-106">**Column**</span></span>|<span data-ttu-id="fe862-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fe862-107">**Type**</span></span>|<span data-ttu-id="fe862-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fe862-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe862-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fe862-109">prinID</span></span>  <br/> |<span data-ttu-id="fe862-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="fe862-110">int, not null</span></span>  <br/> |<span data-ttu-id="fe862-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fe862-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fe862-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="fe862-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="fe862-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="fe862-113">int, not null</span></span>  <br/> |<span data-ttu-id="fe862-114">Último identificador de invitación usado.</span><span class="sxs-lookup"><span data-stu-id="fe862-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="fe862-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="fe862-115">**Keys**</span></span>

|<span data-ttu-id="fe862-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fe862-116">**Column**</span></span>|<span data-ttu-id="fe862-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fe862-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe862-118">prinID</span><span class="sxs-lookup"><span data-stu-id="fe862-118">prinID</span></span>  <br/> |<span data-ttu-id="fe862-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="fe862-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fe862-120">prinID</span><span class="sxs-lookup"><span data-stu-id="fe862-120">prinID</span></span>  <br/> |<span data-ttu-id="fe862-121">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="fe862-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fe862-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe862-122">See also</span></span>

[<span data-ttu-id="fe862-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="fe862-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
