---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último ID de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a><span data-ttu-id="8f8e4-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="8f8e4-103">tblLastInviteId</span></span>
 
<span data-ttu-id="8f8e4-104">tblLastInviteId contiene el último ID de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="8f8e4-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="8f8e4-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="8f8e4-105">**Columns**</span></span>

|<span data-ttu-id="8f8e4-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8f8e4-106">**Column**</span></span>|<span data-ttu-id="8f8e4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8f8e4-107">**Type**</span></span>|<span data-ttu-id="8f8e4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8f8e4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f8e4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="8f8e4-109">prinID</span></span>  <br/> |<span data-ttu-id="8f8e4-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="8f8e4-110">int, not null</span></span>  <br/> |<span data-ttu-id="8f8e4-111">Id. principal</span><span class="sxs-lookup"><span data-stu-id="8f8e4-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8f8e4-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="8f8e4-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="8f8e4-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="8f8e4-113">int, not null</span></span>  <br/> |<span data-ttu-id="8f8e4-114">ID de invitación utilizados anterior.</span><span class="sxs-lookup"><span data-stu-id="8f8e4-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="8f8e4-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="8f8e4-115">**Keys**</span></span>

|<span data-ttu-id="8f8e4-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8f8e4-116">**Column**</span></span>|<span data-ttu-id="8f8e4-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8f8e4-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f8e4-118">prinID</span><span class="sxs-lookup"><span data-stu-id="8f8e4-118">prinID</span></span>  <br/> |<span data-ttu-id="8f8e4-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="8f8e4-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8f8e4-120">prinID</span><span class="sxs-lookup"><span data-stu-id="8f8e4-120">prinID</span></span>  <br/> |<span data-ttu-id="8f8e4-121">Clave externa con la búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="8f8e4-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8f8e4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f8e4-122">See also</span></span>

#### 

[<span data-ttu-id="8f8e4-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="8f8e4-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)

