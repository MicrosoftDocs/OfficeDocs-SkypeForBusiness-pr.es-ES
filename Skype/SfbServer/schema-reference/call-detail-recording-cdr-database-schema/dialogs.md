---
title: Tabla Dialogs en Skype Empresarial Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabla Cuadros de diálogo es una tabla compatible que almacena la información acerca de dialogIDs para sesiones punto a punto.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816050"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3cbbe-103">Tabla Dialogs en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cbbe-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3cbbe-104">La tabla Cuadros de diálogo es una tabla compatible que almacena la información acerca de dialogIDs para sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3cbbe-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="3cbbe-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-105">**Column**</span></span>|<span data-ttu-id="3cbbe-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-106">**Data Type**</span></span>|<span data-ttu-id="3cbbe-107">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-107">**Key/Index**</span></span>|<span data-ttu-id="3cbbe-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3cbbe-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="3cbbe-110">datetime</span><span class="sxs-lookup"><span data-stu-id="3cbbe-110">datetime</span></span>  <br/> |<span data-ttu-id="3cbbe-111">Principal</span><span class="sxs-lookup"><span data-stu-id="3cbbe-111">Primary</span></span>  <br/> |<span data-ttu-id="3cbbe-112">Hora de la solicitud de sesión; se usa junto con SessionIDSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="3cbbe-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="3cbbe-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="3cbbe-114">entero</span><span class="sxs-lookup"><span data-stu-id="3cbbe-114">int</span></span>  <br/> |<span data-ttu-id="3cbbe-115">Principal</span><span class="sxs-lookup"><span data-stu-id="3cbbe-115">Primary</span></span>  <br/> |<span data-ttu-id="3cbbe-116">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="3cbbe-116">ID number to identify the session.</span></span> <span data-ttu-id="3cbbe-117">Se usa junto con SessionIDTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="3cbbe-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="3cbbe-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="3cbbe-119">entero</span><span class="sxs-lookup"><span data-stu-id="3cbbe-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="3cbbe-120">Suma de comprobación de ExternalID.</span><span class="sxs-lookup"><span data-stu-id="3cbbe-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="3cbbe-121">Este campo se usa para aumentar la velocidad de las búsquedas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3cbbe-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="3cbbe-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="3cbbe-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="3cbbe-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="3cbbe-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="3cbbe-124">Identificador de cuadro de diálogo SIP, almacenado como binario.</span><span class="sxs-lookup"><span data-stu-id="3cbbe-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="3cbbe-125">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="3cbbe-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="3cbbe-126">dialog;from-tag;to-tag</span><span class="sxs-lookup"><span data-stu-id="3cbbe-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="3cbbe-127">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3cbbe-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

