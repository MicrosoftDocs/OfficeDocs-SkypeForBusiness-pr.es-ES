---
title: Configurar la autenticación de servidor a servidor para un Skype Empresarial Server híbrido
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumen: configure la autenticación de servidor a servidor para un entorno Skype Empresarial Server híbrido.'
ms.openlocfilehash: f07c5f9fb930910422c264d1ca61f992c84f1600
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391182"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configure la autenticación de servidor a servidor para un Skype Empresarial Server híbrido.

**Resumen:** Configure la autenticación de servidor a servidor Skype Empresarial Server entorno híbrido.

En una configuración híbrida, algunos de los usuarios se encuentran en una instalación local de Skype Empresarial Server mientras que otros usuarios se encuentran en la versión Microsoft 365 o Office 365 de Skype Empresarial Server. Para configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype Empresarial Server para confiar en el servidor de autorización. El paso inicial de este proceso se puede llevar a cabo ejecutando el siguiente script Skype Empresarial Server Shell de administración:

```PowerShell
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
```

Tenga en cuenta que el nombre de dominio kerberos de un inquilino normalmente es diferente al nombre de la organización; de hecho, el nombre de dominio kerberos casi siempre es igual al identificador del inquilino. Por tanto, la primera línea del script se usa para devolver el valor de la propiedad TenantId del inquilino especificado (en este caso, fabrikam.com) y para asignar después dicho nombre a la variable $TenantId:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Para ejecutar este script, debe haber instalado Skype Empresarial módulo de PowerShell en línea y conectarse al espacio empresarial con este módulo. Si no ha instalado estos cmdlets, el script producirá un error porque el cmdlet Get-CsTenant no estará disponible. Una vez completado el script, debe configurar una relación de confianza entre Skype Empresarial Server y el servidor de autorización y una segunda relación de confianza entre Exchange 2013/2016 y el servidor de autorización. Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.

> [!NOTE]
> Si no ha instalado los cmdlets Microsoft Online Services, deberá instalarlo desde el repositorio de PowerShell con el cmdlet `install-module MSOnline`. Encontrará información detallada para instalar y usar el Microsoft Online Services módulo en el Microsoft 365 web. Estas instrucciones también le indican cómo configurar el inicio de sesión único, la federación y la sincronización entre Microsoft 365 o Office 365 Active Directory. 



Después de configurar Microsoft 365 o Office 365 y después de crear Microsoft 365 o Office 365 de servicio para Skype Empresarial Server y Exchange  2013, tendrá que registrar sus credenciales con estas entidades de servicio. Para ello, primero debe obtener un certificado X.509 Base64 guardado como . Archivo CER. A continuación, este certificado se aplicará a las entidades Microsoft 365 o Office 365 de servicio.

Cuando haya obtenido el certificado X.509, abra la consola de PowerShell e importe el módulo de Microsoft Online Windows PowerShell que contiene los cmdlets que se pueden usar para administrar entidades de servicio:

```PowerShell
Import-Module MSOnline
```

Cuando se haya importado el módulo, escriba el siguiente comando y, a continuación, presione ENTRAR:

```PowerShell
Connect-MsolService
```

Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales. Escriba su Microsoft 365 o Office 365 nombre de usuario y contraseña en el cuadro de diálogo y, a continuación, haga clic en Aceptar.

En cuanto esté conectado a Microsoft 365 o Office 365, puede ejecutar el siguiente comando para devolver información sobre las entidades de servicio:

```PowerShell
Get-MsolServicePrincipal
```

La información relativa a todas las entidades de servicio que aparecerá será similar a esta:

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

El paso siguiente es importar, codificar y asignar el certificado X.509. Para importar y codificar el certificado, use los siguientes comandos Windows PowerShell, asegurándose de especificar la ruta de acceso completa del archivo a su . CER al llamar al método Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Después de importar y codificar el certificado, puede asignar el certificado a las entidades de Microsoft 365 o Office 365 de servicio. Para ello, primero use el Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId para las entidades de servicio de Skype Empresarial Server y Microsoft Exchange; el valor de la propiedad AppPrincipalId se usará para identificar la entidad de servicio a la que se asigna el certificado. Con el valor de la propiedad AppPrincipalId para Skype Empresarial Server en mano, use el siguiente comando para asignar el certificado a Skype versión de For Business Online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

A continuación, debe repetir el comando, esta vez con el valor de la propiedad AppPrincipalId para Exchange 2013.

Si más adelante necesita eliminar ese certificado, por ejemplo, si ha expirado, puede hacerlo recuperando primero keyid para el certificado:

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

El comando devolverá datos similares a estos:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

Entonces podrá eliminar el certificado usando un comando como el siguiente:

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Además de asignar un certificado, también debe configurar la entidad de servicio de Exchange Online y configurar la versión local de las direcciones URL de servicios web externos Skype Empresarial Server como entidad de servicio Microsoft 365 o Office 365. Para ello, lleve a cabo los dos comandos siguientes. 

En el siguiente ejemplo, Pool1ExternalWebFQDN.contoso.com es la dirección URL de servicios web externos para el Skype Empresarial Server grupo de servidores. Debe repetir estos pasos para agregar todas las direcciones URL de servicios web externos en la implementación.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
