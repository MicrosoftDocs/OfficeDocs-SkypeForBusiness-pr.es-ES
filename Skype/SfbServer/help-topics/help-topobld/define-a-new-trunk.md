---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Definir un tronco de protocolo (SIP) de inicio de sesión nuevo al proporcionar la siguiente información:'
ms.openlocfilehash: 669f896e9a51a2f7f229a065a867f8ce8e48bcdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903785"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="6e7a8-103">Definir un nuevo tronco</span><span class="sxs-lookup"><span data-stu-id="6e7a8-103">Define a New Trunk</span></span>

<span data-ttu-id="6e7a8-104">Definir un tronco de protocolo (SIP) de inicio de sesión nuevo al proporcionar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="6e7a8-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="6e7a8-105">**Nombre del tronco**: nombre único en la topología que identificará este tronco</span><span class="sxs-lookup"><span data-stu-id="6e7a8-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="6e7a8-106">**Puerta de enlace de RTC asociada**: seleccione una puerta de enlace RTC implementada y configurada en la implementación de la lista</span><span class="sxs-lookup"><span data-stu-id="6e7a8-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="6e7a8-107">**Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP-PBX o RTC.</span><span class="sxs-lookup"><span data-stu-id="6e7a8-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="6e7a8-108">Debe ser único entre todos los otros puertos de escucha de tronco configurados en la implementación</span><span class="sxs-lookup"><span data-stu-id="6e7a8-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="6e7a8-109">**Protocolo de transporte SIP**: seleccione en la lista TCP o TLS</span><span class="sxs-lookup"><span data-stu-id="6e7a8-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="6e7a8-110">**Servidor de mediación asociado**: seleccione en la lista de un servidor de mediación que se ha implementado y configurado en la implementación</span><span class="sxs-lookup"><span data-stu-id="6e7a8-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="6e7a8-111">**Puerto del servidor de mediación asociado**: establecer el valor de puerto igual que el valor de puerto TCP o TLS del servidor de mediación que va a usar este tronco SIP</span><span class="sxs-lookup"><span data-stu-id="6e7a8-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="6e7a8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e7a8-112">See also</span></span>

[<span data-ttu-id="6e7a8-113">Tronco M:N en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6e7a8-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="6e7a8-114">¿Cómo se puede implementar el enlace troncal SIP?</span><span class="sxs-lookup"><span data-stu-id="6e7a8-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
