---
title: Vista ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount almacena información acerca de la cantidad de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901418"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="c390d-104">Vista ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="c390d-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="c390d-105">La vista ConferenceMessageCount almacena información acerca de la cantidad de mensajes enviados por un usuario a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="c390d-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="c390d-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c390d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c390d-107">La vista ConferenceMessageCount todas las columnas en la [vista ConferenceSessionDetails](conferencesessiondetails.md) contiene además en las columnas enumeradas a continuación.</span><span class="sxs-lookup"><span data-stu-id="c390d-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="c390d-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c390d-108">**Column**</span></span>|<span data-ttu-id="c390d-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c390d-109">**Data Type**</span></span>|<span data-ttu-id="c390d-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c390d-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c390d-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="c390d-111">**UserUri**</span></span> <br/> |<span data-ttu-id="c390d-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c390d-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c390d-113">URI del usuario que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c390d-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="c390d-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="c390d-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="c390d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c390d-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c390d-116">Tipo de URI del usuario que envía los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c390d-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="c390d-117">Consulte la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c390d-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c390d-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="c390d-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="c390d-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c390d-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c390d-120">Inquilino del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c390d-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="c390d-121">Consulte la [tabla de los inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c390d-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c390d-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="c390d-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="c390d-123">smallint</span><span class="sxs-lookup"><span data-stu-id="c390d-123">smallint</span></span>  <br/> |<span data-ttu-id="c390d-124">Número de mensajes enviados por el usuario durante la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c390d-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

