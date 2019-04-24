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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212421"
---
# <a name="tblserveridentity"></a><span data-ttu-id="1d096-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="1d096-103">tblServerIdentity</span></span>
 
<span data-ttu-id="1d096-104">la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1d096-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="1d096-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1d096-105">**Columns**</span></span>

|<span data-ttu-id="1d096-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1d096-106">**Column**</span></span>|<span data-ttu-id="1d096-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1d096-107">**Type**</span></span>|<span data-ttu-id="1d096-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1d096-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d096-109">serverID</span><span class="sxs-lookup"><span data-stu-id="1d096-109">serverID</span></span>  <br/> |<span data-ttu-id="1d096-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="1d096-110">int, not null</span></span>  <br/> |<span data-ttu-id="1d096-111">Identificador de servidor.</span><span class="sxs-lookup"><span data-stu-id="1d096-111">Server ID.</span></span> <span data-ttu-id="1d096-112">Se corresponde con un identificador de instancia de almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="1d096-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="1d096-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="1d096-113">serverAddress</span></span>  <br/> |<span data-ttu-id="1d096-114">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="1d096-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1d096-115">Dirección de servidor con la dirección de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="1d096-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="1d096-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="1d096-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="1d096-117">datetime</span><span class="sxs-lookup"><span data-stu-id="1d096-117">datetime</span></span>  <br/> |<span data-ttu-id="1d096-118">La última vez que el servidor de canal actualizó esta fila para probar que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="1d096-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="1d096-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="1d096-119">**Key**</span></span>

|<span data-ttu-id="1d096-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1d096-120">**Column**</span></span>|<span data-ttu-id="1d096-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1d096-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d096-122">serverID</span><span class="sxs-lookup"><span data-stu-id="1d096-122">serverID</span></span>  <br/> |<span data-ttu-id="1d096-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="1d096-123">Primary key.</span></span>  <br/> |
   

