---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.
ms.openlocfilehash: 074b65d3f701d122bbb311da3096e6727dd17264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924967"
---
# <a name="tblroletype"></a><span data-ttu-id="d3db1-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="d3db1-103">tblRoleType</span></span>
 
<span data-ttu-id="d3db1-104">tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="d3db1-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="d3db1-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d3db1-105">**Columns**</span></span>

|<span data-ttu-id="d3db1-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d3db1-106">**Column**</span></span>|<span data-ttu-id="d3db1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d3db1-107">**Type**</span></span>|<span data-ttu-id="d3db1-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d3db1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3db1-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="d3db1-109">rtypeID</span></span>  <br/> |<span data-ttu-id="d3db1-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d3db1-110">int, not null</span></span>  <br/> |<span data-ttu-id="d3db1-111">Identificador de tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="d3db1-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="d3db1-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="d3db1-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="d3db1-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="d3db1-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="d3db1-114">Descripción del tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="d3db1-114">Role type description.</span></span> <span data-ttu-id="d3db1-115">Hay cuatro roles disponibles:</span><span class="sxs-lookup"><span data-stu-id="d3db1-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="d3db1-116">Miembro: miembro de salón de Chat</span><span class="sxs-lookup"><span data-stu-id="d3db1-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="d3db1-117">Administrador: Administrador de salón de Chat</span><span class="sxs-lookup"><span data-stu-id="d3db1-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="d3db1-118">Miembro con voz: Moderador de un salón de chat de tipo auditorio</span><span class="sxs-lookup"><span data-stu-id="d3db1-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="d3db1-119">Creador: Puede crear salones de chat</span><span class="sxs-lookup"><span data-stu-id="d3db1-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="d3db1-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="d3db1-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="d3db1-121">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="d3db1-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="d3db1-122">Conjunto de permisos para el rol.</span><span class="sxs-lookup"><span data-stu-id="d3db1-122">Permission set for the role.</span></span> <span data-ttu-id="d3db1-123">Los bits usados son:</span><span class="sxs-lookup"><span data-stu-id="d3db1-123">The used bits are:</span></span> <br/>  <span data-ttu-id="d3db1-124">2: true si el rol puede administrar nodos.</span><span class="sxs-lookup"><span data-stu-id="d3db1-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="d3db1-125">4: true si el rol puede crear nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="d3db1-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="d3db1-126">7: true si el rol puede unirse a un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="d3db1-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="d3db1-127">8: true si el rol puede hablar en un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="d3db1-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="d3db1-128">10: true si el rol puede leer el historial de chat incluso cuando no está unido a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="d3db1-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="d3db1-129">11: true si la función puede ver el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="d3db1-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="d3db1-130">(Esto se refina por factores, como el ámbito y visibilidad.)</span><span class="sxs-lookup"><span data-stu-id="d3db1-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="d3db1-131">12: true si el rol puede hablar en un salón de chat de auditorio.</span><span class="sxs-lookup"><span data-stu-id="d3db1-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="d3db1-132">13: true si el rol puede omitir las reglas de visibilidad al ver nodos.</span><span class="sxs-lookup"><span data-stu-id="d3db1-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="d3db1-133">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d3db1-133">**Key**</span></span>

|<span data-ttu-id="d3db1-134">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d3db1-134">**Column**</span></span>|<span data-ttu-id="d3db1-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d3db1-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3db1-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="d3db1-136">rtypeID</span></span>  <br/> |<span data-ttu-id="d3db1-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="d3db1-137">Primary key.</span></span>  <br/> |
   

