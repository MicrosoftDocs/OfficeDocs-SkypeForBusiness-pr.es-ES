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
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a><span data-ttu-id="280d7-103">Configurar un entorno híbrido en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="280d7-103">Configure a hybrid environment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="280d7-104">**Resumen:** Configurar Skype para el año 2015 de servidor empresarial en un entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="280d7-104">**Summary:** Configure Skype for Business Server 2015 in a hybrid environment.</span></span>
  
<span data-ttu-id="280d7-105">En una configuración híbrida, algunos de los usuarios alojados en una instalación local de Skype para Business Server 2015 mientras otros usuarios están alojados en la versión de Office 365 de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="280d7-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server 2015 while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="280d7-106">Para configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype para Business Server 2015 confiar en el servidor de autorización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="280d7-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server 2015 to trust the Office 365 authorization server.</span></span> <span data-ttu-id="280d7-107">El paso inicial en este proceso puede llevarse a cabo ejecutando el siguiente Skype para secuencia de comandos de Shell de administración de servidor de negocios:</span><span class="sxs-lookup"><span data-stu-id="280d7-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>
  
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

<span data-ttu-id="280d7-p102">Tenga en cuenta que el nombre de dominio kerberos de un inquilino normalmente es diferente al nombre de la organización; de hecho, el nombre de dominio kerberos casi siempre es igual al identificador del inquilino. Por tanto, la primera línea del script se usa para devolver el valor de la propiedad TenantId del inquilino especificado (en este caso, fabrikam.com) y para asignar después dicho nombre a la variable $TenantId:</span><span class="sxs-lookup"><span data-stu-id="280d7-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>
  
```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="280d7-110">Una vez completada la secuencia de comandos, a continuación, debe configurar una relación de confianza entre Skype para Business Server 2015 y el servidor de autorización y una segunda relación de confianza entre 2013 de Exchange y el servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="280d7-110">After the script completes, you must then configure a trust relationship between Skype for Business Server 2015 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="280d7-111">Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="280d7-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="280d7-112">Si no ha instalado los cmdlets de Microsoft Online Services, antes de continuar necesitará realizar dos tareas.</span><span class="sxs-lookup"><span data-stu-id="280d7-112">If you have not installed the Microsoft Online Services cmdlets, you will need to do two things before proceeding.</span></span> <span data-ttu-id="280d7-113">En primer lugar, descargue e instale la versión de 64 bits de Microsoft Online Services - Ayudante para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="280d7-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="280d7-114">Una vez completada la instalación, descargue e instale la versión de 64 bits de Microsoft Online Services módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="280d7-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="280d7-115">Información detallada para instalar y utilizar el módulo de Microsoft Online Services puede encontrarse en el sitio web de Office 365.</span><span class="sxs-lookup"><span data-stu-id="280d7-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="280d7-116">Estas instrucciones también describen cómo configurar un inicio de sesión único, federación y la sincronización entre Active Directory y de Office 365.</span><span class="sxs-lookup"><span data-stu-id="280d7-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 
  
<span data-ttu-id="280d7-117">Si no ha instalado estos cmdlets, el script dará un error porque el cmdlet Get-CsTenant no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="280d7-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>
  
<span data-ttu-id="280d7-118">Después de configurar Office 365 y después de haber creado Office 365 principales de servicio para Skype para Business Server 2015 y 2013 de Exchange, necesitará registrar sus credenciales con estas entidades de servicio.</span><span class="sxs-lookup"><span data-stu-id="280d7-118">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server 2015 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="280d7-119">Para ello, primero debe obtener un Base64 X.509 que se guarda como un. Archivo CER.</span><span class="sxs-lookup"><span data-stu-id="280d7-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="280d7-120">Este certificado se aplicará a las entidades de seguridad del servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="280d7-120">This certificate will then be applied to the Office 365 service principals.</span></span>
  
<span data-ttu-id="280d7-121">Cuando haya obtenido el certificado X.509, iniciar el módulo de Microsoft Online Services (haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Microsoft Online Services**y, a continuación, haga clic en **Microsoft Online Services Module para Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="280d7-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="280d7-122">Cuando se abra el módulo de servicios, escriba lo siguiente para importar el módulo de Microsoft en línea de Windows PowerShell con los cmdlets que se puede utilizar para administrar a identidades de servicio:</span><span class="sxs-lookup"><span data-stu-id="280d7-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>
  
```
Import-Module MSOnlineExtended
```

<span data-ttu-id="280d7-123">Cuando se ha importado el módulo, escriba el comando siguiente y presione ENTRAR para conectarse a Office 365:</span><span class="sxs-lookup"><span data-stu-id="280d7-123">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>
  
```
Connect-MsolService
```

<span data-ttu-id="280d7-124">Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales.</span><span class="sxs-lookup"><span data-stu-id="280d7-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="280d7-125">Escriba su nombre de usuario de Office 365 y contraseña en el cuadro de diálogo y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="280d7-125">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>
  
<span data-ttu-id="280d7-126">Tan pronto como está conectado a Office 365, a continuación, puede ejecutar el siguiente comando para devolver información acerca de las entidades de su servicio:</span><span class="sxs-lookup"><span data-stu-id="280d7-126">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>
  
```
Get-MsolServicePrincipal
```

<span data-ttu-id="280d7-127">La información relativa a todas las entidades de servicio que aparecerá será similar a esta:</span><span class="sxs-lookup"><span data-stu-id="280d7-127">You should get back information similar to this for all your service principals:</span></span>
  
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

<span data-ttu-id="280d7-128">El paso siguiente es importar, codificar y asignar el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="280d7-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="280d7-129">Para importar y codificar el certificado, utilice los siguientes comandos de Windows PowerShell, asegúrese de especificar la ruta de acceso completa del archivo a su. Archivo CER cuando se llama al método de importación:</span><span class="sxs-lookup"><span data-stu-id="280d7-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="280d7-130">Una vez importado el certificado y codificado, a continuación, puede asignar el certificado a sus principales de servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="280d7-130">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="280d7-131">Para ello, utilice primero la MsolServicePrincipal Get para recuperar el valor de la propiedad AppPrincipalId para el Skype para Business Server y las identidades de servicio de Microsoft Exchange; el valor de la propiedad AppPrincipalId se utilizará para identificar la entidad de seguridad de servicio que se asigna el certificado.</span><span class="sxs-lookup"><span data-stu-id="280d7-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="280d7-132">Con el AppPrincipalId propiedad valor de Skype para Business Server 2015 en la mano, utilice el comando siguiente para asignar el certificado a la versión de Office 365 de Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="280d7-132">With the AppPrincipalId property value for Skype for Business Server 2015 in hand, use the following command to assign the certificate to the Office 365 version of Skype for Business Server:</span></span>
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="280d7-133">A continuación, debe repetir el comando, esta vez utilizando el valor de la propiedad AppPrincipalId para Exchange de 2013.</span><span class="sxs-lookup"><span data-stu-id="280d7-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>
  
<span data-ttu-id="280d7-134">Si más tarde necesita eliminar el certificado, primero recupere el KeyId del certificado con:</span><span class="sxs-lookup"><span data-stu-id="280d7-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="280d7-135">El comando devolverá datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="280d7-135">That command will return data like this one:</span></span>
  
```
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
```

<span data-ttu-id="280d7-136">Entonces podrá eliminar el certificado usando un comando como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="280d7-136">You can then delete the certificate by using a command similar to this:</span></span>
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="280d7-137">Además de asignar un certificado, también debe configurar la entidad de seguridad de servicio en línea de Exchange y configurar su versión local de Skype para la URL de servicios Web externas Business Server 2015 como una entidad de seguridad del servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="280d7-137">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server 2015 external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="280d7-138">Para hacerlo, ejecute estos dos comandos:</span><span class="sxs-lookup"><span data-stu-id="280d7-138">That can be done by carrying out the following two commands.</span></span> 
  
<span data-ttu-id="280d7-139">En el ejemplo siguiente, lync.contoso.com es la URL de servicios Web externa para el Skype para el grupo de servidores empresariales.</span><span class="sxs-lookup"><span data-stu-id="280d7-139">In the following example, lync.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="280d7-140">Debe repetir estos pasos para agregar todas las URL de servicios Web externas en la implementación.</span><span class="sxs-lookup"><span data-stu-id="280d7-140">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true

$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```