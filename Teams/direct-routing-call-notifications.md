---
title: Enrutamiento directo del sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notificación de llamada de enrutamiento directo
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341805"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="f26c4-103">Administrar notificaciones perdidas</span><span class="sxs-lookup"><span data-stu-id="f26c4-103">Manage call notifications</span></span>

<span data-ttu-id="f26c4-104">En este artículo se describe cómo administrar las notificaciones de llamadas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f26c4-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="f26c4-105">Puede configurar los puntos de conexión de llamada tanto en Teams como en una central de conmutación (PBX) privada de terceros o en un controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="f26c4-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="f26c4-106">Esto resulta útil, por ejemplo, si quiere enviar una llamada a los teléfonos móviles y de escritorio de un usuario al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f26c4-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="f26c4-107">En el siguiente diagrama, el usuario Irena tiene dos puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="f26c4-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="f26c4-108">Un punto de conexión de Teams</span><span class="sxs-lookup"><span data-stu-id="f26c4-108">A Teams endpoint</span></span>
- <span data-ttu-id="f26c4-109">Un teléfono SIP conectado a un SBC de terceros</span><span class="sxs-lookup"><span data-stu-id="f26c4-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="f26c4-110">Cuando llega una llamada, SBC bifurca la llamada entre el enrutamiento directo del sistema telefónico y el SBC de terceros.</span><span class="sxs-lookup"><span data-stu-id="f26c4-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Diagrama que muestra puntos de conexión de Teams bifurcados](media/direct-routing-call-notification-1.png)

<span data-ttu-id="f26c4-112">Si se acepta la llamada en la bifurcación 2 (por el SBC de terceros), Teams generará una notificación de "Llamada perdida".</span><span class="sxs-lookup"><span data-stu-id="f26c4-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="f26c4-113">Puede evitar la notificación "Llamada perdida" configurando el SBC para enviar una cancelación en bifurcación 1 como se explica a continuación:</span><span class="sxs-lookup"><span data-stu-id="f26c4-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="f26c4-114">RAZÓN: SIP; cause=200;text"Llamada completada en otro lugar"</span><span class="sxs-lookup"><span data-stu-id="f26c4-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="f26c4-115">Tenga en cuenta que la llamada no se registrará en los registros de detalles de la llamada de Microsoft Phone System como una llamada correcta.</span><span class="sxs-lookup"><span data-stu-id="f26c4-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="f26c4-116">La llamada se registrará como un "Intento" con código SIP final "487", subcodificación final de Microsoft "540200" y frase final de código SIP "Llamada completada en otro lugar".</span><span class="sxs-lookup"><span data-stu-id="f26c4-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="f26c4-117">(Para ver los registros de detalles de las llamadas, vaya al Portal de administración de Teams, Análisis e informes, Informes de uso y seleccione Uso de RTC).</span><span class="sxs-lookup"><span data-stu-id="f26c4-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="f26c4-118">En el diagrama siguiente se muestra la bifurcación SIP para bifurcación 1, se explica el flujo de llamadas y el motivo esperado en el mensaje de cancelación.</span><span class="sxs-lookup"><span data-stu-id="f26c4-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Diagrama que muestra puntos de conexión de Teams bifurcados](media/direct-routing-call-notification-2.png)
