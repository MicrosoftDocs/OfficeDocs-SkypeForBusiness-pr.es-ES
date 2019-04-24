---
title: Tabla Dialog
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabla diálogo es una tabla de apoyo; cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).
ms.openlocfilehash: 017da65154d12c89aeed63ea59269639d23b2129
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212575"
---
# <a name="dialog-table"></a><span data-ttu-id="df877-103">Tabla Dialog</span><span class="sxs-lookup"><span data-stu-id="df877-103">Dialog table</span></span>
 
<span data-ttu-id="df877-104">La tabla diálogo es una tabla de apoyo; cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="df877-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="df877-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="df877-105">**Column**</span></span>|<span data-ttu-id="df877-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="df877-106">**Data Type**</span></span>|<span data-ttu-id="df877-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="df877-107">**Key/Index**</span></span>|<span data-ttu-id="df877-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="df877-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="df877-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="df877-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="df877-110">datetime</span><span class="sxs-lookup"><span data-stu-id="df877-110">datetime</span></span>  <br/> |<span data-ttu-id="df877-111">Primary</span><span class="sxs-lookup"><span data-stu-id="df877-111">Primary</span></span>  <br/> |<span data-ttu-id="df877-112">Hora cuando el agente de calidad de excelencia (QoE) recibe el primer informe de autor de la llamada o destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="df877-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="df877-113">Se utiliza junto con SessionSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="df877-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="df877-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="df877-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="df877-115">int</span><span class="sxs-lookup"><span data-stu-id="df877-115">int</span></span>  <br/> |<span data-ttu-id="df877-116">Primary</span><span class="sxs-lookup"><span data-stu-id="df877-116">Primary</span></span>  <br/> |<span data-ttu-id="df877-117">Número de secuencia para diferenciar sesiones cuando tienen el mismo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="df877-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="df877-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="df877-118">**DialogID**</span></span> <br/> |<span data-ttu-id="df877-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="df877-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="df877-120">Identificador del cuadro de diálogo que es globalmente único.</span><span class="sxs-lookup"><span data-stu-id="df877-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="df877-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="df877-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="df877-122">int</span><span class="sxs-lookup"><span data-stu-id="df877-122">int</span></span>  <br/> |<span data-ttu-id="df877-123">índice</span><span class="sxs-lookup"><span data-stu-id="df877-123">index</span></span>  <br/> |<span data-ttu-id="df877-124">Suma de comprobación del identificador del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="df877-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

