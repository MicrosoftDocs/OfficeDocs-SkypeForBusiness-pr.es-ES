---
title: Cmdlets que usan el parámetro Tenant
TOCTitle: Cmdlets que usan el parámetro Tenant
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56271366
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets que usan el parámetro Tenant

 

_**Última modificación del tema:** 2015-06-22_

Para modificar la configuración de proveedor público debe especificarse la identidad del inquilino (incluso cuando solo hay un inquilino). Por ejemplo, este comando establece Windows Live como el único proveedor público con el que podrán comunicarse los usuarios:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Afortunadamente no tendrá que escribir el identificador de inquilino (como bf19b7db-6960-41e5-a139-2aa373474354) cada vez que ejecute uno de estos cmdlets. De hecho, si desea recuperar este dato, ejecute el cmdlet [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant), almacénelo en una variable y use la variable cuando llame a los demás cmdlets. Por ejemplo:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Si lo prefiere, puede realizar este procedimiento con un solo comando. Para ello, recupere el identificador de inquilino y canalice el valor hacia el cmdlet Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

No es necesario que especifique el identificador de inquilino para llamar al cmdlet **Get-CsTenant**, ya que este comando devuelve información sobre el inquilino:

    Get-CsTenant

Los cmdlets siguientes aceptan la identidad de inquilino. Sin embargo, en estos casos el parámetro es opcional y no es necesario escribirlo para llamar al cmdlet. En su lugar, Windows PowerShell escribirá correctamente la identidad del inquilino de Skype Empresarial Online con el que se haya establecido la conexión:

  - [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant)

  - [Set-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantFederationConfiguration)

  - [Set-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTenantHybridConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

Por ejemplo, puede llamar al cmdlet **Get-CsTenantFederationConfiguration** con este comando:

    Get-CsTenantFederationConfiguration

Aunque no es necesario, cuando llame a Get-CsTenantFederationConfiguration puede incluir el parámetro Tenant:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## Vea también

#### Conceptos

[Identidades, ámbitos e inquilinos](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

