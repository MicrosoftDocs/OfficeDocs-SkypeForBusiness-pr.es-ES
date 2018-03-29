---
title: Vista de Bloqueandote
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTranfer almacena información acerca de las sesiones de transferencia de archivos de igual a igual. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a><span data-ttu-id="06f53-104">Vista de Bloqueandote</span><span class="sxs-lookup"><span data-stu-id="06f53-104">FileTransfers view</span></span>
 
<span data-ttu-id="06f53-105">La vista FileTranfer almacena información acerca de las sesiones de transferencia de archivos de igual a igual.</span><span class="sxs-lookup"><span data-stu-id="06f53-105">The FileTranfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="06f53-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06f53-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06f53-107">La vista Bloqueandote contiene todas las columnas en la [vista SessionDetails](sessiondetails-0.md) además las columnas enumeradas a continuación.</span><span class="sxs-lookup"><span data-stu-id="06f53-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="06f53-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="06f53-108">**Column**</span></span>|<span data-ttu-id="06f53-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="06f53-109">**Data Type**</span></span>|<span data-ttu-id="06f53-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="06f53-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="06f53-111">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="06f53-111">**FileName**</span></span> <br/> |<span data-ttu-id="06f53-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06f53-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="06f53-113">Nombre del archivo transferido.</span><span class="sxs-lookup"><span data-stu-id="06f53-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="06f53-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="06f53-114">**Cookie**</span></span> <br/> |<span data-ttu-id="06f53-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="06f53-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="06f53-116">Se utiliza para identificar cada mensaje de seguimiento que están asociadas con éste.</span><span class="sxs-lookup"><span data-stu-id="06f53-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="06f53-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="06f53-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="06f53-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="06f53-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="06f53-119">Identificador único para distinguir entre las transferencias de archivos con el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="06f53-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="06f53-120">**Aceptar**</span><span class="sxs-lookup"><span data-stu-id="06f53-120">**Accept**</span></span> <br/> |<span data-ttu-id="06f53-121">bit</span><span class="sxs-lookup"><span data-stu-id="06f53-121">bit</span></span>  <br/> |<span data-ttu-id="06f53-122">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="06f53-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="06f53-123">Si es TRUE, a continuación, rechazar y cancelar será NULL.</span><span class="sxs-lookup"><span data-stu-id="06f53-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="06f53-124">**Rechazar**</span><span class="sxs-lookup"><span data-stu-id="06f53-124">**Reject**</span></span> <br/> |<span data-ttu-id="06f53-125">bit</span><span class="sxs-lookup"><span data-stu-id="06f53-125">bit</span></span>  <br/> |<span data-ttu-id="06f53-126">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="06f53-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="06f53-127">Si es TRUE, a continuación, Aceptar y cancelar será NULL.</span><span class="sxs-lookup"><span data-stu-id="06f53-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="06f53-128">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="06f53-128">**Cancel**</span></span> <br/> |<span data-ttu-id="06f53-129">bit</span><span class="sxs-lookup"><span data-stu-id="06f53-129">bit</span></span>  <br/> |<span data-ttu-id="06f53-130">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="06f53-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="06f53-131">Si es TRUE, a continuación, Aceptar y rechazar será NULL.</span><span class="sxs-lookup"><span data-stu-id="06f53-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

