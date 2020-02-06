---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies de sincronización LDAP (Protocolo ligero de acceso a directorios) actuales.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814708"
---
# <a name="tbladcookie"></a><span data-ttu-id="b67af-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="b67af-103">tblADCookie</span></span>
 
<span data-ttu-id="b67af-104">tblADCookie contiene las cookies de sincronización LDAP (Protocolo ligero de acceso a directorios) actuales.</span><span class="sxs-lookup"><span data-stu-id="b67af-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="b67af-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b67af-105">**Columns**</span></span>

|<span data-ttu-id="b67af-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b67af-106">**Column**</span></span>|<span data-ttu-id="b67af-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b67af-107">**Type**</span></span>|<span data-ttu-id="b67af-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b67af-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b67af-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b67af-109">prinGuid</span></span>  <br/> |<span data-ttu-id="b67af-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="b67af-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="b67af-111">GUID principal del dominio que se está supervisando.</span><span class="sxs-lookup"><span data-stu-id="b67af-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="b67af-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="b67af-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="b67af-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="b67af-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="b67af-114">Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene valor informativo.</span><span class="sxs-lookup"><span data-stu-id="b67af-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="b67af-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="b67af-115">adcContent</span></span>  <br/> |<span data-ttu-id="b67af-116">imagen (binario)</span><span class="sxs-lookup"><span data-stu-id="b67af-116">image (binary)</span></span>  <br/> |<span data-ttu-id="b67af-117">Cookie de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b67af-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="b67af-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="b67af-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="b67af-119">datetime</span><span class="sxs-lookup"><span data-stu-id="b67af-119">datetime</span></span>  <br/> |<span data-ttu-id="b67af-120">Marca de tiempo con la hora de actualización de la fila.</span><span class="sxs-lookup"><span data-stu-id="b67af-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="b67af-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="b67af-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="b67af-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b67af-122">datetime</span></span>  <br/> |<span data-ttu-id="b67af-123">Tiempo hasta que se bloquean los cambios en la fila.</span><span class="sxs-lookup"><span data-stu-id="b67af-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="b67af-124">Esto forma parte de un mecanismo de interbloqueo de software que garantiza que solo uno de los servicios de chat realiza la sincronización de Active Directory a la vez.</span><span class="sxs-lookup"><span data-stu-id="b67af-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="b67af-125">**Sus**</span><span class="sxs-lookup"><span data-stu-id="b67af-125">**Keys**</span></span>

|<span data-ttu-id="b67af-126">**Columna (s)**</span><span class="sxs-lookup"><span data-stu-id="b67af-126">**Column(s)**</span></span>|<span data-ttu-id="b67af-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b67af-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b67af-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b67af-128">prinGuid</span></span>  <br/> |<span data-ttu-id="b67af-129">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b67af-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b67af-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b67af-130">prinGuid</span></span>  <br/> |<span data-ttu-id="b67af-131">Clave externa con la búsqueda en la tabla principal. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="b67af-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

