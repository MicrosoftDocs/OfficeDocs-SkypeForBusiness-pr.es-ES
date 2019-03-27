---
title: Visualización de información de interfaz de red
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede ver información de interfaz de red mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkInterface. Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.
ms.openlocfilehash: df4424e33cb42f3c1b2311cc822c762a2c4878f1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888032"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Visualización de información de interfaz de red en Skype para Business Server

Puede ver información de interfaz de red mediante el uso de Windows PowerShell y el cmdlet **Get-CsNetworkInterface** . Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Para ver la información de interfaz de red

  - Para ver la información de interfaz de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsNetworkInterface
    
    Este comando devuelve información similar a la siguiente para cada interfaz de red:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Para obtener información detallada, vea [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


