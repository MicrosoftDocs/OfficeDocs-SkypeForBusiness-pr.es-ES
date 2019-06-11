---
title: 'Lync Server 2013: eliminar una colección de parámetros de configuración de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6de7e3e6ecef8338a3a5514cf3a84180e05ca276
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7b9ab-102">Eliminar una colección de parámetros de configuración de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b9ab-102">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b9ab-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7b9ab-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7b9ab-104">La configuración de la actualización de dispositivos también se puede eliminar con Windows PowerShell y el cmdlet **Remove-CsdeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7b9ab-104">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="7b9ab-105">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b9ab-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7b9ab-106">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="7b9ab-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="7b9ab-107">Para quitar una colección específica de parámetros de configuración de actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b9ab-107">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="7b9ab-108">Este comando elimina la configuración de actualización de dispositivo aplicada al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="7b9ab-108">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="7b9ab-109">Para quitar todas las opciones de configuración de actualización de dispositivos que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="7b9ab-109">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="7b9ab-110">Este comando elimina todas las opciones de configuración de la actualización de dispositivos que se aplican al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="7b9ab-110">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="7b9ab-111">Para quitar la configuración de actualización de dispositivos según el valor de la propiedad LogCleanUpInterval</span><span class="sxs-lookup"><span data-stu-id="7b9ab-111">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="7b9ab-112">El siguiente comando elimina todos los parámetros de configuración de actualización de dispositivos en los que el intervalo de limpieza de registro es superior a 10 días (10,00:00:00):</span><span class="sxs-lookup"><span data-stu-id="7b9ab-112">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="7b9ab-113">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="7b9ab-113">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

