---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de chat persistente.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831500"
---
# <a name="tblserveridentity"></a><span data-ttu-id="5e6ca-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="5e6ca-103">tblServerIdentity</span></span>
 
<span data-ttu-id="5e6ca-104">tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="5e6ca-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-105">**Columns**</span></span>

|<span data-ttu-id="5e6ca-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-106">**Column**</span></span>|<span data-ttu-id="5e6ca-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-107">**Type**</span></span>|<span data-ttu-id="5e6ca-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e6ca-109">serverID</span><span class="sxs-lookup"><span data-stu-id="5e6ca-109">serverID</span></span>  <br/> |<span data-ttu-id="5e6ca-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="5e6ca-110">int, not null</span></span>  <br/> |<span data-ttu-id="5e6ca-111">Id. de servidor.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-111">Server ID.</span></span> <span data-ttu-id="5e6ca-112">Corresponde al identificador de instancia del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="5e6ca-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="5e6ca-113">serverAddress</span></span>  <br/> |<span data-ttu-id="5e6ca-114">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="5e6ca-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="5e6ca-115">Dirección de servidor con la dirección de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="5e6ca-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="5e6ca-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="5e6ca-117">datetime</span><span class="sxs-lookup"><span data-stu-id="5e6ca-117">datetime</span></span>  <br/> |<span data-ttu-id="5e6ca-118">La última hora en la que el servidor de canal actualizó esta fila para probar que está ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="5e6ca-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-119">**Key**</span></span>

|<span data-ttu-id="5e6ca-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-120">**Column**</span></span>|<span data-ttu-id="5e6ca-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5e6ca-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5e6ca-122">serverID</span><span class="sxs-lookup"><span data-stu-id="5e6ca-122">serverID</span></span>  <br/> |<span data-ttu-id="5e6ca-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5e6ca-123">Primary key.</span></span>  <br/> |
   

