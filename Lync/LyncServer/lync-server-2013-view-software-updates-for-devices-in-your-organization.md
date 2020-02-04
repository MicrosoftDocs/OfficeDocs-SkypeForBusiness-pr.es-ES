---
title: 'Lync Server 2013: ver actualizaciones de software para dispositivos de su organización'
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
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="3d286-102">Ver actualizaciones de software para dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d286-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d286-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3d286-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3d286-104">Con Lync Server 2013, puede usar el servicio Web de actualización de dispositivos para ver y administrar las actualizaciones de software para los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="3d286-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="3d286-105">Estas actualizaciones están disponibles en archivos. cab (Cabinet) del sitio web de soporte técnico [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)de Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="3d286-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="3d286-106">Una vez que haya descargado el archivo. cab, ejecute el cmdlet **Import-CSDeviceUpdate** para importar las reglas de actualización del dispositivo desde el archivo. cab.</span><span class="sxs-lookup"><span data-stu-id="3d286-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="3d286-107">Para obtener más información sobre el cmdlet **Import-CSDeviceUpdate** , consulte [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d286-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="3d286-108">Antes de implementar una nueva actualización de su organización, compruebe que funciona correctamente en un dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="3d286-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="3d286-109">Para ver las actualizaciones de software para los dispositivos de comunicaciones unificadas</span><span class="sxs-lookup"><span data-stu-id="3d286-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="3d286-110">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3d286-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d286-111">En el sitio web de soporte [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)técnico de Microsoft, descargue el archivo. cab en una ubicación de un equipo de Lync Server 2013 (por\\ejemplo\\, C: actualizaciones UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="3d286-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="3d286-112">Importe las reglas de actualización de dispositivos desde el\\archivo\\C: updates UCUpdates. cab ejecutando uno de los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3d286-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="3d286-113">Si el archivo. cab se encuentra en el mismo equipo que el que está ejecutando el servicio que se va a actualizar (servicio: Redmond-websvc-2), ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3d286-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="3d286-114">Si el archivo. cab se encuentra en un equipo diferente del que está ejecutando el servicio que se va a actualizar (servicio: Redmond-websvc-3), ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3d286-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="3d286-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d286-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3d286-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3d286-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="3d286-117">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, en **actualización de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="3d286-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="3d286-118">En la página **actualización de dispositivo** , haga clic en una actualización de la lista y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="3d286-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="3d286-119">**Cancelar una actualización pendiente.**</span><span class="sxs-lookup"><span data-stu-id="3d286-119">**Cancel a pending update.**</span></span> <span data-ttu-id="3d286-120">Para evitar que la actualización seleccionada se implemente en los dispositivos de su organización, haga clic en el menú **acción** y, a continuación, haga clic en **Cancelar actualizaciones pendientes**.</span><span class="sxs-lookup"><span data-stu-id="3d286-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="3d286-121">**Aprobar una actualización.**</span><span class="sxs-lookup"><span data-stu-id="3d286-121">**Approve an update.**</span></span> <span data-ttu-id="3d286-122">Para permitir que la actualización seleccionada se implemente en los dispositivos de su organización, haga clic en el menú **acción** y, a continuación, haga clic en **aprobar**.</span><span class="sxs-lookup"><span data-stu-id="3d286-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="3d286-123">**Restaurar una actualización.**</span><span class="sxs-lookup"><span data-stu-id="3d286-123">**Restore an update.**</span></span> <span data-ttu-id="3d286-124">Para permitir que se implemente una actualización aprobada previamente en los dispositivos de su organización, haga clic en el menú **acción** y, a continuación, haga clic en **restaurar**.</span><span class="sxs-lookup"><span data-stu-id="3d286-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d286-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d286-125">See Also</span></span>


[<span data-ttu-id="3d286-126">Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d286-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

