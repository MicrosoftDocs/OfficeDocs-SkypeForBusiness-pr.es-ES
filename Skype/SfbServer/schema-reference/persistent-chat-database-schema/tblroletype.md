---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212414"
---
# <a name="tblroletype"></a><span data-ttu-id="07a9d-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="07a9d-103">tblRoleType</span></span>
 
<span data-ttu-id="07a9d-104">tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="07a9d-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="07a9d-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="07a9d-105">**Columns**</span></span>

|<span data-ttu-id="07a9d-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="07a9d-106">**Column**</span></span>|<span data-ttu-id="07a9d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="07a9d-107">**Type**</span></span>|<span data-ttu-id="07a9d-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="07a9d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07a9d-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="07a9d-109">rtypeID</span></span>  <br/> |<span data-ttu-id="07a9d-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="07a9d-110">int, not null</span></span>  <br/> |<span data-ttu-id="07a9d-111">Identificador de tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="07a9d-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="07a9d-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="07a9d-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="07a9d-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="07a9d-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="07a9d-114">Descripción del tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="07a9d-114">Role type description.</span></span> <span data-ttu-id="07a9d-115">Hay cuatro roles disponibles:</span><span class="sxs-lookup"><span data-stu-id="07a9d-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="07a9d-116">Miembro: miembro de salón de Chat</span><span class="sxs-lookup"><span data-stu-id="07a9d-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="07a9d-117">Administrador: Administrador de salón de Chat</span><span class="sxs-lookup"><span data-stu-id="07a9d-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="07a9d-118">Miembro con voz: Moderador de un salón de chat de tipo auditorio</span><span class="sxs-lookup"><span data-stu-id="07a9d-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="07a9d-119">Creador: Puede crear salones de chat</span><span class="sxs-lookup"><span data-stu-id="07a9d-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="07a9d-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="07a9d-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="07a9d-121">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="07a9d-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="07a9d-122">Conjunto de permisos para el rol.</span><span class="sxs-lookup"><span data-stu-id="07a9d-122">Permission set for the role.</span></span> <span data-ttu-id="07a9d-123">Los bits usados son:</span><span class="sxs-lookup"><span data-stu-id="07a9d-123">The used bits are:</span></span> <br/>  <span data-ttu-id="07a9d-124">2: true si el rol puede administrar nodos.</span><span class="sxs-lookup"><span data-stu-id="07a9d-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="07a9d-125">4: true si el rol puede crear nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="07a9d-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="07a9d-126">7: true si el rol puede unirse a un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="07a9d-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="07a9d-127">8: true si el rol puede hablar en un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="07a9d-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="07a9d-128">10: true si el rol puede leer el historial de chat incluso cuando no está unido a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="07a9d-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="07a9d-129">11: true si la función puede ver el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="07a9d-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="07a9d-130">(Esto se refina por factores, como el ámbito y visibilidad.)</span><span class="sxs-lookup"><span data-stu-id="07a9d-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="07a9d-131">12: true si el rol puede hablar en un salón de chat de auditorio.</span><span class="sxs-lookup"><span data-stu-id="07a9d-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="07a9d-132">13: true si el rol puede omitir las reglas de visibilidad al ver nodos.</span><span class="sxs-lookup"><span data-stu-id="07a9d-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="07a9d-133">**Clave**</span><span class="sxs-lookup"><span data-stu-id="07a9d-133">**Key**</span></span>

|<span data-ttu-id="07a9d-134">**Columna**</span><span class="sxs-lookup"><span data-stu-id="07a9d-134">**Column**</span></span>|<span data-ttu-id="07a9d-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="07a9d-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07a9d-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="07a9d-136">rtypeID</span></span>  <br/> |<span data-ttu-id="07a9d-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="07a9d-137">Primary key.</span></span>  <br/> |
   

