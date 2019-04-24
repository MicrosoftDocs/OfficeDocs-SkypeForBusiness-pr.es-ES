---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Definir un tronco de protocolo (SIP) de inicio de sesión nuevo al proporcionar la siguiente información:'
ms.openlocfilehash: eba7dec862cf359a8670bcfbf7f0b475575a26ec
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220828"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="28248-103">Definir un nuevo tronco</span><span class="sxs-lookup"><span data-stu-id="28248-103">Define a New Trunk</span></span>

<span data-ttu-id="28248-104">Definir un tronco de protocolo (SIP) de inicio de sesión nuevo al proporcionar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="28248-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="28248-105">**Nombre del tronco**: nombre único en la topología que identificará este tronco</span><span class="sxs-lookup"><span data-stu-id="28248-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="28248-106">**Puerta de enlace de RTC asociada**: seleccione una puerta de enlace RTC implementada y configurada en la implementación de la lista</span><span class="sxs-lookup"><span data-stu-id="28248-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="28248-107">**Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP-PBX o RTC.</span><span class="sxs-lookup"><span data-stu-id="28248-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="28248-108">Debe ser único entre todos los otros puertos de escucha de tronco configurados en la implementación</span><span class="sxs-lookup"><span data-stu-id="28248-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="28248-109">**Protocolo de transporte SIP**: seleccione en la lista TCP o TLS</span><span class="sxs-lookup"><span data-stu-id="28248-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="28248-110">**Servidor de mediación asociado**: seleccione en la lista de un servidor de mediación que se ha implementado y configurado en la implementación</span><span class="sxs-lookup"><span data-stu-id="28248-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="28248-111">**Puerto del servidor de mediación asociado**: establecer el valor de puerto igual que el valor de puerto TCP o TLS del servidor de mediación que va a usar este tronco SIP</span><span class="sxs-lookup"><span data-stu-id="28248-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="28248-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="28248-112">See also</span></span>

[<span data-ttu-id="28248-113">Tronco m: n en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="28248-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="28248-114">¿Cómo se puede implementar el enlace troncal SIP?</span><span class="sxs-lookup"><span data-stu-id="28248-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
