---
title: Tabla Dialog
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: El cuadro de diálogo es una tabla de soporte; cada registro representa un cuadro de diálogo Protocolo de inicio de sesión (SIP).
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a><span data-ttu-id="0ffbc-103">Tabla Dialog</span><span class="sxs-lookup"><span data-stu-id="0ffbc-103">Dialog table</span></span>
 
<span data-ttu-id="0ffbc-104">El cuadro de diálogo es una tabla de soporte; cada registro representa un cuadro de diálogo Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="0ffbc-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="0ffbc-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-105">**Column**</span></span>|<span data-ttu-id="0ffbc-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-106">**Data Type**</span></span>|<span data-ttu-id="0ffbc-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-107">**Key/Index**</span></span>|<span data-ttu-id="0ffbc-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ffbc-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="0ffbc-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0ffbc-110">datetime</span></span>  <br/> |<span data-ttu-id="0ffbc-111">Primary</span><span class="sxs-lookup"><span data-stu-id="0ffbc-111">Primary</span></span>  <br/> |<span data-ttu-id="0ffbc-112">Tiempo cuando el agente de excelencia de la calidad (QoE) recibe el primer informe de llamador o destinatario.</span><span class="sxs-lookup"><span data-stu-id="0ffbc-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="0ffbc-113">Se utiliza junto con SessionSeq para identificar una sesión.</span><span class="sxs-lookup"><span data-stu-id="0ffbc-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="0ffbc-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="0ffbc-115">int</span><span class="sxs-lookup"><span data-stu-id="0ffbc-115">int</span></span>  <br/> |<span data-ttu-id="0ffbc-116">Primary</span><span class="sxs-lookup"><span data-stu-id="0ffbc-116">Primary</span></span>  <br/> |<span data-ttu-id="0ffbc-117">Número de secuencia para diferenciar las sesiones cuando tienen el mismo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="0ffbc-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="0ffbc-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-118">**DialogID**</span></span> <br/> |<span data-ttu-id="0ffbc-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0ffbc-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="0ffbc-120">Id. de cuadro de diálogo que es globalmente único.</span><span class="sxs-lookup"><span data-stu-id="0ffbc-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="0ffbc-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="0ffbc-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="0ffbc-122">int</span><span class="sxs-lookup"><span data-stu-id="0ffbc-122">int</span></span>  <br/> |<span data-ttu-id="0ffbc-123">índice</span><span class="sxs-lookup"><span data-stu-id="0ffbc-123">index</span></span>  <br/> |<span data-ttu-id="0ffbc-124">Suma de comprobación de la Id.</span><span class="sxs-lookup"><span data-stu-id="0ffbc-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

