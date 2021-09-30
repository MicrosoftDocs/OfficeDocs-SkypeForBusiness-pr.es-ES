---
title: Configurar una aplicación de asociado local para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Resumen: configure una aplicación de socio local para Skype Empresarial Server.'
ms.openlocfilehash: d0907d73d6a23c0a5b9a1f1725503b72c5bce993
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012624"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Configurar una aplicación de asociado local para Skype Empresarial Server
 
**Resumen:** Configure una aplicación de socio local para Skype Empresarial Server.
  
Después de asignar el certificado OAuthTokenIssuer, debe configurar las Skype Empresarial Server asociadas. (El procedimiento que está a punto de tratarse configura Microsoft Exchange Server 2013 y SharePoint para que actúen como aplicaciones asociadas, que es opcional). Para configurar una aplicación de socio local, debe empezar copiando el siguiente script de Windows PowerShell y pegando el código en Bloc de notas (o cualquier otro editor de texto):
  
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

Una vez copiado el código, guarde el script con una extensión de archivo .PS1 (por ejemplo, C:\Scripts\ServerToServerAuth.ps1). Tenga en cuenta que, antes de ejecutar este script, debe reemplazar las direcciones URL de metadatos y las direcciones URL de metadatos usadas por los servidores Exchange `https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1` `http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1` 2013 y SharePoint, respectivamente. Consulte la documentación del producto Exchange 2013 y SharePoint para obtener información sobre cómo identificar la dirección URL de metadatos del producto correspondiente.
  
Si observamos la última línea del script, veremos que se usa la siguiente sintaxis para llamar al cmdlet Set-CsOAuthConfiguration:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Como no se usó el parámetro Realm al llamar a Set-CsOAuthConfiguration, el dominio kerberos se establecerá automáticamente en el nombre de dominio completo (FQDN) de la organización (por ejemplo, litwareinc.com). Si el nombre de dominio kerberos es distinto del nombre de la organización, deberá incluirlo del siguiente modo:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Después de realizar estos cambios, puede ejecutar el script y configurar Exchange 2013 y SharePoint como aplicaciones asociadas, ejecutando el archivo de script desde el Shell de administración de Skype Empresarial Server. Por ejemplo:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Tenga en cuenta que puede ejecutar este script incluso si no tiene instalado Exchange 2013 y SharePoint Server:, no se producirá ningún problema si, por ejemplo, configura SharePoint Server como una aplicación asociada aunque no tenga instalado SharePoint Server.
  
Cuando este script se ejecuta, es posible que aparezca un mensaje de error parecido al siguiente:
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Este mensaje de error suele indicar una de estas dos situaciones: 1) una de las direcciones URL especificadas en el script no es válida (dicho de otro modo, una de las direcciones URL de metadatos no es realmente una dirección URL de metadatos) o 2) no se pudo establecer contacto con una de las direcciones URL de metadatos. Si esto sucede, compruebe que las direcciones URL son correctas y accesibles y vuelva a ejecutar el script.
  
Después de crear la aplicación de asociado para Skype Empresarial Server debe configurar Skype Empresarial Server para que sea una aplicación de socio para Exchange 2013. Puede configurar aplicaciones de asociado para Exchange 2013 ejecutando el script Configure-EnterprisePartnerApplication.ps1; Todo lo que necesita hacer es especificar la dirección URL de metadatos para Skype Empresarial Server e indicar que Skype Empresarial Server es la nueva aplicación asociada. 
  
Para configurar Skype Empresarial Server como una aplicación asociada para Exchange, abra el Shell de administración de Exchange y ejecute un comando similar a este
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


