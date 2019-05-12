---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924811"
---
# <a name="tblserveridentity"></a><span data-ttu-id="1fc48-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="1fc48-103">tblServerIdentity</span></span>
 
<span data-ttu-id="1fc48-104">la tabla tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1fc48-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="1fc48-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1fc48-105">**Columns**</span></span>

|<span data-ttu-id="1fc48-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1fc48-106">**Column**</span></span>|<span data-ttu-id="1fc48-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1fc48-107">**Type**</span></span>|<span data-ttu-id="1fc48-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1fc48-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1fc48-109">serverID</span><span class="sxs-lookup"><span data-stu-id="1fc48-109">serverID</span></span>  <br/> |<span data-ttu-id="1fc48-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="1fc48-110">int, not null</span></span>  <br/> |<span data-ttu-id="1fc48-111">Identificador de servidor.</span><span class="sxs-lookup"><span data-stu-id="1fc48-111">Server ID.</span></span> <span data-ttu-id="1fc48-112">Se corresponde con un identificador de instancia de almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="1fc48-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="1fc48-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="1fc48-113">serverAddress</span></span>  <br/> |<span data-ttu-id="1fc48-114">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="1fc48-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1fc48-115">Dirección de servidor con la dirección de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="1fc48-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="1fc48-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="1fc48-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="1fc48-117">datetime</span><span class="sxs-lookup"><span data-stu-id="1fc48-117">datetime</span></span>  <br/> |<span data-ttu-id="1fc48-118">La última vez que el servidor de canal actualizó esta fila para probar que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="1fc48-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="1fc48-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="1fc48-119">**Key**</span></span>

|<span data-ttu-id="1fc48-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1fc48-120">**Column**</span></span>|<span data-ttu-id="1fc48-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1fc48-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fc48-122">serverID</span><span class="sxs-lookup"><span data-stu-id="1fc48-122">serverID</span></span>  <br/> |<span data-ttu-id="1fc48-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="1fc48-123">Primary key.</span></span>  <br/> |
   

