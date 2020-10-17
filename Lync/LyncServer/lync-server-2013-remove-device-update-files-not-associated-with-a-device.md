---
title: 'Lync Server 2013: quitar archivos de actualización de dispositivo no asociados con un dispositivo'
description: 'Lync Server 2013: quitar archivos de actualización de dispositivo que no estén asociados con un dispositivo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8338f7274d1d27e2290d822324986238f4856fe4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553506"
---
# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="9a879-103">Quitar los archivos de actualización de dispositivos que no estén asociados con un dispositivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a879-103">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a879-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9a879-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9a879-105">Cada vez que se carga una nueva actualización de dispositivo en el sistema, se crea la regla de actualización de dispositivos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9a879-105">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="9a879-106">De forma predeterminada, estas nuevas reglas de actualización de dispositivos se asignan al estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="9a879-106">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="9a879-107">Esto significa que las reglas se pueden descargar e instalar en dispositivos de prueba, pero no en dispositivos de producción, lo que permite probar las actualizaciones antes de ponerlas a disposición de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9a879-107">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="9a879-108">En función de las pruebas, puede aceptar e implementar o rechazar y eliminar la actualización.</span><span class="sxs-lookup"><span data-stu-id="9a879-108">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="9a879-109">Cuando rechaza una actualización, la actualización del dispositivo no está asociada a su regla de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9a879-109">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="9a879-110">Los archivos de actualización de dispositivos que ya no están asociados con un dispositivo se pueden quitar con Windows PowerShell y el cmdlet **Clear-CsDeviceUpdateFile** .</span><span class="sxs-lookup"><span data-stu-id="9a879-110">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="9a879-111">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a879-111">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a879-112">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="9a879-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="9a879-113">Por ejemplo, el siguiente comando quita las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com que ya no están asociados con un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="9a879-113">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="9a879-114">Para obtener más información, consulte el tema de ayuda para el cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .</span><span class="sxs-lookup"><span data-stu-id="9a879-114">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

