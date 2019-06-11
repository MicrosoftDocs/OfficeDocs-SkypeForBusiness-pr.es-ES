---
title: Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4cdfd80c368558ee034369eba0ca0cb9e89ecea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="d75a6-102">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d75a6-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d75a6-103">_**Última modificación del tema:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="d75a6-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="d75a6-104">Microsoft Lync Server 2013 debe ser capaz de comunicarse de manera segura y sin problemas con otras aplicaciones y productos de servidor.</span><span class="sxs-lookup"><span data-stu-id="d75a6-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="d75a6-105">Por ejemplo, puede configurar Lync Server 2013 para que los datos de los contactos o los datos de archivado se almacenen en Microsoft Exchange Server 2013; sin embargo, esto solo se puede hacer si Lync Server y Exchange pueden comunicarse con seguridad entre sí.</span><span class="sxs-lookup"><span data-stu-id="d75a6-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="d75a6-106">Del mismo modo, puede programar una conferencia de Lync Server desde Microsoft SharePoint Server; de nuevo, sin embargo, esto solo se puede hacer si los dos servidores (SharePoint y Lync Server) confían entre sí.</span><span class="sxs-lookup"><span data-stu-id="d75a6-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="d75a6-107">Aunque es posible usar un mecanismo de autenticación para la comunicación entre usuarios de Lync y un mecanismo independiente para la comunicación entre usuarios de Lync, un enfoque mejor y más eficaz es usar un método estándar para todos los servidores autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="d75a6-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="d75a6-108">Usar un único método estándar para la autenticación de servidor a servidor es el método que toma Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d75a6-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="d75a6-109">En el caso de la versión 2013, Lync Server 2013 (así como otros productos de Microsoft Server, incluidos Exchange 2013 y Microsoft SharePoint Server) son compatibles con el protocolo OAuth (Open Authorization) para la autenticación y la autorización de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="d75a6-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="d75a6-110">Con OAuth, un protocolo de autorización estándar usado por varios sitios web grandes, las credenciales de usuario y las contraseñas no pasan de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="d75a6-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="d75a6-111">En su lugar, la autenticación y la autorización se basan en el intercambio de tokens de seguridad; Estos tokens conceden acceso a un conjunto de recursos específico durante un período de tiempo específico.</span><span class="sxs-lookup"><span data-stu-id="d75a6-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="d75a6-112">Por lo general, la autenticación de OAuth implica tres partes: un único servidor de autorización y los dos territorios que necesitan comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="d75a6-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="d75a6-113">(También puede realizar la autenticación de servidor a servidor sin usar un servidor de autorización, un proceso que se tratará más adelante en este documento). El servidor de autorización emite los tokens de seguridad (también conocido como servidor de token de seguridad) a los dos territorios que necesitan comunicarse; Estos tokens verifican que el otro dominio confía en las comunicaciones que se originan en un dominio.</span><span class="sxs-lookup"><span data-stu-id="d75a6-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="d75a6-114">Por ejemplo, es posible que el servidor de autorización emita tokens que comprueben que los usuarios de un territorio específico de Lync Server 2013 pueden tener acceso a un dominio Kerberos 2013 específico y viceversa.</span><span class="sxs-lookup"><span data-stu-id="d75a6-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d75a6-115">Un dominio es un contenedor de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d75a6-115">A realm is simply a security container.</span></span> <span data-ttu-id="d75a6-116">De forma predeterminada, Lync Server 2013 usa su dominio SIP predeterminado como su dominio de OAuth.</span><span class="sxs-lookup"><span data-stu-id="d75a6-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="d75a6-117">Se agregan espacios de nombres SIP a la lista Nombre alternativo del sujeto en el certificado OAuth.</span><span class="sxs-lookup"><span data-stu-id="d75a6-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="d75a6-118">Lync Server 2013 admite tres escenarios de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="d75a6-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="d75a6-119">Con Lync Server 2013 puede:</span><span class="sxs-lookup"><span data-stu-id="d75a6-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="d75a6-120">Configure la autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y una instalación local de Exchange 2013 o Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="d75a6-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="d75a6-121">Configure la autenticación de servidor a servidor entre un par de componentes de Office 365 (por ejemplo, entre Microsoft Exchange y Microsoft Lync Server, o entre Microsoft Lync Server y Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="d75a6-121">Configure server-to-server authentication between a pair of Office 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="d75a6-122">Configurar la autenticación de servidor a servidor en un entorno entre locales (es decir, la autenticación de servidor a servidor entre un servidor local y un componente de Office 365).</span><span class="sxs-lookup"><span data-stu-id="d75a6-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Office 365 component).</span></span>

<span data-ttu-id="d75a6-123">Tenga en cuenta que, en este momento, solo Exchange 2013, SharePoint Server y Lync Server 2013 son compatibles con la autenticación de servidor a servidor; Si no está ejecutando uno de estos servidores, no podrá implementar completamente la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="d75a6-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="d75a6-124">También debe señalarse que no es necesario usar autenticación de servidor a servidor: la autenticación de servidor a servidor no es necesaria para implementar Lync Server 2013...</span><span class="sxs-lookup"><span data-stu-id="d75a6-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="d75a6-125">Si Lync Server 2013 no necesita comunicarse con otros servidores (como Exchange 2013), no se necesita la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="d75a6-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="d75a6-126">Sin embargo, se necesita la autenticación de servidor a servidor si desea usar algunas de las nuevas características de Lync Server, como el "almacén de contactos unificado".</span><span class="sxs-lookup"><span data-stu-id="d75a6-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="d75a6-127">Con el almacenamiento de contactos unificado, la información de contacto de Lync Server 2013 se almacena en Exchange 2013 en lugar de en Lync Server; Esto permite que los usuarios tengan un único conjunto de contactos accesible fácilmente desde Lync, Microsoft Outlook o Microsoft Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="d75a6-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="d75a6-128">Puesto que el almacén de contactos unificado requiere Lync Server 2013 para poder compartir información con Exchange 2013, debe usar la autenticación de servidor a servidor para implementar la característica.</span><span class="sxs-lookup"><span data-stu-id="d75a6-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="d75a6-129">También se necesita la autenticación de servidor a servidor si elige usar el archivado de Exchange, en el que las transcripciones de las sesiones de mensajería instantánea se guardan como correos electrónicos de Exchange 2013 en lugar de como registros de base de datos individuales.</span><span class="sxs-lookup"><span data-stu-id="d75a6-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="d75a6-130">Para que la versión de Office 365 de Lync Server se comunique con su equivalente de Exchange, Lync Server 2013 primero debe obtener un token de seguridad del servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="d75a6-130">For the Office 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="d75a6-131">A continuación, Lync Server usa ese token de seguridad para identificarse en Exchange.</span><span class="sxs-lookup"><span data-stu-id="d75a6-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="d75a6-132">La versión de Office 365 de Exchange debe pasar por el mismo proceso para poder comunicarse con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d75a6-132">The Office 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="d75a6-133">Sin embargo, para una autenticación de servidor a servidor local entre dos servidores Microsoft, no es necesario usar ningún servidor de tokens de otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="d75a6-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="d75a6-134">Los productos de servidor, como Lync Server 2013 y Exchange 2013, tienen un servidor de tokens integrado que se puede usar para fines de autenticación con otros servidores de Microsoft (como SharePoint Server) que admiten autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="d75a6-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="d75a6-135">Por ejemplo, Lync Server 2013 puede emitir e iniciar por sí mismo un token de seguridad y, a continuación, usar ese token para comunicarse con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d75a6-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="d75a6-136">En este caso, no es necesario usar ningún servidor de tokens de un tercero.</span><span class="sxs-lookup"><span data-stu-id="d75a6-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="d75a6-137">Para configurar la autenticación de servidor a servidor para una implementación local de Lync Server 2013 debe hacer dos cosas:</span><span class="sxs-lookup"><span data-stu-id="d75a6-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="d75a6-138">Asigne un certificado al emisor de token integrado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d75a6-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="d75a6-139">Configure el servidor al que se comunicará Lync Server 2013 para que sea una "aplicación asociada".</span><span class="sxs-lookup"><span data-stu-id="d75a6-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="d75a6-140">Por ejemplo, si Lync Server 2013 necesita comunicarse con Exchange 2013, tendrá que configurar Exchange para que sea una aplicación de socio.</span><span class="sxs-lookup"><span data-stu-id="d75a6-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d75a6-141">Una "aplicación asociada" es cualquier aplicación con la que Lync Server 2013 pueda intercambiar directamente tokens de seguridad con, sin tener que pasar por un servidor de token de seguridad de terceros.</span><span class="sxs-lookup"><span data-stu-id="d75a6-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="d75a6-142">Tenga en cuenta que OAuth es una parte fundamental del producto y no se puede desactivar ni eliminar.</span><span class="sxs-lookup"><span data-stu-id="d75a6-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d75a6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="d75a6-143">See Also</span></span>


[<span data-ttu-id="d75a6-144">Asignación de un certificado de autenticación de servidor a servidor a Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d75a6-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="d75a6-145">Configuración de Microsoft Lync Server 2013 en un entorno entre entornos</span><span class="sxs-lookup"><span data-stu-id="d75a6-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

