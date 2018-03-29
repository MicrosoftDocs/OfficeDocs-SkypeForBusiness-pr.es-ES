---
title: Tabla Roles
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla de funciones es una tabla estática que almacena la lista de funciones de conferencia posibles, como asistente y moderador.
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a><span data-ttu-id="1f5e3-103">Tabla Roles</span><span class="sxs-lookup"><span data-stu-id="1f5e3-103">Roles table</span></span>
 
<span data-ttu-id="1f5e3-104">La tabla de funciones es una tabla estática que almacena la lista de funciones de conferencia posibles, como asistente y moderador.</span><span class="sxs-lookup"><span data-stu-id="1f5e3-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="1f5e3-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1f5e3-105">**Column**</span></span>|<span data-ttu-id="1f5e3-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1f5e3-106">**Data Type**</span></span>|<span data-ttu-id="1f5e3-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1f5e3-107">**Key/Index**</span></span>|<span data-ttu-id="1f5e3-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1f5e3-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f5e3-109">**Identificador de función**</span><span class="sxs-lookup"><span data-stu-id="1f5e3-109">**RoleId**</span></span> <br/> |<span data-ttu-id="1f5e3-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1f5e3-110">tinyint</span></span>  <br/> |<span data-ttu-id="1f5e3-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1f5e3-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="1f5e3-112">**Rol**</span><span class="sxs-lookup"><span data-stu-id="1f5e3-112">**Role**</span></span> <br/> |<span data-ttu-id="1f5e3-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f5e3-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1f5e3-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="1f5e3-114">Allowed values:</span></span> <br/>  <span data-ttu-id="1f5e3-115">0 - desconocido</span><span class="sxs-lookup"><span data-stu-id="1f5e3-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="1f5e3-116">1 - presenter</span><span class="sxs-lookup"><span data-stu-id="1f5e3-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="1f5e3-117">2 - Asistente</span><span class="sxs-lookup"><span data-stu-id="1f5e3-117">2 - Attendee</span></span> <br/> |
   

