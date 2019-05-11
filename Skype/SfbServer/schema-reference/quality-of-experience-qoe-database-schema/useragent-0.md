---
title: Vista UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 942093ece5706115cc4e90171c09df8a8a169b09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907027"
---
# <a name="useragent-view"></a><span data-ttu-id="fecb9-104">Vista UserAgent</span><span class="sxs-lookup"><span data-stu-id="fecb9-104">UserAgent view</span></span>
 
<span data-ttu-id="fecb9-105">La vista UserAgent almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fecb9-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="fecb9-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fecb9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fecb9-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fecb9-107">**Column**</span></span>|<span data-ttu-id="fecb9-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fecb9-108">**Data Type**</span></span>|<span data-ttu-id="fecb9-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="fecb9-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fecb9-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="fecb9-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="fecb9-111">int</span><span class="sxs-lookup"><span data-stu-id="fecb9-111">int</span></span>  <br/> |<span data-ttu-id="fecb9-112">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="fecb9-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="fecb9-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="fecb9-113">UserAgent</span></span>  <br/> |<span data-ttu-id="fecb9-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fecb9-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fecb9-115">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="fecb9-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="fecb9-116">UAType</span><span class="sxs-lookup"><span data-stu-id="fecb9-116">UAType</span></span>  <br/> |<span data-ttu-id="fecb9-117">smallint</span><span class="sxs-lookup"><span data-stu-id="fecb9-117">smallint</span></span>  <br/> |<span data-ttu-id="fecb9-118">Tipo de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="fecb9-118">Type of user agent.</span></span> <span data-ttu-id="fecb9-119">Consulte la [tabla UserAgent](useragent.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="fecb9-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="fecb9-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="fecb9-120">UACategory</span></span>  <br/> |<span data-ttu-id="fecb9-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="fecb9-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="fecb9-122">Categoría a la que pertenece el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="fecb9-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="fecb9-123">Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="fecb9-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

