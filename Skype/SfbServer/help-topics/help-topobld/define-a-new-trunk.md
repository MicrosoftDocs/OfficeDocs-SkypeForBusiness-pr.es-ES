---
title: Definir un nuevo tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Para definir un nuevo tronco de protocolo de inicio de sesión (SIP), proporcione la siguiente información:'
ms.openlocfilehash: 9de4808bc7a53aae79c2373116e74be98c7ae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684843"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="045fe-103">Definir un nuevo tronco</span><span class="sxs-lookup"><span data-stu-id="045fe-103">Define a New Trunk</span></span>

<span data-ttu-id="045fe-104">Para definir un nuevo tronco de protocolo de inicio de sesión (SIP), proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="045fe-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="045fe-105">**Nombre del tronco**: nombre único de la topología que identificará este tronco</span><span class="sxs-lookup"><span data-stu-id="045fe-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="045fe-106">**Puerta de enlace RTC asociada**: Seleccione una puerta de enlace RTC implementada y configurada en la implementación de la lista</span><span class="sxs-lookup"><span data-stu-id="045fe-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="045fe-107">**Puerto de escucha para la puerta de enlace IP/RTC**: puerto en el que escuchará la puerta de enlace IP o RTC.</span><span class="sxs-lookup"><span data-stu-id="045fe-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="045fe-108">Debe ser único de todos los demás puertos de escucha de troncal configurados en su implementación</span><span class="sxs-lookup"><span data-stu-id="045fe-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="045fe-109">**Protocolo de transporte SIP**: seleccione de la lista TCP o TLS.</span><span class="sxs-lookup"><span data-stu-id="045fe-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="045fe-110">**Servidor de mediación asociado**: seleccione en la lista un servidor de mediación implementado y configurado en su implementación.</span><span class="sxs-lookup"><span data-stu-id="045fe-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="045fe-111">**Puerto de servidor de mediación asociado**: establezca el valor de puerto igual al valor del puerto TCP o TLS del servidor de mediación que usará este tronco de SIP.</span><span class="sxs-lookup"><span data-stu-id="045fe-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="045fe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="045fe-112">See also</span></span>

[<span data-ttu-id="045fe-113">Tronco M:N en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="045fe-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="045fe-114">¿Cómo implemento la Troncalización SIP?</span><span class="sxs-lookup"><span data-stu-id="045fe-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
