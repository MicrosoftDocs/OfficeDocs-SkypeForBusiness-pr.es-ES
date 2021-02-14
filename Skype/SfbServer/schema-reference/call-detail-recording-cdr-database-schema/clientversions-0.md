---
title: Vista ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813360"
---
# <a name="clientversions-view"></a><span data-ttu-id="63779-105">Vista ClientVersions</span><span class="sxs-lookup"><span data-stu-id="63779-105">ClientVersions view</span></span>
 
<span data-ttu-id="63779-106">La vista ClientVersions almacena información sobre los diversos tipos de clientes y versiones que han participado en las sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="63779-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="63779-107">Cada registro de la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="63779-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="63779-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63779-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63779-109">Puede haber varios registros para determinadas columnas.</span><span class="sxs-lookup"><span data-stu-id="63779-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="63779-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="63779-110">**Column**</span></span>|<span data-ttu-id="63779-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="63779-111">**Data Type**</span></span>|<span data-ttu-id="63779-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="63779-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63779-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="63779-113">**VersionId**</span></span> <br/> |<span data-ttu-id="63779-114">entero</span><span class="sxs-lookup"><span data-stu-id="63779-114">int</span></span>  <br/> |<span data-ttu-id="63779-115">Número único de identificación de esta versión y este tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="63779-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="63779-116">**Versión**</span><span class="sxs-lookup"><span data-stu-id="63779-116">**Version**</span></span> <br/> |<span data-ttu-id="63779-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63779-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="63779-118">Representa el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="63779-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="63779-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="63779-119">**ClientType**</span></span> <br/> |<span data-ttu-id="63779-120">entero</span><span class="sxs-lookup"><span data-stu-id="63779-120">int</span></span>  <br/> |<span data-ttu-id="63779-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="63779-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="63779-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="63779-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="63779-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="63779-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="63779-p103">Categoría a la que pertenece el cliente. Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="63779-p103">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

