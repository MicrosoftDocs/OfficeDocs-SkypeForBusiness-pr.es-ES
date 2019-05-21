---
title: Tabla IMReportSummary en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea que se mantienen en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296129"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="dc584-104">Tabla IMReportSummary en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc584-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dc584-105">El IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea que se mantienen en una organización.</span><span class="sxs-lookup"><span data-stu-id="dc584-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="dc584-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc584-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="dc584-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dc584-107">**Column**</span></span>|<span data-ttu-id="dc584-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="dc584-108">**Data Type**</span></span>|<span data-ttu-id="dc584-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="dc584-109">**Key/Index**</span></span>|<span data-ttu-id="dc584-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="dc584-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc584-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="dc584-111">**StartTime**</span></span> <br/> |<span data-ttu-id="dc584-112">datetime</span><span class="sxs-lookup"><span data-stu-id="dc584-112">datetime</span></span>  <br/> |<span data-ttu-id="dc584-113">Primary</span><span class="sxs-lookup"><span data-stu-id="dc584-113">Primary</span></span>  <br/> |<span data-ttu-id="dc584-114">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="dc584-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="dc584-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="dc584-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="dc584-116">Char (1)</span><span class="sxs-lookup"><span data-stu-id="dc584-116">char(1)</span></span>  <br/> |<span data-ttu-id="dc584-117">Primary</span><span class="sxs-lookup"><span data-stu-id="dc584-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="dc584-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="dc584-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="dc584-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="dc584-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="dc584-120">Primary</span><span class="sxs-lookup"><span data-stu-id="dc584-120">Primary</span></span>  <br/> |<span data-ttu-id="dc584-121">Nombre de dominio completo del grupo que hospeda la sesión.</span><span class="sxs-lookup"><span data-stu-id="dc584-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="dc584-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="dc584-122">**AuthType**</span></span> <br/> |<span data-ttu-id="dc584-123">int</span><span class="sxs-lookup"><span data-stu-id="dc584-123">int</span></span>  <br/> |<span data-ttu-id="dc584-124">Primary</span><span class="sxs-lookup"><span data-stu-id="dc584-124">Primary</span></span>  <br/> |<span data-ttu-id="dc584-125">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="dc584-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="dc584-126">La información de prioridad se almacena en la [tabla CallPriorities en Skype empresarial Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="dc584-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="dc584-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="dc584-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="dc584-128">BIGINT</span><span class="sxs-lookup"><span data-stu-id="dc584-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="dc584-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="dc584-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="dc584-130">BIGINT</span><span class="sxs-lookup"><span data-stu-id="dc584-130">bigint</span></span>  <br/> ||<span data-ttu-id="dc584-131">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="dc584-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

