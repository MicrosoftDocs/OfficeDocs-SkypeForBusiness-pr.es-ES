---
title: Tabla ConferenceMessageCount en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representado por varios registros de esta tabla; un registro para cada usuario.
ms.openlocfilehash: f45de53333b23368351c8c5330b474cd3260192b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901432"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ba005-104">Tabla ConferenceMessageCount en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba005-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ba005-105">Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario.</span><span class="sxs-lookup"><span data-stu-id="ba005-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="ba005-106">Cada conferencia está representado por varios registros de esta tabla; un registro para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="ba005-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="ba005-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ba005-107">**Column**</span></span>|<span data-ttu-id="ba005-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ba005-108">**Data Type**</span></span>|<span data-ttu-id="ba005-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ba005-109">**Key/Index**</span></span>|<span data-ttu-id="ba005-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ba005-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba005-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="ba005-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ba005-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ba005-112">datetime</span></span>  <br/> |<span data-ttu-id="ba005-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="ba005-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ba005-114">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ba005-114">Time of conference instance.</span></span> <span data-ttu-id="ba005-115">Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="ba005-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="ba005-116">Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ba005-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ba005-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ba005-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ba005-118">int</span><span class="sxs-lookup"><span data-stu-id="ba005-118">int</span></span>  <br/> |<span data-ttu-id="ba005-119">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="ba005-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ba005-120">Número de identificador para identificar la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ba005-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="ba005-121">Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="ba005-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="ba005-122">Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ba005-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ba005-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="ba005-123">**UserId**</span></span> <br/> |<span data-ttu-id="ba005-124">int</span><span class="sxs-lookup"><span data-stu-id="ba005-124">int</span></span>  <br/> |<span data-ttu-id="ba005-125">Externa</span><span class="sxs-lookup"><span data-stu-id="ba005-125">Foreign</span></span>  <br/> |<span data-ttu-id="ba005-126">Número único que identifica a este usuario, de la [tabla de usuarios](users.md).</span><span class="sxs-lookup"><span data-stu-id="ba005-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="ba005-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="ba005-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="ba005-128">smallint</span><span class="sxs-lookup"><span data-stu-id="ba005-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="ba005-129">El número de mensajes enviados por este usuario durante la conferencia.</span><span class="sxs-lookup"><span data-stu-id="ba005-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

