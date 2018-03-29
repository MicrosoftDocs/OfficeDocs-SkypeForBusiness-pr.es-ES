---
title: Tabla de ubicaciones en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de ubicación de una llamada de emergencia, al igual que una llamada E9-1-1.
ms.openlocfilehash: b15e7f0b7930871b97dc3341a47153965529810e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3cc66-103">Tabla de ubicaciones en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cc66-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3cc66-104">Cada registro representa una referencia de ubicación de una llamada de emergencia, al igual que una llamada E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="3cc66-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="3cc66-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3cc66-105">**Column**</span></span>|<span data-ttu-id="3cc66-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3cc66-106">**Data Type**</span></span>|<span data-ttu-id="3cc66-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="3cc66-107">**Key/Index**</span></span>|<span data-ttu-id="3cc66-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3cc66-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3cc66-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="3cc66-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="3cc66-110">datetime</span><span class="sxs-lookup"><span data-stu-id="3cc66-110">datetime</span></span>  <br/> |<span data-ttu-id="3cc66-111">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="3cc66-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3cc66-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="3cc66-112">Time of session request.</span></span> <span data-ttu-id="3cc66-113">Se utiliza junto con **SessionIdSeq** para identificar una sesión.</span><span class="sxs-lookup"><span data-stu-id="3cc66-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="3cc66-114">Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3cc66-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3cc66-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="3cc66-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="3cc66-116">int</span><span class="sxs-lookup"><span data-stu-id="3cc66-116">int</span></span>  <br/> |<span data-ttu-id="3cc66-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="3cc66-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3cc66-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="3cc66-118">ID number to identify the session.</span></span> <span data-ttu-id="3cc66-119">Se utiliza junto con **SessionIdTime** para identificar una sesión.</span><span class="sxs-lookup"><span data-stu-id="3cc66-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="3cc66-120">Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3cc66-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3cc66-121">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="3cc66-121">**Location**</span></span> <br/> |<span data-ttu-id="3cc66-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3cc66-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="3cc66-123">Ubicación de llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="3cc66-123">Location of emergency call.</span></span>  <br/> |
   

