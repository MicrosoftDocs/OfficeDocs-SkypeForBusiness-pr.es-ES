---
title: Configurar la autenticación de servidor a servidor para un entorno híbrido de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumen: configurar la autenticación de servidor a servidor para un entorno híbrido de Skype empresarial Server.'
ms.openlocfilehash: d0c82d39c5232ccc3d425bad9533bf23b67dc8a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285536"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurar la autenticación de servidor a servidor para un entorno híbrido de Skype empresarial Server.

**Resumen:** Configurar la autenticación de servidor a servidor para el entorno híbrido de Skype empresarial Server.

En una configuración híbrida, algunos de los usuarios están alojados en una instalación local de Skype empresarial Server, mientras que otros usuarios están alojados en la versión de Office 365 de Skype empresarial Server. Para poder configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype empresarial Server para que confíe en el servidor de autorización de Office 365. El paso inicial de este proceso se puede llevar a cabo ejecutando la siguiente secuencia de comandos del shell de administración de Skype empresarial Server:

```
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

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

Para ejecutar este script, debe tener instalado el módulo de PowerShell de Skype empresarial online y conectarse a su inquilino con este módulo. Si no ha instalado estos cmdlets, el script dará un error porque el cmdlet Get-CsTenant no estará disponible. Una vez completada la secuencia de comandos, debe configurar una relación de confianza entre Skype empresarial Server y el servidor de autorización, y una segunda relación de confianza entre Exchange 2013/2016 y el servidor de autorización. Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.

> [!NOTE]
> Si no ha instalado los cmdlets de Microsoft Online Services, tendrá que instalarlos desde el repositorio de PowerShell con el cmdlet install-Module MSOnline. Puede encontrar información detallada para instalar y usar el módulo Microsoft Online Services en el sitio web de Office 365. Estas instrucciones también le indicarán cómo configurar el inicio de sesión único, la Federación y la sincronización entre Office 365 y Active Directory. 



Una vez que haya configurado Office 365 y haya creado entidades de servicio de Office 365 para Skype empresarial Server y Exchange 2013, tendrá que registrar sus credenciales con estas entidades de servicio. Para ello, primero debe obtener una X. 509 Base64 guardada como un. Archivo CER. Este certificado se aplicará a las entidades de servicio de Office 365.

Cuando haya obtenido el certificado X. 509, abra la consola de PowerShell e importe el módulo Microsoft online Windows PowerShell que contiene los cmdlets que se pueden usar para administrar las entidades de servicio:

```
Import-Module MSOnline
```

Cuando se haya importado el módulo, escriba el siguiente comando y, a continuación, presione Entrar para conectarse a Office 365:

```
Connect-MsolService
```

Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales. Escriba su nombre de usuario y contraseña de Office 365 en el cuadro de diálogo y, a continuación, haga clic en Aceptar.

En cuanto esté conectado a Office 365, puede ejecutar el comando siguiente para obtener información sobre las entidades de servicio:

```
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

El paso siguiente es importar, codificar y asignar el certificado X.509. Para importar y codificar el certificado, use los siguientes comandos de Windows PowerShell y asegúrese de especificar la ruta de acceso completa del archivo a su. CER al llamar al método Import:

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Después de que el certificado se haya importado y codificado, podrá asignar el certificado a las entidades de servicio de Office 365. Para ello, en primer lugar use Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId para las entidades de servicio de Skype empresarial Server y Microsoft Exchange; el valor de la propiedad AppPrincipalId se usará para identificar la entidad de servicio a la que se asigna el certificado. Con el valor de la propiedad AppPrincipalId para Skype empresarial Server, use el siguiente comando para asignar el certificado a la versión de Skype empresarial online:

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Después, debe repetir el comando, esta vez usando el valor de la propiedad AppPrincipalId para Exchange 2013.

Si posteriormente necesita eliminar el certificado, por ejemplo, si ha expirado, puede hacerlo recuperando primero el ID para el certificado:

```
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

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Además de asignar un certificado, también debe configurar la entidad de servicio de Exchange Online y configurar la versión local de Skype empresarial Server direcciones URL de servicios web externos como una entidad de servicio de Office 365. Para hacerlo, ejecute estos dos comandos: 

En el siguiente ejemplo, Pool1ExternalWebFQDN.contoso.com es la dirección URL de los servicios web externos para el grupo de servidores de Skype empresarial. Debe repetir estos pasos para agregar todas las direcciones URL de servicios web externos en la implementación.

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
