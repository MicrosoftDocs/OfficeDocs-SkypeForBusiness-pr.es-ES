---
title: Vista UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294610"
---
# <a name="useragent-view"></a><span data-ttu-id="b1d3f-104">Vista UserAgent</span><span class="sxs-lookup"><span data-stu-id="b1d3f-104">UserAgent view</span></span>
 
<span data-ttu-id="b1d3f-105">La vista UserAgent almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1d3f-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="b1d3f-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1d3f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b1d3f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b1d3f-107">**Column**</span></span>|<span data-ttu-id="b1d3f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b1d3f-108">**Data Type**</span></span>|<span data-ttu-id="b1d3f-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b1d3f-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b1d3f-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="b1d3f-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="b1d3f-111">int</span><span class="sxs-lookup"><span data-stu-id="b1d3f-111">int</span></span>  <br/> |<span data-ttu-id="b1d3f-112">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="b1d3f-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="b1d3f-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="b1d3f-113">UserAgent</span></span>  <br/> |<span data-ttu-id="b1d3f-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b1d3f-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b1d3f-115">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="b1d3f-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="b1d3f-116">UAType</span><span class="sxs-lookup"><span data-stu-id="b1d3f-116">UAType</span></span>  <br/> |<span data-ttu-id="b1d3f-117">smallint</span><span class="sxs-lookup"><span data-stu-id="b1d3f-117">smallint</span></span>  <br/> |<span data-ttu-id="b1d3f-118">Tipo de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="b1d3f-118">Type of user agent.</span></span> <span data-ttu-id="b1d3f-119">Para obtener más información, consulta la [tabla UserAgent](useragent.md) .</span><span class="sxs-lookup"><span data-stu-id="b1d3f-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="b1d3f-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="b1d3f-120">UACategory</span></span>  <br/> |<span data-ttu-id="b1d3f-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b1d3f-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="b1d3f-122">Categoría a la que pertenece el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="b1d3f-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="b1d3f-123">Por ejemplo, el agente de usuario Conferencing_Attendant_ 1.0 pertenece a la UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="b1d3f-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

