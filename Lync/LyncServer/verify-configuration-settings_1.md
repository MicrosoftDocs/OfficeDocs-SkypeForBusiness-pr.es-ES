---
title: Comprobar los valores de configuración
TOCTitle: Comprobar los valores de configuración
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48275039
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar los valores de configuración

 

_**Última modificación del tema:** 2015-03-09_

Una vez que haya combinado la topología y ejecutado el cmdlet **Import-CsLegacyConfiguration**, compruebe que la configuración y las directivas de Office Communications Server 2007 R2 se han importado en Lync Server 2013. En la siguiente tabla se enumeran las directivas y la configuración que debería comprobar.

## Directivas y configuración para comprobar después de la migración


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


## Para comprobar directivas y configuración

1.  En su entorno de Office Communications Server 2007 R2, anote los nombres de los planes de marcado (anteriormente conocidos como perfiles de ubicación), los números de acceso telefónico de marcado (regiones y números de teléfono de acceso de operador de conferencias), las rutas de voz y las directivas enumeradas en la tabla anterior, además las direcciones URL usadas para Communicator Web Access.

2.  En el servidor front-end de Lync Server 2013, abra Panel de control de Lync Server.

3.  Para comprobar las directivas de conferencia importadas, en el panel izquierdo, haga clic en **Conferencia**, en **Directiva de conferencia** y, a continuación, compruebe que todas las directivas de conferencia de su entorno de Office Communications Server 2007 R2 se incluyen en la lista.
    

    > [!NOTE]
    > La directiva <STRONG>Reunión</STRONG> de las versiones anteriores de Office Communications Server se conoce ahora como la directiva de conferencia en Lync Server 2013. Además, la configuración <STRONG>Participantes anónimos</STRONG> de las versiones anteriores de Office Communications Server es ahora una configuración en la directiva de conferencia de Lync Server 2013.

    

    > [!NOTE]
    > En Office Communications Server 2007 R2, si la directiva de conferencia no se establece en el <STRONG>uso por usuario</STRONG>, solo se importa la configuración de la directiva global. No se importa ninguna otra directivas de conferencia en esta situación.

    

    > [!NOTE]
    > Si <STRONG>Participantes anónimos</STRONG> se establece en <STRONG>Aplicar por usuario</STRONG> en su directiva de conferencia Office Communications Server 2007 R2, se crean dos directivas de conferencia durante la migración: una con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecida en <STRONG>True</STRONG> y otra con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> establecida en <STRONG>False</STRONG>.



4.  Para comprobar los planes de marcado importados, haga clic en **Enrutamiento de voz**, en **Plan de marcado** y, a continuación, compruebe que todos los planes de marcado de su entorno de Office Communicator 2007 R2 están incluidos en la lista.
    

    > [!NOTE]
    > En Lync Server 2013, los <STRONG>perfiles de ubicación</STRONG> se denominan ahora <STRONG>planes de marcado</STRONG>.



5.  Para comprobar las directivas de voz importadas, haga clic en **Enrutamiento de voz**, haga clic en **Directiva de voz** y, a continuación, compruebe que todas las directivas de voz de su entorno de Office Communicator 2007 R2 están incluidas en la lista.
    

    > [!NOTE]
    > Si la directiva de voz no está establecida en el <STRONG>uso por usuario</STRONG> en su entorno de Office Communications Server 2007 R2, solo se importará la configuración de la directiva global. No se importará ninguna otra directiva de voz en esta situación.



6.  Para comprobar las rutas de voz importadas, haga clic en **Enrutamiento de voz**, en **Ruta**y, a continuación, compruebe que todas las rutas de voz de su entorno de Office Communicator 2007 R2 están incluidas en la lista.

7.  Para comprobar la configuración del uso de RTC importado, haga clic en **Enrutamiento de voz**, en **Uso de RTC** y, a continuación, compruebe que la configuración del uso de RTC de su entorno de Office Communicator 2007 R2 está incluida en la lista.

8.  Para comprobar las directivas de acceso externo importado, haga clic en **Federación y acceso externo**, haga clic en **Directiva de acceso externo** y, a continuación, compruebe que todas las directivas de acceso externo de su entorno de Office Communicator 2007 R2 están incluidas en la lista.

9.  Para comprobar las directivas de archivado, haga clic en **Supervisión y archivado**, en **Directiva de archivado** y, a continuación, compruebe que todas las directivas de archivado en su entorno de Office Communications Server 2007 R2 se incluyen en la lista.

10. Abra Shell de administración de Lync Server.

11. Para comprobar las directivas de presencia, en la línea de comandos, escriba lo siguiente:
    
        Get-CsPresencePolicy
    
    Mirando el nombre del parámetro **Identidad**, compruebe que se han importado todas las directivas de presencia de su entorno de Office Communications Server 2007 R2.

## Para comprobar las directivas y la configuración mediante el uso de cmdlets

1.  Abra Shell de administración de Lync Server.

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

