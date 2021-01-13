---
title: Configurar una aplicación de socio local para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Resumen: configure una aplicación de socio local para Skype Empresarial Server.'
ms.openlocfilehash: 82db666dbbd94fdae8a99bca13954d33d6d5805f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828440"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="2bcf7-103">Configurar una aplicación de socio local para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2bcf7-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="2bcf7-104">**Resumen:** Configurar una aplicación de socio local para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="2bcf7-105">Después de asignar el certificado OAuthTokenIssuer, debe configurar las aplicaciones de socio de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="2bcf7-106">(El procedimiento que se va a tratar configura tanto Microsoft Exchange Server 2013 como SharePoint para que actúen como aplicaciones de asociado, lo cual es opcional). Para configurar una aplicación de socio local, debe empezar copiando el siguiente script Windows PowerShell y pegando el código en el Bloc de notas (o en cualquier otro editor de texto):</span><span class="sxs-lookup"><span data-stu-id="2bcf7-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
```PowerShell
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

<span data-ttu-id="2bcf7-107">Una vez copiado el código, guarde el script con una extensión de archivo .PS1 (por ejemplo, C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="2bcf7-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="2bcf7-108">Tenga en cuenta que, antes de ejecutar este script, debe reemplazar las direcciones URL de metadatos y las direcciones URL de metadatos usadas por los servidores de https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 Exchange 2013 y SharePoint, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="2bcf7-109">Consulte la documentación del producto para Exchange 2013 y SharePoint para obtener información sobre cómo puede identificar la dirección URL de metadatos del producto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="2bcf7-110">Si observamos la última línea del script, veremos que se usa la siguiente sintaxis para llamar al cmdlet Set-CsOAuthConfiguration:</span><span class="sxs-lookup"><span data-stu-id="2bcf7-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="2bcf7-p103">Como no se usó el parámetro Realm al llamar a Set-CsOAuthConfiguration, el dominio kerberos se establecerá automáticamente en el nombre de dominio completo (FQDN) de la organización (por ejemplo, litwareinc.com). Si el nombre de dominio kerberos es distinto del nombre de la organización, deberá incluirlo del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="2bcf7-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="2bcf7-113">Después de realizar estos cambios, puede ejecutar el script y configurar Exchange 2013 y SharePoint como aplicaciones de socio, ejecutando el archivo de script desde el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2bcf7-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2bcf7-114">For example:</span></span>
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="2bcf7-115">Tenga en cuenta que puede ejecutar este script aunque no tenga instalados Exchange 2013 y SharePoint Server: no se producirán problemas si, por ejemplo, configura SharePoint Server como una aplicación de socio aunque no tenga instalado SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="2bcf7-116">Cuando este script se ejecuta, es posible que aparezca un mensaje de error parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bcf7-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="2bcf7-p105">Este mensaje de error suele indicar una de estas dos situaciones: 1) una de las direcciones URL especificadas en el script no es válida (dicho de otro modo, una de las direcciones URL de metadatos no es realmente una dirección URL de metadatos) o 2) no se pudo establecer contacto con una de las direcciones URL de metadatos. Si esto sucede, compruebe que las direcciones URL son correctas y accesibles y vuelva a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="2bcf7-119">Después de crear la aplicación de socio para Skype Empresarial Server, debe configurar Skype Empresarial Server para que sea una aplicación de socio para Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="2bcf7-120">Puede configurar aplicaciones de asociados para Exchange 2013 ejecutando el script Configure-EnterprisePartnerApplication.ps1; Todo lo que necesita hacer es especificar la dirección URL de metadatos para Skype Empresarial Server e indicar que Skype Empresarial Server es la nueva aplicación de socio.</span><span class="sxs-lookup"><span data-stu-id="2bcf7-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="2bcf7-121">Para configurar Skype Empresarial Server como una aplicación de socio para Exchange, abra el Shell de administración de Exchange y ejecute un comando similar a este</span><span class="sxs-lookup"><span data-stu-id="2bcf7-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


