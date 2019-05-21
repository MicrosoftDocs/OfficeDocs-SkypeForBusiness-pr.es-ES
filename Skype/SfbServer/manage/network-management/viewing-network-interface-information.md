---
title: Ver información de la interfaz de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede ver la información de la interfaz de red con Windows PowerShell y el cmdlet Get-CsNetworkInterface. Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279392"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="23265-104">Ver información de la interfaz de red en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="23265-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="23265-105">Puede ver la información de la interfaz de red con Windows PowerShell y el cmdlet **Get-CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="23265-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="23265-106">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23265-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="23265-107">Para ver información sobre la interfaz de red</span><span class="sxs-lookup"><span data-stu-id="23265-107">To view network interface information</span></span>

  - <span data-ttu-id="23265-108">Para ver la información de la interfaz de red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="23265-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="23265-109">Este comando devuelve información similar a la siguiente para cada interfaz de red:</span><span class="sxs-lookup"><span data-stu-id="23265-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="23265-110">Para obtener más información, vea [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="23265-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


