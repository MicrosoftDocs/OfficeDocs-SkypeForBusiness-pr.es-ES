---
title: Administrar la mensajería unificada de Exchange y el correo de voz hospedado
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Uso de PowerShell para administrar las funciones de mensajería unificada de Exchange, como operador automático y acceso de suscriptor y correo de voz hospedado en Skype para profesionales en línea.
ms.openlocfilehash: 10c1891272a81731c94e5f0f459bb91e532e8387
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849797"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="68b61-103">Administrar la mensajería unificada de Exchange y el correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="68b61-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="68b61-104">Puede administrar la mensajería unificada de Exchange y hospedada de correo de voz de Skype para profesionales en línea mediante el uso de un conjunto de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="68b61-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="68b61-105">Administrar la mensajería unificada de Exchange y hospedado de correo de voz</span><span class="sxs-lookup"><span data-stu-id="68b61-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="68b61-106">Los cmdlets siguientes pueden usarse para administrar la mensajería unificada de Exchange (MU) y las directivas de correo de voz hospedado:</span><span class="sxs-lookup"><span data-stu-id="68b61-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="68b61-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="68b61-107">**Cmdlet**</span></span>|<span data-ttu-id="68b61-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="68b61-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="68b61-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="68b61-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="68b61-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="68b61-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="68b61-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="68b61-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="68b61-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="68b61-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="68b61-113">Crea y administra objetos de contacto que usa para los servicios de operador automático y acceso de suscriptor, cuando la mensajería unificada de Exchange es un servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="68b61-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="68b61-114">Skype para profesionales Online funciona con mensajería unificada de Exchange para proporcionar varias capacidades relacionadas con la voz, incluido el acceso de suscriptor y operador automático.</span><span class="sxs-lookup"><span data-stu-id="68b61-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="68b61-115">Operador automático proporciona una manera para llamadas a automáticamente se ha atendido y redirige a la persona correcta.</span><span class="sxs-lookup"><span data-stu-id="68b61-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="68b61-116">Acceso de suscriptor permite a los usuarios para conectarse a la mensajería unificada de Exchange y recuperar información de calendario, contactos, los mensajes de voz y correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="68b61-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="68b61-117">Cuando la mensajería unificada de Exchange se proporciona como un servicio hospedado, usados para los servicios de acceso de suscriptor y operador automático de los objetos de contacto deben crearse mediante el uso de Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68b61-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="68b61-118">Estos objetos se crean y administran mediante los cmdlets de **CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="68b61-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
|[<span data-ttu-id="68b61-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="68b61-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="68b61-120">GRANT-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="68b61-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="68b61-121">Administra las directivas de correo de voz hospedado utilizadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="68b61-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="68b61-122">Las directivas de correo de voz hospedado especifican las llamadas no respondidas cómo se enrutan al servicio de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="68b61-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="68b61-123">Estas directivas afectan a sólo los usuarios que han sido habilitados para mensajería unificada de Exchange hospedado en el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="68b61-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="68b61-124">Para comprobar si un usuario está habilitado para correo de voz hospedado, ejecute un comando similar al siguiente desde el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68b61-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="68b61-125">' Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="68b61-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="68b61-126">Select-Object HostedVoiceMail'</span><span class="sxs-lookup"><span data-stu-id="68b61-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="68b61-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="68b61-127">Related topics</span></span>
[<span data-ttu-id="68b61-128">Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="68b61-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 