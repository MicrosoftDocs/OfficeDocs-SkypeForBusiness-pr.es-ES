---
title: 'Lync Server 2013: Planeación de direcciones URL sencillas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36e730aeef637c12102fbf425c04235d72eb382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planeación de direcciones URL sencillas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-12-11_

Las direcciones URL sencillas facilitan la Unión de reuniones a los usuarios y facilitan la obtención de herramientas administrativas de Lync Server para los administradores.

Lync Server admite tres direcciones URL sencillas:

  - **Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Un ejemplo de una dirección URL sencilla de https://meet.contoso.comreunión es. Una dirección URL de una reunión concreta podría https://meet.contoso.com/ser *nombre de usuario*/7322994.
    
    Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir.

  - **Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. Esta página muestra los números de acceso telefónico de conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no necesitan programarse) y los controles de DTMF en conferencia, y admite la administración del número de identificación personal ( PIN) y la información de conferencia asignada. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios. Un ejemplo de la dirección URL sencilla de acceso telefónico https://dialin.contoso.comes.

  - El **Administrador** habilita el acceso rápido al panel de control de Lync Server. Desde cualquier equipo de los firewalls de su organización, un administrador puede abrir el panel de control de Lync Server escribiendo la dirección URL sencilla de administración en un explorador. La dirección URL simple de administración es de uso interno para la organización. Un ejemplo de la dirección URL sencilla de administración eshttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Ámbito de dirección URL sencilla

Las direcciones URL sencillas se pueden configurar para que tengan un ámbito global, o bien se puede especificar una distinta por cada sitio central de la organización. Si se especifican una dirección URL sencilla de ámbito global y una dirección URL sencilla de ámbito de sitio, la dirección URL sencilla de ámbito del sitio tiene prioridad.

La mayor parte de las veces es recomendable definir direcciones URL sencillas únicamente en el nivel global, ya que así la dirección URL sencilla de reunión de un usuario no cambiará si se traslada de un sitio a otro. Una excepción a esto serían aquellas organizaciones que necesitan usar números de teléfono distintos para los usuarios de acceso telefónicos localizados en sitios distintos. Tenga en cuenta que, si una dirección URL sencilla (como, por ejemplo, de acceso telefónico) se establece en un sitio como dirección URL sencilla de nivel de sitio, también deberá definir el resto de direcciones URL sencillas como de nivel de sitio.

<div>


> [!NOTE]  
> Si decide usar direcciones URL sencillas con ámbito de sitio, los usuarios no podrán moverse entre los grupos de servidores front-end de sitios diferentes sin que los usuarios vuelvan a programar todas sus reuniones programadas, ya que las direcciones URL sencillas de reunión son diferentes entre los sitios. Esto incluye escenarios de conmutación por error en los que los grupos de servidores de las relaciones de copia de seguridad se encuentran en sitios independientes. Cuando necesite conmutar por error entre sitios en los que se implementen direcciones URL sencillas en el ámbito del sitio, los usuarios no podrán unirse a sus reuniones debido al ámbito de la dirección URL. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Puede establecer direcciones URL simples globales en el generador de topologías. Para establecer una dirección URL sencilla en el nivel de sitio, debe usar el cmdlet Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Nomenclatura de las direcciones URL sencillas

Son tres las opciones recomendadas de nomenclatura de las direcciones URL sencillas. Aquella que elija conllevará una serie de implicaciones a la hora de configurar los registros A de DNS y certificados que admiten direcciones URL sencillas. Con cada opción deberá configurar una dirección URL sencilla de reunión por cada dominio SIP existente en la organización. Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya.

Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya.

Para obtener más información sobre los certificados y registros A de DNS necesarios, consulte [requisitos de DNS para direcciones URL sencillas en Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) y [requisitos de certificado para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.

Con la opción 1, se crea un nombre de dominio SIP nuevo por cada dirección URL sencilla.

Si se decanta por esta opción, necesitará un registro A de DNS por cada dirección URL sencilla y en los certificados deberá aparecer el nombre de todas las direcciones URL sencillas de reunión.

### <a name="simple-url-naming-option-1"></a>Opción 1 de nomenclatura de dirección URL sencilla

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
<td><p>Cumplir</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.comy así sucesivamente (uno para cada dominio SIP de la organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Administración</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Con la opción 2, las direcciones URL sencillas se basan en el nombre de dominio lync.contoso.com, de modo que solo es necesario un registro A de DNS que permita los tres tipos de dirección URL sencilla. Este registro A de DNS hace referencia a lync.contoso.com. También necesitará registros A de DNS para otros dominios SIP de la organización.

### <a name="simple-url-naming-option-2"></a>Opción 2 de nomenclatura de dirección URL sencilla

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
<td><p>Cumplir</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meety así sucesivamente (uno para cada dominio SIP de la organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administración</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


La opción 3 es la más práctica si existen muchos dominios SIP y quiere que cada uno de ellos tenga una dirección URL sencilla de reunión pero, al mismo tiempo, desea reducir al mínimo los requisitos de registros DNS y certificados para dichas direcciones.

### <a name="simple-url-naming-option-3"></a>Opción 3 de nomenclatura de dirección URL sencilla

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
<td><p>Cumplir</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administración</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Nomenclatura de direcciones URL sencillas y reglas de validación

El generador de topologías y los cmdlets del shell de administración de Lync Server exigen varias reglas de validación para las direcciones URL simples. Las direcciones URL sencillas para reunión y acceso telefónico deben definirse obligatoriamente, si bien esto es opcional en el caso de las direcciones URL de administración. Cada dominio SIP debe tener una dirección URL sencilla de reunión particular, mientras que solo es preciso tener una dirección URL sencilla de acceso telefónico y de administración para toda la organización.

Cada dirección URL sencilla de la organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL sencilla (por ejemplo, no es posible definir lync.contoso.com/Meet como dirección URL sencilla de reunión y lync.contoso.com/Meet/Dialin como dirección URL sencilla de acceso telefónico). Los nombres de dirección URL simple no pueden contener el FQDN de ninguno de sus grupos o cualquier información de puerto https://FQDN:88/meet (por ejemplo, no está permitido). Todas las direcciones URL sencillas deben empezar por el prefijo https://.

Las direcciones URL sencillas solo pueden contener caracteres alfanuméricos, esto es, a-z, A-Z, 0-9 y el signo de punto (.); si usa otros caracteres, podrían no funcionar del modo previsto.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Cambiar las direcciones URL sencillas tras la implementación

Si modifica una dirección URL sencilla tras la implementación inicial, deberá tener presentes los cambios que podrían afectar a los registros DNS y certificados de dichas direcciones. Si el cambio afecta a la base de una dirección URL sencilla, deberá modificar también los certificados y registros DNS. Por ejemplo, si se https://lync.contoso.com/Meet cambia https://meet.contoso.com de para cambia la dirección URL base de Lync.contoso.com a meet.contoso.com, es necesario cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com. Si ha cambiado la dirección URL sencilla https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingsa, la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario ningún cambio de certificado o DNS.

Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar **enable-CsComputer** en cada director y en el servidor front-end para registrar el cambio.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de DNS para direcciones URL sencillas en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

