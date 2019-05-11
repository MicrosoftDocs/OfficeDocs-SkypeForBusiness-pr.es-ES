---
title: Tabla Roles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: En la tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930307"
---
# <a name="roles-table"></a><span data-ttu-id="ff872-103">Tabla Roles</span><span class="sxs-lookup"><span data-stu-id="ff872-103">Roles table</span></span>
 
<span data-ttu-id="ff872-104">En la tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.</span><span class="sxs-lookup"><span data-stu-id="ff872-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="ff872-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ff872-105">**Column**</span></span>|<span data-ttu-id="ff872-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ff872-106">**Data Type**</span></span>|<span data-ttu-id="ff872-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ff872-107">**Key/Index**</span></span>|<span data-ttu-id="ff872-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ff872-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff872-109">**Identificador de función**</span><span class="sxs-lookup"><span data-stu-id="ff872-109">**RoleId**</span></span> <br/> |<span data-ttu-id="ff872-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ff872-110">tinyint</span></span>  <br/> |<span data-ttu-id="ff872-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ff872-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ff872-112">**Rol**</span><span class="sxs-lookup"><span data-stu-id="ff872-112">**Role**</span></span> <br/> |<span data-ttu-id="ff872-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ff872-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ff872-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="ff872-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ff872-115">0 - Unknown (desconocido)</span><span class="sxs-lookup"><span data-stu-id="ff872-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="ff872-116">1 - moderador</span><span class="sxs-lookup"><span data-stu-id="ff872-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="ff872-117">2 - attendee</span><span class="sxs-lookup"><span data-stu-id="ff872-117">2 - Attendee</span></span> <br/> |
   

