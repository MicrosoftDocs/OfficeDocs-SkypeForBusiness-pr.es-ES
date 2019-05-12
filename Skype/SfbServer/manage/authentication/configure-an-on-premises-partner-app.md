---
title: Configurar una aplicación de socio local para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Resumen: Configurar una aplicación de socio local para Skype para Business Server.'
ms.openlocfilehash: a13157d590d6cdd067ed2a0a717fd744adb9de4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913380"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="26497-103">Configurar una aplicación de socio local para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="26497-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="26497-104">**Resumen:** Configurar una aplicación de socio local para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="26497-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="26497-105">Una vez que haya asignado el certificado OAuthTokenIssuer, a continuación, debe configurar su Skype para aplicaciones de socio Business Server.</span><span class="sxs-lookup"><span data-stu-id="26497-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="26497-106">(El procedimiento a se tratan configura tanto Microsoft Exchange Server 2013 y SharePoint para que actúen como aplicaciones de socio, que es opcional). Para configurar una aplicación de socio local, debe empezar por el siguiente script de Windows PowerShell de copiar y pegar el código en el Bloc de notas (o cualquier otro editor de texto):</span><span class="sxs-lookup"><span data-stu-id="26497-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
```
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
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="26497-107">Una vez copiado el código, guarde el script con una extensión de archivo .PS1 (por ejemplo, C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="26497-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="26497-108">Tenga en cuenta que, antes de ejecutar este script, debe reemplazar las direcciones URL de metadatos https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 y http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 con las direcciones URL de metadatos utilizadas por los servidores de Exchange 2013 y SharePoint, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="26497-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="26497-109">Vea la documentación del producto Exchange 2013 y SharePoint para obtener información sobre cómo se puede identificar la dirección URL de metadatos del producto respectivos.</span><span class="sxs-lookup"><span data-stu-id="26497-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="26497-110">Si observamos la última línea del script, veremos que se usa la siguiente sintaxis para llamar al cmdlet Set-CsOAuthConfiguration:</span><span class="sxs-lookup"><span data-stu-id="26497-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="26497-p103">Como no se usó el parámetro Realm al llamar a Set-CsOAuthConfiguration, el dominio kerberos se establecerá automáticamente en el nombre de dominio completo (FQDN) de la organización (por ejemplo, litwareinc.com). Si el nombre de dominio kerberos es distinto del nombre de la organización, deberá incluirlo del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="26497-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="26497-113">Después de realizar estos cambios, a continuación, puede ejecutar el script y configure Exchange 2013 y SharePoint como aplicaciones de los socios, ejecutando el archivo de secuencia de comandos desde el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="26497-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="26497-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="26497-114">For example:</span></span>
  
```
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="26497-115">Tenga en cuenta que puede ejecutar este script, incluso si no tienen ambos Exchange 2013 y SharePoint Server instalado:, no se producirá ningún problema si, por ejemplo, configurar SharePoint Server como una aplicación de socio, aunque no es necesario instalar SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="26497-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="26497-116">Cuando se ejecuta este script, es posible que aparezca un mensaje de error parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="26497-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="26497-p105">Este mensaje de error suele indicar una de estas dos situaciones: 1) una de las direcciones URL especificadas en el script no es válida (dicho de otro modo, una de las direcciones URL de metadatos no es realmente una dirección URL de metadatos) o 2) no se pudo establecer contacto con una de las direcciones URL de metadatos. Si esto sucede, compruebe que las direcciones URL son correctas y accesibles y vuelva a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="26497-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="26497-119">Después de crear la aplicación de socio de Skype para Business Server, a continuación, debe configurar Skype para Business Server como una aplicación de socio para Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="26497-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="26497-120">Puede configurar las aplicaciones de socios para Exchange 2013, ejecute el script Configure-EnterprisePartnerApplication.ps1; todo lo que necesita hacer es especificar la dirección URL de metadatos de Skype para Business Server e indicar que Skype para Business Server es la nueva aplicación de socio.</span><span class="sxs-lookup"><span data-stu-id="26497-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="26497-121">Para configurar Skype para Business Server como una aplicación de socio para Exchange, abra el Shell de administración de Exchange y ejecute un comando similar al siguiente</span><span class="sxs-lookup"><span data-stu-id="26497-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


