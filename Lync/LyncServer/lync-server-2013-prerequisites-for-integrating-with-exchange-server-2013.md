---
title: 'Lync Server 2013: requisitos previos para la integración con Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92f88d35e573f0914698db28ddcf1fa54967f97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="c3699-102">Requisitos previos para integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3699-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3699-103">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="c3699-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="c3699-104">Para poder integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013, debe asegurarse de que se han completado todos los pasos de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="c3699-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="c3699-105">Como cabría esperar, la integración no puede llevarse a cabo hasta que Exchange 2013 y Lync Server 2013 estén completamente instalados y en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="c3699-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="c3699-106">Para más información sobre la instalación de Exchange, consulte la documentación de planeación [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)e implementación de Exchange 2013 en.</span><span class="sxs-lookup"><span data-stu-id="c3699-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="c3699-107">Para obtener más información sobre la instalación de Lync Server 2013, consulte la documentación [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)de planeación e implementación en.</span><span class="sxs-lookup"><span data-stu-id="c3699-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="c3699-108">Una vez que los servidores estén en funcionamiento, debe asignar certificados de autenticación de servidor a servidor tanto en Lync Server 2013 como en Exchange 2013; Estos certificados permiten que Lync Server y Exchange puedan intercambiar información y comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="c3699-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="c3699-109">Al instalar Exchange 2013, se creará automáticamente un certificado autofirmado con el nombre certificado de autenticación de Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c3699-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="c3699-110">Este certificado, que puede encontrarse en el almacén de certificados del equipo local, debe usarse para la autenticación de servidor a servidor en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c3699-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="c3699-111">Para obtener más información acerca de la asignación de certificados en Exchange 2013, consulte "configurar el flujo de correo [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)y el acceso de cliente" en.</span><span class="sxs-lookup"><span data-stu-id="c3699-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="c3699-112">Para Lync Server 2013 puede usar un certificado de Lync Server existente como certificado de autenticación de servidor a servidor; por ejemplo, el certificado predeterminado también puede usarse como certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="c3699-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="c3699-113">Lync Server 2013 permite usar cualquier certificado de servidor web como certificado para la autenticación de servidor a servidor, siempre que:</span><span class="sxs-lookup"><span data-stu-id="c3699-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="c3699-114">El certificado incluya el nombre del dominio SIP en el campo Asunto.</span><span class="sxs-lookup"><span data-stu-id="c3699-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="c3699-115">Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c3699-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="c3699-116">El certificado tenga una longitud de al menos 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="c3699-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="c3699-117">Para obtener más información acerca de los certificados de autenticación de servidor a servidor para Microsoft Lync Server 2013, consulte [asignar un certificado de autenticación de servidor a servidor a Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="c3699-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="c3699-118">Después de que se hayan asignado los certificados, debe configurar el servicio Detección automática en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c3699-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="c3699-119">En Exchange 2013, el servicio de detección automática configura perfiles de usuario y proporciona acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema.</span><span class="sxs-lookup"><span data-stu-id="c3699-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="c3699-120">Los usuarios presentan el servicio de detección automática con su dirección de correo electrónico y contraseña; a su vez, los servicios proporcionan al usuario información como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3699-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="c3699-121">Información de conexión para la conectividad interna y externa a Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c3699-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="c3699-122">La ubicación del servidor de Buzón de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="c3699-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="c3699-123">Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="c3699-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="c3699-124">Configuración del servidor Outlook Anywhere.</span><span class="sxs-lookup"><span data-stu-id="c3699-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="c3699-125">El servicio Detección automática debe estar configurado para poder integrar Lync Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c3699-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="c3699-126">Para comprobar si el servicio de detección automática se ha configurado o no, ejecute el siguiente comando desde el shell de administración de Exchange y compruebe el valor de la propiedad AutoDiscoverServiceInternalUri:</span><span class="sxs-lookup"><span data-stu-id="c3699-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="c3699-p106">Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Por lo general, este URI será similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3699-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="c3699-129">Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3699-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="c3699-130">Para obtener más información sobre el servicio de detección automática, consulte "Descripción del servicio detección [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)automática" en.</span><span class="sxs-lookup"><span data-stu-id="c3699-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="c3699-131">Una vez configurado el servicio de detección automática, debe modificar las opciones de configuración de OAuth de Lync Server; Esto garantiza que Lync Server sepa dónde encontrar el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="c3699-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="c3699-132">Para modificar las opciones de configuración de OAuth en Lync Server 2013, ejecute el siguiente comando desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3699-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="c3699-133">Al ejecutar este comando, asegúrese de especificar el URI para el servicio de detección automática que se está ejecutando en el servidor de Exchange y de que usa **Autodiscover. SVC** para apuntar a la ubicación del servicio en lugar de **Autodiscover. XML** (que apunta al archivo XML usado por el servicio):</span><span class="sxs-lookup"><span data-stu-id="c3699-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="c3699-134">El parámetro Identity en el comando anterior es opcional; Esto se debe a que Lync Server solo permite tener una única colección global de opciones de configuración de OAuth.</span><span class="sxs-lookup"><span data-stu-id="c3699-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="c3699-135">Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple:</span><span class="sxs-lookup"><span data-stu-id="c3699-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="c3699-136">Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="c3699-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="c3699-p109">Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto.</span><span class="sxs-lookup"><span data-stu-id="c3699-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="c3699-140">Además de configurar el servicio Detección automática, también debe crear un registro DNS para el servicio que apunta al servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="c3699-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="c3699-141">Por ejemplo, si el servicio de detección automática está ubicado en autodiscover.litwareinc.com, deberá crear un registro DNS para autodiscover.litwareinc.com que se resuelva en el nombre de dominio completo del servidor Exchange (por ejemplo, atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="c3699-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

