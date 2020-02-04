---
title: Configurar una aplicación de socio local para Lync Server 2013
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
ms.openlocfilehash: 6fe3597f873e8f3bcf66eba922624e4c13ab3f3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Configurar una aplicación de socio local para Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-04_

Después de asignar el certificado OAuthTokenIssuer, debe configurar las aplicaciones de socio de Microsoft Lync Server 2013. (El procedimiento que se va a analizar configura tanto Microsoft Exchange Server 2013 como Microsoft SharePoint para que actúen como aplicaciones de socio). Para configurar una aplicación de socio local, debe empezar copiando el siguiente script de Windows PowerShell y pegando el código en el Bloc de notas (o cualquier otro editor de texto):

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

Después de copiar el código, guárdelo con un archivo. Extensión de archivo PS1 (por ejemplo, C\\:\\scripts ServerToServerAuth. PS1). Tenga en cuenta que, antes de ejecutar este script, debe reemplazar las direcciones https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 URL http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx de los metadatos y las direcciones URL de metadatos usadas por los servidores de Exchange 2013 y SharePoint, respectivamente. Consulte la documentación del producto de Exchange 2013 y SharePoint para obtener información sobre cómo puede identificar la dirección URL de los metadatos del producto correspondiente.

Si observamos la última línea del script, veremos que se usa la siguiente sintaxis para llamar al cmdlet Set-CsOAuthConfiguration:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Como no se usó el parámetro Realm al llamar a Set-CsOAuthConfiguration, el dominio kerberos se establecerá automáticamente en el nombre de dominio completo (FQDN) de la organización (por ejemplo, litwareinc.com). Si el nombre de dominio kerberos es distinto del nombre de la organización, deberá incluirlo del siguiente modo:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

Después de realizar estos cambios, puede ejecutar el script y configurar Exchange 2013 y SharePoint como aplicaciones asociadas, ejecutando el archivo de scripts desde el shell de administración de Lync Server 2013. Por ejemplo:

    C:\Scripts\ServerToServerAuth.ps1

Tenga en cuenta que puede ejecutar este script incluso si no tiene instalado Exchange 2013 y SharePoint Server:, no se producirá ningún problema si, por ejemplo, configura SharePoint Server como una aplicación de socio, aunque no tenga instalado SharePoint Server.

Cuando se ejecuta este script, es posible que aparezca un mensaje de error parecido al siguiente:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Este mensaje de error suele indicar una de estas dos situaciones: 1) una de las direcciones URL especificadas en el script no es válida (dicho de otro modo, una de las direcciones URL de metadatos no es realmente una dirección URL de metadatos) o 2) no se pudo establecer contacto con una de las direcciones URL de metadatos. Si esto sucede, compruebe que las direcciones URL son correctas y accesibles y vuelva a ejecutar el script.

Después de crear la aplicación de socio para Lync Server 2013, debe configurar Lync Server para que sea una aplicación de asociado para Exchange 2013. Puede configurar las aplicaciones de socio para Exchange 2013 ejecutando el script Configure-EnterprisePartnerApplication. ps1; todo lo que debe hacer es especificar la dirección URL de los metadatos de Lync Server e indicar que Lync Server es la nueva aplicación de socio.

Para configurar Lync Server como una aplicación asociada para Exchange, abra el shell de administración de Exchange y ejecute un comando similar a este

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

