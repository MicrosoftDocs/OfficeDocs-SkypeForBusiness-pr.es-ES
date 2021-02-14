---
title: Vista ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vista ProgressReport almacena información sobre las sesiones finalizadas. Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823190"
---
# <a name="progressreport-view"></a><span data-ttu-id="a4bc8-105">Vista ProgressReport</span><span class="sxs-lookup"><span data-stu-id="a4bc8-105">ProgressReport view</span></span>
 
<span data-ttu-id="a4bc8-106">La vista ProgressReport almacena información sobre las sesiones finalizadas.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="a4bc8-107">Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="a4bc8-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4bc8-109">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no necesariamente hacen referencia a errores, sino a mensajes que indican el estado de las llamadas o mensajes.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="a4bc8-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-110">**Column**</span></span>|<span data-ttu-id="a4bc8-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-111">**Data Type**</span></span>|<span data-ttu-id="a4bc8-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4bc8-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="a4bc8-114">datetime</span><span class="sxs-lookup"><span data-stu-id="a4bc8-114">datetime</span></span>  <br/> |<span data-ttu-id="a4bc8-p103">Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="a4bc8-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="a4bc8-118">entero</span><span class="sxs-lookup"><span data-stu-id="a4bc8-118">int</span></span>  <br/> |<span data-ttu-id="a4bc8-p104">Número para identificar el error. Se usa junto con ErrorTime como identificación única de un error.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="a4bc8-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="a4bc8-122">entero</span><span class="sxs-lookup"><span data-stu-id="a4bc8-122">int</span></span>  <br/> |<span data-ttu-id="a4bc8-123">Identificador del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-123">ID to identify the progress report.</span></span> <span data-ttu-id="a4bc8-124">Se usa para diferenciar informes de progreso del mismo informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="a4bc8-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="a4bc8-126">entero</span><span class="sxs-lookup"><span data-stu-id="a4bc8-126">int</span></span>  <br/> |<span data-ttu-id="a4bc8-127">Identificador de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="a4bc8-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-128">**Source**</span></span> <br/> |<span data-ttu-id="a4bc8-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a4bc8-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a4bc8-130">Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="a4bc8-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="a4bc8-131">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-131">**Application**</span></span> <br/> |<span data-ttu-id="a4bc8-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a4bc8-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a4bc8-133">Nombre de la aplicación que generó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="a4bc8-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="a4bc8-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="a4bc8-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a4bc8-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a4bc8-136">Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="a4bc8-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="a4bc8-138">entero</span><span class="sxs-lookup"><span data-stu-id="a4bc8-138">int</span></span>  <br/> |<span data-ttu-id="a4bc8-139">Tiempo (en milisegundos) necesario para que un componente específico se una a las conferencias.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="a4bc8-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="a4bc8-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="a4bc8-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="a4bc8-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="a4bc8-142">Información adicional del error.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-142">Additional error information.</span></span>  <br/> |
   

