---
title: Vista ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813300"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="a821e-104">Vista ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="a821e-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="a821e-105">La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a821e-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="a821e-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a821e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a821e-107">La vista ConferenceMessageCount contiene todas las columnas de la vista [ConferenceSessionDetails](conferencesessiondetails.md) además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="a821e-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a821e-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a821e-108">**Column**</span></span>|<span data-ttu-id="a821e-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a821e-109">**Data Type**</span></span>|<span data-ttu-id="a821e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a821e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a821e-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="a821e-111">**UserUri**</span></span> <br/> |<span data-ttu-id="a821e-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a821e-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a821e-113">URI del usuario que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a821e-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="a821e-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="a821e-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="a821e-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a821e-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a821e-116">Tipo de URI del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a821e-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="a821e-117">Vea la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a821e-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a821e-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="a821e-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="a821e-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a821e-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a821e-120">Inquilino del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a821e-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="a821e-121">Vea la [tabla Inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a821e-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a821e-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="a821e-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="a821e-123">smallint</span><span class="sxs-lookup"><span data-stu-id="a821e-123">smallint</span></span>  <br/> |<span data-ttu-id="a821e-124">Número de mensajes que envió el usuario durante la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a821e-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

