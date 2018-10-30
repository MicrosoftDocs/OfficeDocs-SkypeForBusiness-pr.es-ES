---
title: "Resumen certif.: Federación del Protocolo extensible de mensajería y presencia (XMPP)"
TOCTitle: "Résumé des certifi. - Féd. XMPP (Extensible Messaging and Presence Protocol)"
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49115311
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Federación del Protocolo extensible de mensajería y presencia (XMPP)

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de certificados para habilitar y establecer comunicaciones con socios del protocolo extensible de mensajería y presencia (XMPP) exigen el registro adicional de los dominios XMPP. El registro incluido en el certificado como nombre alternativo del firmante (SAN) será el dominio que puede participar en las comunicaciones XMPP. El dominio puede ser el dominio de nivel de raíz (por ejemplo, contoso.com) si desea habilitar XMPP para todo el dominio, o bien dominios secundarios seleccionados (por ejemplo, corp.contoso.com, finance.contoso.com) si desea habilitar XMPP para un subconjunto de usuarios.

## Resumen de certificados para el protocolo extensible de mensajería y presencia


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nombre del firmante</th>
<th>Nombres alternativos del firmante (SAN)/Orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Asignar a Servidor perimetral de acceso de Servidor perimetral o Grupo de servidores perimetrales</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Las primeras tres entradas SAN son las entradas SAN normales para un Servidor perimetral completo. contoso.com es la entrada necesaria para la federación con el socio XMPP en el nivel de dominio raíz. Esta entrada habilitará XMPP en todos los dominios que tengan el sufijo .contoso.com.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Tareas

[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Conceptos

[Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  

#### Otros recursos

[Configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

