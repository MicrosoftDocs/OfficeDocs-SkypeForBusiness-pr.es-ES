---
title: Configurar una aplicación de socio local de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Resumen: Configurar una aplicación de socio local para Skype para Business Server 2015.'
ms.openlocfilehash: 4a31d97f7a4c2f717084c72cbc349c4f495597ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server-2015"></a>Configurar una aplicación de socio local de Skype Empresarial Server 2015
 
**Resumen:** Configurar una aplicación de socio local para Skype para Business Server 2015.
  
Después de haber asignado el certificado OAuthTokenIssuer, a continuación, debe configurar su Skype para aplicaciones de socios de negocios servidor 2015. (El procedimiento va a ser tratado configura tanto 2013 de Microsoft Exchange Server y SharePoint para actuar como aplicaciones de asociados de negocios, que es opcional). Para configurar una aplicación de socio local, debe comenzar por la siguiente secuencia de comandos de Windows PowerShell de copiar y pegar el código en el Bloc de notas (o cualquier otro editor de texto):
  
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

Una vez copiado el código, guarde el script con una extensión de archivo .PS1 (por ejemplo, C:\Scripts\ServerToServerAuth.ps1). Nota que, antes de ejecutar esta secuencia de comandos, debe reemplazar las direcciones URL de metadatos https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 y http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 con las direcciones URL de metadatos utilizadas por los servidores de 2013 Exchange y SharePoint, respectivamente. Consulte la documentación del producto para 2013 de Exchange y SharePoint para obtener información sobre cómo se puede identificar la dirección URL de metadatos del producto correspondiente.
  
Si observamos la última línea del script, veremos que se usa la siguiente sintaxis para llamar al cmdlet Set-CsOAuthConfiguration:
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Como no se usó el parámetro Realm al llamar a Set-CsOAuthConfiguration, el dominio kerberos se establecerá automáticamente en el nombre de dominio completo (FQDN) de la organización (por ejemplo, litwareinc.com). Si el nombre de dominio kerberos es distinto del nombre de la organización, deberá incluirlo del siguiente modo:
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Después de realizar estos cambios, a continuación, puede ejecutar la secuencia de comandos y configurar 2013 de Exchange y SharePoint como aplicaciones de asociados de negocios, ejecutando el archivo de secuencia de comandos desde el Skype para el Shell de administración de servidor de Business. Por ejemplo:
  
```
C:\Scripts\ServerToServerAuth.ps1
```

Tenga en cuenta que puede ejecutar esta secuencia de comandos incluso si no tiene ambos 2013 Exchange y SharePoint Server instalado:, ningún problema se producirá si, digamos, configurar SharePoint Server como una aplicación asociada aunque no tenga instalado SharePoint Server.
  
Cuando se ejecuta este script, es posible que aparezca un mensaje de error parecido al siguiente:
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Este mensaje de error suele indicar una de estas dos situaciones: 1) una de las direcciones URL especificadas en el script no es válida (dicho de otro modo, una de las direcciones URL de metadatos no es realmente una dirección URL de metadatos) o 2) no se pudo establecer contacto con una de las direcciones URL de metadatos. Si esto sucede, compruebe que las direcciones URL son correctas y accesibles y vuelva a ejecutar el script.
  
Después de crear la aplicación de Skype para Business Server 2015, a continuación, debe configurar Skype para Business Server sea una aplicación asociada para 2013 de Exchange. Puede configurar las aplicaciones de socios para 2013 de Exchange mediante la ejecución de la secuencia de comandos configurar-EnterprisePartnerApplication.ps1; todo lo que necesita hacer es especificar la dirección URL de metadatos de Skype para Business Server e indicar que Skype para Business Server es la nueva aplicación. 
  
Para configurar Skype para Business Server como una aplicación asociada para Exchange, abra el Shell de administración de Exchange y ejecutar un comando similar a éste
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


