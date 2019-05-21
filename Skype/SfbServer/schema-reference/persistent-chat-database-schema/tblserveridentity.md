---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de chat persistente.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295191"
---
# <a name="tblserveridentity"></a><span data-ttu-id="89297-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="89297-103">tblServerIdentity</span></span>
 
<span data-ttu-id="89297-104">tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="89297-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="89297-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="89297-105">**Columns**</span></span>

|<span data-ttu-id="89297-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="89297-106">**Column**</span></span>|<span data-ttu-id="89297-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="89297-107">**Type**</span></span>|<span data-ttu-id="89297-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="89297-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89297-109">serverID</span><span class="sxs-lookup"><span data-stu-id="89297-109">serverID</span></span>  <br/> |<span data-ttu-id="89297-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="89297-110">int, not null</span></span>  <br/> |<span data-ttu-id="89297-111">IDENTIFICADOR de servidor.</span><span class="sxs-lookup"><span data-stu-id="89297-111">Server ID.</span></span> <span data-ttu-id="89297-112">Corresponde al identificador de instancia del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="89297-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="89297-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="89297-113">serverAddress</span></span>  <br/> |<span data-ttu-id="89297-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="89297-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="89297-115">Dirección del servidor con la dirección de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="89297-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="89297-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="89297-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="89297-117">datetime</span><span class="sxs-lookup"><span data-stu-id="89297-117">datetime</span></span>  <br/> |<span data-ttu-id="89297-118">La última vez que el servidor de canal actualizó esta fila para proporcionar evidencia de que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="89297-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="89297-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="89297-119">**Key**</span></span>

|<span data-ttu-id="89297-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="89297-120">**Column**</span></span>|<span data-ttu-id="89297-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="89297-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89297-122">serverID</span><span class="sxs-lookup"><span data-stu-id="89297-122">serverID</span></span>  <br/> |<span data-ttu-id="89297-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="89297-123">Primary key.</span></span>  <br/> |
   

