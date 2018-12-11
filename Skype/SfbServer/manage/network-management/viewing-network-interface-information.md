---
title: Visualización de información de interfaz de red
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede ver información de interfaz de red mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkInterface. Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.
ms.openlocfilehash: b3f1217c53176ae2a67ba81893864e1fb3a4e384
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222768"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="cdc59-104">Visualización de información de interfaz de red en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cdc59-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="cdc59-105">Puede ver información de interfaz de red mediante el uso de Windows PowerShell y el cmdlet **Get-CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="cdc59-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="cdc59-106">Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdc59-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="cdc59-107">Para ver la información de interfaz de red</span><span class="sxs-lookup"><span data-stu-id="cdc59-107">To view network interface information</span></span>

  - <span data-ttu-id="cdc59-108">Para ver la información de interfaz de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="cdc59-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="cdc59-109">Este comando devuelve información similar a la siguiente para cada interfaz de red:</span><span class="sxs-lookup"><span data-stu-id="cdc59-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="cdc59-110">Para obtener información detallada, vea [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="cdc59-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


