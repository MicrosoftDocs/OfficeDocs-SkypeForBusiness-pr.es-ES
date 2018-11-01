---
title: Cmdlets exclusivamente de ámbito global
TOCTitle: Cmdlets exclusivamente de ámbito global
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56271266
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets exclusivamente de ámbito global

 

_**Última modificación del tema:** 2015-06-22_

Algunas opciones de configuración de Skype Empresarial Online solo están disponibles en el *ámbito global*. Esto significa que hay una sola colección de configuraciones que se aplica a todos los usuarios que están asignados a ese inquilino. (Cada inquilino tiene su propia colección única de configuraciones globales). Al usar cmdlets limitados al ámbito global, el parámetro Identity es opcional. Por ejemplo, para recuperar opciones de configuración de reunión, puede usar este comando:

    Get-CsMeetingConfiguration -Identity "global"

Si lo prefiere, puede omitir el parámetro Identity y usar este otro comando más simple:

    Get-CsMeetingConfiguration

Como solo hay una colección global de opciones de configuración de reunión, los dos comandos devuelven exactamente la misma información. El parámetro Identity también se puede omitir al usar uno de los cmdlets de **Set-Cs**. Estos dos comandos son idénticos:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Los dos comandos son idénticos porque, de manera predeterminada, Windows PowerShell modifica la colección global si no se incluye el parámetro Identity.

Los cmdlets siguientes solo funcionan en el ámbito global:

  - [Get-CsImFilterConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsImFilterConfiguration)

  - [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration)

  - [Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

  - [Get-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantPublicProvider)

  - [Remove-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsVoicePolicy)

  - [Set-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingConfiguration)

  - [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

Observe que el cmdlet **Remove-CsVoicePolicy** es un poco inusual. En primer lugar, no exige incluir el parámetro Identity:

    Remove-CsVoicePolicy -Identity "global"

En segundo lugar, el cmdlet **Remove-CsVoicePolicy**, en realidad, no elimina la directiva de voz global; Skype Empresarial Online no permite eliminar directivas globales ni opciones de configuración. Lo que hace el cmdlet es permitir restablecer todas las propiedades de la directiva de voz global a los valores predeterminados. Por ejemplo, la propiedad AllowCallForwarding está definida en False de manera predeterminada, pero puede haberse cambiado y tener el valor definido en True. Al ejecutar el cmdlet **Remove-CsVoicePolicy**, la propiedad AllowCallForwarding recupera su valor predeterminado: False. En la tabla siguiente se resume este escenario:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor de AllowCallForwarding</th>
<th>Escenario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>Después de modificar la directiva global</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>Después de ejecutar el cmdlet <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[Identidades, ámbitos e inquilinos](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Los cmdlets de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

