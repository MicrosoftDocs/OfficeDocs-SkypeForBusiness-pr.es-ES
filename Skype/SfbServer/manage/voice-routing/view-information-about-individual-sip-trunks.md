---
title: Ver información sobre troncos SIP individuales en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En Skype Empresarial Server, se pueden asignar varios troncos a una sola puerta de enlace RTC; Esto significa que las puertas de enlace y los troncos no son iguales y los administradores deben usar el cmdlet Get-CsTrunk para ver información sobre un tronco SIP individual.
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826180"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="9cfab-103">Ver información sobre troncos SIP individuales en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9cfab-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="9cfab-104">En Skype Empresarial Server, se pueden asignar varios troncos a una sola puerta de enlace RTC; esto significa que las puertas de enlace y los troncos no son uno y los mismos, y que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="9cfab-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="9cfab-105">El Get-CsTrunk cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cfab-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="9cfab-106">**Para ver información de todos los troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="9cfab-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="9cfab-107">El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:</span><span class="sxs-lookup"><span data-stu-id="9cfab-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="9cfab-108">**Para ver información de un tronco SIP específico**</span><span class="sxs-lookup"><span data-stu-id="9cfab-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="9cfab-109">Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="9cfab-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="9cfab-110">**Ver información sobre todos los enlaces troncales SIP asignados a un grupo**</span><span class="sxs-lookup"><span data-stu-id="9cfab-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="9cfab-111">En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="9cfab-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
