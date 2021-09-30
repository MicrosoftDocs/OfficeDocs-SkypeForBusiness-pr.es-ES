---
title: Visualización de información de interfaz de red
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet Get-CsNetworkInterface de red. Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.
ms.openlocfilehash: 56d6abcd804a5dd525bdc1d9f7b3e5df74f756b0
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015364"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Ver información de interfaz de red en Skype Empresarial Server

Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkInterface.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.

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
