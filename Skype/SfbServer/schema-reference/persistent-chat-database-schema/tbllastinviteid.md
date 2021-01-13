---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815970"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="fc9ce-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="fc9ce-103">tblLastInviteId</span></span>
 
<span data-ttu-id="fc9ce-104">tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="fc9ce-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="fc9ce-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="fc9ce-105">**Columns**</span></span>

|<span data-ttu-id="fc9ce-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fc9ce-106">**Column**</span></span>|<span data-ttu-id="fc9ce-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fc9ce-107">**Type**</span></span>|<span data-ttu-id="fc9ce-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fc9ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fc9ce-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fc9ce-109">prinID</span></span>  <br/> |<span data-ttu-id="fc9ce-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="fc9ce-110">int, not null</span></span>  <br/> |<span data-ttu-id="fc9ce-111">Id. de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fc9ce-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fc9ce-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="fc9ce-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="fc9ce-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="fc9ce-113">int, not null</span></span>  <br/> |<span data-ttu-id="fc9ce-114">Identificador de invitación usado por última vez.</span><span class="sxs-lookup"><span data-stu-id="fc9ce-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="fc9ce-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="fc9ce-115">**Keys**</span></span>

|<span data-ttu-id="fc9ce-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fc9ce-116">**Column**</span></span>|<span data-ttu-id="fc9ce-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fc9ce-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc9ce-118">prinID</span><span class="sxs-lookup"><span data-stu-id="fc9ce-118">prinID</span></span>  <br/> |<span data-ttu-id="fc9ce-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="fc9ce-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fc9ce-120">prinID</span><span class="sxs-lookup"><span data-stu-id="fc9ce-120">prinID</span></span>  <br/> |<span data-ttu-id="fc9ce-121">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="fc9ce-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fc9ce-122">Ver también</span><span class="sxs-lookup"><span data-stu-id="fc9ce-122">See also</span></span>

[<span data-ttu-id="fc9ce-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="fc9ce-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
