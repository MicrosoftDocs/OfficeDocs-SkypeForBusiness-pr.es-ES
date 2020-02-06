---
title: Vista ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vista ProgressReport almacena información sobre las sesiones completadas. Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814988"
---
# <a name="progressreport-view"></a><span data-ttu-id="c8e98-105">Vista ProgressReport</span><span class="sxs-lookup"><span data-stu-id="c8e98-105">ProgressReport view</span></span>
 
<span data-ttu-id="c8e98-106">La vista ProgressReport almacena información sobre las sesiones completadas.</span><span class="sxs-lookup"><span data-stu-id="c8e98-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="c8e98-107">Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c8e98-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="c8e98-108">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8e98-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8e98-109">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia a errores sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c8e98-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="c8e98-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c8e98-110">**Column**</span></span>|<span data-ttu-id="c8e98-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c8e98-111">**Data Type**</span></span>|<span data-ttu-id="c8e98-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c8e98-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8e98-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="c8e98-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="c8e98-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c8e98-114">datetime</span></span>  <br/> |<span data-ttu-id="c8e98-115">Hora de error.</span><span class="sxs-lookup"><span data-stu-id="c8e98-115">Time of error occurred.</span></span> <span data-ttu-id="c8e98-116">Se usa junto con ErrorReportSeq para identificar de forma única un error.</span><span class="sxs-lookup"><span data-stu-id="c8e98-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="c8e98-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="c8e98-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="c8e98-118">int</span><span class="sxs-lookup"><span data-stu-id="c8e98-118">int</span></span>  <br/> |<span data-ttu-id="c8e98-119">Número de identificación para identificar el error.</span><span class="sxs-lookup"><span data-stu-id="c8e98-119">ID number to identify the error.</span></span> <span data-ttu-id="c8e98-120">Se usa junto con ErrorTime para identificar de forma única un error.</span><span class="sxs-lookup"><span data-stu-id="c8e98-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="c8e98-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="c8e98-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="c8e98-122">int</span><span class="sxs-lookup"><span data-stu-id="c8e98-122">int</span></span>  <br/> |<span data-ttu-id="c8e98-123">IDENTIFICADOR para identificar el informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="c8e98-123">ID to identify the progress report.</span></span> <span data-ttu-id="c8e98-124">Se usa para distinguir los informes de progreso del mismo informe de errores.</span><span class="sxs-lookup"><span data-stu-id="c8e98-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="c8e98-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="c8e98-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="c8e98-126">int</span><span class="sxs-lookup"><span data-stu-id="c8e98-126">int</span></span>  <br/> |<span data-ttu-id="c8e98-127">IDENTIFICADOR de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="c8e98-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="c8e98-128">**Origen**</span><span class="sxs-lookup"><span data-stu-id="c8e98-128">**Source**</span></span> <br/> |<span data-ttu-id="c8e98-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8e98-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8e98-130">Nombre del servidor que originó el error (si el informe fue enviado desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="c8e98-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="c8e98-131">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="c8e98-131">**Application**</span></span> <br/> |<span data-ttu-id="c8e98-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8e98-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8e98-133">Nombre de la aplicación que originó el error (si el informe fue enviado desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="c8e98-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="c8e98-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="c8e98-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="c8e98-135">identificador</span><span class="sxs-lookup"><span data-stu-id="c8e98-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c8e98-136">Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="c8e98-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="c8e98-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="c8e98-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="c8e98-138">int</span><span class="sxs-lookup"><span data-stu-id="c8e98-138">int</span></span>  <br/> |<span data-ttu-id="c8e98-139">Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="c8e98-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="c8e98-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="c8e98-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="c8e98-141">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="c8e98-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="c8e98-142">Información de error adicional.</span><span class="sxs-lookup"><span data-stu-id="c8e98-142">Additional error information.</span></span>  <br/> |
   

