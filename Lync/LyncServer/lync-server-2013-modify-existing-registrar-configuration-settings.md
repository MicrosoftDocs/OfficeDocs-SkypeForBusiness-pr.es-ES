---
title: 'Lync Server 2013: modificar las opciones de configuración de registrador existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d7297ed0df352090f08b90475778f1bde788c8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1bfec-102">Modificar las opciones de configuración existentes del registrador en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bfec-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bfec-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1bfec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1bfec-104">Puede usar el registrador para configurar los protocolos de autenticación del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="1bfec-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="1bfec-105">Para obtener información sobre los protocolos disponibles, consulte [crear opciones de configuración de registrador en Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1bfec-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1bfec-p102">Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1bfec-p102">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="1bfec-110">Siga los pasos a continuación para modificar un registrador existente.</span><span class="sxs-lookup"><span data-stu-id="1bfec-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="1bfec-111">Para modificar las opciones de configuración existentes del registrador</span><span class="sxs-lookup"><span data-stu-id="1bfec-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="1bfec-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1bfec-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1bfec-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1bfec-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1bfec-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1bfec-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1bfec-115">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="1bfec-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="1bfec-116">En la página **Registrador**, haga clic en un servicio, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1bfec-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1bfec-117">En **Editar configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno:</span><span class="sxs-lookup"><span data-stu-id="1bfec-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="1bfec-118">**Habilitar autenticación Kerberos**: para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1bfec-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="1bfec-119">**Habilitar autenticación NTLM**: para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.</span><span class="sxs-lookup"><span data-stu-id="1bfec-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="1bfec-120">**Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="1bfec-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="1bfec-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1bfec-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

