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
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Ver información sobre los troncos SIP individuales en Skype para Business Server

En Skype para Business Server, se pueden asignar varios troncos a una única puerta de enlace de RTC; Esto significa que las puertas de enlace y troncos no son el mismos, y que los administradores deben usar el cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.

El cmdlet Get-CsTrunk se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.

**Para ver información sobre todos los enlaces troncales SIP**

El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:

`Get-CsTrunk`

**Para ver información sobre un enlace troncal SIP específico**

Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Visualización de información de todos los enlaces troncales SIP asignados a un grupo de servidores**

En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
