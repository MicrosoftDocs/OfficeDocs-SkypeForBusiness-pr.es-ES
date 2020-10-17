---
title: 'Lync Server 2013: solución de problemas del panel de control de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535937"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="86b4e-102">Solución de problemas del Panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4e-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b4e-103">_**Última modificación del tema:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="86b4e-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="86b4e-104">En este tema se proporciona información y procedimientos que pueden ayudarle a solucionar problemas de acceso al panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86b4e-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="86b4e-105">Requisitos del explorador de Internet</span><span class="sxs-lookup"><span data-stu-id="86b4e-105">Internet Browser Requirements</span></span>

<span data-ttu-id="86b4e-106">El panel de control de Lync Server requiere que esté instalada la versión 4.0.50524.0 o la versión más reciente del complemento del explorador Microsoft Silverlight.</span><span class="sxs-lookup"><span data-stu-id="86b4e-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="86b4e-107">Si Silverlight no está instalado o si se ha instalado una versión anterior, siga las instrucciones del mensaje para instalar la versión requerida.</span><span class="sxs-lookup"><span data-stu-id="86b4e-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86b4e-108">Otros requisitos de software para el panel de control de Lync Server pertenecen al sistema operativo en el que se pueden instalar el panel de control de Lync Server y todas las demás herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86b4e-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="86b4e-109">Para obtener más información, consulte <A href="lync-server-2013-server-and-tools-operating-system-support.md">compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013</A> en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="86b4e-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="86b4e-110">Si su explorador de Internet bloquea la instalación de Silverlight por motivos de seguridad, agregue el localizador uniforme de recursos (URL) que abre el panel de control de Lync Server a la lista de sitios de confianza.</span><span class="sxs-lookup"><span data-stu-id="86b4e-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="86b4e-111">En la configuración de seguridad de Internet Explorer, asegúrese de que **Ejecutar controles y complementos de ActiveX** esté **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="86b4e-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="86b4e-112">Para obtener más información, consulte [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) .</span><span class="sxs-lookup"><span data-stu-id="86b4e-112">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="86b4e-113">Además, asegúrese de que el explorador esté configurado para usar SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="86b4e-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="86b4e-p104">Si el explorador de Internet está configurado para usar un servidor proxy, compruebe que el explorador esté configurado para omitir el servidor proxy en sitios detectados automáticamente como sitios internos. También puede agregar la dirección a la lista de excepciones del explorador en los valores de configuración del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="86b4e-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="86b4e-116">Requisitos de certificado y registro DNS para la dirección URL de acceso administrativo</span><span class="sxs-lookup"><span data-stu-id="86b4e-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="86b4e-117">Si configuró una dirección URL sencilla para acceder al panel de control de Lync Server, asegúrese de que también configuró el registro de recursos de host (A) del sistema de nombres de dominio (DNS) estático y el certificado necesario para usar esa dirección URL de acceso administrativo.</span><span class="sxs-lookup"><span data-stu-id="86b4e-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="86b4e-118">Si cambia la dirección URL base en cualquier momento, asegúrese de que el cambio se refleja en el registro DNS y el certificado adecuados, y que ejecuta el *-CsComputer* en cada director y en el servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="86b4e-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="86b4e-119">Para obtener más información, consulte los siguientes temas en la documentación de planeación:</span><span class="sxs-lookup"><span data-stu-id="86b4e-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="86b4e-120">Planeación de direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4e-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="86b4e-121">Requisitos de DNS para direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4e-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="86b4e-122">Requisitos de certificado para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4e-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="86b4e-123">Para conocer los procedimientos paso a paso para configurar la dirección URL de acceso administrativo, consulte [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="86b4e-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="86b4e-124">Requisitos de Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="86b4e-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="86b4e-125">El panel de control de Lync Server es uno de los componentes de Lync Server 2013 que requiere Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="86b4e-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="86b4e-126">En concreto, asegúrese de que estén habilitadas las características de autenticación de Windows y de redirección HTTP, y de que se esté ejecutando el servicio de publicación World Wide Web (W3SVC).</span><span class="sxs-lookup"><span data-stu-id="86b4e-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="86b4e-127">Dependencia del servicio de publicación World Wide (servicio de Windows)</span><span class="sxs-lookup"><span data-stu-id="86b4e-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="86b4e-128">Cuando se detiene el servicio de publicación World Wide Web, no se puede tener acceso al panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86b4e-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="86b4e-129">Puede reiniciar el servicio usando Windows Services Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="86b4e-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="86b4e-130">**Para iniciar el servicio de publicación World Wide Web**</span><span class="sxs-lookup"><span data-stu-id="86b4e-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="86b4e-131">Inicie sesión en el equipo donde está instalado el servicio de publicación World Wide Web como parte de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="86b4e-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="86b4e-132">Haga clic en **Inicio**, haga clic en **Herramientas administrativas** y, a continuación, haga clic en **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="86b4e-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="86b4e-133">Haga clic con el botón secundario del mouse en **Servicio de publicación World Wide Web** y, a continuación, haga clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="86b4e-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="86b4e-134">Modo Grupo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="86b4e-134">Application Pool Mode</span></span>

<span data-ttu-id="86b4e-135">Configure IIS de modo que el grupo de aplicaciones CsManagementAppPool use la cuenta del servicio de red como identidad de modelo de proceso.</span><span class="sxs-lookup"><span data-stu-id="86b4e-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="86b4e-136">Permisos y derechos de usuario</span><span class="sxs-lookup"><span data-stu-id="86b4e-136">User Rights and Permissions</span></span>

<span data-ttu-id="86b4e-137">Debe iniciar sesión en el panel de control de Lync Server con una cuenta de dominio que sea miembro del grupo CsAdministrator o con una cuenta a la que haya delegado derechos y permisos de usuario.</span><span class="sxs-lookup"><span data-stu-id="86b4e-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="86b4e-138">No puede iniciar sesión en el panel de control de Lync Server con una cuenta de equipo local.</span><span class="sxs-lookup"><span data-stu-id="86b4e-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="86b4e-139">Para obtener más información sobre cómo delegar tareas administrativas mediante el control de acceso basado en roles (RBAC), consulte [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="86b4e-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="86b4e-140">Si usa una dirección URL sencilla para acceder al panel de control de Lync Server, asegúrese de que los servidores Web se agregan a los grupos RTCUniversalServerAdmins y RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="86b4e-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86b4e-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86b4e-141">See Also</span></span>


[<span data-ttu-id="86b4e-142">Herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4e-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

