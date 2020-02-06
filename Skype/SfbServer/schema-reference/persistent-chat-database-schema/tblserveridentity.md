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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de chat persistente.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812278"
---
# <a name="tblserveridentity"></a><span data-ttu-id="8dfb6-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="8dfb6-103">tblServerIdentity</span></span>
 
<span data-ttu-id="8dfb6-104">tblServerIdentity contiene los servidores de chat activos en el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="8dfb6-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="8dfb6-105">**Columns**</span></span>

|<span data-ttu-id="8dfb6-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8dfb6-106">**Column**</span></span>|<span data-ttu-id="8dfb6-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8dfb6-107">**Type**</span></span>|<span data-ttu-id="8dfb6-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8dfb6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8dfb6-109">serverID</span><span class="sxs-lookup"><span data-stu-id="8dfb6-109">serverID</span></span>  <br/> |<span data-ttu-id="8dfb6-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="8dfb6-110">int, not null</span></span>  <br/> |<span data-ttu-id="8dfb6-111">IDENTIFICADOR de servidor.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-111">Server ID.</span></span> <span data-ttu-id="8dfb6-112">Corresponde al identificador de instancia del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="8dfb6-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="8dfb6-113">serverAddress</span></span>  <br/> |<span data-ttu-id="8dfb6-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="8dfb6-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="8dfb6-115">Dirección del servidor con la dirección de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="8dfb6-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="8dfb6-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="8dfb6-117">datetime</span><span class="sxs-lookup"><span data-stu-id="8dfb6-117">datetime</span></span>  <br/> |<span data-ttu-id="8dfb6-118">La última vez que el servidor de canal actualizó esta fila para proporcionar evidencia de que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="8dfb6-119">**Clave**</span><span class="sxs-lookup"><span data-stu-id="8dfb6-119">**Key**</span></span>

|<span data-ttu-id="8dfb6-120">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8dfb6-120">**Column**</span></span>|<span data-ttu-id="8dfb6-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8dfb6-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8dfb6-122">serverID</span><span class="sxs-lookup"><span data-stu-id="8dfb6-122">serverID</span></span>  <br/> |<span data-ttu-id="8dfb6-123">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-123">Primary key.</span></span>  <br/> |
   

