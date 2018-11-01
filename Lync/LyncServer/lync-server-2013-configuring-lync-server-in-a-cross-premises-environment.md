---
title: Configuración de Microsoft Lync Server 2013 en un entorno externo
TOCTitle: Configuración de Microsoft Lync Server 2013 en un entorno externo
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48275610
ms.date: 02/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Microsoft Lync Server 2013 en un entorno externo

 

_**Última modificación del tema:** 2017-02-21_

En una configuración entre entornos, algunos de los usuarios se hospedan en una instalación local de Microsoft Lync Server 2013, mientras que otros se hospedan en la versión Office 365 de Lync Server. Para configurar la autenticación de servidor a servidor en un entorno entre entornos, es necesario configurar primero la instalación local de Lync Server 2013 para que confíe en el servidor de autorización de Office 365. El primer paso del proceso se puede realizar con la ejecución de este script del Shell de administración de Lync Server:

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

Cuando el script finalice, configure dos relaciones de confianza: una entre Lync Server 2013 y el servidor de autorización, y otra entre Exchange 2013 y el servidor de autorización. Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.


> [!NOTE]
> Si no ha instalado los cmdlets de Microsoft Online Services, antes de continuar deberá realizar dos tareas. En primer lugar, descargue e instale la versión de 64 bits de Microsoft Online Services - Ayudante para el inicio de sesión. Una vez instalada, descargue e instale la versión de 64 bits del Módulo Microsoft Online Services para Windows PowerShell. Puede encontrar información detallada sobre la instalación y el funcionamiento del Módulo Microsoft Online Services en el sitio web de Office 365. En las instrucciones también podrá ver cómo configurar el inicio de sesión único, la federación y la sincronización entre Office 365 y Active Directory.<BR>Si no ha instalado estos cmdlets, el script dará un error porque el cmdlet Get-CsTenant no estará disponible.



Tras configurar Office 365 y crear las entidades de servicio de Office 365 para Lync Server 2013 y Exchange 2013, tendrá que registrar sus credenciales con dichas entidades de servicio. Para hacerlo, necesitará obtener un certificado X.509 Base64 guardado como archivo .CER que posteriormente se aplicará a las entidades de servicio de Office 365.

Cuando haya obtenido el certificado X.509, inicie el Módulo Microsoft Online Services (haga clic en **Inicio**, **Todos los programas**, **Microsoft Online Services** y, después, haga clic en **Módulo Microsoft Online Services para Windows PowerShell**). Cuando el módulo se abra, escriba lo siguiente para importar el módulo de Microsoft Online Windows PowerShell que contiene los cmdlets que se utilizarán para administrar las entidades de servicio:

    Import-Module MSOnlineExtended

Una vez importado el módulo, escriba el comando siguiente y presione ENTRAR para conectarse a Office 365:

    Connect-MsolService

Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales. Escriba su nombre de usuario y su contraseña de 365 en el cuadro de diálogo y haga clic en Aceptar.

Cuando se haya conectado a Office 365, podrá ejecutar este comando para obtener información sobre sus entidades de servicio:

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

El paso siguiente es importar, codificar y asignar el certificado X.509. Para importar y codificar el certificado, use los comandos de Windows PowerShell que se muestran a continuación y asegúrese de especificar la ruta completa del archivo .CER cuando llama al método Import:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Cuando haya importado y codificado el certificado, deberá asignarlo a sus entidades de servicio de Office 365. En primer lugar, utilice Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId para las entidades de servicio tanto de Lync Server como de Microsoft Exchange; este valor se usará para identificar la entidad de servicio que se asigne al certificado. Cuando tenga el valor de la propiedad AppPrincipalId para Lync Server 2013, use el comando siguiente para asignar el certificado a la versión Office 365 de Lync Server (las propiedades StartDate y EndDate deben corresponderse con el período de validez del certificado):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Después, repita el mismo comando, pero utilizando el valor de la propiedad AppPrincipalId para Exchange 2013.

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

Además de asignar un certificado, también deberá configurar la entidad de servicio de Exchange Online y su versión local de Lync Server 2013 como entidad de servicio de Office 365. Para hacerlo, ejecute estos dos comandos:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

