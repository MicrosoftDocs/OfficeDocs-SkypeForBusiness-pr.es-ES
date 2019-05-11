---
title: Tabla CallType en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: En la tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamada.
ms.openlocfilehash: a75ae3e22d435241e6bf2eb81b8268a7f1bb5a40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924797"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="48d33-103">Tabla CallType en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="48d33-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="48d33-104">En la tabla CallType es una tabla estática que almacena la lista de posibles tipos de llamada.</span><span class="sxs-lookup"><span data-stu-id="48d33-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="48d33-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="48d33-105">**Column**</span></span>|<span data-ttu-id="48d33-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="48d33-106">**Data Type**</span></span>|<span data-ttu-id="48d33-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="48d33-107">**Key/Index**</span></span>|<span data-ttu-id="48d33-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="48d33-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48d33-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="48d33-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="48d33-110">int</span><span class="sxs-lookup"><span data-stu-id="48d33-110">int</span></span>  <br/> |<span data-ttu-id="48d33-111">Primary</span><span class="sxs-lookup"><span data-stu-id="48d33-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="48d33-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="48d33-112">**CallType**</span></span> <br/> |<span data-ttu-id="48d33-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="48d33-113">nvarchar</span></span>  <br/> || <span data-ttu-id="48d33-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="48d33-114">Allowed values:</span></span> <br/>  <span data-ttu-id="48d33-115">0--Unknown (desconocido)</span><span class="sxs-lookup"><span data-stu-id="48d33-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="48d33-116">1: instantánea de mensajería</span><span class="sxs-lookup"><span data-stu-id="48d33-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="48d33-117">2--Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="48d33-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="48d33-118">3--audio</span><span class="sxs-lookup"><span data-stu-id="48d33-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="48d33-119">4 - audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="48d33-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="48d33-120">5 - transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="48d33-120">5 - File Transfer</span></span> <br/> |
   

