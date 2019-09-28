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
ms.openlocfilehash: 2879a1acc35a2c8928a95af913476c26028d6e6c
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305776"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="718d5-103">Configurar la autenticación de servidor a servidor para un entorno híbrido de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="718d5-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="718d5-104">**Resumen:** Configurar la autenticación de servidor a servidor para el entorno híbrido de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="718d5-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="718d5-105">En una configuración híbrida, algunos de los usuarios están alojados en una instalación local de Skype empresarial Server, mientras que otros usuarios están alojados en la versión de Office 365 de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="718d5-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="718d5-106">Para poder configurar la autenticación de servidor a servidor en un entorno híbrido, primero debe configurar la instalación local de Skype empresarial Server para que confíe en el servidor de autorización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="718d5-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="718d5-107">El paso inicial de este proceso se puede llevar a cabo ejecutando la siguiente secuencia de comandos del shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="718d5-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="718d5-p102">Tenga en cuenta que el nombre de dominio kerberos de un inquilino normalmente es diferente al nombre de la organización; de hecho, el nombre de dominio kerberos casi siempre es igual al identificador del inquilino. Por tanto, la primera línea del script se usa para devolver el valor de la propiedad TenantId del inquilino especificado (en este caso, fabrikam.com) y para asignar después dicho nombre a la variable $TenantId:</span><span class="sxs-lookup"><span data-stu-id="718d5-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="718d5-110">Para ejecutar este script, debe tener instalado el módulo de PowerShell de Skype empresarial online y conectarse a su inquilino con este módulo.</span><span class="sxs-lookup"><span data-stu-id="718d5-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="718d5-111">Si no ha instalado estos cmdlets, el script dará un error porque el cmdlet Get-CsTenant no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="718d5-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="718d5-112">Una vez completada la secuencia de comandos, debe configurar una relación de confianza entre Skype empresarial Server y el servidor de autorización, y una segunda relación de confianza entre Exchange 2013/2016 y el servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="718d5-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="718d5-113">Solo podrá hacer esto usando los cmdlets de Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="718d5-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="718d5-114">Si no ha instalado los cmdlets de Microsoft Online Services, tendrá que instalarlos desde el repositorio de PowerShell con el cmdlet `install-module MSOnline`.</span><span class="sxs-lookup"><span data-stu-id="718d5-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="718d5-115">Puede encontrar información detallada para instalar y usar el módulo Microsoft Online Services en el sitio web de Office 365.</span><span class="sxs-lookup"><span data-stu-id="718d5-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="718d5-116">Estas instrucciones también le indicarán cómo configurar el inicio de sesión único, la Federación y la sincronización entre Office 365 y Active Directory.</span><span class="sxs-lookup"><span data-stu-id="718d5-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="718d5-117">Una vez que haya configurado Office 365 y haya creado entidades de servicio de Office 365 para Skype empresarial Server y Exchange 2013, tendrá que registrar sus credenciales con estas entidades de servicio.</span><span class="sxs-lookup"><span data-stu-id="718d5-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="718d5-118">Para ello, primero debe obtener un certificado X. 509 Base64 guardado como un. Archivo CER.</span><span class="sxs-lookup"><span data-stu-id="718d5-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="718d5-119">Este certificado se aplicará a las entidades de servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="718d5-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="718d5-120">Cuando haya obtenido el certificado X. 509, abra la consola de PowerShell e importe el módulo Microsoft online Windows PowerShell que contiene los cmdlets que se pueden usar para administrar las entidades de servicio:</span><span class="sxs-lookup"><span data-stu-id="718d5-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnline
```

<span data-ttu-id="718d5-121">Cuando se haya importado el módulo, escriba el siguiente comando y, a continuación, presione Entrar para conectarse a Office 365:</span><span class="sxs-lookup"><span data-stu-id="718d5-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="718d5-122">Tras presionar ENTRAR, aparecerá un cuadro de diálogo de credenciales.</span><span class="sxs-lookup"><span data-stu-id="718d5-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="718d5-123">Escriba su nombre de usuario y contraseña de Office 365 en el cuadro de diálogo y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="718d5-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="718d5-124">En cuanto esté conectado a Office 365, puede ejecutar el comando siguiente para obtener información sobre las entidades de servicio:</span><span class="sxs-lookup"><span data-stu-id="718d5-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="718d5-125">La información relativa a todas las entidades de servicio que aparecerá será similar a esta:</span><span class="sxs-lookup"><span data-stu-id="718d5-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="718d5-126">El paso siguiente es importar, codificar y asignar el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="718d5-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="718d5-127">Para importar y codificar el certificado, use los siguientes comandos de Windows PowerShell y asegúrese de especificar la ruta de acceso completa del archivo a su. CER al llamar al método Import:</span><span class="sxs-lookup"><span data-stu-id="718d5-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="718d5-128">Después de que el certificado se haya importado y codificado, podrá asignar el certificado a las entidades de servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="718d5-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="718d5-129">Para ello, en primer lugar use Get-MsolServicePrincipal para recuperar el valor de la propiedad AppPrincipalId para las entidades de servicio de Skype empresarial Server y Microsoft Exchange; el valor de la propiedad AppPrincipalId se usará para identificar la entidad de servicio a la que se asigna el certificado.</span><span class="sxs-lookup"><span data-stu-id="718d5-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="718d5-130">Con el valor de la propiedad AppPrincipalId para Skype empresarial Server, use el siguiente comando para asignar el certificado a la versión de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="718d5-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="718d5-131">Después, debe repetir el comando, esta vez usando el valor de la propiedad AppPrincipalId para Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="718d5-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="718d5-132">Si posteriormente necesita eliminar el certificado, por ejemplo, si ha expirado, puede hacerlo recuperando primero el ID para el certificado:</span><span class="sxs-lookup"><span data-stu-id="718d5-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="718d5-133">El comando devolverá datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="718d5-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="718d5-134">Entonces podrá eliminar el certificado usando un comando como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="718d5-134">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="718d5-135">Además de asignar un certificado, también debe configurar la entidad de servicio de Exchange Online y configurar la versión local de Skype empresarial Server direcciones URL de servicios web externos como una entidad de servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="718d5-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="718d5-136">Para hacerlo, ejecute estos dos comandos:</span><span class="sxs-lookup"><span data-stu-id="718d5-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="718d5-137">En el siguiente ejemplo, Pool1ExternalWebFQDN.contoso.com es la dirección URL de los servicios web externos para el grupo de servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="718d5-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="718d5-138">Debe repetir estos pasos para agregar todas las direcciones URL de servicios web externos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="718d5-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
