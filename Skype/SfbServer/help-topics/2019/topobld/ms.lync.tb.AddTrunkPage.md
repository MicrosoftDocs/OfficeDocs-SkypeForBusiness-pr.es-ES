---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:'
ms.openlocfilehash: 540076814d2916f74a5e11be42f99b57711da2b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093278"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="3fe02-103">Definir un nuevo tronco</span><span class="sxs-lookup"><span data-stu-id="3fe02-103">Define a New Trunk</span></span>

<span data-ttu-id="3fe02-104">Para definir un nuevo un tronco de protocolo de inicio de sesión (SIP) proporcione la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="3fe02-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="3fe02-105">**Nombre del tronco**: nombre único en la topología que identificará este tronco</span><span class="sxs-lookup"><span data-stu-id="3fe02-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="3fe02-106">**Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC implementada y configurada de la lista en la implementación</span><span class="sxs-lookup"><span data-stu-id="3fe02-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="3fe02-p101">**Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP-PBX o RTC. Debe ser distinto de todos los demás puertos de escucha de tronco configurados en la implementación</span><span class="sxs-lookup"><span data-stu-id="3fe02-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="3fe02-109">**Protocolo de transporte SIP**: seleccione TCP o TLS de la lista</span><span class="sxs-lookup"><span data-stu-id="3fe02-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="3fe02-110">**Servidor de mediación asociado:** seleccione en la lista un servidor de mediación que se implemente y configure en la implementación.</span><span class="sxs-lookup"><span data-stu-id="3fe02-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="3fe02-111">**Puerto del servidor de mediación** asociado: establezca el valor de puerto igual al valor de puerto TCP o TLS del servidor de mediación que usará este tronco SIP</span><span class="sxs-lookup"><span data-stu-id="3fe02-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="3fe02-112">Ver también</span><span class="sxs-lookup"><span data-stu-id="3fe02-112">See also</span></span>

[<span data-ttu-id="3fe02-113">Tronco M:N en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3fe02-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="3fe02-114">¿Cómo implemento el enlace troncal SIP?</span><span class="sxs-lookup"><span data-stu-id="3fe02-114">How do I implement SIP trunking?</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)