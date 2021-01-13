---
title: Vista FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos punto a punto. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821690"
---
# <a name="filetransfers-view"></a><span data-ttu-id="29ba8-104">Vista FileTransfers</span><span class="sxs-lookup"><span data-stu-id="29ba8-104">FileTransfers view</span></span>
 
<span data-ttu-id="29ba8-105">La vista FileTransfer almacena información sobre las sesiones de transferencia de archivos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="29ba8-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="29ba8-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29ba8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29ba8-107">La vista FileTransfers contiene todas las columnas de la vista [SessionDetails](sessiondetails-0.md) además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="29ba8-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="29ba8-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="29ba8-108">**Column**</span></span>|<span data-ttu-id="29ba8-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="29ba8-109">**Data Type**</span></span>|<span data-ttu-id="29ba8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="29ba8-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29ba8-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="29ba8-111">**FileName**</span></span> <br/> |<span data-ttu-id="29ba8-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="29ba8-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="29ba8-113">Nombre del archivo transferido.</span><span class="sxs-lookup"><span data-stu-id="29ba8-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="29ba8-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="29ba8-114">**Cookie**</span></span> <br/> |<span data-ttu-id="29ba8-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="29ba8-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="29ba8-116">Se usa para identificar cada mensaje de seguimiento como mensaje asociado a este.</span><span class="sxs-lookup"><span data-stu-id="29ba8-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="29ba8-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="29ba8-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="29ba8-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="29ba8-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="29ba8-119">Identificador único para distinguir entre las transferencias de archivos en las que participa el mismo nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="29ba8-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="29ba8-120">**Accept**</span><span class="sxs-lookup"><span data-stu-id="29ba8-120">**Accept**</span></span> <br/> |<span data-ttu-id="29ba8-121">bit</span><span class="sxs-lookup"><span data-stu-id="29ba8-121">bit</span></span>  <br/> |<span data-ttu-id="29ba8-p103">Puede ser TRUE o NULL. Si es TRUE, Rechazar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="29ba8-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="29ba8-124">**Reject**</span><span class="sxs-lookup"><span data-stu-id="29ba8-124">**Reject**</span></span> <br/> |<span data-ttu-id="29ba8-125">bit</span><span class="sxs-lookup"><span data-stu-id="29ba8-125">bit</span></span>  <br/> |<span data-ttu-id="29ba8-p104">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Cancelar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="29ba8-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="29ba8-128">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="29ba8-128">**Cancel**</span></span> <br/> |<span data-ttu-id="29ba8-129">bit</span><span class="sxs-lookup"><span data-stu-id="29ba8-129">bit</span></span>  <br/> |<span data-ttu-id="29ba8-p105">Puede ser TRUE o NULL. Si es TRUE, Aceptar y Rechazar serán NULL.</span><span class="sxs-lookup"><span data-stu-id="29ba8-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

