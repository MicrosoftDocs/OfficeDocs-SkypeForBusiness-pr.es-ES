---
title: Vista FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos de punto a punto. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815208"
---
# <a name="filetransfers-view"></a><span data-ttu-id="8562c-104">Vista FileTransfers</span><span class="sxs-lookup"><span data-stu-id="8562c-104">FileTransfers view</span></span>
 
<span data-ttu-id="8562c-105">La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="8562c-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="8562c-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8562c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8562c-107">La vista FileTransfers contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las columnas que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="8562c-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="8562c-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8562c-108">**Column**</span></span>|<span data-ttu-id="8562c-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="8562c-109">**Data Type**</span></span>|<span data-ttu-id="8562c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="8562c-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8562c-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="8562c-111">**FileName**</span></span> <br/> |<span data-ttu-id="8562c-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8562c-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8562c-113">Nombre del archivo transferido.</span><span class="sxs-lookup"><span data-stu-id="8562c-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="8562c-114">**Ésta**</span><span class="sxs-lookup"><span data-stu-id="8562c-114">**Cookie**</span></span> <br/> |<span data-ttu-id="8562c-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8562c-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="8562c-116">Se usa para identificar cada mensaje de seguimiento como asociado con este.</span><span class="sxs-lookup"><span data-stu-id="8562c-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="8562c-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="8562c-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="8562c-118">identificador</span><span class="sxs-lookup"><span data-stu-id="8562c-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="8562c-119">Identificador único para distinguir entre transferencias de archivos que impliquen el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="8562c-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="8562c-120">**Aceptable**</span><span class="sxs-lookup"><span data-stu-id="8562c-120">**Accept**</span></span> <br/> |<span data-ttu-id="8562c-121">bit</span><span class="sxs-lookup"><span data-stu-id="8562c-121">bit</span></span>  <br/> |<span data-ttu-id="8562c-122">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="8562c-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="8562c-123">Si es verdadero, rechazar y cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="8562c-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="8562c-124">**Rechace**</span><span class="sxs-lookup"><span data-stu-id="8562c-124">**Reject**</span></span> <br/> |<span data-ttu-id="8562c-125">bit</span><span class="sxs-lookup"><span data-stu-id="8562c-125">bit</span></span>  <br/> |<span data-ttu-id="8562c-126">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="8562c-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="8562c-127">Si es verdadero, aceptar y cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="8562c-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="8562c-128">**Cancelar.**</span><span class="sxs-lookup"><span data-stu-id="8562c-128">**Cancel**</span></span> <br/> |<span data-ttu-id="8562c-129">bit</span><span class="sxs-lookup"><span data-stu-id="8562c-129">bit</span></span>  <br/> |<span data-ttu-id="8562c-130">Puede ser TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="8562c-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="8562c-131">Si es verdadero, aceptar y rechazar serán NULOs.</span><span class="sxs-lookup"><span data-stu-id="8562c-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

