---
title: "Resumen de DNS - Federación del Protocolo extensible de mensajería y presencia (XMPP)"
TOCTitle: "Résumé des enr. DNS - Féd. XMPP (Extensible Messaging and Presence Protocol)"
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49115268
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de DNS - Federación del Protocolo extensible de mensajería y presencia (XMPP)

 

_**Última modificación del tema:** 2015-03-09_

Para configurar el Protocolo extensible de presencia y mensajería (XMPP) para su implementación, puede crear dos registros de sistemas de nombre de dominio (DNS) en un servidor DNS externo que resolverá los registros al Servidor perimetral de acceso de su Servidor perimetral o Grupo de servidores perimetrales.

## Resumen del DNS para el Protocolo extensible de presencia y mensajería


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN</th>
<th>Dirección IP/registro de host FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>La interfaz externa de proxy XMPP en el Servidor perimetral de acceso o Grupo de servidores perimetrales. Repetir la cantidad de veces que sea necesario para todos los dominios SIP internos con usuarios habilitados en Lync donde el contacto con contactos de XMPP está permitido mediante la configuración de la directiva de acceso externo a través de una directiva global, directiva de sitio en la que se ubica al usuario o directiva de usuario aplicada al usuario habilitado en Lync. Un dominio de XMPP permitido también debe configurarse en la directiva de socios federados de XMPP. Consulte los temas que se encuentran en <strong>Ver también</strong> para obtener más detalles</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP de Servidor perimetral de acceso en su Servidor perimetral o Grupo de servidores perimetrales que hospede el proxy de XMPP</p></td>
<td><p>Señala el Servidor perimetral de acceso o Grupo de servidores perimetrales que hospeda el servicio de proxy de XMPP. Normalmente, el registro SRV que crea señalará a este registro (A o AAAA) de host</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Tareas

[Configurar la federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  

#### Conceptos

[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

