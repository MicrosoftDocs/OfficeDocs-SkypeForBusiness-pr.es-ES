---
title: 'Lync Server 2013: Planeación de las direcciones URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17dbfce9f699f31e09bb66d6d596e0a3cbf0ba96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planeación de las direcciones URL simples en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-12-11_

Las direcciones URL simples facilitan la Unión a las reuniones para los usuarios y hacen que los administradores faciliten las herramientas administrativas de Lync Server.

Lync Server admite tres direcciones URL simples:

  - **Reunirse** se usa como la dirección URL base para todas las conferencias del sitio o la organización. Un ejemplo de una dirección URL simple de https://meet.contoso.comreunirse es. Una dirección URL de una reunión determinada puede https://meet.contoso.com/ser *username*/7322994.
    
    Con la dirección URL simple, los vínculos a las reuniones de unirse son fáciles de comprender y se pueden comunicar y distribuir fácilmente.

  - El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencias de acceso telefónico local. Esta página muestra los números de acceso telefónico de la Conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no es necesario programar) y los controles de DTMF de la Conferencia, y admite la administración del número de identificación personal ( PIN) y la información de conferencia asignada. La dirección URL de acceso telefónico simple está incluida en todas las invitaciones a reuniones para que los usuarios que deseen llamar a la reunión puedan tener acceso a la información del número de teléfono y del PIN necesarios. Un ejemplo de la dirección URL simple de acceso telefónico https://dialin.contoso.comes.

  - El **Administrador** permite acceder rápidamente al panel de control de Lync Server. Desde cualquier equipo de los servidores de seguridad de su organización, un administrador puede abrir el panel de control de Lync Server escribiendo la dirección URL simple de administrador en un explorador. La dirección URL simple de administración es interna de su organización. Un ejemplo de la dirección URL simple de administración eshttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Ámbito de dirección URL simple

Puede configurar las direcciones URL simples para que tengan ámbito global o puede especificar direcciones URL simples diferentes para cada sitio central de su organización. Si se especifican una dirección URL simple de ámbito global y una dirección URL simple de ámbito de sitio, la dirección URL simple de ámbito del sitio tiene prioridad.

En la mayoría de los casos, se recomienda establecer direcciones URL simples solo en el nivel global, de modo que la dirección URL simple de un usuario no cambie si se mueve de un sitio a otro. La excepción serían organizaciones que necesitan usar números de teléfono diferentes para los usuarios de acceso telefónico local en diferentes sitios. Tenga en cuenta que si establece una dirección URL simple (como la dirección URL de acceso telefónico simple) en un sitio para que sea una dirección URL simple de nivel de sitio, también debe establecer las otras direcciones URL simples en ese sitio para que también sean del nivel del sitio.

<div>


> [!NOTE]  
> Si elige usar direcciones URL simples en el ámbito del sitio, los usuarios no podrán pasar de un grupo de servidores front-end a otro diferente sin que esos usuarios reprogramen todas las reuniones programadas porque las direcciones URL simples difieren entre los sitios. Esto incluye escenarios de conmutación por error en los que los grupos de las relaciones de copia de seguridad están en sitios independientes. Si necesita conmutación por error entre los sitios donde se implementan direcciones URL simples en el ámbito del sitio, los usuarios no podrán unirse a sus reuniones debido al ámbito de la dirección URL. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Puede establecer direcciones URL globales simples en el generador de topología. Para establecer una dirección URL simple en el nivel del sitio, debe usar el cmdlet Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Asignar un nombre a las direcciones URL simples

Hay tres opciones recomendadas para asignar nombres a las direcciones URL simples. La opción que elija tiene implicaciones en cuanto a la configuración de los registros A de DNS y los certificados que admiten direcciones URL simples. En cada opción, debe configurar una dirección URL simple para cada dominio SIP de su organización.

Siempre necesita una única dirección URL en toda la organización para el acceso telefónico y otra para el administrador, independientemente del número de dominios SIP que tenga.

Para obtener más información sobre los certificados y los registros de DNS necesarios, consulte [requisitos de DNS para direcciones URL simples en Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) y [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.

En la opción 1, puede crear un nuevo nombre de dominio SIP para cada dirección URL simple.

Si usa esta opción, necesita un registro DNS (A) independiente para cada dirección URL simple, y cada reunión dirección URL simple debe tener un nombre en los certificados.

### <a name="simple-url-naming-option-1"></a>Opción de nomenclatura de URL simple 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Dirección URL sencilla</strong></p></td>
<td><p><strong>Ejemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Reunión</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com, y así sucesivamente (uno para cada dominio SIP de su organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Con la opción 2, las direcciones URL simples se basan en el nombre de dominio lync.contoso.com. Por lo tanto, solo necesita un registro DNS para habilitar los tres tipos de direcciones URL simples. Este registro A DNS hace referencia a lync.contoso.com. Además, aún necesitará un registro DNS A para otros dominios SIP de su organización.

### <a name="simple-url-naming-option-2"></a>Opción de nomenclatura de URL simple 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Dirección URL sencilla</strong></p></td>
<td><p><strong>Ejemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Reunión</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, y así sucesivamente (uno para cada dominio SIP de su organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


La opción 3 es más útil si tiene muchos dominios SIP y desea que tengan diferentes direcciones URL simples, pero quiere minimizar los requisitos de certificados y registros DNS para estas direcciones URL simples.

### <a name="simple-url-naming-option-3"></a>Opción de nomenclatura de URL simple 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Dirección URL sencilla</strong></p></td>
<td><p><strong>Ejemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Reunión</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Nomenclatura de URL simple y reglas de validación

El generador de topología y los cmdlets del shell de administración de Lync Server exigen varias reglas de validación para las direcciones URL simples. Debe establecer direcciones URL simples para reunirse y llamar, pero establecer una para administrador es opcional. Cada dominio SIP debe tener una dirección URL simple de reunirse, pero solo se necesita una dirección URL simple de marcación y una dirección URL simple de administración para toda la organización.

Cada dirección URL simple de su organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL simple (por ejemplo, no puede establecer lync.contoso.com/Meet como su dirección URL simple y lync.contoso.com/Meet/Dialin como la dirección URL simple de marcado). Los nombres de direcciones URL simples no pueden contener el FQDN de ninguna de sus agrupaciones ni ninguna información de https://FQDN:88/meet puerto (por ejemplo, no está permitido). Todas las direcciones URL simples deben comenzar con el prefijo https://.

Las direcciones URL simples solo pueden contener caracteres alfanuméricos (es decir, a-z, A-Z, 0-9 y el punto (.). Si usa otros caracteres, es posible que las direcciones URL simples no funcionen de la manera esperada.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Cambiar direcciones URL simples después de la implementación

Si cambia una dirección URL simple después de la implementación inicial, debe tener en cuenta cómo afecta el cambio a los registros DNS y los certificados para las direcciones URL simples. Si cambia la base de una dirección URL simple, debe cambiar también los certificados y los registros DNS. Por ejemplo, si cambia https://lync.contoso.com/Meet de https://meet.contoso.com para cambia la dirección URL base de Lync.contoso.com a meet.contoso.com, tendrá que cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com. Si cambió la dirección URL simple de https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings, la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario realizar cambios en el certificado o DNS.

Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar **enable-CsComputer** en cada director y en el servidor front-end para registrar el cambio.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

