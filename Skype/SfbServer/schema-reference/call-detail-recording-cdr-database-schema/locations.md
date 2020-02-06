---
title: Tabla localidades en Skype empresarial Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de una ubicación en una llamada de emergencia, como una llamada de E9-1-1.
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815118"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="40354-103">Tabla localidades en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="40354-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="40354-104">Cada registro representa una referencia de una ubicación en una llamada de emergencia, como una llamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="40354-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="40354-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="40354-105">**Column**</span></span>|<span data-ttu-id="40354-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="40354-106">**Data Type**</span></span>|<span data-ttu-id="40354-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="40354-107">**Key/Index**</span></span>|<span data-ttu-id="40354-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="40354-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="40354-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="40354-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="40354-110">datetime</span><span class="sxs-lookup"><span data-stu-id="40354-110">datetime</span></span>  <br/> |<span data-ttu-id="40354-111">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="40354-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="40354-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="40354-112">Time of session request.</span></span> <span data-ttu-id="40354-113">Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="40354-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="40354-114">Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="40354-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="40354-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="40354-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="40354-116">int</span><span class="sxs-lookup"><span data-stu-id="40354-116">int</span></span>  <br/> |<span data-ttu-id="40354-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="40354-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="40354-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="40354-118">ID number to identify the session.</span></span> <span data-ttu-id="40354-119">Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="40354-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="40354-120">Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="40354-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="40354-121">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="40354-121">**Location**</span></span> <br/> |<span data-ttu-id="40354-122">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="40354-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="40354-123">Ubicación de la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="40354-123">Location of emergency call.</span></span>  <br/> |
   

