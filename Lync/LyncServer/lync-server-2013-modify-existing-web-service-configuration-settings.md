---
title: 'Lync Server 2013: modificar las opciones de configuración de un servicio web existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa146ef8d56d080c468d8e2748355d70ef928ff2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c3aff-102">Modificación de las opciones de configuración de un servicio web existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3aff-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3aff-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c3aff-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c3aff-104">Puede usar la página **servicio Web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3aff-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="c3aff-105">Siga estos pasos para modificar una directiva de servicio web existente.</span><span class="sxs-lookup"><span data-stu-id="c3aff-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="c3aff-106">Para modificar las opciones de configuración de un servicio web existente</span><span class="sxs-lookup"><span data-stu-id="c3aff-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="c3aff-107">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3aff-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="c3aff-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3aff-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c3aff-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c3aff-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c3aff-110">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="c3aff-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="c3aff-111">En la página **Servicio web**, haga clic en una configuración, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c3aff-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c3aff-112">En **Editar configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **NTLM** o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="c3aff-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="c3aff-113">Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="c3aff-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="c3aff-114">**Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.</span><span class="sxs-lookup"><span data-stu-id="c3aff-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="c3aff-115">**Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="c3aff-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="c3aff-116">**Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.</span><span class="sxs-lookup"><span data-stu-id="c3aff-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="c3aff-117">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c3aff-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3aff-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c3aff-118">See Also</span></span>


[<span data-ttu-id="c3aff-119">Configuración de la autenticación en el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3aff-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

