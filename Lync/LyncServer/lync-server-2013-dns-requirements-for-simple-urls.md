---
title: 'Lync Server 2013: Requisitos de DNS para direcciones URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcf537db908fcc0b69e95bec99b73a0e57e9ab4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Requisitos de DNS para direcciones URL simples en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Lync Server 2013 admite direcciones URL simples, que facilitan la Unión de las reuniones a los usuarios, y facilitan la aplicación a las herramientas administrativas de Lync Server. Para obtener más información sobre las direcciones URL simples, consulte [planeamiento de direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server admite las siguientes tres direcciones URL sencillas: reunirse, acceso telefónico y administrador. Es necesario configurar direcciones URL simples para la reunión y el acceso telefónico, y la dirección URL simple de administración es opcional. Los registros del sistema de nombres de dominio (DNS) necesarios para admitir direcciones URL sencillas varían en función de la forma en que se hayan definido dichas direcciones URL sencillas y de si desea admitir la recuperación ante desastres para las direcciones URL sencillas.

<div>

## <a name="simple-url-option-1"></a>Opción 1 de dirección URL sencilla

En la opción 1, se crea una dirección URL base para cada dirección URL sencilla.

<div class="">


> [!NOTE]  
> Cuando un usuario hace clic en un vínculo de reunión de dirección URL sencilla, el servidor en el que se resuelve el registro A de DNS determina el software cliente correcto para iniciarlo. Una vez iniciado, el software cliente se comunica automáticamente con el grupo de servidores en el que se hospeda la conferencia. De este modo, los usuarios se dirigen al servidor adecuado para el contenido de la reunión, independientemente del servidor o del grupo de servidores en el que se resuelvan los registros A de DNS de la dirección URL sencilla.



</div>

### <a name="simple-url-option-1"></a>Opción 1 de dirección URL sencilla

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


Si usa la opción 1, necesita definir lo siguiente:

  - Para cada URL sencilla de reunión, necesita un registro A de DNS que resuelva la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, necesita resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro A de DNS necesita resolverse en la dirección IP de un servidor Standard Edition de su organización.
    
    Si dispone de más de un dominio SIP en la organización y usa esta opción, necesita crear direcciones URL sencillas de reunión para cada dominio SIP y se necesita un registro A de DNS para cada dirección URL sencilla de reunión. Por ejemplo, si tiene tanto contoso.com como fabrikam.com, creará registros A de DNS para https://meet.contoso.com y. https://meet.fabrikam.com
    
    Asimismo, si tiene varios dominios SIP y desea reducir los requisitos de registro de DNS y de certificado de estas direcciones URL sencillas, use la opción 3 que se describe más adelante en este tema.

  - Para la dirección URL de acceso telefónico, necesita un registro A de DNS que se resuelva en la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, necesita resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y usa una implementación de servidores Standard Edition, el registro A de DNS necesita resolverse en la dirección IP de un servidor Standard Edition de su organización.

  - La dirección URL sencilla de administrador es solo de uso interno. Necesita un registro A de DNS que se resuelva en la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, necesita resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y usa una implementación de servidores Standard Edition, el registro A de DNS necesita resolverse en la dirección IP de un servidor Standard Edition de su organización.

</div>

<div>

## <a name="simple-url-option-2"></a>Opción 2 de dirección URL sencilla

Con la opción 2, todas las direcciones URL sencillas de reunión, de acceso telefónico y de administrador tienen una dirección URL base común, como lync.contoso.com. Por lo tanto, solo necesita un registro DNS A para estas simples direcciones URL, que resuelve lync.contoso.com en la dirección IP de un grupo de directores o grupo de servidores front-end. Si no ha implementado un grupo de servidores y usa una implementación de servidores Standard Edition, el registro A de DNS necesita resolverse en la dirección IP de un servidor Standard Edition de su organización.

Tenga en cuenta que si dispone de más de un dominio SIP en la organización y usa esta opción, aún necesita crear direcciones URL sencillas de reunión para cada dominio SIP y necesita un registro A de DNS para cada dirección URL sencilla de reunión. En este ejemplo, aunque las tres direcciones URL sencillas se basan en lync.contoso.com, se configura una dirección URL sencilla de reunión adicional para fabrikam.com con una dirección URL base distinta. En este ejemplo, debe crear registros A de DNS para ambos https://lync.contoso.com y https://lync.fabrikam.com. La opción 3 de dirección URL sencilla muestra otra forma de administrar registros A de DNS y de nomenclatura si tiene varios dominios SIP.

### <a name="simple-url-option-2"></a>Opción 2 de dirección URL sencilla

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


</div>

<div>

## <a name="simple-url-option-3"></a>Opción 3 de dirección URL sencilla

La opción 3 es más útil si tiene muchos dominios SIP y desea que tengan direcciones URL simples independientes pero desee minimizar los requisitos de certificados y registros DNS para estas direcciones URL simples. En este ejemplo, solo se necesita un registro A de DNS, que resuelve lync.contoso.com en la dirección IP de un grupo de director o un grupo de servidores front-end.

### <a name="simple-url-option-3"></a>Opción 3 de dirección URL sencilla

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
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Opción de recuperación ante desastres para direcciones URL sencillas

Si tiene varios sitios que contienen grupos front-end y su proveedor DNS admite GeoDNS, puede configurar los registros DNS para que las direcciones URL simples admitan la recuperación ante desastres, de modo que la funcionalidad de dirección URL simple continuará incluso si se produce un grupo de servidores front-end completo. Esta característica de recuperación ante desastres admite las direcciones URL sencillas de acceso telefónico y de reunión.

Para configurar esto, cree dos direcciones de GeoDNS. Cada dirección tiene dos registros A de DNS o CNAME que se resuelven en dos grupos de servidores que funcionan juntos con fines de recuperación ante desastres. Una dirección de GeoDNS se utiliza para el acceso interno y se resuelve en el FQDN web interno o la dirección IP del equilibrador de carga para dos grupos de servidores. La otra dirección de GeoDNS se utiliza para el acceso externo y se resuelve en el FQDN web externo o la dirección IP del equilibrador de carga para dos grupos de servidores. Lo siguiente es un ejemplo de dirección URL sencilla de reunión, que utiliza los FQDN para los grupos de servidores.

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

Luego, cree registros CNAME que se resuelven en la dirección URL sencilla de reunión (como meet.contoso.com) en las dos direcciones de GeoDNS.

<div class="">


> [!NOTE]  
> Si su red utiliza <EM>vinculaciones</EM> (enrutamiento de todo el tráfico de direcciones URL sencillas a través del vínculo externo, incluido el tráfico que proviene desde su organización), puede sencillamente configurar la dirección de GeoDNS externa y resolver la dirección URL sencilla de reunión en solo esa dirección externa.



</div>

Al utilizar este método, puede configurar cada dirección de GeoDNS para que utilice un método round robin para distribuir solicitudes en los dos grupos de servidores, o bien para que se conecte principalmente a un grupo de servidores (como el grupo de servidores más cercano) y utilizar el otro grupo solo en caso de que no se pueda establecer la conexión.

Puede configurar las mismas opciones para la dirección URL sencilla de acceso telefónico. Para ello, cree registros adicionales, como los que se han en el ejemplo anterior `dialin` , `meet` que se sustituirán por los registros DNS. Para la dirección URL sencilla de administrador, utilice una de las tres opciones que se mencionaron antes en esta sección.

Una vez que esta configuración esté definida, necesita utilizar una aplicación de supervisión para configurar la supervisión HTTP para que busque errores. Para el acceso externo, supervise para asegurarse de que HTTPS Obtenga solicitudes de descubrimiento automático para el FQDN de la web externa o la dirección IP del equilibrador de carga de los dos grupos se hayan realizado correctamente. Por ejemplo, las siguientes solicitudes no tienen que contener ningún encabezado **ACCEPT** y necesitan devolver **200 OK**.

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

Para el acceso interno, necesita supervisar el puerto 5061 en el FQDN web interno o la dirección IP del equilibrador de carga para los dos grupos de servidores. Si se detectan errores de conectividad, la VIP de estos grupos debe cerrar los puertos 80, 443 y 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

