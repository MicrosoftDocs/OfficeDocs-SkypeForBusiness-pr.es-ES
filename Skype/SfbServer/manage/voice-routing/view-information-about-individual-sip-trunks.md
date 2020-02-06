---
title: Ver información sobre los troncos SIP individuales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En Skype empresarial Server, se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos no son uno y el mismo, y los administradores deben usar el cmdlet Get-CsTrunk para ver información sobre un tronco SIP individual.
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816929"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="ccb24-103">Ver información sobre los troncos SIP individuales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ccb24-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="ccb24-104">En Skype empresarial Server, se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos no son una y la misma y que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="ccb24-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="ccb24-105">El cmdlet Get-CsTrunk se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccb24-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="ccb24-106">**Para ver información sobre todos los enlaces troncales SIP**</span><span class="sxs-lookup"><span data-stu-id="ccb24-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="ccb24-107">El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:</span><span class="sxs-lookup"><span data-stu-id="ccb24-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="ccb24-108">**Para ver información sobre un enlace troncal SIP específico**</span><span class="sxs-lookup"><span data-stu-id="ccb24-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="ccb24-109">Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="ccb24-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="ccb24-110">**Ver información de todos los troncos SIP asignados a un grupo**</span><span class="sxs-lookup"><span data-stu-id="ccb24-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="ccb24-111">En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ccb24-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
