---
title: 'Lync Server 2013: eliminar las opciones de configuración de un servicio web existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6b1ddb7d4bf36186bec0ade8cacf75b15e8b70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4a7a3-102">Eliminación de las opciones de configuración de un servicio web existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a7a3-102">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a7a3-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4a7a3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4a7a3-104">Siga estos pasos para eliminar las opciones de configuración del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-104">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="4a7a3-105">Para eliminar las opciones de configuración de un servicio Web</span><span class="sxs-lookup"><span data-stu-id="4a7a3-105">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="4a7a3-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4a7a3-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4a7a3-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4a7a3-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4a7a3-109">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-109">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="4a7a3-110">En la página **servicio Web** , en el campo de búsqueda, escriba todo o parte del nombre de la Directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-110">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="4a7a3-111">En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-111">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="4a7a3-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-112">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4a7a3-113">Eliminación de opciones de configuración del servicio Web mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a7a3-113">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4a7a3-114">Puede eliminar las opciones de configuración del servicio Web con Windows PowerShell y el cmdlet **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4a7a3-114">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="4a7a3-115">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4a7a3-116">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="4a7a3-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="4a7a3-117">Para eliminar una colección específica de opciones de configuración de un servicio Web</span><span class="sxs-lookup"><span data-stu-id="4a7a3-117">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="4a7a3-118">El siguiente comando quita la configuración de seguridad del servicio Web que se aplica al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="4a7a3-118">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="4a7a3-119">Para eliminar todas las opciones de configuración de los servicios web que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="4a7a3-119">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="4a7a3-120">El siguiente comando quita todas las configuraciones de seguridad del servicio Web que se aplican al ámbito de servicio:</span><span class="sxs-lookup"><span data-stu-id="4a7a3-120">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="4a7a3-121">Para eliminar todas las opciones de configuración de los servicios web que permiten la autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="4a7a3-121">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="4a7a3-122">El siguiente comando quita toda la configuración de seguridad del servicio Web que permite el uso de la autenticación de certificados:</span><span class="sxs-lookup"><span data-stu-id="4a7a3-122">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="4a7a3-123">Para obtener más información, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="4a7a3-123">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a7a3-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="4a7a3-124">See Also</span></span>


[<span data-ttu-id="4a7a3-125">Configuración de la autenticación en el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a7a3-125">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

