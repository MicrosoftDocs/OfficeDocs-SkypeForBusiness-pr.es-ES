---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9871d16c3e5b0af894653ac5d60c4614201e8e24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Después de combinar la topología y ejecutar el cmdlet **Import-CsLegacyConfiguration** , compruebe que la configuración y las directivas de Office Communications Server 2007 R2 se han importado a Lync Server 2013. En la siguiente tabla se enumeran las directivas y la configuración que debería comprobar.

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
<th>Compruebe estas directivas y configuración:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mensajería instantánea (MI) y conferencia</p></td>
<td><p>Directiva de presencia</p>
<p>Directiva de conferencia</p></td>
</tr>
<tr class="even">
<td><p>Conferencia de acceso telefónico local</p></td>
<td><p>Números de acceso telefónico</p>
<p>Planes de marcado</p></td>
</tr>
<tr class="odd">
<td><p>Telefonía IP empresarial</p></td>
<td><p>Directiva de voz</p>
<p>Rutas de voz</p>
<p>Planes de marcado</p>
<p>Configuración de uso RTC</p></td>
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

## <a name="to-verify-policies-and-settings"></a>Para comprobar directivas y configuración

1.  En el entorno de Office Communications Server 2007 R2, tome nota de los nombres de los planes de marcado (antes conocidos como perfiles de ubicación), los números de acceso telefónico (regiones y números de teléfono de acceso del operador de conferencia), las rutas de voz y las directivas que aparecen en la lista tabla anterior, además de las direcciones URL que se usan para Communicator Web Access.

2.  En el servidor front-end de Lync Server 2013, abra el panel de control de Lync Server.

3.  Para comprobar las directivas de conferencia importadas, en el panel izquierdo, haga clic en **Conferencia**, en **Directiva de conferencia**y, a continuación, compruebe que todas las directivas de conferencia del entorno de Office Communications Server 2007 R2 están incluidas en la lista.
    
    <div>
    

    > [!NOTE]  
    > La Directiva de <STRONG>reunión</STRONG> de las versiones anteriores de Office Communications Server ahora se conoce como la Directiva de conferencia en Lync Server 2013. Además, la configuración de <STRONG>Particpants anónima</STRONG> de versiones anteriores de Office Communications Server es ahora una configuración de la Directiva de conferencia de Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > En Office Communications Server 2007 R2, si la Directiva de conferencia no está configurada para <STRONG>usarse por usuario</STRONG>, solo se importa la configuración de directiva global. No se importa ninguna otra directivas de conferencia en esta situación.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si <STRONG>participantes anónimos</STRONG> se establece en <STRONG>exigir por usuario</STRONG> en la Directiva de conferencia de Office Communications Server 2007 R2, durante la migración se crean dos directivas de Conferencia: una con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecida en <STRONG>true</STRONG> y otra con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecido en <STRONG>false</STRONG>.

    
    </div>

4.  Para comprobar los planes de marcado importados, haga clic en **Enrutamiento de voz  **, en **Plan de marcado** y, a continuación, compruebe que todos los planes de marcado de su entorno de Office Communicator 2007 R2 están incluidos en la lista.
    
    <div>
    

    > [!NOTE]  
    > En Lync Server 2013, los <STRONG>perfiles de ubicación</STRONG> se denominan ahora <STRONG>planes de marcado</STRONG>.

    
    </div>

5.  Para comprobar las directivas de voz importadas, haga clic en **Enrutamiento de voz**, haga clic en **Directiva de voz** y, a continuación, compruebe que todas las directivas de voz de su entorno de Office Communicator 2007 R2 están incluidas en la lista.
    
    <div>
    

    > [!NOTE]  
    > Si la Directiva de voz no está configurada para <STRONG>usarse por usuario</STRONG> en el entorno de Office Communications Server 2007 R2, solo se importa la configuración de directiva global. No se importará ninguna otra directiva de voz en esta situación.

    
    </div>

6.  Para comprobar las rutas de voz importadas, haga clic en **Enrutamiento de voz**, en **Ruta  **y, a continuación, compruebe que todas las rutas de voz de su entorno de Office Communicator 2007 R2 están incluidas en la lista.

7.  Para comprobar la configuración del uso de RTC importado, haga clic en **Enrutamiento de voz**, en **Uso de RTC** y, a continuación, compruebe que la configuración del uso de RTC de su entorno de Office Communicator 2007 R2 está incluida en la lista.

8.  Para comprobar las directivas de acceso externo importado, haga clic en **Federación y acceso externo**, haga clic en **Directiva de acceso externo** y, a continuación, compruebe que todas las directivas de acceso externo de su entorno de Office Communicator 2007 R2 están incluidas en la lista.

9.  Para comprobar las directivas de archivado, haga clic en **supervisión y archivado**, haga clic en **Directiva de archivado**y, a continuación, compruebe que todas las directivas de archivado del entorno de Office Communications Server 2007 R2 están incluidas en la lista.

10. Abra el Shell de administración de Lync Server.

11. Para comprobar las directivas de presencia, en la línea de comandos, escriba lo siguiente:
    
        Get-CsPresencePolicy
    
    Si observa el nombre en el parámetro **Identity** , compruebe que se han importado todas las directivas de presencia en el entorno de Office Communications Server 2007 R2.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Para comprobar las directivas y la configuración mediante el uso de cmdlets

1.  Abra el Shell de administración de Lync Server.

2.  Ejecute los cmdlets en la tabla siguiente para comprobar las directivas y configuración.
    
    La sintaxis de estos cmdlets es similar al siguiente ejemplo:
    
        Get-CsConferencingPolicy
    
    Para más información sobre estos cmdlets, ejecute:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para esta directiva o configuración:</th>
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
<td><p>Números de acceso telefónico</p></td>
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

