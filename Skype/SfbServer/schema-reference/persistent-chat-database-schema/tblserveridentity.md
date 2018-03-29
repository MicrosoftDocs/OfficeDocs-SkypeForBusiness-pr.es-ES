---
title: tblServerIdentity
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene los servidores de chat activo en el grupo de servidor de charla persistente.
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a><span data-ttu-id="2b83f-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="2b83f-103">tblServerIdentity</span></span>
 
<span data-ttu-id="2b83f-104">tblServerIdentity contiene los servidores de chat activo en el grupo de servidor de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="2b83f-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="2b83f-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="2b83f-105">**Columns**</span></span>

|<span data-ttu-id="2b83f-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2b83f-106">**Column**</span></span>|<span data-ttu-id="2b83f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2b83f-107">**Type**</span></span>|<span data-ttu-id="2b83f-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2b83f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2b83f-109">serverID</span><span class="sxs-lookup"><span data-stu-id="2b83f-109">serverID</span></span>  <br/> |<span data-ttu-id="2b83f-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="2b83f-110">int, not null</span></span>  <br/> |<span data-ttu-id="2b83f-111">Identificador de servidor.</span><span class="sxs-lookup"><span data-stu-id="2b83f-111">Server ID.</span></span> <span data-ttu-id="2b83f-112">Corresponde a la ID de instancia de almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="2b83f-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="2b83f-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="2b83f-113">serverAddress</span></span>  <br/> |<span data-ttu-id="2b83f-114">nvarchar (256), no nulo</span><span class="sxs-lookup"><span data-stu-id="2b83f-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2b83f-115">Dirección del servidor mediante la dirección de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="2b83f-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="2b83f-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="2b83f-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="2b83f-117">datetime</span><span class="sxs-lookup"><span data-stu-id="2b83f-117">datetime</span></span>  <br/> |<span data-ttu-id="2b83f-118">La última hora en la que el servidor de canal actualizar esta fila para proporcionar evidencia de que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2b83f-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="2b83f-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="2b83f-119">**Key**</span></span>

|<span data-ttu-id="2b83f-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2b83f-120">**Column**</span></span>|<span data-ttu-id="2b83f-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2b83f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b83f-122">serverID</span><span class="sxs-lookup"><span data-stu-id="2b83f-122">serverID</span></span>  <br/> |<span data-ttu-id="2b83f-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="2b83f-123">Primary key.</span></span>  <br/> |
   

