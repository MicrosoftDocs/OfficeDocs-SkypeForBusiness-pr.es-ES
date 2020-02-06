---
title: Tabla Roles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814938"
---
# <a name="roles-table"></a><span data-ttu-id="1fd4e-103">Tabla Roles</span><span class="sxs-lookup"><span data-stu-id="1fd4e-103">Roles table</span></span>
 
<span data-ttu-id="1fd4e-104">La tabla roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.</span><span class="sxs-lookup"><span data-stu-id="1fd4e-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="1fd4e-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1fd4e-105">**Column**</span></span>|<span data-ttu-id="1fd4e-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1fd4e-106">**Data Type**</span></span>|<span data-ttu-id="1fd4e-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1fd4e-107">**Key/Index**</span></span>|<span data-ttu-id="1fd4e-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1fd4e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1fd4e-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="1fd4e-109">**RoleId**</span></span> <br/> |<span data-ttu-id="1fd4e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1fd4e-110">tinyint</span></span>  <br/> |<span data-ttu-id="1fd4e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1fd4e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="1fd4e-112">**Rol**</span><span class="sxs-lookup"><span data-stu-id="1fd4e-112">**Role**</span></span> <br/> |<span data-ttu-id="1fd4e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1fd4e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1fd4e-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="1fd4e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="1fd4e-115">0: desconocido</span><span class="sxs-lookup"><span data-stu-id="1fd4e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="1fd4e-116">1: moderador</span><span class="sxs-lookup"><span data-stu-id="1fd4e-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="1fd4e-117">2-asistente</span><span class="sxs-lookup"><span data-stu-id="1fd4e-117">2 - Attendee</span></span> <br/> |
   

