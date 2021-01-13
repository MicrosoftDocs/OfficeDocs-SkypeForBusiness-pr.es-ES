---
title: Tabla dialog
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabla Diálogo es una tabla de apoyo, en la que cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815850"
---
# <a name="dialog-table"></a><span data-ttu-id="10ab1-103">Tabla dialog</span><span class="sxs-lookup"><span data-stu-id="10ab1-103">Dialog table</span></span>
 
<span data-ttu-id="10ab1-104">La tabla Diálogo es una tabla de apoyo, en la que cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="10ab1-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="10ab1-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="10ab1-105">**Column**</span></span>|<span data-ttu-id="10ab1-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ab1-106">**Data Type**</span></span>|<span data-ttu-id="10ab1-107">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="10ab1-107">**Key/Index**</span></span>|<span data-ttu-id="10ab1-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="10ab1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10ab1-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="10ab1-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="10ab1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="10ab1-110">datetime</span></span>  <br/> |<span data-ttu-id="10ab1-111">Principal</span><span class="sxs-lookup"><span data-stu-id="10ab1-111">Primary</span></span>  <br/> |<span data-ttu-id="10ab1-p101">Momento en el que el agente de calidad de la experiencia (QoE) recibe el primer informe del autor o del destinatario de la llamada. Se usa junto con SessionSeq para identificar una sesión de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="10ab1-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="10ab1-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="10ab1-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="10ab1-115">entero</span><span class="sxs-lookup"><span data-stu-id="10ab1-115">int</span></span>  <br/> |<span data-ttu-id="10ab1-116">Principal</span><span class="sxs-lookup"><span data-stu-id="10ab1-116">Primary</span></span>  <br/> |<span data-ttu-id="10ab1-117">Número de secuencia que se usa para diferenciar sesiones cuando tienen el mismo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="10ab1-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="10ab1-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="10ab1-118">**DialogID**</span></span> <br/> |<span data-ttu-id="10ab1-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="10ab1-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="10ab1-120">Id. de diálogo, exclusivo a nivel global.</span><span class="sxs-lookup"><span data-stu-id="10ab1-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="10ab1-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="10ab1-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="10ab1-122">entero</span><span class="sxs-lookup"><span data-stu-id="10ab1-122">int</span></span>  <br/> |<span data-ttu-id="10ab1-123">index</span><span class="sxs-lookup"><span data-stu-id="10ab1-123">index</span></span>  <br/> |<span data-ttu-id="10ab1-124">Suma de comprobación del Id. de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10ab1-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

