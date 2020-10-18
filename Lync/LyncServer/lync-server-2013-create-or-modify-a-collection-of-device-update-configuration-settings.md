---
title: Crear o modificar una colección de opciones de configuración de actualización de dispositivos
description: Cree o modifique una colección de opciones de configuración de actualización de dispositivos.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 593a1a0cb0f68254748ee48440cda18c78989780
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578276"
---
# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2d234-103">Crear o modificar una colección de opciones de configuración de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d234-103">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d234-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2d234-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2d234-105">Se pueden crear opciones de configuración de actualización de dispositivos (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet **New-CsDeviceUpdateConfiguration** y modificados mediante el cmdlet **set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2d234-105">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="2d234-106">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d234-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2d234-107">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="2d234-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="2d234-108">Para crear valores de configuración de actualización de dispositivos que usen los valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="2d234-108">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="2d234-109">Este comando crea un nuevo conjunto de opciones de configuración de actualización de dispositivos para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="2d234-109">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="2d234-110">Como no se especificó ningún parámetro que no sea el parámetro de identidad obligatorio en el comando anterior, la nueva colección de opciones de configuración usará los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="2d234-110">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="2d234-111">Para cambiar un valor de propiedad único al crear opciones de configuración de actualización de dispositivo</span><span class="sxs-lookup"><span data-stu-id="2d234-111">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="2d234-112">Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado.</span><span class="sxs-lookup"><span data-stu-id="2d234-112">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="2d234-113">Por ejemplo, para crear una colección de opciones de configuración de actualización de dispositivos que, de forma predeterminada, elimina los archivos de registro antiguos cada 21 días, use un comando como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d234-113">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="2d234-114">Para cambiar varios valores de propiedad al crear opciones de configuración de actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2d234-114">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="2d234-115">Puede cambiar varios valores de propiedad incluyendo varios parámetros.</span><span class="sxs-lookup"><span data-stu-id="2d234-115">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="2d234-116">Por ejemplo, este comando establece el intervalo de limpieza del registro en 21 días y el intervalo de vaciado del registro en 30 minutos:</span><span class="sxs-lookup"><span data-stu-id="2d234-116">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="2d234-117">Para obtener información detallada sobre cómo modificar las opciones de configuración existentes de los dispositivos, consulte el tema de ayuda del cmdlet [set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="2d234-117">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="2d234-118">Para obtener más información sobre cómo crear colecciones de opciones de configuración, consulte el tema de ayuda del cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="2d234-118">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

