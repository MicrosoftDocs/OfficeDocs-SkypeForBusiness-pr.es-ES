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
description: 'Resumen: Configure Skype para Business Server 2015 en un entorno híbrido.'
ms.openlocfilehash: 4798839bd001e6320870d7ca97ba99108e3b32de
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570188"
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a>Configurar un entorno híbrido en Skype Empresarial Server 2015
 
**Resumen:** Configure Skype para Business Server 2015 en un entorno híbrido.
  
En una configuración híbrida, algunos de los usuarios están hospedados en una instalación local de Skype para Business Server 2015 mientras otros usuarios están hospedados en la versión de Office 365 de Skype para Business Server. Con el fin de configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype para Business Server 2015 para que confíe en el servidor de autorización de Office 365. El paso inicial en este proceso puede llevarse a cabo mediante la ejecución de la siguiente Skype para el script de Shell de administración de servidor empresarial:
  
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

Una vez completada la secuencia de comandos, a continuación, debe configurar una relación de confianza entre Skype para Business Server 2015 y el servidor de autorización y una segunda relación de confianza entre Exchange 2013 y el servidor de autorización. Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.
  
> [!NOTE]
> Si no ha instalado los cmdlets de Microsoft Online Services, antes de continuar necesitará realizar dos tareas. En primer lugar, descargue e instale la versión de 64 bits de Microsoft Online Services - Ayudante para el inicio de sesión. Una vez finalizada la instalación, descargue e instale la versión de 64 bits de Microsoft Online Services Module para Windows PowerShell. Puede encontrar información detallada para instalar y usar el módulo de Microsoft Online Services en el sitio web de Office 365. Estas instrucciones también describen cómo configurar el inicio de sesión único, la federación y la sincronización entre Active Directory y de Office 365. 
  
Si no ha instalado estos cmdlets, el script dará un error porque el cmdlet Get-CsTenant no estará disponible.
  
Después de configurar Office 365, y después de haber creado Office 365 entidades de seguridad de servicio de Skype para Business Server 2015 y Exchange 2013, a continuación, necesitará registrar sus credenciales con estas entidades de seguridad del servicio. Para hacer esto, primero debe obtener un Base64 X.509 que se guarda como un. Archivo CER. Este certificado, a continuación, se aplicará a las entidades de seguridad del servicio de Office 365.
  
Cuando haya obtenido el certificado X.509, iniciar el módulo Microsoft Online Services (haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Online Services**y, a continuación, haga clic en **Microsoft Online Services Module para Windows PowerShell**). Una vez que se abre el módulo de servicios, escriba lo siguiente para importar el módulo Microsoft Online Windows PowerShell que contiene los cmdlets que se pueden usar para administrar las entidades de seguridad de servicio:
  
```
Import-Module MSOnlineExtended
```

Cuando se ha importado el módulo, escriba el siguiente comando y, a continuación, presione ENTRAR para poder conectarse a Office 365:
  
```
Connect-MsolService
```

Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales. Escriba su nombre de usuario de Office 365 y la contraseña en el cuadro de diálogo y, a continuación, haga clic en Aceptar.
  
Tan pronto como se conecta a Office 365, a continuación, puede ejecutar el siguiente comando con el fin de devolver información sobre sus entidades de servicio:
  
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

El paso siguiente es importar, codificar y asignar el certificado X.509. Para importar y codificar el certificado, use los siguientes comandos de Windows PowerShell, asegúrese de especificar la ruta de acceso completa a su. Archivo CER cuando se llama al método de importación:
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Después de que el certificado se ha importado y codificado, a continuación, puede asignar el certificado a entidades de servicio de Office 365. Para ello, use primero el Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId para el Skype para Business Server y las entidades de seguridad del servicio de Microsoft Exchange; el valor de la propiedad AppPrincipalId se usará para identificar la entidad de seguridad de servicio que se va a asignar el certificado. Con el AppPrincipalId (propiedad) valor de la mano de Skype para Business Server 2015, use el siguiente comando para asignar el certificado a la versión de Office 365 de Skype para Business Server:
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

A continuación, debe repetir el comando, esta vez utilizando el valor de la propiedad AppPrincipalId para Exchange 2013.
  
Si más tarde necesita eliminar el certificado, primero recupere el KeyId del certificado con:
  
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

Además de asignar un certificado, también debe configurar la entidad de seguridad de servicio en línea de Exchange y configurar la versión local de Skype para direcciones URL de servicios externas de Web de Business Server 2015 como una entidad de seguridad del servicio de Office 365. Para hacerlo, ejecute estos dos comandos: 
  
En el ejemplo siguiente, lync.contoso.com es la URL de servicios Web externa para el Skype para grupo de servidores empresariales. Debe repetir estos pasos para agregar todas las URL de servicios Web externas en la implementación.
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```