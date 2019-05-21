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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295898"
---
# <a name="roles-table"></a><span data-ttu-id="0d4d1-103">Tabla Roles</span><span class="sxs-lookup"><span data-stu-id="0d4d1-103">Roles table</span></span>
 
<span data-ttu-id="0d4d1-104">La tabla roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.</span><span class="sxs-lookup"><span data-stu-id="0d4d1-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="0d4d1-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0d4d1-105">**Column**</span></span>|<span data-ttu-id="0d4d1-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0d4d1-106">**Data Type**</span></span>|<span data-ttu-id="0d4d1-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0d4d1-107">**Key/Index**</span></span>|<span data-ttu-id="0d4d1-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0d4d1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0d4d1-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="0d4d1-109">**RoleId**</span></span> <br/> |<span data-ttu-id="0d4d1-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d4d1-110">tinyint</span></span>  <br/> |<span data-ttu-id="0d4d1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="0d4d1-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="0d4d1-112">**Rol**</span><span class="sxs-lookup"><span data-stu-id="0d4d1-112">**Role**</span></span> <br/> |<span data-ttu-id="0d4d1-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0d4d1-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="0d4d1-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="0d4d1-114">Allowed values:</span></span> <br/>  <span data-ttu-id="0d4d1-115">0: desconocido</span><span class="sxs-lookup"><span data-stu-id="0d4d1-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="0d4d1-116">1: moderador</span><span class="sxs-lookup"><span data-stu-id="0d4d1-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="0d4d1-117">2-asistente</span><span class="sxs-lookup"><span data-stu-id="0d4d1-117">2 - Attendee</span></span> <br/> |
   

