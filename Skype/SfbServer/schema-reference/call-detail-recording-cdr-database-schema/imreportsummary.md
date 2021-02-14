---
title: Tabla IMReportSummary en Skype Empresarial Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821530"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="472c3-104">Tabla IMReportSummary en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="472c3-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="472c3-105">La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización.</span><span class="sxs-lookup"><span data-stu-id="472c3-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="472c3-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="472c3-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="472c3-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="472c3-107">**Column**</span></span>|<span data-ttu-id="472c3-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="472c3-108">**Data Type**</span></span>|<span data-ttu-id="472c3-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="472c3-109">**Key/Index**</span></span>|<span data-ttu-id="472c3-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="472c3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="472c3-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="472c3-111">**StartTime**</span></span> <br/> |<span data-ttu-id="472c3-112">datetime</span><span class="sxs-lookup"><span data-stu-id="472c3-112">datetime</span></span>  <br/> |<span data-ttu-id="472c3-113">Principal</span><span class="sxs-lookup"><span data-stu-id="472c3-113">Primary</span></span>  <br/> |<span data-ttu-id="472c3-114">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="472c3-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="472c3-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="472c3-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="472c3-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="472c3-116">char(1)</span></span>  <br/> |<span data-ttu-id="472c3-117">Principal</span><span class="sxs-lookup"><span data-stu-id="472c3-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="472c3-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="472c3-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="472c3-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="472c3-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="472c3-120">Principal</span><span class="sxs-lookup"><span data-stu-id="472c3-120">Primary</span></span>  <br/> |<span data-ttu-id="472c3-121">Nombre de dominio completo del grupo de servidores que hospeda la sesión.</span><span class="sxs-lookup"><span data-stu-id="472c3-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="472c3-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="472c3-122">**AuthType**</span></span> <br/> |<span data-ttu-id="472c3-123">entero</span><span class="sxs-lookup"><span data-stu-id="472c3-123">int</span></span>  <br/> |<span data-ttu-id="472c3-124">Principal</span><span class="sxs-lookup"><span data-stu-id="472c3-124">Primary</span></span>  <br/> |<span data-ttu-id="472c3-125">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="472c3-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="472c3-126">La información de prioridad se almacena [en la tabla CallPriorities en Skype Empresarial Server 2015.](callpriorities.md)</span><span class="sxs-lookup"><span data-stu-id="472c3-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="472c3-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="472c3-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="472c3-128">bigint</span><span class="sxs-lookup"><span data-stu-id="472c3-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="472c3-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="472c3-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="472c3-130">bigint</span><span class="sxs-lookup"><span data-stu-id="472c3-130">bigint</span></span>  <br/> ||<span data-ttu-id="472c3-131">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="472c3-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

