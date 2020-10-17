---
title: 'Lync Server 2013: ver actualizaciones de software para dispositivos de la organización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3141f08e7973b123b8c8ee0fe9b9c3c93c8e752
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518407"
---
# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="f288b-102">Ver actualizaciones de software para dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f288b-102">View software updates for devices in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f288b-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f288b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f288b-104">Con Lync Server 2013, use el servicio Web de actualización de dispositivos para ver y administrar las actualizaciones de software para los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="f288b-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="f288b-105">Estas actualizaciones están disponibles en los archivos. cab (Cabinet) del sitio web de soporte técnico de Microsoft en [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) .</span><span class="sxs-lookup"><span data-stu-id="f288b-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="f288b-106">Una vez que haya descargado el archivo. cab, ejecute el cmdlet **Import-CSDeviceUpdate** para importar las reglas de actualización de dispositivos del archivo. cab.</span><span class="sxs-lookup"><span data-stu-id="f288b-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="f288b-107">Para obtener más información sobre el cmdlet **Import-CSDeviceUpdate** , consulte [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f288b-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f288b-108">Antes de implementar una actualización nueva para la organización, compruebe que funciona correctamente en un dispositivo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="f288b-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="f288b-109">Para ver actualizaciones de software para dispositivos de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="f288b-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="f288b-110">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f288b-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f288b-111">En el sitio web de soporte técnico de Microsoft en [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) , descargue el archivo. cab en una ubicación de un equipo de Lync Server 2013 (por ejemplo, C: \\ actualizaciones \\UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="f288b-111">From the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="f288b-112">Para importar las reglas de actualización de dispositivos del \\ archivo C: updates \\UCUpdates.cab, ejecute uno de los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f288b-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="f288b-113">Si el archivo .cab se encuentra en el mismo equipo que el que ejecuta el servicio a actualizar (service:Redmond-websvc-2), ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="f288b-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="f288b-114">Si el archivo .cab se encuentra en un equipo diferente al que ejecuta el servicio a actualizar (service:Redmond-websvc-3), ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="f288b-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="f288b-115">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f288b-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f288b-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f288b-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="f288b-117">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Actualización de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f288b-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="f288b-118">En la página **Actualización de dispositivos**, haga clic en una actualización de la lista y, a continuación, siga uno de los procedimientos a continuación:</span><span class="sxs-lookup"><span data-stu-id="f288b-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="f288b-p103">**Cancelar una actualización pendiente.** Para impedir que se implemente la actualización seleccionada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, haga clic en **Cancelar actualizaciones pendientes**.</span><span class="sxs-lookup"><span data-stu-id="f288b-p103">**Cancel a pending update.** To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="f288b-p104">**Aprobar y actualizar.** Para permitir que se implemente la actualización seleccionada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, en **Aprobar**.</span><span class="sxs-lookup"><span data-stu-id="f288b-p104">**Approve an update.** To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="f288b-p105">**Restaurar y actualizar.** Para permitir que se implemente una actualización anteriormente aprobada en los dispositivos de la organización, haga clic en el menú **Acción** y, a continuación, en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="f288b-p105">**Restore an update.** To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f288b-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f288b-125">See Also</span></span>


[<span data-ttu-id="f288b-126">Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f288b-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

