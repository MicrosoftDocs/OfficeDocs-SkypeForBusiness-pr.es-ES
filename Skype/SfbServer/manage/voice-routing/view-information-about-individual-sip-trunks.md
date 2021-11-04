---
title: 'Skype Empresarial Server: ver información sobre troncos SIP individuales'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: En Skype Empresarial Server, se pueden asignar varios troncos a una única puerta de enlace RTC. Las puertas de enlace y los troncos no son iguales y los administradores deben usar el cmdlet Get-CsTrunk para ver información sobre un tronco SIP individual.
ms.openlocfilehash: dc5ccfdb5e248d843fb3a8a4e926a7e462097789
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774720"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype Empresarial Server: ver información sobre troncos SIP individuales

En Skype Empresarial Server, se pueden asignar varios troncos a una única puerta de enlace RTC; esto significa que las puertas de enlace y los troncos no son iguales y que los administradores deben usar el cmdlet [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) para ver información sobre un tronco SIP individual.

El cmdlet Get-CsTrunk puede ejecutarse desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.

**Para ver información de todos los troncos SIP**

El siguiente comando devuelve información sobre todos los enlaces troncales SIP que se usan en su organización:

`Get-CsTrunk`

**Para ver información de un tronco SIP específico**

Este comando devuelve información solamente para el enlace troncal SIP con el valor Identity PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Ver información sobre todos los enlaces troncales SIP asignados a un grupo**

En este ejemplo, se devuelve información para todos los enlaces troncales SIP asignados al grupo atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
