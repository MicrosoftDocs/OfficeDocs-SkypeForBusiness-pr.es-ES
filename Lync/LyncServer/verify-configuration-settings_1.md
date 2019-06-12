---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Después de combinar la topología y ejecutar el cmdlet **Import-CsLegacyConfiguration** , compruebe que las directivas y la configuración de Office Communications Server 2007 R2 se han importado a Lync Server 2013. En la tabla siguiente se enumeran las directivas y la configuración que debe comprobar.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Directivas y configuración para comprobar después de la migración


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si usa esta carga de trabajo:</th>
<th>Compruebe estas directivas y la configuración:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mensajería instantánea (mi) y Conferencia</p></td>
<td><p>Directiva de presencia</p>
<p>Directiva de conferencia</p></td>
</tr>
<tr class="even">
<td><p>Conferencia de acceso telefónico local</p></td>
<td><p>Números de acceso telefónico local</p>
<p>Planes de marcado</p></td>
</tr>
<tr class="odd">
<td><p>Telefonía IP empresarial</p></td>
<td><p>Directiva de voz</p>
<p>Rutas de voz</p>
<p>Planes de marcado</p>
<p>Configuración de uso de RTC</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>Direcciones URL simples</p></td>
</tr>
<tr class="odd">
<td><p>Usuarios externos</p></td>
<td><p>Directivas de acceso externo</p></td>
</tr>
<tr class="even">
<td><p>Archivado</p></td>
<td><p>Directiva de archivado</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Para comprobar las directivas y la configuración

1.  En el entorno de Office Communications Server 2007 R2, tome nota de los nombres de los planes de marcado (anteriormente conocidos como perfiles de ubicación), números de acceso telefónico local (números de teléfono y regiones de acceso al operador de conferencias), rutas de voz y las directivas que aparecen en la lista tabla anterior, además de las direcciones URL que se usan para Communicator Web Access.

2.  En el servidor front-end de Lync Server 2013, abra el panel de control de Lync Server.

3.  Para comprobar las directivas de conferencia importadas, en el panel izquierdo, haga clic en **conferencias**, en **Directiva de conferencia**y, a continuación, compruebe que todas las directivas de conferencia del entorno de Office Communications Server 2007 R2 están incluidas en la lista.
    
    <div>
    

    > [!NOTE]  
    > La Directiva de <STRONG>reunión</STRONG> de las versiones anteriores de Office Communications Server ahora se conoce como la Directiva de conferencia en Lync Server 2013. Además, la configuración <STRONG>Particpants anónima</STRONG> de versiones anteriores de Office Communications Server es ahora una configuración de la Directiva de conferencia de Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > En Office Communications Server 2007 R2, si la Directiva de conferencia no está configurada para <STRONG>usarse por usuario</STRONG>, solo se importa la configuración de directiva global. En esta situación no se importa ninguna otra política de conferencia.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si los <STRONG>participantes anónimos</STRONG> están configurados para exigir el <STRONG>cumplimiento de cada usuario</STRONG> en su Directiva de conferencia de Office Communications Server 2007 R2, durante la migración se crean dos directivas de Conferencia: una con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecido en <STRONG>True</STRONG> y otro con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecido en <STRONG>false</STRONG>.

    
    </div>

4.  Para comprobar los planes de marcado importados, haga clic en **enrutamiento de voz**, haga clic en **plan de marcado**y compruebe que todos los planes de marcado en el entorno de Office Communicator 2007 R2 están incluidos en la lista.
    
    <div>
    

    > [!NOTE]  
    > En Lync Server 2013, los <STRONG>perfiles de ubicación</STRONG> se conocen ahora como <STRONG>planes de marcado</STRONG>.

    
    </div>

5.  Para comprobar las directivas de voz importadas, haga clic en **enrutamiento de voz**, en **Directiva de voz**y, a continuación, compruebe que todas las directivas de voz del entorno de Office Communicator 2007 R2 están incluidas en la lista.
    
    <div>
    

    > [!NOTE]  
    > Si la Directiva de voz no está configurada para <STRONG>usarse por usuario</STRONG> en el entorno de Office Communications Server 2007 R2, solo se importan las opciones de directiva global. No se importa ninguna otra política de voz en esta situación.

    
    </div>

6.  Para comprobar las rutas de voz importadas, haga clic en **enrutamiento de voz**, en **ruta**y, a continuación, compruebe que todas las rutas de voz de su entorno de Office Communicator 2007 R2 están incluidas en la lista.

7.  Para comprobar la configuración de uso de RTC importada, haga clic en **enrutamiento de voz**, haga clic en **uso de RTC**y compruebe que la configuración de uso de RTC del entorno de Office Communicator 2007 R2 esté incluida en la lista.

8.  Para comprobar las directivas de acceso externo importadas, haga clic en **Federación y acceso externo**, haga clic en **Directiva de acceso externo**y compruebe que todas las directivas de acceso externas de su entorno de Office Communicator 2007 R2 están incluidas en la lista.

9.  Para comprobar las directivas de archivado, haga clic en **supervisión y archivado**, haga clic en **Directiva**de archivado y compruebe que todas las directivas de archivado del entorno de Office Communications Server 2007 R2 están incluidas en la lista.

10. Abra el shell de administración de Lync Server.

11. Para comprobar las directivas de presencia, en la línea de comandos, escriba lo siguiente:
    
        Get-CsPresencePolicy
    
    Al mirar el nombre en el parámetro **Identity** , compruebe que se han importado todas las directivas de presencia en el entorno de Office Communications Server 2007 R2.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Para comprobar las directivas y la configuración mediante cmdlets

1.  Abra el shell de administración de Lync Server.

2.  Ejecute los cmdlets de la tabla siguiente para comprobar las directivas y la configuración.
    
    La sintaxis de estos cmdlets es como en el ejemplo siguiente:
    
        Get-CsConferencingPolicy
    
    Para obtener más información sobre estos cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para esta Directiva o configuración:</th>
<th>Use este cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva de presencia</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Directiva de conferencia</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>Números de acceso telefónico local</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Planes de marcado</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>Directiva de voz</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Rutas de voz</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>Uso de RTC</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>Direcciones URL</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>Directivas de acceso externo</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Directiva de archivado</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

