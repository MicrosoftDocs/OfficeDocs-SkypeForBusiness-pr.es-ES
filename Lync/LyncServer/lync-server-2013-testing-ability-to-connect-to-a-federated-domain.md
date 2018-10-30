﻿---
title: 'Lync Server 2013: Testing ability to connect to a federated domain'
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn743840(v=OCS.15)
ms:contentKeyID: 62279350
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testing ability to connect to a federated domain from Lync Server 2013

 

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
<p>When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet. To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


## Description

Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner. To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains. You can retrieve a list of the domains on your allowed domains list by using this command:

    Get-CsAllowedDomain

For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner) cmdlet.

## Running the test

The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner. For example, this command tests the ability to connect to the domain contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

This command enables you to test the connections to all the domains currently on your allowed domains list:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner) cmdlet.

## Determining success or failure

If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**

TargetFqdn : atl-cs-001.litwareinc.com

Result : Success

Latency : 00:00:00

Error :

Diagnosis :

If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:

TargetFqdn : atl-cs-001.litwareinc.com

Result : Failure

Latency : 00:00:00

Error : 504, Server time-out

Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See

response code and reason phrase.

Microsoft.Rtc.Signaling.DiagnosticHeader

For example, the previous output states that the test failed because of a server time-out error. This typically indicates either network connectivity problems or problems contacting the Edge Server.

If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

## Reasons why the test might have failed

Here are some common reasons why Test-CsFederatedPartner might fail:

  - The Edge Server might not be available. You can the FQDNs of your Edge Servers by using this command:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    You can then ping each Edge Server to verify that it can be accessed over the network. For example:
    
        ping atl-edge-001.litwareinc.com

  - The specified domain might not be listed on the allowed domains list. To verify the domains that were added to the allowed domains list, use this command:
    
        Get-CsAllowedDomain
    
    If you’d like to see a list of domains that users were blocked from communicating with, then use this command:
    
        Get-CsBlockedDomain

