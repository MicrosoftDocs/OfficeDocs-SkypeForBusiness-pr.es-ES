---
title: Tabla ContentTypes en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabla ContentTypes es una tabla de soporte que almacena una lista de los tipos de contenido que se usan en sesiones de punto a punto y en sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296374"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9920a-104">Tabla ContentTypes en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9920a-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9920a-105">La tabla ContentTypes es una tabla de soporte que almacena una lista de los tipos de contenido que se usan en sesiones de punto a punto y en sesiones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9920a-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="9920a-106">Cada registro de la tabla representa un tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="9920a-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="9920a-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9920a-107">**Column**</span></span>|<span data-ttu-id="9920a-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9920a-108">**Data Type**</span></span>|<span data-ttu-id="9920a-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="9920a-109">**Key/Index**</span></span>|<span data-ttu-id="9920a-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9920a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9920a-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="9920a-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="9920a-112">int</span><span class="sxs-lookup"><span data-stu-id="9920a-112">int</span></span>  <br/> |<span data-ttu-id="9920a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9920a-113">Primary</span></span>  <br/> |<span data-ttu-id="9920a-114">Número único que identifica el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="9920a-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="9920a-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="9920a-115">**ContentType**</span></span> <br/> |<span data-ttu-id="9920a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9920a-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9920a-117">Nombre del tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="9920a-117">Content type name.</span></span>  <br/> |
   

