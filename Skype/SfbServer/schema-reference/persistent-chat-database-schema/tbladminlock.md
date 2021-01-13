---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809890"
---
# <a name="tbladminlock"></a><span data-ttu-id="a948b-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="a948b-103">tblAdminLock</span></span>
 
<span data-ttu-id="a948b-104">La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="a948b-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="a948b-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="a948b-105">**Columns**</span></span>

|<span data-ttu-id="a948b-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a948b-106">**Column**</span></span>|<span data-ttu-id="a948b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a948b-107">**Type**</span></span>|<span data-ttu-id="a948b-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a948b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a948b-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="a948b-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="a948b-110">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="a948b-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="a948b-p101">Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.</span><span class="sxs-lookup"><span data-stu-id="a948b-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="a948b-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="a948b-113">lockServerID</span></span>  <br/> |<span data-ttu-id="a948b-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="a948b-114">int, not null</span></span>  <br/> |<span data-ttu-id="a948b-115">Identificador del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a948b-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="a948b-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="a948b-116">lockActorID</span></span>  <br/> |<span data-ttu-id="a948b-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="a948b-117">int, not null</span></span>  <br/> |<span data-ttu-id="a948b-118">Identificador de la entidad de seguridad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a948b-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

