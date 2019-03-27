---
title: Ver información sobre los troncos SIP individuales en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En Skype para Business Server, se pueden asignar varios troncos a una única puerta de enlace de RTC; Esto significa que las puertas de enlace y troncos no son el mismos, y los administradores deben usar el cmdlet Get-CsTrunk para ver información sobre un tronco SIP individual.
ms.openlocfilehash: 4c57bdfb8671c8aee3f0bb3dbc48fdc5cb920b07
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885180"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="af019-103">Ver información sobre los troncos SIP individuales en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="af019-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="af019-104">En Skype para Business Server, se pueden asignar varios troncos a una única puerta de enlace de RTC; Esto significa que las puertas de enlace y troncos no son el mismos, y que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="af019-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="af019-105">El cmdlet Get-CsTrunk se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af019-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="af019-106">**Para ver información sobre todos los enlaces troncales SIP**</span><span class="sxs-lookup"><span data-stu-id="af019-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="af019-107">El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:</span><span class="sxs-lookup"><span data-stu-id="af019-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="af019-108">**Para ver información sobre un enlace troncal SIP específico**</span><span class="sxs-lookup"><span data-stu-id="af019-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="af019-109">Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="af019-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="af019-110">**Visualización de información de todos los enlaces troncales SIP asignados a un grupo de servidores**</span><span class="sxs-lookup"><span data-stu-id="af019-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="af019-111">En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="af019-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
