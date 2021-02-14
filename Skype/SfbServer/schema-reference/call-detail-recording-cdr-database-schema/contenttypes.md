---
title: Tabla ContentTypes en Skype Empresarial Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabla ContentTypes es una tabla auxiliar que almacena una lista de los tipos de contenido utilizados en sesiones punto a punto y sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816090"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9de4d-104">Tabla ContentTypes en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9de4d-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9de4d-p102">La tabla ContentTypes es una tabla auxiliar que almacena una lista de los tipos de contenido utilizados en sesiones punto a punto y sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="9de4d-p102">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions. Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="9de4d-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9de4d-107">**Column**</span></span>|<span data-ttu-id="9de4d-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9de4d-108">**Data Type**</span></span>|<span data-ttu-id="9de4d-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="9de4d-109">**Key/Index**</span></span>|<span data-ttu-id="9de4d-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9de4d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9de4d-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="9de4d-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="9de4d-112">entero</span><span class="sxs-lookup"><span data-stu-id="9de4d-112">int</span></span>  <br/> |<span data-ttu-id="9de4d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="9de4d-113">Primary</span></span>  <br/> |<span data-ttu-id="9de4d-114">Número único de identificación del tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="9de4d-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="9de4d-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="9de4d-115">**ContentType**</span></span> <br/> |<span data-ttu-id="9de4d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9de4d-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9de4d-117">Nombre del tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="9de4d-117">Content type name.</span></span>  <br/> |
   

