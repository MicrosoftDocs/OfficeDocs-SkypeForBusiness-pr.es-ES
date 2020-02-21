---
title: 'Lync Server 2013: ver la Directiva de PIN información'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5dad362c4291f83c6feb261247a0b90ba47e16
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a><span data-ttu-id="492de-102">Ver información de directivas de PIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="492de-102">View PIN policy inforrmation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="492de-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="492de-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="492de-104">Puede usar la pestaña **Directiva de PIN** para ver la autenticación del número de identificación personal (PIN) de los usuarios que se conectan a Lync 2013 con teléfonos IP.</span><span class="sxs-lookup"><span data-stu-id="492de-104">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="492de-105">Para usar la autenticación PIN, asegúrese de que la opción **Habilitar autenticación PIN** esté seleccionada en la configuración del servicio web.</span><span class="sxs-lookup"><span data-stu-id="492de-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="492de-106">Para obtener más información, consulte [modificar las opciones de configuración de un servicio web existente en Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="492de-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="492de-107">Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio.</span><span class="sxs-lookup"><span data-stu-id="492de-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a><span data-ttu-id="492de-108">Para ver información sobre una directiva de PIN en el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="492de-108">To view information about a PIN policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="492de-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="492de-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="492de-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="492de-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="492de-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="492de-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="492de-112">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="492de-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="492de-113">En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="492de-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="492de-114">Ver directivas de PIN con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="492de-114">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="492de-115">También puede ver directivas de PIN con Windows PowerShell y el cmdlet Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="492de-115">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="492de-116">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="492de-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="492de-117">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="492de-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pin-policies"></a><span data-ttu-id="492de-118">Para ver las directivas de PIN</span><span class="sxs-lookup"><span data-stu-id="492de-118">To view PIN policies</span></span>

  - <span data-ttu-id="492de-119">Para ver información sobre todas las directivas de PIN, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="492de-119">To view information about all your PIN policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPinPolicy
    
    <span data-ttu-id="492de-120">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="492de-120">That will return information similar to this:</span></span>
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

<span data-ttu-id="492de-121">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="492de-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="492de-122">Consulta también</span><span class="sxs-lookup"><span data-stu-id="492de-122">See Also</span></span>


[<span data-ttu-id="492de-123">Modificación de las opciones de configuración de un servicio web existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="492de-123">Modify existing Web Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[<span data-ttu-id="492de-124">Crear una directiva de PIN nueva en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="492de-124">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

