---
title: Ver información sobre troncos SIP individuales en Skype empresarial Server
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
description: En Skype empresarial Server, se pueden asignar varios troncos a una única puerta de enlace RTC; Esto significa que las puertas de enlace y los troncos no son uno y el mismo, y los administradores deben usar el cmdlet Get-CsTrunk para ver información sobre un tronco SIP individual.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048183"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Ver información sobre troncos SIP individuales en Skype empresarial Server

En Skype empresarial Server, se pueden asignar varios troncos a una única puerta de enlace RTC; Esto significa que las puertas de enlace y los troncos no son un y el mismo, y que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.

El cmdlet Get-CsTrunk se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.

**Para ver la información de todos los troncos SIP**

El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:

`Get-CsTrunk`

**Para ver la información de un tronco SIP específico**

Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Ver información sobre todos los enlaces troncales SIP asignados a un grupo**

En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
