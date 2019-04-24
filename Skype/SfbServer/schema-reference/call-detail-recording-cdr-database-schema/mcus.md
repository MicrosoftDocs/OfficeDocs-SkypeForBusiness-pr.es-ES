---
title: Tabla de MCU en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: En la tabla de MCU es una tabla de apoyo. Cada registro almacena información acerca de un servicio de conferencia. Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencias telefónicas (que se ejecutan como procesos en servidores front-end) y el servicio de conferencia Web y A / servicio de conferencia A/v.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212976"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="885a0-105">Tabla de MCU en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="885a0-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="885a0-106">En la tabla de MCU es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="885a0-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="885a0-107">Cada registro almacena información acerca de un servicio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="885a0-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="885a0-108">Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencias telefónicas (que se ejecutan como procesos en servidores front-end) y el servicio de conferencia Web y A / servicio de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="885a0-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="885a0-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="885a0-109">**Column**</span></span>|<span data-ttu-id="885a0-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="885a0-110">**Data Type**</span></span>|<span data-ttu-id="885a0-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="885a0-111">**Key/Index**</span></span>|<span data-ttu-id="885a0-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="885a0-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="885a0-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="885a0-113">**McuId**</span></span> <br/> |<span data-ttu-id="885a0-114">int</span><span class="sxs-lookup"><span data-stu-id="885a0-114">int</span></span>  <br/> |<span data-ttu-id="885a0-115">Primary</span><span class="sxs-lookup"><span data-stu-id="885a0-115">Primary</span></span>  <br/> |<span data-ttu-id="885a0-116">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="885a0-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="885a0-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="885a0-117">**McuUri**</span></span> <br/> |<span data-ttu-id="885a0-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="885a0-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="885a0-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="885a0-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="885a0-120">inyint</span><span class="sxs-lookup"><span data-stu-id="885a0-120">inyint</span></span>  <br/> | <span data-ttu-id="885a0-121">Externa</span><span class="sxs-lookup"><span data-stu-id="885a0-121">Foreign</span></span> <br/> |<span data-ttu-id="885a0-122">Tipo de servidor de conferencia, como conf:chat (para mensajes instantáneos) o conf:audio-vídeo.</span><span class="sxs-lookup"><span data-stu-id="885a0-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="885a0-123">Consulte la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="885a0-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

