---
title: Script de autenticación del panel de control de Skype empresarial Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/23/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Script auxiliar para configurar la autenticación del panel de control de SFB 2019 con Office 365 a través del protocolo OAuth.
ms.openlocfilehash: d434ad1530e05af396982a6c6278a80b9a416aa6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824064"
---
# <a name="skype-for-business-server-2019-control-panel-authentication-script"></a><span data-ttu-id="0dde5-103">Script de autenticación del panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="0dde5-103">Skype for Business Server 2019 control panel authentication script</span></span>

<span data-ttu-id="0dde5-104">Este script debe ejecutarse después de instalar la actualización acumulativa 1 de Skype empresarial Server 2019, como parte de la configuración del nuevo panel de control.</span><span class="sxs-lookup"><span data-stu-id="0dde5-104">This script should be run after installing Skype for Business Server 2019 Cumulative Update 1, as part of the set-up for the new Control Panel.</span></span> <span data-ttu-id="0dde5-105">Este script creará una aplicación de Azure AD en Azure.</span><span class="sxs-lookup"><span data-stu-id="0dde5-105">This script will create an Azure AD Application on Azure.</span></span> <span data-ttu-id="0dde5-106">Esto le ayudará a iniciar sesión en Office 365 con OAuth en el nuevo panel de control.</span><span class="sxs-lookup"><span data-stu-id="0dde5-106">This will help in signing into Office 365 using OAuth in the new Control Panel.</span></span>

```
<#
 .SYNOPSIS
 Helper script to configure SFB 2019 control panel authentication with Office 365 via OAuth protocol.

 .DESCRIPTION
 Copyright (c) Microsoft Corporation. All rights reserved.

 THIS CODE IS MADE AVAILABLE AS IS, WITHOUT WARRANTY OF ANY KIND. THE ENTIRE RISK
 OF THE USE OR THE RESULTS FROM THE USE OF THIS CODE REMAINS WITH THE USER.

 .EXAMPLE
 Creates a native client application on azure active directory with name "MACP"
#>

Write-Host "Getting external FQDN of SFB pools"
$externalFqdns=(Get-CsService -WebServer).ExternalFqdn

Write-Host "Getting internal FQDN of SFB pools"
$internalFqdns=(Get-csService -WebServer).poolfqdn

$replyUrls=New-Object System.Collections.Generic.List[string]

Write-Host "Generating Redirect URIs for modern admin control panel"
#Generating replyUrls using external fqdns
foreach ($externalFqdn in $externalFqdns) {
  if ($externalFqdn -ne $null) {
    $replyUrls.Add('https://' + $externalFqdn + '/macp/iframe.html');
  }
}

#Generating replyUrls using internal fqdns
foreach($internalFqdn in $internalFqdns) {
  if ($internalFqdn -ne $null) {
    $replyUrls.Add('https://' + $internalFqdn + '/macp/iframe.html');
  }
}

if (Get-Module -ListAvailable -Name "AzureAd") {
  Write-Host "AzureAD module exists"
}
else {
  Write-Host "Installing AzureAD module";
  Install-Module -name AzureAD
}

$uniqueReplyUrls = $replyUrls | sort -Unique

#Importing AzureAd module
Write-Host "Importing AzureAD module";
Import-module AzureAD

Write-Host "Connect to Azure AD using your azure tenant admin credentials"
Connect-azureAd

$requiredResourceAccess1 = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
$requiredResourceAccess1.ResourceAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.ResourceAccess" -ArgumentList "921df259-ef26-44e6-b99e-69e13226d635","Scope"
$requiredResourceAccess1.ResourceAppId = "39624784-6cbe-4a60-afbe-9f46d10fdb27"

$requiredResourceAccess2 = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
$requiredResourceAccess2.ResourceAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.ResourceAccess" -ArgumentList "311a71cc-e848-46a1-bdf8-97ff7156d8e6","Scope"
$requiredResourceAccess2.ResourceAppId = "00000002-0000-0000-c000-000000000000"

$requiredResourceAccess = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.RequiredResourceAccess]
$requiredResourceAccess.Add($requiredResourceAccess1)
$requiredResourceAccess.Add($requiredResourceAccess2)

$azureADApplication=Get-AzureADApplication -Filter "DisplayName eq 'MACP'"

if ($azureADApplication -eq $null) {
  Write-Host "Creating Azure AD application for modern admin control panel (MACP)"
  $azureADApplication = New-AzureADApplication -DisplayName "MACP" -PublicClient $true -Oauth2AllowImplicitFlow $true -ReplyUrls $uniqueReplyUrls -RequiredResourceAccess $requiredResourceAccess
}
else {
  Write-Host "Azure ad application for modern admin control panel (MACP) already exists with displayName: " $azureADApplication.DisplayName ". Updating the properties"
  Write-Host $uniqueReplyUrls
  Set-AzureADApplication -ObjectId $azureADApplication.ObjectId -PublicClient $true -Oauth2AllowImplicitFlow $true -ReplyUrls $uniqueReplyUrls
}

Write-Host "Updating the AzureAD application Id in CMS"
Set-CsHybridConfiguration -ClientId $azureADApplication.AppId
```
