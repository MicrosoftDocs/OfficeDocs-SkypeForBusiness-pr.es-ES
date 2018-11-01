---
title: 'Lync Server 2013: Check trunk configuration against a phone number'
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn725206(v=OCS.15)
ms:contentKeyID: 62335999
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Check trunk configuration against a phone number in Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Verification schedule</p></td>
<td><p>Monthly</p></td>
</tr>
<tr class="even">
<td><p>Testing tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissions required</p></td>
<td><p>When run locally using the Shell de administración de Lync Server, users must be members of the RTCUniversalServerAdmins security group.</p>
<p>When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet. To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


## Description

SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:

  - The Public Switched Telephone network (PSTN).

  - An IP-public branch exchange (PBX).

  - A Session Border Controller (SBC).

The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.

## Running the test

To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work. For example, this command will fail without returning any data:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.

## Determining success or failure

If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 Global/Redmond

If the test fails, Test-CsTrunkConfiguration will return empty property values:

TranslatedNumber MatchingRule

\---------------- ------------

## Reasons why the test might have failed

If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format. To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

That returns information similar to this for each translation rule:

Description : Phone numbers without a country code or area code.

Pattern : ^\\+(\\d\*)$

`Translation : $1`

Name : NoAreaCode

At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number. If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.

## Vea también

#### Otros recursos

[Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration)

