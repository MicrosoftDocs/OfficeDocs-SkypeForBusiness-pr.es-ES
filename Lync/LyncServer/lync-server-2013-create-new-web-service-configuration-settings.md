---
title: 'Lync Server 2013: crear nuevas opciones de configuración de un servicio Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79508e99c8bc70e7781e77cd7727be30ebdda58f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="df941-102">Crear nuevas opciones de configuración de servicio Web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df941-102">Create new Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df941-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="df941-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="df941-104">Puede usar la página **servicio Web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df941-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="df941-105">Siga estos pasos para crear una nueva Directiva de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="df941-105">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="df941-106">Para crear nuevas opciones de configuración de un servicio Web</span><span class="sxs-lookup"><span data-stu-id="df941-106">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="df941-107">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df941-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="df941-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df941-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df941-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df941-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df941-110">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="df941-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="df941-111">En la página **servicio Web** , haga clic en **nuevo**y, a continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="df941-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="df941-112">Para configurar el servicio web para un sitio, haga clic en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="df941-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="df941-113">En **seleccionar un sitio**, haga clic en el sitio al que se aplicará la Directiva de servicio Web y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df941-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="df941-114">Para configurar el servicio web para un grupo de servidores, haga clic en **configuración del grupo**.</span><span class="sxs-lookup"><span data-stu-id="df941-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="df941-115">En **seleccionar un servicio**, haga clic en el servicio al que se aplicará la Directiva de servicio Web y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df941-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="df941-116">En **nueva configuración de servicio Web**, en **autenticación integrada de Windows**, seleccione **negociar**, **autenticación de Windows integrada**o **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="df941-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="df941-117">Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="df941-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="df941-118">**Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.</span><span class="sxs-lookup"><span data-stu-id="df941-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="df941-119">**Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="df941-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="df941-120">**Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.</span><span class="sxs-lookup"><span data-stu-id="df941-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="df941-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="df941-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

