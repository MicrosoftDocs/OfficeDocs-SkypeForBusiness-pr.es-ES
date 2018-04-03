---
title: Administrar la mensajería unificada de Exchange y aloja el correo de voz
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Usar PowerShell para administrar las capacidades de mensajería unificada de Exchange como Operador automático y acceso de suscriptor y correo de voz hospedado en Skype para los negocios en línea.
ms.openlocfilehash: 1ececaf2eaefa7373a6707dd4e81f0a3bcaa6d38
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="4d0de-103">Administrar la mensajería unificada de Exchange y aloja el correo de voz</span><span class="sxs-lookup"><span data-stu-id="4d0de-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="4d0de-104">Puede administrar la mensajería unificada de Exchange y alojado el correo de voz de Skype para los negocios en línea mediante un conjunto de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4d0de-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="4d0de-105">Administrar la mensajería unificada de Exchange y aloja el correo de voz</span><span class="sxs-lookup"><span data-stu-id="4d0de-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="4d0de-106">Los cmdlets siguientes puede utilizarse para administrar Exchange Unified Messaging (UM) y alojada en las directivas de buzón de voz:</span><span class="sxs-lookup"><span data-stu-id="4d0de-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="4d0de-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="4d0de-107">**Cmdlet**</span></span>|<span data-ttu-id="4d0de-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d0de-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4d0de-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4d0de-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="4d0de-110">Nueva CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4d0de-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="4d0de-111">Quitar CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4d0de-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="4d0de-112">Conjunto de CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4d0de-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="4d0de-113">Crea y administra objetos de contacto utilizados para los servicios de Operador automático y acceso de suscriptor, cuando la mensajería unificada de Exchange es un servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="4d0de-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="4d0de-114">Skype para los negocios en línea funciona con mensajería unificada de Exchange para proporcionar varias capacidades relacionadas con la voz, incluyendo acceso de suscriptor y Operador automático.</span><span class="sxs-lookup"><span data-stu-id="4d0de-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="4d0de-115">Operador automático proporciona una forma de llamadas a automáticamente se responden y se enruta a la persona correcta.</span><span class="sxs-lookup"><span data-stu-id="4d0de-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="4d0de-116">Acceso de suscriptores permite a los usuarios conectarse a mensajería unificada de Exchange y recuperar la información de calendario, contactos, mensajes de voz y correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4d0de-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="4d0de-117">Cuando la mensajería unificada de Exchange se proporciona como un servicio hospedado, objetos de contacto utilizados para los servicios de Operador automático y acceso de suscriptor deben crearse utilizando Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d0de-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="4d0de-118">Estos objetos se crean y se administran mediante los cmdlets de **CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="4d0de-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
|[<span data-ttu-id="4d0de-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4d0de-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="4d0de-120">Concesión CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4d0de-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="4d0de-121">Administra las políticas de correo de voz hospedado utilizadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="4d0de-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="4d0de-122">Las políticas de correo de voz hospedado especifican cómo sin contestar las llamadas se enrutan al servicio de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4d0de-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="4d0de-123">Estas directivas afectan a sólo los usuarios que han sido habilitados para mensajería unificada de Exchange alojado en el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="4d0de-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="4d0de-124">Para comprobar si un usuario está habilitado para correo de voz hospedado, ejecute un comando similar al siguiente en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d0de-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="4d0de-125">' Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="4d0de-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="4d0de-126">Select-Object HostedVoiceMail'</span><span class="sxs-lookup"><span data-stu-id="4d0de-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="4d0de-127">See also</span><span class="sxs-lookup"><span data-stu-id="4d0de-127">Related topics</span></span>
[<span data-ttu-id="4d0de-128">Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d0de-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 