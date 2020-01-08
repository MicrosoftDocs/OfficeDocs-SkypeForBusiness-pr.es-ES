---
title: 'Lync Server 2013: configuración de la autenticación pasiva'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590a196ca0e34c0c063b10703c7edd131eb82c50
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="1b056-102">Configuración de la autenticación pasiva de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b056-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b056-103">_**Última modificación del tema:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="1b056-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="1b056-104">En la sección siguiente se describe cómo configurar Lync Server 2013 con las actualizaciones acumulativas: 2013 de julio para admitir la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="1b056-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="1b056-105">Una vez habilitado, los usuarios de Lync que tengan habilitada la autenticación de dos factores deberán usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión con la 2013 de Lync con las actualizaciones acumulativas: cliente de 2013 de julio.</span><span class="sxs-lookup"><span data-stu-id="1b056-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1b056-106">Se recomienda encarecidamente a los clientes que habiliten la autenticación pasiva del registrador y los servicios web en el nivel de servicios.</span><span class="sxs-lookup"><span data-stu-id="1b056-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="1b056-107">Si la autenticación pasiva está habilitada para el registrador y los servicios web en el nivel global, es probable que se produzcan errores de autenticación en toda la organización para los usuarios que no están iniciando sesión con el 2013 de Lync con las actualizaciones acumulativas: cliente de escritorio cliente de 2013 de julio.</span><span class="sxs-lookup"><span data-stu-id="1b056-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="1b056-108">Configuración de servicios web</span><span class="sxs-lookup"><span data-stu-id="1b056-108">Web Service Configuration</span></span>

<span data-ttu-id="1b056-109">En los siguientes pasos, se describe cómo crear una configuración de servicios web personalizada para los Directores, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="1b056-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="1b056-110">**Para crear una configuración de servicios web personalizada**</span><span class="sxs-lookup"><span data-stu-id="1b056-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="1b056-111">Inicie sesión en su Lync Server 2013 con las actualizaciones acumulativas: 2013 servidor front-end de julio mediante una cuenta de administrador de Lync.</span><span class="sxs-lookup"><span data-stu-id="1b056-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="1b056-112">Inicie el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b056-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="1b056-113">Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de servicio web para cada director, grupo de servidores Enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1b056-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="1b056-p103">El valor del FQDN WsFedPassiveMetadataUri es el Nombre del servicio de federación de su servidor AD FS 2.0. El valor de Nombre del servicio de federación se puede consultar en la consola de administración de AD FS 2.0 al hacer clic en <STRONG>Servicio</STRONG> en el panel de navegación y, luego, elegir <STRONG>Editar propiedades del servicio de federación</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1b056-p103">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="1b056-116">Para comprobar que los valores de UseWsFedPassiveAuth y WsFedPassiveMetadataUri se configuraron correctamente, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1b056-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="1b056-117">En los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de WebTicket.</span><span class="sxs-lookup"><span data-stu-id="1b056-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="1b056-118">Para todos los directores, grupos empresariales y servidores Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben estar deshabilitados en los servicios Web de Lync ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1b056-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="1b056-119">Compruebe que todos los demás tipos de autenticación se han deshabilitado ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1b056-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="1b056-120">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="1b056-120">Proxy Configuration</span></span>

<span data-ttu-id="1b056-121">Cuando la autenticación de certificados está deshabilitada para los servicios Web de Lync, el cliente de Lync usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticar el servicio de registro.</span><span class="sxs-lookup"><span data-stu-id="1b056-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="1b056-122">La autenticación de certificados sigue siendo necesaria para permitir que el cliente de Lync recupere un webvale, pero Kerberos y NTLM deben estar deshabilitados para el servicio de registro.</span><span class="sxs-lookup"><span data-stu-id="1b056-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="1b056-123">En los siguientes pasos, se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="1b056-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="1b056-124">**Para crear una configuración de proxy personalizada**</span><span class="sxs-lookup"><span data-stu-id="1b056-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="1b056-125">Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de proxy para cada servidor de Lync 2013 con actualizaciones acumulativas: 2013 de julio, grupo de servidores Enterprise y servidor Standard Edition que se habilitarán para la autenticación pasiva mediante la ejecución de la siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="1b056-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="1b056-126">Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1b056-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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

