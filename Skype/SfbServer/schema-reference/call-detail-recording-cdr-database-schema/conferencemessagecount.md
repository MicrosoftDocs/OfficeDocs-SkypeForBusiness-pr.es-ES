---
title: Tabla ConferenceMessageCount en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representado por varios registros de esta tabla; un registro para cada usuario.
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874360"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0bdc7-104">Tabla ConferenceMessageCount en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0bdc7-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0bdc7-105">Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="0bdc7-106">Cada conferencia está representado por varios registros de esta tabla; un registro para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="0bdc7-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-107">**Column**</span></span>|<span data-ttu-id="0bdc7-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-108">**Data Type**</span></span>|<span data-ttu-id="0bdc7-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-109">**Key/Index**</span></span>|<span data-ttu-id="0bdc7-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0bdc7-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="0bdc7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0bdc7-112">datetime</span></span>  <br/> |<span data-ttu-id="0bdc7-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="0bdc7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0bdc7-114">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-114">Time of conference instance.</span></span> <span data-ttu-id="0bdc7-115">Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="0bdc7-116">Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0bdc7-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="0bdc7-118">int</span><span class="sxs-lookup"><span data-stu-id="0bdc7-118">int</span></span>  <br/> |<span data-ttu-id="0bdc7-119">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="0bdc7-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0bdc7-120">Número de identificador para identificar la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="0bdc7-121">Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="0bdc7-122">Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0bdc7-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-123">**UserId**</span></span> <br/> |<span data-ttu-id="0bdc7-124">int</span><span class="sxs-lookup"><span data-stu-id="0bdc7-124">int</span></span>  <br/> |<span data-ttu-id="0bdc7-125">Externa</span><span class="sxs-lookup"><span data-stu-id="0bdc7-125">Foreign</span></span>  <br/> |<span data-ttu-id="0bdc7-126">Número único que identifica a este usuario, de la [tabla de usuarios](users.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc7-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="0bdc7-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="0bdc7-128">smallint</span><span class="sxs-lookup"><span data-stu-id="0bdc7-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="0bdc7-129">El número de mensajes enviados por este usuario durante la conferencia.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

