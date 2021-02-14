---
title: Visualización de la información de la interfaz de red
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
description: Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet Get-CsNetworkInterface web. Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815140"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="74d24-104">Visualización de la información de la interfaz de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="74d24-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="74d24-105">Puede ver la información de la interfaz de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkInterface.**</span><span class="sxs-lookup"><span data-stu-id="74d24-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="74d24-106">Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74d24-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="74d24-107">Para ver la información de interfaz de red</span><span class="sxs-lookup"><span data-stu-id="74d24-107">To view network interface information</span></span>

  - <span data-ttu-id="74d24-108">Para ver la información de la interfaz de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="74d24-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="74d24-109">Este comando produce información similar a la siguiente para cada interfaz de red:</span><span class="sxs-lookup"><span data-stu-id="74d24-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="74d24-110">Para más información, vea [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="74d24-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


