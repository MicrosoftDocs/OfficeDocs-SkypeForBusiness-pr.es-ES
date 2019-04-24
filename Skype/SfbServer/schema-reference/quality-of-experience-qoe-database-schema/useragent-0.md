---
title: Vista UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212070"
---
# <a name="useragent-view"></a><span data-ttu-id="efe76-104">Vista UserAgent</span><span class="sxs-lookup"><span data-stu-id="efe76-104">UserAgent view</span></span>
 
<span data-ttu-id="efe76-105">La vista UserAgent almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="efe76-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="efe76-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efe76-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="efe76-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="efe76-107">**Column**</span></span>|<span data-ttu-id="efe76-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="efe76-108">**Data Type**</span></span>|<span data-ttu-id="efe76-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="efe76-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="efe76-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="efe76-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="efe76-111">int</span><span class="sxs-lookup"><span data-stu-id="efe76-111">int</span></span>  <br/> |<span data-ttu-id="efe76-112">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="efe76-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="efe76-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="efe76-113">UserAgent</span></span>  <br/> |<span data-ttu-id="efe76-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="efe76-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="efe76-115">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="efe76-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="efe76-116">UAType</span><span class="sxs-lookup"><span data-stu-id="efe76-116">UAType</span></span>  <br/> |<span data-ttu-id="efe76-117">smallint</span><span class="sxs-lookup"><span data-stu-id="efe76-117">smallint</span></span>  <br/> |<span data-ttu-id="efe76-118">Tipo de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="efe76-118">Type of user agent.</span></span> <span data-ttu-id="efe76-119">Consulte la [tabla UserAgent](useragent.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="efe76-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="efe76-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="efe76-120">UACategory</span></span>  <br/> |<span data-ttu-id="efe76-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="efe76-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="efe76-122">Categoría a la que pertenece el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="efe76-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="efe76-123">Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="efe76-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

