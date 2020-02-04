---
title: 'Lync Server 2013: configuración de Lync Server en un entorno entre entornos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02696b85921e2f408b7a7ec5531b0596aaef49ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Configuración de Microsoft Lync Server 2013 en un entorno entre entornos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-02-21_

En una configuración entre locales, algunos usuarios se alojan en una instalación local de Microsoft Lync Server 2013 mientras otros usuarios están alojados en la versión de Office 365 de Lync Server. Para configurar la autenticación de servidor a servidor en un entorno entre locales, primero debe configurar la instalación local de Lync Server 2013 para que confíe en el servidor de autorización de Office 365. El paso inicial de este proceso se puede llevar a cabo ejecutando la siguiente secuencia de comandos del shell de administración de Lync Server:

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Tenga en cuenta que el nombre de dominio kerberos de un inquilino normalmente es diferente al nombre de la organización; de hecho, el nombre de dominio kerberos casi siempre es igual al identificador del inquilino. Por tanto, la primera línea del script se usa para devolver el valor de la propiedad TenantId del inquilino especificado (en este caso, fabrikam.com) y para asignar después dicho nombre a la variable $TenantId:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Una vez completada la secuencia de comandos, debe configurar una relación de confianza entre Lync Server 2013 y el servidor de autorización, y una segunda relación de confianza entre Exchange 2013 y el servidor de autorización. Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.

<div>


> [!NOTE]  
> Si no ha instalado los cmdlets de Microsoft Online Services, tendrá que realizar dos acciones antes de continuar. En primer lugar, descargue e instale la versión de 64 bits de Microsoft Online Services - Ayudante para el inicio de sesión. Una vez completada la instalación, descargue e instale la versión de 64 del módulo Microsoft Online Services para Windows PowerShell. Puede encontrar información detallada para instalar y usar el módulo Microsoft Online Services en el sitio web de Office 365. Estas instrucciones también le indicarán cómo configurar el inicio de sesión único, la Federación y la sincronización entre Office 365 y Active Directory.<BR>Si no ha instalado estos cmdlets, el script dará un error porque el cmdlet Get-CsTenant no estará disponible.



</div>

Una vez que haya configurado Office 365, y después de haber creado las entidades de servicio de Office 365 para Lync Server 2013 y Exchange 2013, tendrá que registrar sus credenciales con estas entidades de servicio. Para ello, primero debe obtener una X. 509 Base64 guardada como un. Archivo CER. Este certificado se aplicará a las entidades de servicio de Office 365.

Cuando haya obtenido el certificado X. 509, inicie el módulo Microsoft Online Services (haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Online Services**y, a continuación, haga clic en **Microsoft Online Services Module para Windows PowerShell**). Después de que se abra el módulo servicios, escriba lo siguiente para importar el módulo Microsoft online Windows PowerShell que contiene los cmdlets que se pueden usar para administrar entidades de servicio:

    Import-Module MSOnlineExtended

Cuando se haya importado el módulo, escriba el siguiente comando y, a continuación, presione Entrar para conectarse a Office 365:

    Connect-MsolService

Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales. Escriba su nombre de usuario y contraseña de Office 365 en el cuadro de diálogo y, a continuación, haga clic en Aceptar.

En cuanto esté conectado a Office 365, puede ejecutar el comando siguiente para obtener información sobre las entidades de servicio:

    Get-MsolServicePrincipal

La información relativa a todas las entidades de servicio que aparecerá será similar a esta:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

El paso siguiente es importar, codificar y asignar el certificado X.509. Para importar y codificar el certificado, use los siguientes comandos de Windows PowerShell y asegúrese de especificar la ruta de acceso completa del archivo a su. CER al llamar al método Import:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Después de que el certificado se haya importado y codificado, podrá asignar el certificado a las entidades de servicio de Office 365. Para ello, en primer lugar use Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId para las entidades de servicio Lync Server y Microsoft Exchange. el valor de la propiedad AppPrincipalId se usará para identificar la entidad de servicio a la que se asigna el certificado. Con el valor de la propiedad AppPrincipalId para Lync Server 2013, use el siguiente comando para asignar el certificado a la versión de Office 365 de Lync Server (las propiedades StartDate y EndDate deben corresponderse con el período de validez del certificado):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Después, debe repetir el comando, esta vez usando el valor de la propiedad AppPrincipalId para Exchange 2013.

Si más tarde necesita eliminar el certificado, primero recupere el KeyId del certificado con:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

El comando devolverá datos similares a estos:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

Entonces podrá eliminar el certificado usando un comando como el siguiente:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Además de asignar un certificado, también debe configurar la entidad de servicio de Office 365 para Exchange Online agregando el nombre principal de servidor de la versión local de Lync Server 2013. Esto puede hacerse ejecutando las cuatro líneas siguientes en una sesión de Microsoft Online Services PowerShell:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

