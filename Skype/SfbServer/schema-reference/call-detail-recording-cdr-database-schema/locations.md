---
title: Tabla de ubicaciones de Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de ubicación en una llamada de emergencia, al igual que una llamada de E9-1-1.
ms.openlocfilehash: 389aa56dfaf6d8b732692909ff3375a992b504b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930244"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8c7b0-103">Tabla de ubicaciones de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8c7b0-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8c7b0-104">Cada registro representa una referencia de ubicación en una llamada de emergencia, al igual que una llamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="8c7b0-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8c7b0-105">**Column**</span></span>|<span data-ttu-id="8c7b0-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="8c7b0-106">**Data Type**</span></span>|<span data-ttu-id="8c7b0-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="8c7b0-107">**Key/Index**</span></span>|<span data-ttu-id="8c7b0-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="8c7b0-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8c7b0-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="8c7b0-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="8c7b0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8c7b0-110">datetime</span></span>  <br/> |<span data-ttu-id="8c7b0-111">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="8c7b0-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8c7b0-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-112">Time of session request.</span></span> <span data-ttu-id="8c7b0-113">Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="8c7b0-114">Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8c7b0-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="8c7b0-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="8c7b0-116">int</span><span class="sxs-lookup"><span data-stu-id="8c7b0-116">int</span></span>  <br/> |<span data-ttu-id="8c7b0-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="8c7b0-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8c7b0-118">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-118">ID number to identify the session.</span></span> <span data-ttu-id="8c7b0-119">Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="8c7b0-120">Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8c7b0-121">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="8c7b0-121">**Location**</span></span> <br/> |<span data-ttu-id="8c7b0-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="8c7b0-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="8c7b0-123">Ubicación de llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="8c7b0-123">Location of emergency call.</span></span>  <br/> |
   

