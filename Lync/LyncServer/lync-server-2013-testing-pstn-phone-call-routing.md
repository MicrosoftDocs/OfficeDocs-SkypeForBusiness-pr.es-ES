---
title: 'Lync Server 2013: Testing PSTN phone call routing'
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn727302(v=OCS.15)
ms:contentKeyID: 62388664
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testing PSTN phone call routing in Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Verification schedule</p></td>
<td><p>Daily</p></td>
</tr>
<tr class="even">
<td><p>Testing tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissions required</p></td>
<td><p>When run locally using the Shell de administración de Lync Server, users must be members of the RTCUniversalServerAdmins security group.</p>
<p>When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet. To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


## Description

The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another. To do this, the cmdlet is given a phone number and a trunk configuration. **Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number. Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.

## Running the test

The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

## Determining success or failure

If calls can be routed from one SIP to another, you'll receive output similar to this:

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

If the test did not succeed, you'll receive output similar to this:

Test-CsInterTrunkRouting : Cannot process argument transformation on parameter

'TrunkConfiguration'. Invalid TrunkConfigurationsetting (parameter). Specify a

valid setting (parameter) and then try again.

At line:1 char:79

\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"

\-TrunkConfiguration $t ...

\+

~~

\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par

ameterBindingArgumentTransformationException

\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R

tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet

## Reasons why the test might have failed

Here are some common reasons why **Test-CsInterTrunkRouting** might fail:

  - You specified invalid parameters. The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.

## Vea también

#### Otros recursos

[Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration)

