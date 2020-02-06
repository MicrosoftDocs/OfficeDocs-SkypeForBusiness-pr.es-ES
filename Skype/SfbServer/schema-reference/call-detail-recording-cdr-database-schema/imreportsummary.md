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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea que se mantienen en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815148"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f3fce-104">Tabla IMReportSummary en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="f3fce-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f3fce-105">El IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea que se mantienen en una organización.</span><span class="sxs-lookup"><span data-stu-id="f3fce-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="f3fce-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3fce-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f3fce-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f3fce-107">**Column**</span></span>|<span data-ttu-id="f3fce-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f3fce-108">**Data Type**</span></span>|<span data-ttu-id="f3fce-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="f3fce-109">**Key/Index**</span></span>|<span data-ttu-id="f3fce-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="f3fce-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3fce-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="f3fce-111">**StartTime**</span></span> <br/> |<span data-ttu-id="f3fce-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f3fce-112">datetime</span></span>  <br/> |<span data-ttu-id="f3fce-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f3fce-113">Primary</span></span>  <br/> |<span data-ttu-id="f3fce-114">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="f3fce-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="f3fce-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="f3fce-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="f3fce-116">Char (1)</span><span class="sxs-lookup"><span data-stu-id="f3fce-116">char(1)</span></span>  <br/> |<span data-ttu-id="f3fce-117">Primary</span><span class="sxs-lookup"><span data-stu-id="f3fce-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="f3fce-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="f3fce-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="f3fce-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="f3fce-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="f3fce-120">Primary</span><span class="sxs-lookup"><span data-stu-id="f3fce-120">Primary</span></span>  <br/> |<span data-ttu-id="f3fce-121">Nombre de dominio completo del grupo que hospeda la sesión.</span><span class="sxs-lookup"><span data-stu-id="f3fce-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="f3fce-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="f3fce-122">**AuthType**</span></span> <br/> |<span data-ttu-id="f3fce-123">int</span><span class="sxs-lookup"><span data-stu-id="f3fce-123">int</span></span>  <br/> |<span data-ttu-id="f3fce-124">Primary</span><span class="sxs-lookup"><span data-stu-id="f3fce-124">Primary</span></span>  <br/> |<span data-ttu-id="f3fce-125">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f3fce-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="f3fce-126">La información de prioridad se almacena en la [tabla CallPriorities en Skype empresarial Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="f3fce-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="f3fce-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="f3fce-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="f3fce-128">BIGINT</span><span class="sxs-lookup"><span data-stu-id="f3fce-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="f3fce-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="f3fce-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="f3fce-130">BIGINT</span><span class="sxs-lookup"><span data-stu-id="f3fce-130">bigint</span></span>  <br/> ||<span data-ttu-id="f3fce-131">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="f3fce-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

