---
title: 'Resumen del certificado: detección automática'
TOCTitle: 'Resumen del certificado: detección automática'
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945616(v=OCS.15)
ms:contentKeyID: 52061597
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen del certificado: detección automática

 

_**Última modificación del tema:** 2015-03-09_

El servicio Detección automática de Lync Server 2013 se ejecuta en los servidores de los grupos de directores y front-end, y, cuando se publica en DNS, los clientes de Lync pueden usarlo para localizar servicios de usuario y de servidor. Si planea actualizar desde Lync Server 2010 y no implementó la movilidad, para que los clientes puedan usar la detección automática, debe modificar las listas de nombres alternativos del sujeto de los certificados en cualquier Director y Servidor front-end que ejecute el servicio Detección automática. Además, es posible que haya que modificar las listas de nombres alternativos del sujeto de los certificados usados para las reglas de publicación de servicios web en los servidores proxy inversos.

La decisión de usar listas de nombres alternativos del sujeto en servidores proxy inversos se basa en si se publica el servicio Detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   No es necesario modificar los certificados si la consulta inicial al servicio Detección automática se realiza en el puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 de forma externa y, a continuación, se redirigirán a un Director o un Servidor front-end en el puerto 8080 de forma interna. Para obtener información detallada, vea la sección "Proceso de detección automática inicial usando el puerto 80” en [Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publicado en el puerto 443**   La lista de nombres alternativos del sujeto de los certificados usados por la regla de publicación de servicios web externos debe contener una entrada *lyncdiscover.\<dominiosip\>* para cada dominio SIP de su organización.
    
    > [!IMPORTANT]  
    > Se recomienda encarecidamente usar HTTPS en lugar de HTTP. HTTPS usa certificados para cifrar el tráfico. HTTP no proporciona cifrado y los datos enviados serán texto sin formato.
    


La reemisión de certificados mediante una entidad de certificación interna suele ser un proceso sencillo, pero para certificados públicos usados en la regla de publicación de servicios web, puede resultar costoso agregar varias entradas de nombres alternativos del sujeto. Para solucionar este problema, se admite la conexión de detección automática inicial a través del puerto 80, que luego se redirige al puerto 8080 en el Director o el Servidor front-end.


> [!NOTE]
> Si su infraestructura de Lync Server 2013 usa certificados internos emitidos por una entidad de certificación (CA) interna y planea admitir dispositivos móviles que se conectan de forma inalámbrica, la cadena del certificado raíz de la CA interna debe instalarse en los dispositivos móviles o debe cambiar a un certificado público en la infraestructura de Lync Server 2013.



En este tema se describen los nuevos nombres alternativos del sujeto necesarios para el Director, el Servidor front-end y el proxy inverso. Solo se hace referencia a los nombres alternativos del sujeto (SAN) nuevos. Consulte las secciones sobre planeación para obtener información sobre las demás entradas de certificados. Para obtener detalles, consulte [Escenarios para el director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) y [Escenarios de proxy inverso en Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

En las siguientes tablas se definen las entradas SAN de Detección automática para el Grupo de directores, el Grupo de servidores front-end y el proxy inverso:

### Requisitos de certificado del grupo de directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servicio Detección automática interna</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;nombre de dominio interno&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>URL del servicio Detección automática externa</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;dominiosip&gt;</em></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Debe asignar el certificado recientemente actualizado con la nueva entrada SAN al certificado Default. Como alternativa, puede usar el SAN=*.<EM>&lt;dominiosip&gt;</EM>



### Requisitos de certificado del grupo de servidores front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servicio Detección automática interna</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;nombre de dominio interno&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>URL del servicio Detección automática externa</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;dominiosip&gt;</em></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Debe asignar el certificado recientemente actualizado con la nueva entrada SAN al certificado Default. Como alternativa, puede usar el SAN=*.<EM>&lt;dominiosip&gt;</EM>



### Requisitos de certificado (CA pública) del proxy inverso

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servicio Detección automática externa</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;dominiosip&gt;</em></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Debe asignar el certificado recientemente actualizado con la nueva entrada SAN a la escucha de SSL en el proxy inverso.


