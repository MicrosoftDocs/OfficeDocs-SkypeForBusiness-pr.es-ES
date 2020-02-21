---
title: 'Lync Server 2013: configuración de la autenticación pasiva'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96c2c94bde12e6b8b77060a82f1990b673421de9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="9b68a-102">Configuración de la autenticación pasiva de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b68a-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b68a-103">_**Última modificación del tema:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="9b68a-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="9b68a-104">En la siguiente sección se describe cómo configurar Lync Server 2013 con actualizaciones acumulativas: 2013 julio para admitir la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="9b68a-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="9b68a-105">Una vez habilitado, los usuarios de Lync que tengan habilitada la autenticación en dos fases deberán usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión mediante el cliente de Lync 2013 con actualizaciones acumulativas: cliente de 2013 de julio.</span><span class="sxs-lookup"><span data-stu-id="9b68a-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9b68a-106">Se recomienda encarecidamente que los clientes habiliten la autenticación pasiva para el registrador y los servicios web en el nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="9b68a-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="9b68a-107">Si la autenticación pasiva está habilitada para el registrador y los servicios web en el nivel global, es probable que se produzcan errores de autenticación en toda la organización para los usuarios que no inician sesión con el cliente de escritorio de Lync 2013 con actualizaciones acumulativas: cliente de escritorio del cliente de julio de 2013.</span><span class="sxs-lookup"><span data-stu-id="9b68a-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="9b68a-108">Configuración del servicio Web</span><span class="sxs-lookup"><span data-stu-id="9b68a-108">Web Service Configuration</span></span>

<span data-ttu-id="9b68a-109">En los siguientes pasos se describe cómo crear una configuración de servicio web personalizada para directores, grupos de servidores Enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="9b68a-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="9b68a-110">**Para crear una configuración de servicio web personalizada**</span><span class="sxs-lookup"><span data-stu-id="9b68a-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="9b68a-111">Inicie sesión en su Lync Server 2013 con actualizaciones acumulativas: 2013 servidor front-end de julio con una cuenta de administrador de Lync.</span><span class="sxs-lookup"><span data-stu-id="9b68a-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="9b68a-112">Inicie el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b68a-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="9b68a-113">Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de servicio web para cada director, grupo de servidores Enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva mediante la ejecución del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9b68a-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="9b68a-114">El valor para el FQDN WsFedPassiveMetadataUri es el nombre del servicio de Federación del servidor 2,0 de AD FS.</span><span class="sxs-lookup"><span data-stu-id="9b68a-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="9b68a-115">El valor del nombre del servicio de Federación se puede encontrar en la consola de administración de AD FS 2,0 al hacer clic con el botón secundario en <STRONG>servicio</STRONG> en el panel de navegación y, a continuación, seleccionar <STRONG>Editar propiedades del servicio de Federación</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9b68a-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="9b68a-116">Ejecute el siguiente comando para comprobar que los valores para y WsFedPassiveMetadataUri se establecieron correctamente:</span><span class="sxs-lookup"><span data-stu-id="9b68a-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="9b68a-117">Para los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de webticket.</span><span class="sxs-lookup"><span data-stu-id="9b68a-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="9b68a-118">Para todos los directores, grupos de servidores Enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben estar deshabilitados en servicios Web de Lync ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9b68a-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="9b68a-119">Ejecute el siguiente comando para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación:</span><span class="sxs-lookup"><span data-stu-id="9b68a-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="9b68a-120">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="9b68a-120">Proxy Configuration</span></span>

<span data-ttu-id="9b68a-121">Cuando la autenticación de certificados está deshabilitada para los servicios Web de Lync, el cliente de Lync usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio de registrador.</span><span class="sxs-lookup"><span data-stu-id="9b68a-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="9b68a-122">La autenticación de certificados sigue siendo necesaria para permitir que el cliente de Lync recupere un webvale, pero Kerberos y NTLM deben estar deshabilitados para el servicio de registrador.</span><span class="sxs-lookup"><span data-stu-id="9b68a-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="9b68a-123">En los pasos siguientes se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="9b68a-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="9b68a-124">**Para crear una configuración de proxy personalizada**</span><span class="sxs-lookup"><span data-stu-id="9b68a-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="9b68a-125">Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de proxy para cada Lync Server 2013 con actualizaciones acumulativas: 2013 el grupo de servidores perimetrales, el grupo de servidores Enterprise y el servidor Standard Edition que se habilitarán para la autenticación pasiva mediante la ejecución del comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b68a-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="9b68a-126">Ejecute el siguiente comando para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy:</span><span class="sxs-lookup"><span data-stu-id="9b68a-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

