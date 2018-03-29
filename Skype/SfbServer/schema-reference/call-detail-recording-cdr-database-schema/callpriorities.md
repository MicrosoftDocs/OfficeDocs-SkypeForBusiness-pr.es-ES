---
title: Tabla CallPriorities en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabla CallPriorities es una tabla estática que almacena la lista de prioridades se puede llamar, como 'emergencia', 'urgente' o 'normal'.
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="80642-103">Tabla CallPriorities en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="80642-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="80642-104">La tabla CallPriorities es una tabla estática que almacena la lista de prioridades se puede llamar, como 'emergencia', 'urgente' o 'normal'.</span><span class="sxs-lookup"><span data-stu-id="80642-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="80642-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="80642-105">**Column**</span></span>|<span data-ttu-id="80642-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="80642-106">**Data Type**</span></span>|<span data-ttu-id="80642-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="80642-107">**Key/Index**</span></span>|<span data-ttu-id="80642-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="80642-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80642-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="80642-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="80642-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="80642-110">tinyint</span></span>  <br/> |<span data-ttu-id="80642-111">Primary</span><span class="sxs-lookup"><span data-stu-id="80642-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="80642-112">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="80642-112">**Priority**</span></span> <br/> |<span data-ttu-id="80642-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="80642-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="80642-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="80642-114">Allowed values:</span></span> <br/>  <span data-ttu-id="80642-115">0 - desconocido</span><span class="sxs-lookup"><span data-stu-id="80642-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="80642-116">1 - no urgente</span><span class="sxs-lookup"><span data-stu-id="80642-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="80642-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="80642-117">2 - Normal</span></span> <br/>  <span data-ttu-id="80642-118">3 - urgente</span><span class="sxs-lookup"><span data-stu-id="80642-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="80642-119">4 - emergencia</span><span class="sxs-lookup"><span data-stu-id="80642-119">4 - Emergency</span></span> <br/> |
   

