---
title: Tabla ConferenceMessageCount en Skype Empresarial Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa a un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813280"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="605f0-104">Tabla ConferenceMessageCount en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="605f0-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="605f0-105">Cada registro de esta tabla representa a un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario.</span><span class="sxs-lookup"><span data-stu-id="605f0-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="605f0-106">Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="605f0-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="605f0-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="605f0-107">**Column**</span></span>|<span data-ttu-id="605f0-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="605f0-108">**Data Type**</span></span>|<span data-ttu-id="605f0-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="605f0-109">**Key/Index**</span></span>|<span data-ttu-id="605f0-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="605f0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="605f0-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="605f0-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="605f0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="605f0-112">datetime</span></span>  <br/> |<span data-ttu-id="605f0-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="605f0-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="605f0-114">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="605f0-114">Time of conference instance.</span></span> <span data-ttu-id="605f0-115">Se usa junto con **SessionIdSeq para** identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="605f0-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="605f0-116">Consulte la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="605f0-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="605f0-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="605f0-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="605f0-118">entero</span><span class="sxs-lookup"><span data-stu-id="605f0-118">int</span></span>  <br/> |<span data-ttu-id="605f0-119">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="605f0-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="605f0-120">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="605f0-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="605f0-121">Se usa junto con **SessionIdTime para** identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="605f0-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="605f0-122">Consulte la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="605f0-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="605f0-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="605f0-123">**UserId**</span></span> <br/> |<span data-ttu-id="605f0-124">entero</span><span class="sxs-lookup"><span data-stu-id="605f0-124">int</span></span>  <br/> |<span data-ttu-id="605f0-125">Externo</span><span class="sxs-lookup"><span data-stu-id="605f0-125">Foreign</span></span>  <br/> |<span data-ttu-id="605f0-126">Número único que identifica a este usuario, al que se hace referencia desde la [tabla Usuarios](users.md).</span><span class="sxs-lookup"><span data-stu-id="605f0-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="605f0-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="605f0-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="605f0-128">smallint</span><span class="sxs-lookup"><span data-stu-id="605f0-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="605f0-129">El número de mensajes enviados por este usuario durante esta conferencia.</span><span class="sxs-lookup"><span data-stu-id="605f0-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

