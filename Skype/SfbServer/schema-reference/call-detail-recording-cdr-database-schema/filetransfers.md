---
title: Vista FileTransfers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTransfer almacena información acerca de las sesiones de transferencia de archivos de punto a punto. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213091"
---
# <a name="filetransfers-view"></a><span data-ttu-id="4c0db-104">Vista FileTransfers</span><span class="sxs-lookup"><span data-stu-id="4c0db-104">FileTransfers view</span></span>
 
<span data-ttu-id="4c0db-105">La vista FileTransfer almacena información acerca de las sesiones de transferencia de archivos de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="4c0db-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="4c0db-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c0db-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c0db-107">La vista FileTransfers contiene todos los de las columnas de la [SessionDetails view](sessiondetails-0.md) además las columnas enumeradas a continuación.</span><span class="sxs-lookup"><span data-stu-id="4c0db-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="4c0db-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4c0db-108">**Column**</span></span>|<span data-ttu-id="4c0db-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4c0db-109">**Data Type**</span></span>|<span data-ttu-id="4c0db-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="4c0db-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c0db-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="4c0db-111">**FileName**</span></span> <br/> |<span data-ttu-id="4c0db-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4c0db-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4c0db-113">Nombre del archivo transferido.</span><span class="sxs-lookup"><span data-stu-id="4c0db-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="4c0db-114">**Galleta**</span><span class="sxs-lookup"><span data-stu-id="4c0db-114">**Cookie**</span></span> <br/> |<span data-ttu-id="4c0db-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="4c0db-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="4c0db-116">Se usa para identificar todos los mensajes de seguimiento que están asociadas con éste.</span><span class="sxs-lookup"><span data-stu-id="4c0db-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="4c0db-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="4c0db-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="4c0db-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4c0db-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4c0db-119">Identificador único para distinguir entre las transferencias de archivos que implican el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="4c0db-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="4c0db-120">**Aceptar**</span><span class="sxs-lookup"><span data-stu-id="4c0db-120">**Accept**</span></span> <br/> |<span data-ttu-id="4c0db-121">bit</span><span class="sxs-lookup"><span data-stu-id="4c0db-121">bit</span></span>  <br/> |<span data-ttu-id="4c0db-122">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="4c0db-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="4c0db-123">Si es TRUE, a continuación, rechazar y cancelar será NULL.</span><span class="sxs-lookup"><span data-stu-id="4c0db-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="4c0db-124">**Rechazar**</span><span class="sxs-lookup"><span data-stu-id="4c0db-124">**Reject**</span></span> <br/> |<span data-ttu-id="4c0db-125">bit</span><span class="sxs-lookup"><span data-stu-id="4c0db-125">bit</span></span>  <br/> |<span data-ttu-id="4c0db-126">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="4c0db-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="4c0db-127">Si es TRUE, a continuación, Aceptar y cancelar será NULL.</span><span class="sxs-lookup"><span data-stu-id="4c0db-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="4c0db-128">**Cancelar.**</span><span class="sxs-lookup"><span data-stu-id="4c0db-128">**Cancel**</span></span> <br/> |<span data-ttu-id="4c0db-129">bit</span><span class="sxs-lookup"><span data-stu-id="4c0db-129">bit</span></span>  <br/> |<span data-ttu-id="4c0db-130">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="4c0db-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="4c0db-131">Si es TRUE, a continuación, Aceptar y rechazar será NULL.</span><span class="sxs-lookup"><span data-stu-id="4c0db-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

