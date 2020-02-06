---
title: Tabla CallPriorities en Skype empresarial Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como ' Emergency ', ' urgente ' o ' normal '.
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815448"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="55447-103">Tabla CallPriorities en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="55447-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55447-104">La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como ' Emergency ', ' urgente ' o ' normal '.</span><span class="sxs-lookup"><span data-stu-id="55447-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="55447-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="55447-105">**Column**</span></span>|<span data-ttu-id="55447-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="55447-106">**Data Type**</span></span>|<span data-ttu-id="55447-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="55447-107">**Key/Index**</span></span>|<span data-ttu-id="55447-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="55447-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55447-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="55447-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="55447-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="55447-110">tinyint</span></span>  <br/> |<span data-ttu-id="55447-111">Primary</span><span class="sxs-lookup"><span data-stu-id="55447-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="55447-112">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="55447-112">**Priority**</span></span> <br/> |<span data-ttu-id="55447-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="55447-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="55447-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="55447-114">Allowed values:</span></span> <br/>  <span data-ttu-id="55447-115">0: desconocido</span><span class="sxs-lookup"><span data-stu-id="55447-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="55447-116">1: no urgente</span><span class="sxs-lookup"><span data-stu-id="55447-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="55447-117">2-normal</span><span class="sxs-lookup"><span data-stu-id="55447-117">2 - Normal</span></span> <br/>  <span data-ttu-id="55447-118">3-urgente</span><span class="sxs-lookup"><span data-stu-id="55447-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="55447-119">4-emergencia</span><span class="sxs-lookup"><span data-stu-id="55447-119">4 - Emergency</span></span> <br/> |
   

