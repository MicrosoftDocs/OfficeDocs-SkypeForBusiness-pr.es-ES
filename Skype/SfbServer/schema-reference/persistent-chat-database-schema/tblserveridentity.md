---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899529"
---
# <a name="tblserveridentity"></a><span data-ttu-id="dcc09-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="dcc09-103">tblServerIdentity</span></span>
 
<span data-ttu-id="dcc09-104">la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dcc09-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="dcc09-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="dcc09-105">**Columns**</span></span>

|<span data-ttu-id="dcc09-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dcc09-106">**Column**</span></span>|<span data-ttu-id="dcc09-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dcc09-107">**Type**</span></span>|<span data-ttu-id="dcc09-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dcc09-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dcc09-109">serverID</span><span class="sxs-lookup"><span data-stu-id="dcc09-109">serverID</span></span>  <br/> |<span data-ttu-id="dcc09-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="dcc09-110">int, not null</span></span>  <br/> |<span data-ttu-id="dcc09-111">Identificador de servidor.</span><span class="sxs-lookup"><span data-stu-id="dcc09-111">Server ID.</span></span> <span data-ttu-id="dcc09-112">Se corresponde con un identificador de instancia de almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="dcc09-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="dcc09-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="dcc09-113">serverAddress</span></span>  <br/> |<span data-ttu-id="dcc09-114">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="dcc09-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="dcc09-115">Dirección de servidor con la dirección de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="dcc09-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="dcc09-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="dcc09-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="dcc09-117">datetime</span><span class="sxs-lookup"><span data-stu-id="dcc09-117">datetime</span></span>  <br/> |<span data-ttu-id="dcc09-118">La última vez que el servidor de canal actualizó esta fila para probar que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="dcc09-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="dcc09-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="dcc09-119">**Key**</span></span>

|<span data-ttu-id="dcc09-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dcc09-120">**Column**</span></span>|<span data-ttu-id="dcc09-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dcc09-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dcc09-122">serverID</span><span class="sxs-lookup"><span data-stu-id="dcc09-122">serverID</span></span>  <br/> |<span data-ttu-id="dcc09-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="dcc09-123">Primary key.</span></span>  <br/> |
   

