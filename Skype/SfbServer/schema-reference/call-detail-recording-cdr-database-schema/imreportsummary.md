---
title: Tabla IMReportSummary en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable proporciona un informe general en la se conserva en una organización de las sesiones de mensajería instantánea. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901048"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="23d4e-104">Tabla IMReportSummary en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="23d4e-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23d4e-105">El IMReportSummaryTable proporciona un informe general en la se conserva en una organización de las sesiones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="23d4e-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="23d4e-106">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d4e-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="23d4e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="23d4e-107">**Column**</span></span>|<span data-ttu-id="23d4e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="23d4e-108">**Data Type**</span></span>|<span data-ttu-id="23d4e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="23d4e-109">**Key/Index**</span></span>|<span data-ttu-id="23d4e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="23d4e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23d4e-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="23d4e-111">**StartTime**</span></span> <br/> |<span data-ttu-id="23d4e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="23d4e-112">datetime</span></span>  <br/> |<span data-ttu-id="23d4e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="23d4e-113">Primary</span></span>  <br/> |<span data-ttu-id="23d4e-114">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="23d4e-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="23d4e-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="23d4e-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="23d4e-116">Char (1)</span><span class="sxs-lookup"><span data-stu-id="23d4e-116">char(1)</span></span>  <br/> |<span data-ttu-id="23d4e-117">Primary</span><span class="sxs-lookup"><span data-stu-id="23d4e-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="23d4e-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="23d4e-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="23d4e-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="23d4e-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="23d4e-120">Primary</span><span class="sxs-lookup"><span data-stu-id="23d4e-120">Primary</span></span>  <br/> |<span data-ttu-id="23d4e-121">Nombre de dominio completo del grupo de servidores que hospeda la sesión.</span><span class="sxs-lookup"><span data-stu-id="23d4e-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="23d4e-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="23d4e-122">**AuthType**</span></span> <br/> |<span data-ttu-id="23d4e-123">int</span><span class="sxs-lookup"><span data-stu-id="23d4e-123">int</span></span>  <br/> |<span data-ttu-id="23d4e-124">Primary</span><span class="sxs-lookup"><span data-stu-id="23d4e-124">Primary</span></span>  <br/> |<span data-ttu-id="23d4e-125">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="23d4e-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="23d4e-126">Información de prioridad se almacena en la [tabla CallPriorities en Skype para Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="23d4e-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="23d4e-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="23d4e-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="23d4e-128">bigint</span><span class="sxs-lookup"><span data-stu-id="23d4e-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="23d4e-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="23d4e-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="23d4e-130">bigint</span><span class="sxs-lookup"><span data-stu-id="23d4e-130">bigint</span></span>  <br/> ||<span data-ttu-id="23d4e-131">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="23d4e-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

