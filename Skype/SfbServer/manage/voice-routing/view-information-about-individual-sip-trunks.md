---
title: Ver información sobre los troncos SIP individuales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En Skype empresarial Server, se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos no son uno y el mismo, y los administradores deben usar el cmdlet Get-CsTrunk para ver información sobre un tronco SIP individual.
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274880"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Ver información sobre los troncos SIP individuales en Skype empresarial Server

En Skype empresarial Server, se pueden asignar varios troncos a una sola puerta de enlace PSTN; Esto significa que las puertas de enlace y los troncos no son una y la misma y que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.

El cmdlet Get-CsTrunk se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.

**Para ver información sobre todos los enlaces troncales SIP**

El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:

`Get-CsTrunk`

**Para ver información sobre un enlace troncal SIP específico**

Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Ver información de todos los troncos SIP asignados a un grupo**

En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
