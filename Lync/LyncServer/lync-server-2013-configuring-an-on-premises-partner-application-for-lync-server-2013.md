---
title: "Conf. d’une application partenaire locale pour Microsoft Lync Server 2013"
TOCTitle: "Conf. d’une application partenaire locale pour Microsoft Lync Server 2013"
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48275541
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de una aplicación de socio local para Microsoft Lync Server 2013

 

_**Última modificación del tema:** 2013-02-04_

Tras asignar el certificado OAuthTokenIssuer, es necesario configurar las aplicaciones de asociado de Microsoft Lync Server 2013 (con el procedimiento que vamos a explicar, tanto Microsoft Exchange Server 2013 como Microsoft SharePoint se configuran como aplicaciones de asociados). Para configurar una aplicación de asociado local, el primer paso consiste en copiar el siguiente script de Windows PowerShell y pegar el código en el Bloc de notas (o cualquier otro editor de texto):

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

Una vez copiado el código, guarde el script con una extensión de archivo .PS1 (por ejemplo, C:\\Scripts\\ServerToServerAuth.ps1). No olvide que, antes de ejecutar este script, deberá reemplazar las direcciones URL de metadatos https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 y http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx por las direcciones URL de metadatos que usen los servidores de Exchange 2013 y SharePoint respectivamente. Consulte la documentación del producto de Exchange 2013 y SharePoint para obtener información sobre cómo identificar la dirección URL de metadatos de cada producto.

Si observamos la última línea del script, veremos que se usa la siguiente sintaxis para llamar al cmdlet Set-CsOAuthConfiguration:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Como no se usó el parámetro Realm al llamar a Set-CsOAuthConfiguration, el dominio kerberos se establecerá automáticamente en el nombre de dominio completo (FQDN) de la organización (por ejemplo, litwareinc.com). Si el nombre de dominio kerberos es distinto del nombre de la organización, deberá incluirlo del siguiente modo:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

Después de realizar estos cambios, puede ejecutar el script y, a continuación, configurar Exchange 2013 y SharePoint como aplicaciones de asociado ejecutando el archivo de script desde el Shell de administración de Lync Server 2013. Por ejemplo:

    C:\Scripts\ServerToServerAuth.ps1

Tenga en cuenta que este script se puede ejecutar aun cuando Exchange 2013 y SharePoint Server no estén instalados. Por lo tanto, no surgirán problemas si, por ejemplo, se configura SharePoint Server como una aplicación de asociado y SharePoint Server no está instalado.

Cuando este script se ejecuta, es posible que aparezca un mensaje de error parecido al siguiente:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Este mensaje de error suele indicar una de estas dos situaciones: 1) una de las direcciones URL especificadas en el script no es válida (dicho de otro modo, una de las direcciones URL de metadatos no es realmente una dirección URL de metadatos) o 2) no se pudo establecer contacto con una de las direcciones URL de metadatos. Si esto sucede, compruebe que las direcciones URL son correctas y accesibles y vuelva a ejecutar el script.

Tras crear la aplicación de asociado para Lync Server 2013, deberá configurar Lync Server para que sea una aplicación de asociado para Exchange 2013. Para configurar aplicaciones de asociado para Exchange 2013, se ejecuta el script Configure-EnterprisePartnerApplication.ps1; lo único que debe hacer es especificar la dirección URL de metadatos de Lync Server e indicar que Lync Server es la nueva aplicación de asociado.

Para configurar Lync Server como una aplicación de asociado para Exchange, abra el Shell de administración de Exchange y ejecute un comando como el siguiente:

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

