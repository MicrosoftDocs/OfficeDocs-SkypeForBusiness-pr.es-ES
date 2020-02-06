---
title: Tabla Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabla de diálogo es una tabla de soporte técnico; cada registro representa un cuadro de diálogo protocolo de inicio de sesión (SIP).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809538"
---
# <a name="dialog-table"></a><span data-ttu-id="d15e5-103">Tabla Dialog</span><span class="sxs-lookup"><span data-stu-id="d15e5-103">Dialog table</span></span>
 
<span data-ttu-id="d15e5-104">La tabla de diálogo es una tabla de soporte técnico; cada registro representa un cuadro de diálogo protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="d15e5-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="d15e5-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d15e5-105">**Column**</span></span>|<span data-ttu-id="d15e5-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d15e5-106">**Data Type**</span></span>|<span data-ttu-id="d15e5-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d15e5-107">**Key/Index**</span></span>|<span data-ttu-id="d15e5-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d15e5-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d15e5-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d15e5-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d15e5-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d15e5-110">datetime</span></span>  <br/> |<span data-ttu-id="d15e5-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d15e5-111">Primary</span></span>  <br/> |<span data-ttu-id="d15e5-112">Hora en que el agente de calidad de excelencia (QoE) recibe el primer informe de quien llama o de quien llama.</span><span class="sxs-lookup"><span data-stu-id="d15e5-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="d15e5-113">Se usa en conjunción con SessionSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="d15e5-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="d15e5-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d15e5-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d15e5-115">int</span><span class="sxs-lookup"><span data-stu-id="d15e5-115">int</span></span>  <br/> |<span data-ttu-id="d15e5-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d15e5-116">Primary</span></span>  <br/> |<span data-ttu-id="d15e5-117">Número de secuencia para diferenciar las sesiones cuando tienen el mismo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="d15e5-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="d15e5-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="d15e5-118">**DialogID**</span></span> <br/> |<span data-ttu-id="d15e5-119">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="d15e5-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="d15e5-120">IDENTIFICADOR de cuadro de diálogo único de forma global.</span><span class="sxs-lookup"><span data-stu-id="d15e5-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="d15e5-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="d15e5-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="d15e5-122">int</span><span class="sxs-lookup"><span data-stu-id="d15e5-122">int</span></span>  <br/> |<span data-ttu-id="d15e5-123">clasificación</span><span class="sxs-lookup"><span data-stu-id="d15e5-123">index</span></span>  <br/> |<span data-ttu-id="d15e5-124">Suma de comprobación del identificador de cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d15e5-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

