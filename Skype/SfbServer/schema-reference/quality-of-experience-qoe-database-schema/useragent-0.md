---
title: UserAgent vista
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información acerca de los agentes de usuario que han participado en sesiones que tengan registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a><span data-ttu-id="a7b18-104">UserAgent vista</span><span class="sxs-lookup"><span data-stu-id="a7b18-104">UserAgent view</span></span>
 
<span data-ttu-id="a7b18-105">La vista UserAgent almacena información acerca de los agentes de usuario que han participado en sesiones que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a7b18-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="a7b18-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7b18-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a7b18-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a7b18-107">**Column**</span></span>|<span data-ttu-id="a7b18-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a7b18-108">**Data Type**</span></span>|<span data-ttu-id="a7b18-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a7b18-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7b18-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="a7b18-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="a7b18-111">int</span><span class="sxs-lookup"><span data-stu-id="a7b18-111">int</span></span>  <br/> |<span data-ttu-id="a7b18-112">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7b18-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="a7b18-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="a7b18-113">UserAgent</span></span>  <br/> |<span data-ttu-id="a7b18-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7b18-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a7b18-115">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7b18-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="a7b18-116">UAType</span><span class="sxs-lookup"><span data-stu-id="a7b18-116">UAType</span></span>  <br/> |<span data-ttu-id="a7b18-117">smallint</span><span class="sxs-lookup"><span data-stu-id="a7b18-117">smallint</span></span>  <br/> |<span data-ttu-id="a7b18-118">Tipo de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7b18-118">Type of user agent.</span></span> <span data-ttu-id="a7b18-119">Consulte la [tabla UserAgent](useragent.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="a7b18-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="a7b18-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="a7b18-120">UACategory</span></span>  <br/> |<span data-ttu-id="a7b18-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="a7b18-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="a7b18-122">Categoría a la que pertenece el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7b18-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="a7b18-123">Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="a7b18-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

