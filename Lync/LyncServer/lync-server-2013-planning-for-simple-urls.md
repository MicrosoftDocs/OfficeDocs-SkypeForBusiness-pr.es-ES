---
title: 'Lync Server 2013: Planeación de las direcciones URL simples'
TOCTitle: Planeación de las direcciones URL simples
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48274635
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación de las direcciones URL simples en Lync Server 2013

 

_**Última modificación del tema:** 2015-12-11_

Las direcciones URL sencillas hacen que los usuarios puedan unirse a las reuniones con mayor facilidad y, al mismo tiempo, que los administradores tengan menos dificultades a la hora de conseguir las herramientas administrativas de Lync Server.

Lync Server admite tres tipos de dirección URL simples:

  - **Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Un ejemplo de dirección URL sencilla de reunión es https://meet.contoso.com, mientras que una para una reunión particular sería https://meet.contoso.com/*nombre de usuario*/7322994.
    
    Con una dirección URL sencilla de reunión, los vínculos para unirse a una reunión son fáciles de identificar, comunicar y distribuir.

  - **Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local, donde se muestran los números de acceso telefónico de conferencia con sus idiomas disponibles, información sobre las conferencias asignadas (es decir, relativa a reuniones que no es necesario programar) y controles DTMF de conferencia de acceso telefónico y donde, asimismo, es posible administrar el número de identificación personal (PIN) y la información sobre conferencias asignadas. La dirección URL sencilla de acceso telefónico aparece en todas las invitaciones a una reunión para que los usuarios que marquen para unirse a la reunión tengan acceso al número de teléfono e información de PIN relevantes. Un ejemplo de este tipo de dirección es https://dialin.contoso.com.

  - **Administración** permite tener acceso rápido al Panel de control de Lync Server. Así, un administrador puede abrir el Panel de control de Lync Server desde cualquier equipo del firewall de la organización simplemente escribiendo la dirección URL sencilla de administración en un explorador. Las direcciones URL sencillas de administración son internas de la organización. Un ejemplo de este tipo de dirección es https://admin.contoso.com.

## Ámbito de dirección URL sencilla

Las direcciones URL sencillas se pueden configurar para que tengan un ámbito global, o bien se puede especificar una distinta por cada sitio central de la organización. En caso de que se haya especificado una dirección URL sencilla y otra de sitio, esta última tendrá prioridad.

La mayor parte de las veces es recomendable definir direcciones URL sencillas únicamente en el nivel global, ya que así la dirección URL sencilla de reunión de un usuario no cambiará si se traslada de un sitio a otro. Una excepción a esto serían aquellas organizaciones que necesitan usar números de teléfono distintos para los usuarios de acceso telefónicos localizados en sitios distintos. Tenga en cuenta que, si una dirección URL sencilla (como, por ejemplo, de acceso telefónico) se establece en un sitio como dirección URL sencilla de nivel de sitio, también deberá definir el resto de direcciones URL sencillas como de nivel de sitio.

Las direcciones URL sencillas globales se definen en Generador de topologías, mientras que para definir una dirección URL sencilla en el nivel de sitio, se deberá usar el cmdlet Set-CsSimpleURLConfiguration.

## Nomenclatura de las direcciones URL sencillas

Son tres las opciones recomendadas de nomenclatura de las direcciones URL sencillas. Aquella que elija conllevará una serie de implicaciones a la hora de configurar los registros A de DNS y certificados que admiten direcciones URL sencillas. Con cada opción deberá configurar una dirección URL sencilla de reunión por cada dominio SIP existente en la organización. Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya.

Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya.

Para obtener información detallada sobre los registros A de DNS y certificados necesarios, vea [Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) y [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.

Con la opción 1, se crea un nombre de dominio SIP nuevo por cada dirección URL sencilla.

Si se decanta por esta opción, necesitará un registro A de DNS por cada dirección URL sencilla y en los certificados deberá aparecer el nombre de todas las direcciones URL sencillas de reunión.

### Opción 1 de nomenclatura de dirección URL sencilla

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Direcciones URL sencillas</strong></p></td>
<td><p><strong>Ejemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Reunión</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com, etc. (una por cada dominio SIP de la organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Administración</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Con la opción 2, las direcciones URL sencillas se basan en el nombre de dominio lync.contoso.com, de modo que solo es necesario un registro A de DNS que permita los tres tipos de dirección URL sencilla. Este registro A de DNS hace referencia a lync.contoso.com. También necesitará registros A de DNS para otros dominios SIP de la organización.

### Opción 2 de nomenclatura de dirección URL sencilla

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Direcciones URL sencillas</strong></p></td>
<td><p><strong>Ejemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Reunión</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, etc. (una por cada dominio SIP de la organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administración</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


La opción 3 es la más práctica si existen muchos dominios SIP y quiere que cada uno de ellos tenga una dirección URL sencilla de reunión pero, al mismo tiempo, desea reducir al mínimo los requisitos de registros DNS y certificados para dichas direcciones.

### Opción 3 de nomenclatura de dirección URL sencilla

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Direcciones URL sencillas</strong></p></td>
<td><p><strong>Ejemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Reunión</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administración</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


## Nomenclatura de direcciones URL sencillas y reglas de validación

Generador de topologías y los cmdlet del Shell de administración de Lync Server aplican diversas reglas de validación relativas a las direcciones URL sencillas. Las direcciones URL sencillas para reunión y acceso telefónico deben definirse obligatoriamente, si bien esto es opcional en el caso de las direcciones URL de administración. Cada dominio SIP debe tener una dirección URL sencilla de reunión particular, mientras que solo es preciso tener una dirección URL sencilla de acceso telefónico y de administración para toda la organización.

Cada dirección URL sencilla de la organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL sencilla (por ejemplo, no es posible definir lync.contoso.com/Meet como dirección URL sencilla de reunión y lync.contoso.com/Meet/Dialin como dirección URL sencilla de acceso telefónico). Los nombres de dirección URL sencilla no pueden contener el FQDN de ningún grupo de servidores, ni tampoco información sobre puertos (por ejemplo, no se admite https://FQDN:88/meet). Todas las direcciones URL sencillas deben empezar por el prefijo https://.

Las direcciones URL sencillas solo pueden contener caracteres alfanuméricos, esto es, a-z, A-Z, 0-9 y el signo de punto (.); si usa otros caracteres, podrían no funcionar del modo previsto.

## Cambiar las direcciones URL sencillas tras la implementación

Si modifica una dirección URL sencilla tras la implementación inicial, deberá tener presentes los cambios que podrían afectar a los registros DNS y certificados de dichas direcciones. Si el cambio afecta a la base de una dirección URL sencilla, deberá modificar también los certificados y registros DNS. Por ejemplo, si se cambia https://lync.contoso.com/Meet por https://meet.contoso.com, se cambia la dirección URL básica lync.contoso.com por meet.contoso.com, por lo que deberá modificar los certificados y registros DNS para hacer referencia a meet.contoso.com. Si cambia la dirección URL sencilla https://lync.contoso.com/Meet por https://lync.contoso.com/Meetings, la dirección URL básica lync.contoso.com permanece sin alterar, por lo que no será necesario cambiar el certificado ni el DNS.

Con todo, cada vez que cambie el nombre de una dirección URL sencilla, deberá ejecutar **Enable-CsComputer** en cada director y servidor front-end para dejar constancia de ello.

## Vea también

#### Conceptos

[Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

