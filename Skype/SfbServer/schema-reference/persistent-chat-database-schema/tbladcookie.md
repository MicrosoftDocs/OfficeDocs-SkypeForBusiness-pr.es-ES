---
title: tblADCookie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies de protocolo ligero de acceso a directorios (LDAP) actuales.
ms.openlocfilehash: 3e7eeeeae6623bbbb308f4e05c4ab8a4b9a7be50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890983"
---
# <a name="tbladcookie"></a><span data-ttu-id="e34e4-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="e34e4-103">tblADCookie</span></span>
 
<span data-ttu-id="e34e4-104">tblADCookie contiene las cookies de protocolo ligero de acceso a directorios (LDAP) actuales.</span><span class="sxs-lookup"><span data-stu-id="e34e4-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="e34e4-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e34e4-105">**Columns**</span></span>

|<span data-ttu-id="e34e4-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e34e4-106">**Column**</span></span>|<span data-ttu-id="e34e4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e34e4-107">**Type**</span></span>|<span data-ttu-id="e34e4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e34e4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e34e4-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e34e4-109">prinGuid</span></span>  <br/> |<span data-ttu-id="e34e4-110">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="e34e4-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="e34e4-111">Entidad de seguridad de GUID del dominio que se está supervisando.</span><span class="sxs-lookup"><span data-stu-id="e34e4-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="e34e4-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="e34e4-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="e34e4-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="e34e4-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="e34e4-114">Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene valor informativo.</span><span class="sxs-lookup"><span data-stu-id="e34e4-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="e34e4-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="e34e4-115">adcContent</span></span>  <br/> |<span data-ttu-id="e34e4-116">imagen (binario)</span><span class="sxs-lookup"><span data-stu-id="e34e4-116">image (binary)</span></span>  <br/> |<span data-ttu-id="e34e4-117">Cookie de sincronización del directorio activo.</span><span class="sxs-lookup"><span data-stu-id="e34e4-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="e34e4-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="e34e4-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="e34e4-119">datetime</span><span class="sxs-lookup"><span data-stu-id="e34e4-119">datetime</span></span>  <br/> |<span data-ttu-id="e34e4-120">Marca de tiempo con la hora de actualización de fila.</span><span class="sxs-lookup"><span data-stu-id="e34e4-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="e34e4-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="e34e4-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="e34e4-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e34e4-122">datetime</span></span>  <br/> |<span data-ttu-id="e34e4-123">Tiempo hasta que la fila está bloqueada para que los cambios.</span><span class="sxs-lookup"><span data-stu-id="e34e4-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="e34e4-124">Esto es parte de un mecanismo de interbloqueo de software que se asegura de que sólo uno de los servicios de chat no la sincronización de Active Directory a la vez.</span><span class="sxs-lookup"><span data-stu-id="e34e4-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="e34e4-125">**Claves**</span><span class="sxs-lookup"><span data-stu-id="e34e4-125">**Keys**</span></span>

|<span data-ttu-id="e34e4-126">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e34e4-126">**Column(s)**</span></span>|<span data-ttu-id="e34e4-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e34e4-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e34e4-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e34e4-128">prinGuid</span></span>  <br/> |<span data-ttu-id="e34e4-129">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="e34e4-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e34e4-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e34e4-130">prinGuid</span></span>  <br/> |<span data-ttu-id="e34e4-131">Clave externa con búsqueda en la tabla Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="e34e4-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

