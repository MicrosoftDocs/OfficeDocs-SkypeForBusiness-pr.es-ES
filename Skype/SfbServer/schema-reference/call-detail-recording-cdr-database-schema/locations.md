---
title: Tabla de ubicaciones de Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de ubicación en una llamada de emergencia, al igual que una llamada de E9-1-1.
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213004"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b34e4-103">Tabla de ubicaciones de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b34e4-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b34e4-104">Cada registro representa una referencia de ubicación en una llamada de emergencia, al igual que una llamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="b34e4-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="b34e4-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b34e4-105">**Column**</span></span>|<span data-ttu-id="b34e4-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b34e4-106">**Data Type**</span></span>|<span data-ttu-id="b34e4-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="b34e4-107">**Key/Index**</span></span>|<span data-ttu-id="b34e4-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b34e4-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b34e4-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="b34e4-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="b34e4-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b34e4-110">datetime</span></span>  <br/> |<span data-ttu-id="b34e4-111">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="b34e4-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b34e4-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="b34e4-112">Time of session request.</span></span> <span data-ttu-id="b34e4-113">Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="b34e4-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="b34e4-114">Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b34e4-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b34e4-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="b34e4-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="b34e4-116">int</span><span class="sxs-lookup"><span data-stu-id="b34e4-116">int</span></span>  <br/> |<span data-ttu-id="b34e4-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="b34e4-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b34e4-118">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="b34e4-118">ID number to identify the session.</span></span> <span data-ttu-id="b34e4-119">Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="b34e4-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="b34e4-120">Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b34e4-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b34e4-121">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="b34e4-121">**Location**</span></span> <br/> |<span data-ttu-id="b34e4-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="b34e4-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="b34e4-123">Ubicación de llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="b34e4-123">Location of emergency call.</span></span>  <br/> |
   

