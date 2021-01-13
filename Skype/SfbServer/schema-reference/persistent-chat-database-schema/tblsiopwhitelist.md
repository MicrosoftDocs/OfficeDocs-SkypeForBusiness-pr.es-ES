---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que es posible asociar con nodos.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831490"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="695da-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="695da-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="695da-104">tblSiopWhiteList es la lista de complementos registrados que es posible asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="695da-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="695da-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="695da-105">**Columns**</span></span>

|<span data-ttu-id="695da-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="695da-106">**Column**</span></span>|<span data-ttu-id="695da-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="695da-107">**Type**</span></span>|<span data-ttu-id="695da-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="695da-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="695da-109">siopID</span><span class="sxs-lookup"><span data-stu-id="695da-109">siopID</span></span>  <br/> |<span data-ttu-id="695da-110">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="695da-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="695da-111">GUID del complemento.</span><span class="sxs-lookup"><span data-stu-id="695da-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="695da-112">siopName</span><span class="sxs-lookup"><span data-stu-id="695da-112">siopName</span></span>  <br/> |<span data-ttu-id="695da-113">nvarchar (50), no NULL</span><span class="sxs-lookup"><span data-stu-id="695da-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="695da-114">Nombre para mostrar del complemento.</span><span class="sxs-lookup"><span data-stu-id="695da-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="695da-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="695da-115">siopUrl</span></span>  <br/> |<span data-ttu-id="695da-116">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="695da-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="695da-117">URL del complemento.</span><span class="sxs-lookup"><span data-stu-id="695da-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="695da-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="695da-118">**Key**</span></span>

|<span data-ttu-id="695da-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="695da-119">**Column**</span></span>|<span data-ttu-id="695da-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="695da-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="695da-121">siopID</span><span class="sxs-lookup"><span data-stu-id="695da-121">siopID</span></span>  <br/> |<span data-ttu-id="695da-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="695da-122">Primary key.</span></span>  <br/> |
   

