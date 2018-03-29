---
title: Tabla de cuadros de diálogo en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabla de cuadros de diálogo es una tabla de soporte que almacena la información acerca de DialogIDs para la sesiones de peer-to-peer.
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7d4f0-103">Tabla de cuadros de diálogo en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7d4f0-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7d4f0-104">La tabla de cuadros de diálogo es una tabla de soporte que almacena la información acerca de DialogIDs para la sesiones de peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="7d4f0-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="7d4f0-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-105">**Column**</span></span>|<span data-ttu-id="7d4f0-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-106">**Data Type**</span></span>|<span data-ttu-id="7d4f0-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-107">**Key/Index**</span></span>|<span data-ttu-id="7d4f0-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d4f0-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="7d4f0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="7d4f0-110">datetime</span></span>  <br/> |<span data-ttu-id="7d4f0-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7d4f0-111">Primary</span></span>  <br/> |<span data-ttu-id="7d4f0-112">Tiempo de solicitud de sesión; se utiliza junto con SessionIDSeq para identificar una sesión.</span><span class="sxs-lookup"><span data-stu-id="7d4f0-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="7d4f0-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="7d4f0-114">int</span><span class="sxs-lookup"><span data-stu-id="7d4f0-114">int</span></span>  <br/> |<span data-ttu-id="7d4f0-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7d4f0-115">Primary</span></span>  <br/> |<span data-ttu-id="7d4f0-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7d4f0-116">ID number to identify the session.</span></span> <span data-ttu-id="7d4f0-117">Se utiliza junto con SessionIDTime para identificar una sesión.</span><span class="sxs-lookup"><span data-stu-id="7d4f0-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="7d4f0-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="7d4f0-119">int</span><span class="sxs-lookup"><span data-stu-id="7d4f0-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="7d4f0-120">Suma de comprobación de la ExternalID no.</span><span class="sxs-lookup"><span data-stu-id="7d4f0-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="7d4f0-121">Este campo se utiliza para aumentar la velocidad de las búsquedas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d4f0-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="7d4f0-122">**ExternalID no**</span><span class="sxs-lookup"><span data-stu-id="7d4f0-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="7d4f0-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="7d4f0-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="7d4f0-124">Identificador de diálogo SIP, almacenado como un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="7d4f0-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="7d4f0-125">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="7d4f0-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="7d4f0-126">diálogo de etiqueta; para etiqueta</span><span class="sxs-lookup"><span data-stu-id="7d4f0-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="7d4f0-127">Estos datos se pueden convertir a formato de texto utilizando esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="7d4f0-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

