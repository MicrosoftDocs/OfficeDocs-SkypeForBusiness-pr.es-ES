---
title: Tabla ConferenceMessageCount en Skype empresarial Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por el usuario. Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815378"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d6470-104">Tabla ConferenceMessageCount en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d6470-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d6470-105">Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d6470-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="d6470-106">Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="d6470-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="d6470-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d6470-107">**Column**</span></span>|<span data-ttu-id="d6470-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d6470-108">**Data Type**</span></span>|<span data-ttu-id="d6470-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d6470-109">**Key/Index**</span></span>|<span data-ttu-id="d6470-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d6470-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d6470-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="d6470-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="d6470-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d6470-112">datetime</span></span>  <br/> |<span data-ttu-id="d6470-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d6470-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d6470-114">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d6470-114">Time of conference instance.</span></span> <span data-ttu-id="d6470-115">Se usa junto con **SessionIdSeq** para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d6470-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="d6470-116">Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="d6470-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d6470-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="d6470-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="d6470-118">int</span><span class="sxs-lookup"><span data-stu-id="d6470-118">int</span></span>  <br/> |<span data-ttu-id="d6470-119">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d6470-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d6470-120">Número de identificación para identificar la instancia de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="d6470-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="d6470-121">Se usa junto con **SessionIdTime** para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d6470-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="d6470-122">Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) .</span><span class="sxs-lookup"><span data-stu-id="d6470-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d6470-123">**Iddeusuario**</span><span class="sxs-lookup"><span data-stu-id="d6470-123">**UserId**</span></span> <br/> |<span data-ttu-id="d6470-124">int</span><span class="sxs-lookup"><span data-stu-id="d6470-124">int</span></span>  <br/> |<span data-ttu-id="d6470-125">Extranjero</span><span class="sxs-lookup"><span data-stu-id="d6470-125">Foreign</span></span>  <br/> |<span data-ttu-id="d6470-126">Número único que identifica a este usuario, al que se hace referencia en la [tabla usuarios](users.md).</span><span class="sxs-lookup"><span data-stu-id="d6470-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="d6470-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="d6470-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="d6470-128">smallint</span><span class="sxs-lookup"><span data-stu-id="d6470-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="d6470-129">El número de mensajes enviados por este usuario durante esta conferencia.</span><span class="sxs-lookup"><span data-stu-id="d6470-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

