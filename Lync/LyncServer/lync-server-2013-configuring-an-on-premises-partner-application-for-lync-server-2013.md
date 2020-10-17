---
title: Configuración de una aplicación de socio local para Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34b6cd21d781f26ca734effd0c574c016aec3266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517587"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="3cd26-102">Configuración de una aplicación de socio local para Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cd26-102">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cd26-103">_**Última modificación del tema:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="3cd26-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="3cd26-104">Una vez que haya asignado el certificado OAuthTokenIssuer, debe configurar las aplicaciones de socio de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cd26-104">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="3cd26-105">(El procedimiento que se va a explicar configura tanto Microsoft Exchange Server 2013 como Microsoft SharePoint para que actúen como aplicaciones de asociado). Para configurar una aplicación de socio local, debe empezar por copiar el siguiente script de Windows PowerShell y pegar el código en el Bloc de notas (o en cualquier otro editor de texto):</span><span class="sxs-lookup"><span data-stu-id="3cd26-105">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="3cd26-106">Después de copiar el código, guarde el script con un. Extensión de archivo PS1 (por ejemplo, C: \\ scripts \\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="3cd26-106">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="3cd26-107">Tenga en cuenta que, antes de ejecutar este script, debe reemplazar las direcciones URL de metadatos https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 y http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx con las direcciones URL de metadatos usadas por los servidores de Exchange 2013 y SharePoint, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3cd26-107">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="3cd26-108">Consulte la documentación del producto de Exchange 2013 y SharePoint para obtener información sobre cómo identificar la dirección URL de metadatos del producto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3cd26-108">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="3cd26-109">Si observamos la última línea del script, veremos que se usa la siguiente sintaxis para llamar al cmdlet Set-CsOAuthConfiguration:</span><span class="sxs-lookup"><span data-stu-id="3cd26-109">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="3cd26-p103">Como no se usó el parámetro Realm al llamar a Set-CsOAuthConfiguration, el dominio kerberos se establecerá automáticamente en el nombre de dominio completo (FQDN) de la organización (por ejemplo, litwareinc.com). Si el nombre de dominio kerberos es distinto del nombre de la organización, deberá incluirlo del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="3cd26-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="3cd26-112">Después de realizar estos cambios, puede ejecutar el script y configurar Exchange 2013 y SharePoint como aplicaciones de socio, para lo que debe ejecutar el archivo de script desde el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cd26-112">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="3cd26-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3cd26-113">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="3cd26-114">Tenga en cuenta que puede ejecutar este script incluso si no tiene instalado Exchange 2013 y SharePoint Server:, no se producirán problemas si, por ejemplo, configura SharePoint Server como una aplicación de asociado aunque no tenga SharePoint Server instalado.</span><span class="sxs-lookup"><span data-stu-id="3cd26-114">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="3cd26-115">Cuando este script se ejecuta, es posible que aparezca un mensaje de error parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cd26-115">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="3cd26-p105">Este mensaje de error suele indicar una de estas dos situaciones: 1) una de las direcciones URL especificadas en el script no es válida (dicho de otro modo, una de las direcciones URL de metadatos no es realmente una dirección URL de metadatos) o 2) no se pudo establecer contacto con una de las direcciones URL de metadatos. Si esto sucede, compruebe que las direcciones URL son correctas y accesibles y vuelva a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="3cd26-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="3cd26-118">Después de crear la aplicación de socio para Lync Server 2013, debe configurar Lync Server para que sea una aplicación de socio para Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3cd26-118">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="3cd26-119">Puede configurar las aplicaciones de socio para Exchange 2013 ejecutando el script Configure-EnterprisePartnerApplication.ps1; todo lo que debe hacer es especificar la dirección URL de los metadatos para Lync Server e indicar que Lync Server es la nueva aplicación de asociado.</span><span class="sxs-lookup"><span data-stu-id="3cd26-119">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="3cd26-120">Para configurar Lync Server como una aplicación de socio para Exchange, abra el shell de administración de Exchange y ejecute un comando similar a este</span><span class="sxs-lookup"><span data-stu-id="3cd26-120">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

