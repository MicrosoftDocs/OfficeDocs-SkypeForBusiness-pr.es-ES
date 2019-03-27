---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873940"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="0e333-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="0e333-103">tblLastInviteId</span></span>
 
<span data-ttu-id="0e333-104">tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="0e333-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="0e333-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="0e333-105">**Columns**</span></span>

|<span data-ttu-id="0e333-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0e333-106">**Column**</span></span>|<span data-ttu-id="0e333-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0e333-107">**Type**</span></span>|<span data-ttu-id="0e333-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0e333-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e333-109">prinID</span><span class="sxs-lookup"><span data-stu-id="0e333-109">prinID</span></span>  <br/> |<span data-ttu-id="0e333-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="0e333-110">int, not null</span></span>  <br/> |<span data-ttu-id="0e333-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e333-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="0e333-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="0e333-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="0e333-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="0e333-113">int, not null</span></span>  <br/> |<span data-ttu-id="0e333-114">Último identificador de invitación usado.</span><span class="sxs-lookup"><span data-stu-id="0e333-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="0e333-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="0e333-115">**Keys**</span></span>

|<span data-ttu-id="0e333-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0e333-116">**Column**</span></span>|<span data-ttu-id="0e333-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0e333-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e333-118">prinID</span><span class="sxs-lookup"><span data-stu-id="0e333-118">prinID</span></span>  <br/> |<span data-ttu-id="0e333-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="0e333-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0e333-120">prinID</span><span class="sxs-lookup"><span data-stu-id="0e333-120">prinID</span></span>  <br/> |<span data-ttu-id="0e333-121">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="0e333-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0e333-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e333-122">See also</span></span>

[<span data-ttu-id="0e333-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="0e333-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
