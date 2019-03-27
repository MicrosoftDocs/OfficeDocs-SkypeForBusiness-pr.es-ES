---
title: Tabla Roles
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: En la tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891716"
---
# <a name="roles-table"></a><span data-ttu-id="63dfe-103">Tabla Roles</span><span class="sxs-lookup"><span data-stu-id="63dfe-103">Roles table</span></span>
 
<span data-ttu-id="63dfe-104">En la tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.</span><span class="sxs-lookup"><span data-stu-id="63dfe-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="63dfe-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="63dfe-105">**Column**</span></span>|<span data-ttu-id="63dfe-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="63dfe-106">**Data Type**</span></span>|<span data-ttu-id="63dfe-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="63dfe-107">**Key/Index**</span></span>|<span data-ttu-id="63dfe-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="63dfe-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63dfe-109">**Identificador de función**</span><span class="sxs-lookup"><span data-stu-id="63dfe-109">**RoleId**</span></span> <br/> |<span data-ttu-id="63dfe-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="63dfe-110">tinyint</span></span>  <br/> |<span data-ttu-id="63dfe-111">Primary</span><span class="sxs-lookup"><span data-stu-id="63dfe-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="63dfe-112">**Rol**</span><span class="sxs-lookup"><span data-stu-id="63dfe-112">**Role**</span></span> <br/> |<span data-ttu-id="63dfe-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63dfe-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="63dfe-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="63dfe-114">Allowed values:</span></span> <br/>  <span data-ttu-id="63dfe-115">0 - Unknown (desconocido)</span><span class="sxs-lookup"><span data-stu-id="63dfe-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="63dfe-116">1 - moderador</span><span class="sxs-lookup"><span data-stu-id="63dfe-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="63dfe-117">2 - attendee</span><span class="sxs-lookup"><span data-stu-id="63dfe-117">2 - Attendee</span></span> <br/> |
   

