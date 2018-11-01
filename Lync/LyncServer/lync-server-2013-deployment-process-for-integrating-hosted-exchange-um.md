---
title: "Implementación para la integración de la mensajería unificada de Exchange hospedada"
TOCTitle: Proceso de implementación para la integración de la mensajería unificada de Exchange hospedada con Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48276874
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de implementación para la integración de la mensajería unificada de Exchange hospedada con Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Una planeación eficaz para integrar Lync Server 2013 con la mensajería unificada hospedada de Exchange requiere que se tengan en cuenta:

  - Los requisitos previos para integrar Lync Server 2013 con la mensajería unificada hospedada de Exchange

  - Los pasos necesarios durante el proceso de integración

## Requisitos previos de implementación para la integración con la mensajería unificada hospedada de Exchange

Antes de iniciar el proceso de integración, tiene que haber implementado Lync Server 2013 (como mínimo, un grupo de servidores front-end o un servidor Standard Edition), un servidor perimetral y clientes de Lync 2013 o Lync 2010.

## Proceso de integración

En la tabla siguiente se proporciona información general del proceso de integración de mensajería unificada hospedada de Exchange. Para más información sobre los pasos de implementación, vea [Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) en la documentación de implementación.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Derechos y permisos</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurar el servidor perimetral.</p></td>
<td><ol>
<li><p>Configure el servidor perimetral para la federación.</p></li>
<li><p>Replique manualmente los datos al servidor perimetral.</p></li>
<li><p>Configure el proveedor de hospedaje en el servidor perimetral.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar el servidor perimetral para la integración con la mensajería unificada de Exchange hospedada</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar la directiva de correo de voz hospedado.</p></td>
<td><ol>
<li><p>Modifique la directiva global de correo de voz hospedado o cree una directiva de correo de voz hospedado con ámbito de sitio o por usuario.</p></li>
<li><p>Para las directivas con ámbito por usuario, asigne la directiva a usuarios o grupos.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Administrar directivas de correo de voz hospedado en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilitar a los usuarios para correo de voz hospedado.</p></td>
<td><ul>
<li><p>Configure cuentas de usuario para los usuarios cuyos buzones de correo se encuentren en un servicio de Exchange hospedado.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar objetos de contacto hospedados.</p></td>
<td><ol>
<li><p>Cree objetos de contacto de operador automático para la mensajería unificada hospedada de Exchange.</p></li>
<li><p>Cree objetos de contacto de acceso de suscriptor para la mensajería unificada hospedada de Exchange.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]
> Para crear, modificar o quitar objetos de contacto, el usuario que ejecuta el cmdlet New-CsExUmContact, Set-CsExUmContact o Remove-CsExUmContact debe tener el permiso correcto para la unidad organizativa de Active Directory donde están almacenados los nuevos objetos de contacto. Este permiso se obtiene si se ejecuta el cmdlet Grant-CsOUPermission. Para más información, vea la documentación del Shell de administración de Lync Server.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

