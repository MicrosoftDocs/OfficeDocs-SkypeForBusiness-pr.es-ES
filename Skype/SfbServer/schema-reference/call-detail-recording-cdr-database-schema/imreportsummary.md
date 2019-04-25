---
title: Tabla IMReportSummary en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable proporciona un informe general en la se conserva en una organización de las sesiones de mensajería instantánea. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213035"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fba81-104">Tabla IMReportSummary en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fba81-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fba81-105">El IMReportSummaryTable proporciona un informe general en la se conserva en una organización de las sesiones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="fba81-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="fba81-106">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fba81-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fba81-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fba81-107">**Column**</span></span>|<span data-ttu-id="fba81-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fba81-108">**Data Type**</span></span>|<span data-ttu-id="fba81-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="fba81-109">**Key/Index**</span></span>|<span data-ttu-id="fba81-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="fba81-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fba81-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="fba81-111">**StartTime**</span></span> <br/> |<span data-ttu-id="fba81-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fba81-112">datetime</span></span>  <br/> |<span data-ttu-id="fba81-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fba81-113">Primary</span></span>  <br/> |<span data-ttu-id="fba81-114">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="fba81-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="fba81-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="fba81-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="fba81-116">Char (1)</span><span class="sxs-lookup"><span data-stu-id="fba81-116">char(1)</span></span>  <br/> |<span data-ttu-id="fba81-117">Primary</span><span class="sxs-lookup"><span data-stu-id="fba81-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="fba81-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="fba81-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="fba81-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="fba81-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="fba81-120">Primary</span><span class="sxs-lookup"><span data-stu-id="fba81-120">Primary</span></span>  <br/> |<span data-ttu-id="fba81-121">Nombre de dominio completo del grupo de servidores que hospeda la sesión.</span><span class="sxs-lookup"><span data-stu-id="fba81-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="fba81-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="fba81-122">**AuthType**</span></span> <br/> |<span data-ttu-id="fba81-123">int</span><span class="sxs-lookup"><span data-stu-id="fba81-123">int</span></span>  <br/> |<span data-ttu-id="fba81-124">Primary</span><span class="sxs-lookup"><span data-stu-id="fba81-124">Primary</span></span>  <br/> |<span data-ttu-id="fba81-125">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fba81-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="fba81-126">Información de prioridad se almacena en la [tabla CallPriorities en Skype para Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="fba81-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="fba81-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="fba81-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="fba81-128">bigint</span><span class="sxs-lookup"><span data-stu-id="fba81-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="fba81-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="fba81-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="fba81-130">bigint</span><span class="sxs-lookup"><span data-stu-id="fba81-130">bigint</span></span>  <br/> ||<span data-ttu-id="fba81-131">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="fba81-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

