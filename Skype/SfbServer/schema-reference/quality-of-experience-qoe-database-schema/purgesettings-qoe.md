---
title: Tabla PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de calidad de experiencia obsoletos se eliminarán automáticamente de la base de datos de QoE. Tenga en cuenta que la información relacionada con la depuración también se puede obtener desde el Shell de administración de Skype Empresarial Server ejecutando el siguiente comando:'
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815810"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="e5b3e-104">Tabla PurgeSettings (QoE)</span><span class="sxs-lookup"><span data-stu-id="e5b3e-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="e5b3e-105">La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de calidad de experiencia obsoletos se eliminarán automáticamente de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="e5b3e-106">Tenga en cuenta que la información relacionada con la depuración también se puede obtener desde el Shell de administración de Skype Empresarial Server ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e5b3e-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="e5b3e-107">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e5b3e-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-108">**Column**</span></span>|<span data-ttu-id="e5b3e-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-109">**Data Type**</span></span>|<span data-ttu-id="e5b3e-110">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-110">**Key/Index**</span></span>|<span data-ttu-id="e5b3e-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5b3e-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-112">**ID**</span></span> <br/> |<span data-ttu-id="e5b3e-113">entero</span><span class="sxs-lookup"><span data-stu-id="e5b3e-113">int</span></span>  <br/> |<span data-ttu-id="e5b3e-114">Principal</span><span class="sxs-lookup"><span data-stu-id="e5b3e-114">Primary</span></span>  <br/> |<span data-ttu-id="e5b3e-115">Identificador único para la colección de valores de depuración de QoE.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="e5b3e-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="e5b3e-117">bit</span><span class="sxs-lookup"><span data-stu-id="e5b3e-117">bit</span></span>  <br/> ||<span data-ttu-id="e5b3e-118">Cuando se establece en True (1), Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="e5b3e-119">La depuración tendrá lugar todos los días en el tomo especificado por la configuración PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="e5b3e-120">Si se establece en False (0), los registros no se depurarán automáticamente desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="e5b3e-121">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="e5b3e-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="e5b3e-123">entero</span><span class="sxs-lookup"><span data-stu-id="e5b3e-123">int</span></span>  <br/> ||<span data-ttu-id="e5b3e-p104">Especifica la antigüedad de los registros de QoE (en días) que se depurarán desde la base de datos: si la depuración está habilitada, se eliminarán de la base de datos los registros de QoE anteriores a este valor. El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="e5b3e-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="e5b3e-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="e5b3e-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="e5b3e-127">entero</span><span class="sxs-lookup"><span data-stu-id="e5b3e-127">int</span></span>  <br/> ||<span data-ttu-id="e5b3e-p105">Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (indicando 10:00 \*AM) pero no se permite un valor de 10:30 de 10.5 (indicando 10:30 AM). El valor predeterminado es 1 (1:00 AM). Especifica la hora local del día en que tendrá lugar la depuración de la base de datos. La hora del día se especifica mediante un reloj de 24 horas, representando el 0 la medianoche (12:00 AM) y el 23, las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 AM) pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="e5b3e-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

