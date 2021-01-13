---
title: Tabla Roles
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809980"
---
# <a name="roles-table"></a><span data-ttu-id="9d835-103">Tabla Roles</span><span class="sxs-lookup"><span data-stu-id="9d835-103">Roles table</span></span>
 
<span data-ttu-id="9d835-104">La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.</span><span class="sxs-lookup"><span data-stu-id="9d835-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="9d835-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9d835-105">**Column**</span></span>|<span data-ttu-id="9d835-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9d835-106">**Data Type**</span></span>|<span data-ttu-id="9d835-107">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="9d835-107">**Key/Index**</span></span>|<span data-ttu-id="9d835-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9d835-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d835-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="9d835-109">**RoleId**</span></span> <br/> |<span data-ttu-id="9d835-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9d835-110">tinyint</span></span>  <br/> |<span data-ttu-id="9d835-111">Principal</span><span class="sxs-lookup"><span data-stu-id="9d835-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9d835-112">**Rol**</span><span class="sxs-lookup"><span data-stu-id="9d835-112">**Role**</span></span> <br/> |<span data-ttu-id="9d835-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9d835-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9d835-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="9d835-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9d835-115">0 - Desconocido</span><span class="sxs-lookup"><span data-stu-id="9d835-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="9d835-116">1 - Moderador</span><span class="sxs-lookup"><span data-stu-id="9d835-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="9d835-117">2 - Asistente</span><span class="sxs-lookup"><span data-stu-id="9d835-117">2 - Attendee</span></span> <br/> |
   

