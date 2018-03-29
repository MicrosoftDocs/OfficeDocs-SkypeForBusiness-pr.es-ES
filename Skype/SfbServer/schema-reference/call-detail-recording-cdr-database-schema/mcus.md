---
title: Tabla de MCU en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La tabla de la MCU es una tabla de soporte. Cada registro almacena información acerca de un servicio de conferencias. Éstos pueden incluir el servicio Conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end) y el servicio de conferencias Web y A / servicio de conferencias audiovisuales.
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5fa2b-105">Tabla de MCU en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5fa2b-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5fa2b-106">La tabla de la MCU es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="5fa2b-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="5fa2b-107">Cada registro almacena información acerca de un servicio de conferencias.</span><span class="sxs-lookup"><span data-stu-id="5fa2b-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="5fa2b-108">Éstos pueden incluir el servicio Conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en servidores front-end) y el servicio de conferencias Web y A / servicio de conferencias audiovisuales.</span><span class="sxs-lookup"><span data-stu-id="5fa2b-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="5fa2b-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5fa2b-109">**Column**</span></span>|<span data-ttu-id="5fa2b-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5fa2b-110">**Data Type**</span></span>|<span data-ttu-id="5fa2b-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="5fa2b-111">**Key/Index**</span></span>|<span data-ttu-id="5fa2b-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5fa2b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5fa2b-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="5fa2b-113">**McuId**</span></span> <br/> |<span data-ttu-id="5fa2b-114">int</span><span class="sxs-lookup"><span data-stu-id="5fa2b-114">int</span></span>  <br/> |<span data-ttu-id="5fa2b-115">Primary</span><span class="sxs-lookup"><span data-stu-id="5fa2b-115">Primary</span></span>  <br/> |<span data-ttu-id="5fa2b-116">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="5fa2b-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="5fa2b-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="5fa2b-117">**McuUri**</span></span> <br/> |<span data-ttu-id="5fa2b-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="5fa2b-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="5fa2b-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="5fa2b-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="5fa2b-120">inyint</span><span class="sxs-lookup"><span data-stu-id="5fa2b-120">inyint</span></span>  <br/> | <span data-ttu-id="5fa2b-121">Externa</span><span class="sxs-lookup"><span data-stu-id="5fa2b-121">Foreign</span></span> <br/> |<span data-ttu-id="5fa2b-122">Tipo de servidor de conferencias, como conf:chat (para IMs) o conf:audio-vídeo.</span><span class="sxs-lookup"><span data-stu-id="5fa2b-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="5fa2b-123">Consulte la [tabla de UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5fa2b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

