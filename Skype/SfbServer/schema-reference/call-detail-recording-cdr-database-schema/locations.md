---
title: Tabla Ubicaciones en Skype Empresarial Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de ubicación en una llamada de emergencia, como una llamada E9-1-1.
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821520"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="24e12-103">Tabla Ubicaciones en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="24e12-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24e12-104">Cada registro representa una referencia de ubicación en una llamada de emergencia, como una llamada E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="24e12-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="24e12-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="24e12-105">**Column**</span></span>|<span data-ttu-id="24e12-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="24e12-106">**Data Type**</span></span>|<span data-ttu-id="24e12-107">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="24e12-107">**Key/Index**</span></span>|<span data-ttu-id="24e12-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="24e12-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24e12-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="24e12-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="24e12-110">datetime</span><span class="sxs-lookup"><span data-stu-id="24e12-110">datetime</span></span>  <br/> |<span data-ttu-id="24e12-111">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="24e12-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="24e12-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="24e12-112">Time of session request.</span></span> <span data-ttu-id="24e12-113">Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="24e12-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="24e12-114">Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="24e12-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="24e12-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="24e12-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="24e12-116">entero</span><span class="sxs-lookup"><span data-stu-id="24e12-116">int</span></span>  <br/> |<span data-ttu-id="24e12-117">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="24e12-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="24e12-118">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="24e12-118">ID number to identify the session.</span></span> <span data-ttu-id="24e12-119">Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="24e12-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="24e12-120">Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="24e12-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="24e12-121">**Location**</span><span class="sxs-lookup"><span data-stu-id="24e12-121">**Location**</span></span> <br/> |<span data-ttu-id="24e12-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="24e12-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="24e12-123">Ubicación de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="24e12-123">Location of emergency call.</span></span>  <br/> |
   

