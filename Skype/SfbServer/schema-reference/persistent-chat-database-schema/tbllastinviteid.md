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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212561"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="70fe7-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="70fe7-103">tblLastInviteId</span></span>
 
<span data-ttu-id="70fe7-104">tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="70fe7-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="70fe7-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="70fe7-105">**Columns**</span></span>

|<span data-ttu-id="70fe7-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="70fe7-106">**Column**</span></span>|<span data-ttu-id="70fe7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="70fe7-107">**Type**</span></span>|<span data-ttu-id="70fe7-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="70fe7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70fe7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="70fe7-109">prinID</span></span>  <br/> |<span data-ttu-id="70fe7-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="70fe7-110">int, not null</span></span>  <br/> |<span data-ttu-id="70fe7-111">Identificador de entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="70fe7-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="70fe7-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="70fe7-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="70fe7-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="70fe7-113">int, not null</span></span>  <br/> |<span data-ttu-id="70fe7-114">Último identificador de invitación usado.</span><span class="sxs-lookup"><span data-stu-id="70fe7-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="70fe7-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="70fe7-115">**Keys**</span></span>

|<span data-ttu-id="70fe7-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="70fe7-116">**Column**</span></span>|<span data-ttu-id="70fe7-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="70fe7-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70fe7-118">prinID</span><span class="sxs-lookup"><span data-stu-id="70fe7-118">prinID</span></span>  <br/> |<span data-ttu-id="70fe7-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="70fe7-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="70fe7-120">prinID</span><span class="sxs-lookup"><span data-stu-id="70fe7-120">prinID</span></span>  <br/> |<span data-ttu-id="70fe7-121">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="70fe7-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="70fe7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="70fe7-122">See also</span></span>

[<span data-ttu-id="70fe7-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="70fe7-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
