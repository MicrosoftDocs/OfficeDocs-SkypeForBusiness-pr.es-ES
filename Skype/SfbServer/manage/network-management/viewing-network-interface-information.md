---
title: Visualización de información de interfaz de red
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet Get-CsNetworkInterface de red. Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.
ms.openlocfilehash: a9407000b6941c60e9ae62935b32308285be827a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386628"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Ver información de interfaz de red en Skype Empresarial Server

Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkInterface**. Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.

## <a name="to-view-network-interface-information"></a>Para ver la información de interfaz de red

Para ver la información de la interfaz de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
`Get-CsNetworkInterface`

Este comando produce información similar a la siguiente para cada interfaz de red:

```console    
Identity              : dc.vdomain.com/Primary/1
ComputerFqdn          : dc.vdomain.com
IPAddress             : 0.0.0.0
IPv6Address           :
Interface             : Primary
InterfaceNumber       : 1
ConfiguredFqdn        :
ConfiguredIPAddress   :
ConfiguredIPv6Address :
```

Para más información, vea [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).
