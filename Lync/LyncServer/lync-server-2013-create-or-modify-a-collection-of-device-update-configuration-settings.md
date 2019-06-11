---
title: Crear o modificar una colección de parámetros de configuración de actualización de dispositivos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8d0ea-102">Crear o modificar una colección de parámetros de configuración de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d0ea-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d0ea-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8d0ea-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8d0ea-104">Se pueden crear parámetros de configuración de actualización de dispositivo (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet **New-CsDeviceUpdateConfiguration** y modificados mediante el cmdlet **set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8d0ea-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="8d0ea-105">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8d0ea-106">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="8d0ea-107">Para crear parámetros de configuración de actualización de dispositivos que usen los valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="8d0ea-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="8d0ea-108">Este comando crea un nuevo conjunto de parámetros de configuración de actualización de dispositivo para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="8d0ea-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="8d0ea-109">Puesto que no se especificó ningún parámetro distinto del parámetro de identidad obligatorio en el comando anterior, la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="8d0ea-110">Para cambiar un único valor de propiedad al crear parámetros de configuración de actualización de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8d0ea-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="8d0ea-111">Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="8d0ea-112">Por ejemplo, para crear una colección de parámetros de configuración de actualización de dispositivos que, de forma predeterminada, elimina los archivos de registro antiguos cada 21 días, use un comando como este:</span><span class="sxs-lookup"><span data-stu-id="8d0ea-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="8d0ea-113">Para cambiar varios valores de propiedad al crear parámetros de configuración de actualización de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8d0ea-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="8d0ea-114">Puede incluir varios parámetros para modificar varios valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8d0ea-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="8d0ea-115">Por ejemplo, este comando establece el intervalo de limpieza de registro en 21 días y el intervalo de vaciado del registro en 30 minutos:</span><span class="sxs-lookup"><span data-stu-id="8d0ea-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="8d0ea-116">Para obtener más información sobre cómo modificar las opciones de configuración existentes, vea el tema de ayuda sobre el cmdlet [set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="8d0ea-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="8d0ea-117">Para obtener más información sobre cómo crear colecciones de opciones de configuración, vea el tema de ayuda sobre el cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="8d0ea-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

