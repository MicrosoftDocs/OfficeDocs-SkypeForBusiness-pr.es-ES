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
localization_priority: Normal
description: Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet Get-CsNetworkInterface de red. Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.
ms.openlocfilehash: 482655d36a16158866207e9157d25288e418f7e9ee00dc88ea7a59d653e5c566
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281803"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Ver información de interfaz de red en Skype Empresarial Server

Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkInterface.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Para ver la información de interfaz de red

  - Para ver la información de la interfaz de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkInterface
    
    Este comando produce información similar a la siguiente para cada interfaz de red:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Para más información, vea [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).