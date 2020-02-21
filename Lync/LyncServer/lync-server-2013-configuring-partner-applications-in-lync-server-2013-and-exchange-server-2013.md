---
title: Configuración de aplicaciones de socio en Lync Server 2013 y Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db2f0df542cb85956ae3efa7321083b99ed561a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="96d6f-102">Configuración de aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="96d6f-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96d6f-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="96d6f-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="96d6f-p101">En la autenticación de servidor a servidor suelen participar tres entidades: los dos servidores que necesitan comunicarse entre sí y un servidor de tokens de seguridad de un tercero. Si dos servidores (por ejemplo, Servidor A y Servidor B) necesitan comunicarse entre sí, normalmente empezarán por ponerse en contacto con un servidor de tokens y obtener un token de seguridad que sea de confianza para ambos. El Servidor A presentará dicho token de seguridad al Servidor B (y viceversa) como forma de garantizar tanto su autenticidad como su confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="96d6f-p101">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server. If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token. Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="96d6f-107">Ahora bien, eso no es sino una regla general.</span><span class="sxs-lookup"><span data-stu-id="96d6f-107">However, that's a general rule.</span></span> <span data-ttu-id="96d6f-108">Lync Server 2013, Microsoft Exchange Server 2013 y Microsoft SharePoint Server 2013 no necesitan usar un servidor de tokens de terceros para comunicarse entre sí; Esto se debe a que estos productos de servidor pueden crear tokens de seguridad que puedan aceptarse entre sí sin necesidad de un servidor de token independiente.</span><span class="sxs-lookup"><span data-stu-id="96d6f-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="96d6f-109">(Esta funcionalidad solo está disponible en Lync Server 2013, Exchange 2013 y SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96d6f-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="96d6f-110">Si necesita configurar una autenticación de servidor a servidor con otros servidores, incluyendo otros productos de servidor de Microsoft, deberá hacerlo con un servidor de tokens de un tercero).</span><span class="sxs-lookup"><span data-stu-id="96d6f-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="96d6f-111">Para configurar la autenticación de servidor a servidor entre Lync Server y Exchange, debe hacer dos cosas: 1) debe asignar los certificados apropiados a cada servidor; y 2) debe configurar cada servidor para que sea una aplicación de socio del otro servidor: Esto significa que debe configurar Lync Server 2013 como una aplicación de socio para Exchange 2013, y debe configurar Exchange 2013 como una aplicación de socio para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96d6f-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="96d6f-112">Configuración de Lync Server 2013 como una aplicación de socio para Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="96d6f-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="96d6f-113">La forma más sencilla de configurar Lync Server 2013 como una aplicación de socio con Exchange 2013 es ejecutar el script configure-enterprisepartnerapplication. ps1, un script de Windows PowerShell que se incluye con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="96d6f-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="96d6f-114">Para ejecutar este script, debe proporcionar la dirección URL del documento de metadatos de autenticación de Lync Server; normalmente será el nombre de dominio completo del grupo de servidores de Lync Server 2013 seguido del sufijo/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="96d6f-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="96d6f-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96d6f-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="96d6f-116">Para configurar Lync Server como una aplicación de socio, abra el shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en la unidad C: y que use la ruta de acceso a la carpeta predeterminada):</span><span class="sxs-lookup"><span data-stu-id="96d6f-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="96d6f-117">Después de configurar la aplicación de socio, se recomienda que detenga y reinicie Internet Information Services (IIS) en los servidores de buzones de correo y de acceso de cliente de Exchange.</span><span class="sxs-lookup"><span data-stu-id="96d6f-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="96d6f-118">Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="96d6f-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="96d6f-119">Este comando se puede ejecutar desde dentro del shell de administración de Exchange o desde cualquier otra ventana de comandos que se ejecute con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="96d6f-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="96d6f-120">Configuración de Exchange 2013 como una aplicación de socio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96d6f-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="96d6f-121">Una vez que haya configurado Lync Server 2013 como una aplicación de socio para Exchange 2013, debe configurar Exchange para que sea una aplicación de socio para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96d6f-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="96d6f-122">Esto puede realizarse mediante el shell de administración de Lync Server y especificando el documento de metadatos de autenticación para Exchange; normalmente será el URI del servicio Detección automática de Exchange seguido del sufijo/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="96d6f-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="96d6f-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96d6f-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="96d6f-124">En Lync Server, las aplicaciones asociadas se configuran con el cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="96d6f-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="96d6f-125">Además de especificar el URI de metadatos, también debe establecer el nivel de confianza de la aplicación en completo; Esto permitirá que Exchange represente tanto a los usuarios autorizados como a los autorizados en el dominio Kerberos.</span><span class="sxs-lookup"><span data-stu-id="96d6f-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="96d6f-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96d6f-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="96d6f-127">Como alternativa, puede crear una aplicación de socio copiando y modificando el código de script que se encuentra en la documentación de autenticación de servidor a servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96d6f-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="96d6f-128">Vea el artículo [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="96d6f-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="96d6f-129">Si ha configurado correctamente aplicaciones de socio tanto para Lync Server como para Exchange, significa que también ha configurado correctamente la autenticación de servidor a servidor entre los dos productos.</span><span class="sxs-lookup"><span data-stu-id="96d6f-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="96d6f-130">Lync Server 2013 incluye un cmdlet de Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), que permite comprobar que la autenticación de servidor a servidor se ha configurado correctamente y que el servicio de almacenamiento de Lync Server puede conectarse a Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="96d6f-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="96d6f-131">Para ello, se conecta al buzón de un usuario de Exchange 2013, escribe un elemento en la carpeta Historial de conversaciones de ese usuario y, a continuación, elimina el elemento de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="96d6f-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="96d6f-132">Para probar la integración de Lync Server 2013 y Exchange 2013, ejecute un comando similar a este desde dentro del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="96d6f-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="96d6f-133">En el comando anterior, SipUri representa la dirección SIP de un usuario con una cuenta en Exchange 2013; el comando no se completará en esta cuenta de usuario no es válida.</span><span class="sxs-lookup"><span data-stu-id="96d6f-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="96d6f-134">Si la prueba se completa correctamente y se establece la conectividad, podrá seguir adelante y configurar las características opcionales, como la integración de archivado y el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="96d6f-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

