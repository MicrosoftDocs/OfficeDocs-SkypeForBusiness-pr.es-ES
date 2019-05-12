---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924776"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="7a463-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="7a463-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="7a463-104">tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="7a463-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="7a463-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="7a463-105">**Columns**</span></span>

|<span data-ttu-id="7a463-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7a463-106">**Column**</span></span>|<span data-ttu-id="7a463-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7a463-107">**Type**</span></span>|<span data-ttu-id="7a463-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7a463-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a463-109">siopID</span><span class="sxs-lookup"><span data-stu-id="7a463-109">siopID</span></span>  <br/> |<span data-ttu-id="7a463-110">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="7a463-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7a463-111">GUID del complemento.</span><span class="sxs-lookup"><span data-stu-id="7a463-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7a463-112">siopName</span><span class="sxs-lookup"><span data-stu-id="7a463-112">siopName</span></span>  <br/> |<span data-ttu-id="7a463-113">nvarchar (50), no es nulo</span><span class="sxs-lookup"><span data-stu-id="7a463-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="7a463-114">Nombre para mostrar del complemento.</span><span class="sxs-lookup"><span data-stu-id="7a463-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7a463-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="7a463-115">siopUrl</span></span>  <br/> |<span data-ttu-id="7a463-116">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="7a463-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7a463-117">Dirección URL del complemento.</span><span class="sxs-lookup"><span data-stu-id="7a463-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="7a463-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="7a463-118">**Key**</span></span>

|<span data-ttu-id="7a463-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7a463-119">**Column**</span></span>|<span data-ttu-id="7a463-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7a463-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a463-121">siopID</span><span class="sxs-lookup"><span data-stu-id="7a463-121">siopID</span></span>  <br/> |<span data-ttu-id="7a463-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="7a463-122">Primary key.</span></span>  <br/> |
   

