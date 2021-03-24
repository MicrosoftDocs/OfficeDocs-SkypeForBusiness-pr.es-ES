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
description: En Skype Empresarial Server, se pueden asignar varios troncos a una única puerta de enlace RTC; esto significa que las puertas de enlace y los troncos no son iguales y los administradores deben usar el cmdlet Get-CsTrunk para ver información sobre un tronco SIP individual.
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103006"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="617a5-103">Ver información sobre troncos SIP individuales en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="617a5-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="617a5-104">En Skype Empresarial Server, se pueden asignar varios troncos a una única puerta de enlace RTC; esto significa que las puertas de enlace y los troncos no son iguales y que los administradores deben usar el cmdlet [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="617a5-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="617a5-105">El cmdlet Get-CsTrunk puede ejecutarse desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="617a5-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="617a5-106">**Para ver información de todos los troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="617a5-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="617a5-107">El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:</span><span class="sxs-lookup"><span data-stu-id="617a5-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="617a5-108">**Para ver información de un tronco SIP específico**</span><span class="sxs-lookup"><span data-stu-id="617a5-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="617a5-109">Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="617a5-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="617a5-110">**Ver información sobre todos los enlaces troncales SIP asignados a un grupo**</span><span class="sxs-lookup"><span data-stu-id="617a5-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="617a5-111">En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="617a5-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`