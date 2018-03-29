---
title: Tabla IMReportSummary en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable proporciona un informe general sobre la celebrada en una organización de sesiones de mensajería instantánea. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: f716a7406f4cf3562e2fa9244e8a766ef8537f53
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c78fa-104">Tabla IMReportSummary en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c78fa-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c78fa-105">El IMReportSummaryTable proporciona un informe general sobre la celebrada en una organización de sesiones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="c78fa-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="c78fa-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c78fa-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c78fa-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c78fa-107">**Column**</span></span>|<span data-ttu-id="c78fa-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c78fa-108">**Data Type**</span></span>|<span data-ttu-id="c78fa-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="c78fa-109">**Key/Index**</span></span>|<span data-ttu-id="c78fa-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c78fa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c78fa-111">**Hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="c78fa-111">**StartTime**</span></span> <br/> |<span data-ttu-id="c78fa-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c78fa-112">datetime</span></span>  <br/> |<span data-ttu-id="c78fa-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c78fa-113">Primary</span></span>  <br/> |<span data-ttu-id="c78fa-114">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="c78fa-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="c78fa-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="c78fa-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="c78fa-116">Char (1)</span><span class="sxs-lookup"><span data-stu-id="c78fa-116">char(1)</span></span>  <br/> |<span data-ttu-id="c78fa-117">Primary</span><span class="sxs-lookup"><span data-stu-id="c78fa-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="c78fa-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="c78fa-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="c78fa-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="c78fa-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="c78fa-120">Primary</span><span class="sxs-lookup"><span data-stu-id="c78fa-120">Primary</span></span>  <br/> |<span data-ttu-id="c78fa-121">Nombre de dominio completo del grupo host de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c78fa-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="c78fa-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="c78fa-122">**AuthType**</span></span> <br/> |<span data-ttu-id="c78fa-123">int</span><span class="sxs-lookup"><span data-stu-id="c78fa-123">int</span></span>  <br/> |<span data-ttu-id="c78fa-124">Primary</span><span class="sxs-lookup"><span data-stu-id="c78fa-124">Primary</span></span>  <br/> |<span data-ttu-id="c78fa-125">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c78fa-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="c78fa-126">Información de prioridad se almacena en la [tabla CallPriorities en Skype para Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="c78fa-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="c78fa-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="c78fa-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="c78fa-128">bigint</span><span class="sxs-lookup"><span data-stu-id="c78fa-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="c78fa-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="c78fa-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="c78fa-130">bigint</span><span class="sxs-lookup"><span data-stu-id="c78fa-130">bigint</span></span>  <br/> ||<span data-ttu-id="c78fa-131">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="c78fa-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

