---
title: Tabla MCU en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabla MCU es una tabla de soporte. Cada registro almacena información acerca de un servicio de conferencia. Estos pueden incluir el servicio de conferencias de mensajería instantánea y el servicio de conferencias de telefonía (que se ejecutan como procesos en servidores de aplicaciones para el usuario), así como el servicio de conferencias por Internet y el servicio de conferencias A/V.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296045"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="882e2-105">Tabla MCU en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="882e2-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="882e2-106">La tabla MCU es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="882e2-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="882e2-107">Cada registro almacena información acerca de un servicio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="882e2-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="882e2-108">Estos pueden incluir el servicio de conferencias de mensajería instantánea y el servicio de conferencias de telefonía (que se ejecutan como procesos en servidores de aplicaciones para el usuario), así como el servicio de conferencias por Internet y el servicio de conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="882e2-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="882e2-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="882e2-109">**Column**</span></span>|<span data-ttu-id="882e2-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="882e2-110">**Data Type**</span></span>|<span data-ttu-id="882e2-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="882e2-111">**Key/Index**</span></span>|<span data-ttu-id="882e2-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="882e2-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="882e2-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="882e2-113">**McuId**</span></span> <br/> |<span data-ttu-id="882e2-114">int</span><span class="sxs-lookup"><span data-stu-id="882e2-114">int</span></span>  <br/> |<span data-ttu-id="882e2-115">Primary</span><span class="sxs-lookup"><span data-stu-id="882e2-115">Primary</span></span>  <br/> |<span data-ttu-id="882e2-116">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="882e2-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="882e2-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="882e2-117">**McuUri**</span></span> <br/> |<span data-ttu-id="882e2-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="882e2-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="882e2-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="882e2-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="882e2-120">inyint</span><span class="sxs-lookup"><span data-stu-id="882e2-120">inyint</span></span>  <br/> | <span data-ttu-id="882e2-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="882e2-121">Foreign</span></span> <br/> |<span data-ttu-id="882e2-122">Tipo de servidor de conferencia, como conf: chat (para mensajes instantáneos) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="882e2-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="882e2-123">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="882e2-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

