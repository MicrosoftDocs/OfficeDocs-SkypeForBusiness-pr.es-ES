---
title: Vista UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800020"
---
# <a name="useragent-view"></a><span data-ttu-id="c3df2-104">Vista UserAgent</span><span class="sxs-lookup"><span data-stu-id="c3df2-104">UserAgent view</span></span>
 
<span data-ttu-id="c3df2-105">La vista UserAgent almacena información sobre los agentes de usuario que han participado en sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3df2-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="c3df2-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3df2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c3df2-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c3df2-107">**Column**</span></span>|<span data-ttu-id="c3df2-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c3df2-108">**Data Type**</span></span>|<span data-ttu-id="c3df2-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c3df2-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3df2-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="c3df2-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="c3df2-111">entero</span><span class="sxs-lookup"><span data-stu-id="c3df2-111">int</span></span>  <br/> |<span data-ttu-id="c3df2-112">Número único que identifica este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="c3df2-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="c3df2-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="c3df2-113">UserAgent</span></span>  <br/> |<span data-ttu-id="c3df2-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c3df2-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c3df2-115">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="c3df2-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="c3df2-116">UAType</span><span class="sxs-lookup"><span data-stu-id="c3df2-116">UAType</span></span>  <br/> |<span data-ttu-id="c3df2-117">smallint</span><span class="sxs-lookup"><span data-stu-id="c3df2-117">smallint</span></span>  <br/> |<span data-ttu-id="c3df2-118">Tipo de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="c3df2-118">Type of user agent.</span></span> <span data-ttu-id="c3df2-119">Consulte la [tabla UserAgent](useragent.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c3df2-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="c3df2-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="c3df2-120">UACategory</span></span>  <br/> |<span data-ttu-id="c3df2-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="c3df2-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="c3df2-p104">Categoría a la que pertenece el agente de usuario. Por ejemplo, el agente de usuario Conferencing_Attendant_1.0 pertenece a la UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="c3df2-p104">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

