---
title: Tabla Mcus en Skype Empresarial Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabla Mcus es una tabla de apoyo. Cada registro almacena información sobre un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end), y el servicio de conferencia web y el servicio de conferencia A/V.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821430"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b9069-105">Tabla Mcus en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9069-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9069-106">La tabla Mcus es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="b9069-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="b9069-107">Cada registro almacena información sobre un servicio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b9069-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="b9069-108">Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end), y el servicio de conferencia web y el servicio de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="b9069-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="b9069-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b9069-109">**Column**</span></span>|<span data-ttu-id="b9069-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b9069-110">**Data Type**</span></span>|<span data-ttu-id="b9069-111">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="b9069-111">**Key/Index**</span></span>|<span data-ttu-id="b9069-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b9069-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9069-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="b9069-113">**McuId**</span></span> <br/> |<span data-ttu-id="b9069-114">entero</span><span class="sxs-lookup"><span data-stu-id="b9069-114">int</span></span>  <br/> |<span data-ttu-id="b9069-115">Principal</span><span class="sxs-lookup"><span data-stu-id="b9069-115">Primary</span></span>  <br/> |<span data-ttu-id="b9069-116">Número único que identifica este servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="b9069-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="b9069-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="b9069-117">**McuUri**</span></span> <br/> |<span data-ttu-id="b9069-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b9069-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="b9069-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="b9069-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="b9069-120">inyint</span><span class="sxs-lookup"><span data-stu-id="b9069-120">inyint</span></span>  <br/> | <span data-ttu-id="b9069-121">Externo</span><span class="sxs-lookup"><span data-stu-id="b9069-121">Foreign</span></span> <br/> |<span data-ttu-id="b9069-122">Tipo de servidor de conferencia, como conf:chat (para IMs) o conf:audio-video.</span><span class="sxs-lookup"><span data-stu-id="b9069-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="b9069-123">Vea la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b9069-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

