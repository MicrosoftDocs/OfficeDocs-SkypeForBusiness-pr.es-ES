---
title: 'Lync Server 2013: requisitos de DNS para direcciones URL sencillas'
description: 'Lync Server 2013: requisitos de DNS para direcciones URL sencillas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564966"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Requisitos de DNS para direcciones URL sencillas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Lync Server 2013 admite direcciones URL sencillas que facilitan la combinación de reuniones con los usuarios y facilitan a los administradores las herramientas administrativas de Lync Server. Para obtener más información sobre las direcciones URL sencillas, consulte [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server admite las siguientes tres direcciones URL sencillas: reunirse, acceso telefónico y administrador. Es necesario configurar direcciones URL sencillas para la reunión y el acceso telefónico, y la dirección URL sencilla de administración es opcional. Los registros del sistema de nombres de dominio (DNS) necesarios para admitir direcciones URL sencillas varían en función de la forma en que se hayan definido dichas direcciones URL sencillas y de si desea admitir la recuperación ante desastres para las direcciones URL sencillas.

<div>

## <a name="simple-url-option-1"></a>Opción 1 de dirección URL sencilla

En la opción 1, se crea una nueva dirección URL base para cada dirección URL sencilla.

<div class="">


> [!NOTE]  
> Cuando un usuario hace clic en un vínculo de reunión de dirección URL sencilla, el servidor en el que se resuelve el registro DNS A determina el software cliente correcto para iniciarlo. Una vez iniciado, el software cliente se comunica automáticamente con el grupo de servidores en el que se hospeda la conferencia. De este modo, los usuarios se dirigen al servidor adecuado para contenido de reunión, con independencia del servidor o grupo de servidores en el que se resuelvan los registros DNS A de la dirección URL sencilla.



</div>

### <a name="simple-url-option-1"></a>Opción 1 de dirección URL sencilla

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
<td><p>https://meet.contoso.com, https://meet.fabrikam.com y así sucesivamente (uno para cada dominio SIP de la organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Si usa la opción 1, debe definir lo siguiente:

  - Para cada URL sencilla de reunión, necesita un registro DNS A que resuelva la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, debe resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.
    
    Si dispone de más de un dominio SIP en la organización y usa esta opción, debe crear direcciones URL sencillas de reunión para cada dominio SIP y se necesita un registro DNS A para cada dirección URL sencilla de reunión. Por ejemplo, si tiene tanto contoso.com como fabrikam.com, se crearán registros A de DNS para https://meet.contoso.com y https://meet.fabrikam.com .
    
    Asimismo, si tiene varios dominios SIP y desea reducir al máximo los requisitos de registro DNS y de certificado de estas direcciones URL sencillas, use la opción 3 que se describe más adelante en este tema.

  - Para la dirección URL de acceso telefónico local, necesita un registro DNS A que resuelva la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, debe resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.

  - La dirección URL sencilla de administrador es solo de uso interno. Necesita un registro DNS A que resuelva la dirección URL en la dirección IP del director, si se ha implementado uno. En caso contrario, debe resolverse en la dirección IP del equilibrador de carga de un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.

</div>

<div>

## <a name="simple-url-option-2"></a>Opción 2 de dirección URL sencilla

Con la opción 2, todas las direcciones URL sencillas de reunión, acceso telefónico local y administrador tienen una dirección URL base, como lync.contoso.com. Por consiguiente, únicamente necesita un registro DNS A para estas direcciones URL sencillas, que resuelve lync.contoso.com en la dirección IP de un grupo de servidores director o un grupo de servidores front-end. Si no ha implementado un grupo de servidores y se usa una implementación de servidor Standard Edition, el registro DNS A debe resolverse en la dirección IP de un servidor Standard Edition de su organización.

Tenga en cuenta que si dispone de más de un dominio SIP en la organización y usa esta opción, debe crear direcciones URL sencillas de reunión para cada dominio SIP y se necesita un registro DNS A para cada dirección URL sencilla de reunión. En este ejemplo, aunque las tres direcciones URL sencillas se basan en lync.contoso.com, se configura una dirección URL sencilla de reunión adicional para fabrikam.com con una dirección URL base distinta. En este ejemplo, debe crear registros A de DNS para https://lync.contoso.com y https://lync.fabrikam.com . La opción 3 de dirección URL sencilla muestra otra forma de administrar registros DNS A y de nomenclatura si tiene varios dominios SIP.

### <a name="simple-url-option-2"></a>Opción 2 de dirección URL sencilla

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
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet y así sucesivamente (uno para cada dominio SIP de la organización)</p></td>
</tr>
<tr class="odd">
<td><p>Acceso telefónico local</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>Opción 3 de dirección URL sencilla

La opción 3 resulta más útil si se tienen varios dominios SIP y se desea que tengan direcciones URL sencillas independientes y al mismo tiempo reducir al máximo los requisitos de registro DNS y de certificado de estas direcciones URL sencillas. En este ejemplo, solo se necesita un solo registro DNS A, que resuelve lync.contoso.com en la dirección IP de un grupo de servidores director o un grupo de servidores front-end.

### <a name="simple-url-option-3"></a>Opción 3 de dirección URL sencilla

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
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Opción de recuperación ante desastres para direcciones URL sencillas

Si tiene varios sitios que contienen grupos de servidores front-end y el proveedor de DNS admite GeoDNS, puede configurar los registros DNS para que las direcciones URL sencillas admitan la recuperación ante desastres, de modo que la funcionalidad de dirección URL sencilla continúe incluso si se produce un grupo de servidores front-end completo. Esta función de recuperación ante desastres admite las direcciones URL sencillas de Acceso telefónico y Reunión.

Para configurar esto, cree dos direcciones de GeoDNS. Cada dirección tiene dos registros DNS A o CNAME que resultan en dos grupos de servidores que funcionan juntos con fines de recuperación ante desastres. Una dirección de GeoDNS se utiliza para el acceso interno y se resuelve en el FQDN web interno o la dirección IP del equilibrador de carga para dos grupos de servidores. La otra dirección de GeoDNS se utiliza para el acceso externo y se resuelve en el FQDN web externo o la dirección IP del equilibrador de carga para dos grupos de servidores. Lo siguiente es un ejemplo de dirección URL sencilla de Reunión, que utiliza los FQDN para los grupos de servidores.

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

Luego cree registros CNAME que se resuelven su dirección URL sencilla de Reunión (como meet.contoso.com) en las dos direcciones de GeoDNS.

<div class="">


> [!NOTE]  
> Si su red utiliza <EM>vinculaciones</EM> (enrutamiento de todo su tráfico de direcciones URL sencillas a través del enlace externo, incluido el tráfico que proviene desde su organización), entonces puede simplemente configurar la dirección de GeoDNS externa y resolver su dirección URL sencilla de Reunión en solo esa dirección externa.



</div>

Al utilizar este método, puede configurar cada dirección de GeoDNS para que utilice un método de operación por turnos para distribuir solicitudes en los dos grupos de servidores, o bien para que se conecte a un grupo de servidores (como el grupo de servidores más cercano) y utilizar el otro grupo solo en caso de que no se pueda establecer la conexión.

Puede configurar los mismos parámetros para la dirección URL sencilla de Acceso telefónico. Para ello, cree registros adicionales como los del ejemplo anterior, sustituyendo `dialin` por `meet` en los registros DNS. Para la dirección URL sencilla de Administrador, utilice una de las tres opciones que se mencionaron antes en esta sección.

Una vez que esta configuración esté definida, debe utilizar una aplicación de supervisión para configurar la supervisión HTTP para que esté alerta de los fallos. Para el acceso externo, supervise para asegurarse de que las solicitudes HTTPS GET AutoDiscovery para el FQDN de Web externo o la dirección IP del equilibrador de carga para los dos grupos de servidores sean correctas. Por ejemplo, las siguientes solicitudes no deben contener ningún encabezado **ACCEPT** y deben devolver **200 OK**.

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para el acceso interno, debe supervisar el puerto 5061 en el FQDN web interno o la dirección IP del equilibrador de carga para los dos grupos de servidores. Si se detecta cualquier problema de conectividad, la VIP de estos grupos de servidores deben cerrar los puertos 80, 443 y 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

