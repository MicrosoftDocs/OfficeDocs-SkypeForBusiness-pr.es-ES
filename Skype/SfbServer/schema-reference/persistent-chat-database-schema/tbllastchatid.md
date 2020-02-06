---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814588"
---
# <a name="tbllastchatid"></a><span data-ttu-id="a5dec-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="a5dec-103">tblLastChatId</span></span>
 
<span data-ttu-id="a5dec-104">tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="a5dec-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="a5dec-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="a5dec-105">**Columns**</span></span>

|<span data-ttu-id="a5dec-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a5dec-106">**Column**</span></span>|<span data-ttu-id="a5dec-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a5dec-107">**Type**</span></span>|<span data-ttu-id="a5dec-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5dec-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a5dec-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="a5dec-109">nodeID</span></span>  <br/> |<span data-ttu-id="a5dec-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="a5dec-110">int, not null</span></span>  <br/> |<span data-ttu-id="a5dec-111">IDENTIFICADOR de nodo (solo tipo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="a5dec-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="a5dec-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="a5dec-112">lastChatID</span></span>  <br/> |<span data-ttu-id="a5dec-113">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="a5dec-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="a5dec-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="a5dec-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="a5dec-115">**Sus**</span><span class="sxs-lookup"><span data-stu-id="a5dec-115">**Keys**</span></span>

|<span data-ttu-id="a5dec-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a5dec-116">**Column**</span></span>|<span data-ttu-id="a5dec-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a5dec-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a5dec-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="a5dec-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="a5dec-119">Clave principal (solo nodeID es suficiente para procesar).</span><span class="sxs-lookup"><span data-stu-id="a5dec-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="a5dec-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="a5dec-120">nodeID</span></span>  <br/> |<span data-ttu-id="a5dec-121">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="a5dec-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a5dec-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5dec-122">See also</span></span>

[<span data-ttu-id="a5dec-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="a5dec-123">tblChat</span></span>](tblchat.md)
