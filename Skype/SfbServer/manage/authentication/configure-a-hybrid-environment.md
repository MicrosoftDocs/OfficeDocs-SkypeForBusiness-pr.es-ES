---
title: Configurar la autenticación de servidor a servidor para un entorno híbrido de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumen: configure la autenticación de servidor a servidor para un entorno híbrido de Skype empresarial Server.'
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221684"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="93322-103">Configure la autenticación de servidor a servidor para un entorno híbrido de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="93322-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="93322-104">**Resumen:** Configure la autenticación de servidor a servidor para el entorno híbrido de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="93322-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="93322-105">En una configuración híbrida, algunos de los usuarios se hospedan en una instalación local de Skype empresarial Server mientras otros usuarios están alojados en la versión de Microsoft 365 o de Office 365 de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="93322-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="93322-106">Para configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype empresarial Server para que confíe en el servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="93322-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="93322-107">El paso inicial de este proceso se puede llevar a cabo mediante la ejecución del siguiente script del shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="93322-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="93322-p102">Tenga en cuenta que el nombre de dominio kerberos de un inquilino normalmente es diferente al nombre de la organización; de hecho, el nombre de dominio kerberos casi siempre es igual al identificador del inquilino. Por tanto, la primera línea del script se usa para devolver el valor de la propiedad TenantId del inquilino especificado (en este caso, fabrikam.com) y para asignar después dicho nombre a la variable $TenantId:</span><span class="sxs-lookup"><span data-stu-id="93322-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="93322-110">Para ejecutar este script, debe tener instalado el módulo de PowerShell de Skype empresarial online y conectarse a su inquilino con este módulo.</span><span class="sxs-lookup"><span data-stu-id="93322-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="93322-111">Si no ha instalado estos cmdlets, se producirá un error en el script porque el cmdlet Get-CsTenant no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="93322-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="93322-112">Una vez finalizado el script, debe configurar una relación de confianza entre Skype empresarial Server y el servidor de autorización, y una segunda relación de confianza entre Exchange 2013/2016 y el servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="93322-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="93322-113">Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="93322-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="93322-114">Si no ha instalado los cmdlets de Microsoft Online Services, tendrá que instalarlos desde el repositorio de PowerShell con el cmdlet `install-module MSOnline` .</span><span class="sxs-lookup"><span data-stu-id="93322-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="93322-115">Puede encontrar información detallada sobre cómo instalar y usar el módulo Microsoft Online Services en el sitio web de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93322-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="93322-116">Estas instrucciones también le indicarán cómo configurar el inicio de sesión único, la Federación y la sincronización entre Microsoft 365 o Office 365 y Active Directory.</span><span class="sxs-lookup"><span data-stu-id="93322-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="93322-117">Una vez que haya configurado Microsoft 365 u Office 365 y después de haber creado las entidades de servicio de Microsoft 365 o Office 365 para Skype empresarial Server y Exchange 2013, deberá registrar sus credenciales con estas entidades de servicio.</span><span class="sxs-lookup"><span data-stu-id="93322-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="93322-118">Para ello, primero debe obtener un certificado X. 509 Base64 guardado como un. Archivo CER.</span><span class="sxs-lookup"><span data-stu-id="93322-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="93322-119">Este certificado se aplicará a las entidades de servicio de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="93322-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="93322-120">Cuando haya obtenido el certificado X. 509, abra la consola de PowerShell e importe el módulo Microsoft online Windows PowerShell que contiene los cmdlets que se pueden usar para administrar las entidades de servicio:</span><span class="sxs-lookup"><span data-stu-id="93322-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="93322-121">Una vez importado el módulo, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="93322-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="93322-122">Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales.</span><span class="sxs-lookup"><span data-stu-id="93322-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="93322-123">Escriba su nombre de usuario y contraseña de Microsoft 365 o Office 365 en el cuadro de diálogo y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="93322-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="93322-124">En cuanto esté conectado a Microsoft 365 u Office 365, puede ejecutar el siguiente comando para devolver información sobre sus entidades de servicio:</span><span class="sxs-lookup"><span data-stu-id="93322-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="93322-125">La información relativa a todas las entidades de servicio que aparecerá será similar a esta:</span><span class="sxs-lookup"><span data-stu-id="93322-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="93322-126">El paso siguiente es importar, codificar y asignar el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="93322-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="93322-127">Para importar y codificar el certificado, use los siguientes comandos de Windows PowerShell y asegúrese de especificar la ruta de acceso completa del archivo a su. CER cuando se llama al m? todo Import:</span><span class="sxs-lookup"><span data-stu-id="93322-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="93322-128">Una vez que el certificado se ha importado y codificado, puede asignar el certificado a las entidades de servicio de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="93322-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="93322-129">Para ello, use primero el Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId de Skype empresarial Server y las entidades de servicio de Microsoft Exchange; el valor de la propiedad AppPrincipalId se usará para identificar la entidad de servicio a la que se asigna el certificado.</span><span class="sxs-lookup"><span data-stu-id="93322-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="93322-130">Con el valor de la propiedad AppPrincipalId de Skype empresarial Server, use el siguiente comando para asignar el certificado a la versión de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="93322-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="93322-131">A continuación, debería repetir el comando, esta vez, usando el valor de la propiedad AppPrincipalId para Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="93322-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="93322-132">Si más tarde necesita eliminar el certificado, por ejemplo, si ha expirado, puede hacerlo recuperando primero el ID del certificado para el certificado:</span><span class="sxs-lookup"><span data-stu-id="93322-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="93322-133">El comando devolverá datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="93322-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="93322-134">Entonces podrá eliminar el certificado usando un comando como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="93322-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="93322-135">Además de asignar un certificado, también debe configurar la entidad de servicio de Exchange Online y configurar la versión local de las direcciones URL de servicios web externos de Skype empresarial Server como una entidad de servicio de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="93322-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="93322-136">Esto se puede llevar a cabo mediante los dos comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="93322-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="93322-137">En el siguiente ejemplo, Pool1ExternalWebFQDN.contoso.com es la dirección URL de servicios web externos para el grupo de servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="93322-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="93322-138">Debe repetir estos pasos para agregar todas las direcciones URL de servicios web externos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="93322-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
