---
title: Configurar la autenticación de servidor a servidor para un entorno híbrido de Skype Empresarial Server
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
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumen: configure la autenticación de servidor a servidor para un entorno híbrido de Skype Empresarial Server.'
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828490"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurar la autenticación de servidor a servidor para un entorno híbrido de Skype Empresarial Server.

**Resumen:** Configurar la autenticación de servidor a servidor para el entorno híbrido de Skype Empresarial Server.

En una configuración híbrida, algunos de los usuarios se encuentran en una instalación local de Skype Empresarial Server, mientras que otros se encuentran en la versión de Microsoft 365 u Office 365 de Skype Empresarial Server. Para configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype Empresarial Server para que confíe en el servidor de autorización. El paso inicial de este proceso se puede llevar a cabo ejecutando el siguiente script del Shell de administración de Skype Empresarial Server:

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

Para ejecutar este script, debe tener instalado el módulo de PowerShell de Skype Empresarial Online y conectarse a su espacio empresarial con este módulo. Si no ha instalado estos cmdlets, se producirá un error en el script porque el cmdlet Get-CsTenant no estará disponible. Una vez completado el script, debe configurar una relación de confianza entre Skype Empresarial Server y el servidor de autorización, y una segunda relación de confianza entre Exchange 2013/2016 y el servidor de autorización. Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.

> [!NOTE]
> Si no ha instalado los cmdlets Microsoft Online Services, deberá instalarlo desde el repositorio de PowerShell con el cmdlet `install-module MSOnline` . Puede encontrar información detallada para instalar y usar el módulo Microsoft Online Services en el sitio web de Microsoft 365. Estas instrucciones también le indican cómo configurar el inicio de sesión único, la federación y la sincronización entre Microsoft 365 u Office 365 y Active Directory. 



Después de configurar Microsoft 365 u Office 365 y después de crear entidades de servicio de Microsoft 365 u Office 365 para Skype Empresarial Server y Exchange 2013, deberá registrar sus credenciales con estas entidades de servicio. Para ello, primero debe obtener un certificado X.509 Base64 guardado como un archivo . Archivo CER. Este certificado se aplicará a las entidades de servicio de Microsoft 365 u Office 365.

Cuando haya obtenido el certificado X.509, abra la consola de PowerShell e importe el módulo Windows PowerShell de Microsoft Online que contiene los cmdlets que se pueden usar para administrar entidades de servicio:

```PowerShell
Import-Module MSOnline
```

Cuando se haya importado el módulo, escriba el siguiente comando y, a continuación, presione ENTRAR:

```PowerShell
Connect-MsolService
```

Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales. Escriba su nombre de usuario y contraseña de Microsoft 365 u Office 365 en el cuadro de diálogo y, a continuación, haga clic en Aceptar.

En cuanto esté conectado a Microsoft 365 u Office 365, puede ejecutar el siguiente comando para devolver información sobre las entidades de servicio:

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

El paso siguiente es importar, codificar y asignar el certificado X.509. Para importar y codificar el certificado, use los siguientes comandos Windows PowerShell, asegurándose de especificar la ruta de acceso completa del archivo a su archivo . Archivo CER cuando se llama al método Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Después de importar y codificar el certificado, puede asignarlo a las entidades de servicio de Microsoft 365 u Office 365. Para ello, use primero el Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId tanto para Skype Empresarial Server como para las entidades de servicio de Microsoft Exchange; El valor de la propiedad AppPrincipalId se usará para identificar la entidad de servicio a la que se asigna el certificado. Con el valor de la propiedad AppPrincipalId para Skype Empresarial Server en mano, use el siguiente comando para asignar el certificado a la versión de Skype Empresarial Online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

A continuación, debe repetir el comando, esta vez con el valor de la propiedad AppPrincipalId para Exchange 2013.

Si más adelante necesita eliminar ese certificado, por ejemplo, si ha expirado, puede hacerlo recuperando primero el KeyId para el certificado:

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

Además de asignar un certificado, también debe configurar la entidad de servicio de Exchange Online y configurar la versión local de las direcciones URL de servicios web externos de Skype Empresarial Server como entidad de servicio de Microsoft 365 u Office 365. Esto se puede hacer mediante la ejecución de los dos comandos siguientes. 

En el siguiente ejemplo, Pool1ExternalWebFQDN.contoso.com es la dirección URL de servicios web externos para el grupo de servidores de Skype Empresarial Server. Debe repetir estos pasos para agregar todas las direcciones URL de servicios web externos en la implementación.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
