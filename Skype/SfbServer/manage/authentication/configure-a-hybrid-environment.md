---
title: Configurar un entorno híbrido en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumen: Configurar Skype para el año 2015 de servidor empresarial en un entorno híbrido.'
ms.openlocfilehash: e31338647338854b260c9f8935cac4dde69df490
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a>Configurar un entorno híbrido en Skype Empresarial Server 2015
 
**Resumen:** Configurar Skype para el año 2015 de servidor empresarial en un entorno híbrido.
  
En una configuración híbrida, algunos de los usuarios alojados en una instalación local de Skype para Business Server 2015 mientras otros usuarios están alojados en la versión de Office 365 de Skype para Business Server. Para configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype para Business Server 2015 confiar en el servidor de autorización de Office 365. El paso inicial en este proceso puede llevarse a cabo ejecutando el siguiente Skype para secuencia de comandos de Shell de administración de servidor de negocios:
  
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

Una vez completada la secuencia de comandos, a continuación, debe configurar una relación de confianza entre Skype para Business Server 2015 y el servidor de autorización y una segunda relación de confianza entre 2013 de Exchange y el servidor de autorización. Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.
  
> [!NOTE]
> Si no ha instalado los cmdlets de Microsoft Online Services, antes de continuar necesitará realizar dos tareas. En primer lugar, descargue e instale la versión de 64 bits de Microsoft Online Services - Ayudante para el inicio de sesión. Una vez completada la instalación, descargue e instale la versión de 64 bits de Microsoft Online Services módulo de Windows PowerShell. Información detallada para instalar y utilizar el módulo de Microsoft Online Services puede encontrarse en el sitio web de Office 365. Estas instrucciones también describen cómo configurar un inicio de sesión único, federación y la sincronización entre Active Directory y de Office 365. 
  
Si no ha instalado estos cmdlets, el script dará un error porque el cmdlet Get-CsTenant no estará disponible.
  
Después de configurar Office 365 y después de haber creado Office 365 principales de servicio para Skype para Business Server 2015 y 2013 de Exchange, necesitará registrar sus credenciales con estas entidades de servicio. Para ello, primero debe obtener un Base64 X.509 que se guarda como un. Archivo CER. Este certificado se aplicará a las entidades de seguridad del servicio de Office 365.
  
Cuando haya obtenido el certificado X.509, iniciar el módulo de Microsoft Online Services (haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Microsoft Online Services**y, a continuación, haga clic en **Microsoft Online Services Module para Windows PowerShell**). Cuando se abra el módulo de servicios, escriba lo siguiente para importar el módulo de Microsoft en línea de Windows PowerShell con los cmdlets que se puede utilizar para administrar a identidades de servicio:
  
```
Import-Module MSOnlineExtended
```

Cuando se ha importado el módulo, escriba el comando siguiente y presione ENTRAR para conectarse a Office 365:
  
```
Connect-MsolService
```

Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales. Escriba su nombre de usuario de Office 365 y contraseña en el cuadro de diálogo y, a continuación, haga clic en Aceptar.
  
Tan pronto como está conectado a Office 365, a continuación, puede ejecutar el siguiente comando para devolver información acerca de las entidades de su servicio:
  
```
Get-MsolServicePrincipal
```

La información relativa a todas las entidades de servicio que aparecerá será similar a esta:
  
```
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
```

El paso siguiente es importar, codificar y asignar el certificado X.509. Para importar y codificar el certificado, utilice los siguientes comandos de Windows PowerShell, asegúrese de especificar la ruta de acceso completa del archivo a su. Archivo CER cuando se llama al método de importación:
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Una vez importado el certificado y codificado, a continuación, puede asignar el certificado a sus principales de servicio de Office 365. Para ello, utilice primero la MsolServicePrincipal Get para recuperar el valor de la propiedad AppPrincipalId para el Skype para Business Server y las identidades de servicio de Microsoft Exchange; el valor de la propiedad AppPrincipalId se utilizará para identificar la entidad de seguridad de servicio que se asigna el certificado. Con el AppPrincipalId propiedad valor de Skype para Business Server 2015 en la mano, utilice el comando siguiente para asignar el certificado a la versión de Office 365 de Skype para Business Server:
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

A continuación, debe repetir el comando, esta vez utilizando el valor de la propiedad AppPrincipalId para Exchange de 2013.
  
Si más tarde necesita eliminar el certificado, primero recupere el KeyId del certificado con:
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

El comando devolverá datos similares a estos:
  
```
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
```

Entonces podrá eliminar el certificado usando un comando como el siguiente:
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Además de asignar un certificado, también debe configurar la entidad de seguridad de servicio en línea de Exchange y configurar su versión local de Skype para la URL de servicios Web externas Business Server 2015 como una entidad de seguridad del servicio de Office 365. Para hacerlo, ejecute estos dos comandos: 
  
En el ejemplo siguiente, lync.contoso.com es la URL de servicios Web externa para el Skype para el grupo de servidores empresariales. Debe repetir estos pasos para agregar todas las URL de servicios Web externas en la implementación.
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true

$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```