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
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de una ubicación en una llamada de emergencia, como una llamada de E9-1-1.
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296122"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0e178-103">Tabla localidades en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e178-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e178-104">Cada registro representa una referencia de una ubicación en una llamada de emergencia, como una llamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0e178-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="0e178-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0e178-105">**Column**</span></span>|<span data-ttu-id="0e178-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0e178-106">**Data Type**</span></span>|<span data-ttu-id="0e178-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0e178-107">**Key/Index**</span></span>|<span data-ttu-id="0e178-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0e178-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e178-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="0e178-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="0e178-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0e178-110">datetime</span></span>  <br/> |<span data-ttu-id="0e178-111">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="0e178-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0e178-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="0e178-112">Time of session request.</span></span> <span data-ttu-id="0e178-113">Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="0e178-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="0e178-114">Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="0e178-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0e178-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="0e178-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="0e178-116">int</span><span class="sxs-lookup"><span data-stu-id="0e178-116">int</span></span>  <br/> |<span data-ttu-id="0e178-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="0e178-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0e178-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="0e178-118">ID number to identify the session.</span></span> <span data-ttu-id="0e178-119">Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="0e178-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="0e178-120">Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="0e178-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0e178-121">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="0e178-121">**Location**</span></span> <br/> |<span data-ttu-id="0e178-122">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="0e178-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="0e178-123">Ubicación de la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="0e178-123">Location of emergency call.</span></span>  <br/> |
   

