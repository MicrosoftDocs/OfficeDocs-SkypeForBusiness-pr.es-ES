---
title: 'Lync Server 2013: Creación de registros DNS para el servicio Detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5307251e9c3dea202b08b48bf45e109ef19449ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Creación de registros DNS para el servicio Detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-20_

Los usuarios de Lync Mobile deberán habilitar la detección automática y una parte de eso implica crear algunos registros del sistema de nombres de dominio (DNS). Según sus necesidades, necesita lo siguiente:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.

  - Registro DNS externo o público para admitir usuarios móviles que se conectan desde Internet

¿Por qué? Debe crear un registro DNS interno y un registro DNS externo para cada dominio SIP.

Los registros DNS que cree pueden ser registros A (hospedaje) o registros CNAME. Para ayudarte, veremos cómo crear estos registros DNS internos y externos a continuación. Si necesita más información sobre los requisitos de DNS para los usuarios móviles, puede consultar [los requisitos técnicos de movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Crear un registro CNAME de DNS interno

1.  Para crear un registro DNS interno, tendrá que iniciar sesión en un servidor DNS de su red con una cuenta de dominio que sea miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.

2.  Abra el complemento administrativo DNS: haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.

3.  En el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory en el que se instalan el grupo de directores de Lync Server 2013 y el grupo de servidores front-end. (por ejemplo, contoso. local).

4.  Compruebe si existe un registro A (AAAA para IPv6) para el grupo de directores para un registro DNS interno, debe existir un registro A host para el nombre de dominio completo (FQDN) del servicio Web interno para el grupo de directores (por ejemplo, lyncwebdir01. contoso. local). Si no está aquí, es posible que no esté usando un grupo de directores y tendrá que usar el FQDN de su grupo de servidores front-end o incluso un FQDN de servidor único, si es su configuración.

5.  Teniendo esto en cuenta, compruebe si existe un registro A (AAAA para IPv6) para el grupo de servidores front-end para un registro DNS interno, debe existir un registro de host A (o AAAA) para el FQDN de los servicios Web internos para el grupo front-end (por ejemplo , lyncwebpool01. contoso. local). Si no es así, tendrá que tomar nota del FQDN para el servidor front-end o del servidor Standard Edition.

6.  Una vez que sepa qué registros de host A (o AAAA) existen, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).

7.  Haga clic con el botón derecho en el nombre de dominio SIP y después haga clic en **nuevo alias (CNAME)**.

8.  En **nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio de detección automática.

9.  En **nombre de dominio completo (FQDN) para el host de destino**, escriba o busque el FQDN de los servicios Web internos de su grupo de directores (por ejemplo, lyncwebdir01. contoso. local) y, a continuación, haga clic en **Aceptar**.

10. Debe crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que admita en el entorno de Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Crear un registro CNAME DNS externo

1.  Para crear un registro CNAME DNS externo, tendrá que conectarse a su proveedor de DNS público y, a continuación, seguir nuestros pasos. No podemos describir exactamente dónde va a estar en el entorno de su proveedor de DNS, ya que puede haber diferentes formas de administrar su DNS externo, pero esperamos que estos pasos le ayuden.

2.  Inicie sesión en su proveedor de DNS externo con una cuenta que pueda crear registros DNS en ese entorno.

3.  Ya se ha creado un dominio SIP para este entorno. Expanda la **zona de búsqueda directa** para este dominio SIP o selecciónela en función de la interfaz DNS externa que se esté usando.

4.  Ya debería ver un registro host A (AAAA para IPv6) para el grupo de directores (como lyncwebexdir01.contoso.com), por lo que debe confirmar que está allí. De lo contrario, es posible que no esté usando un grupo de directores. Si este es el caso, tendrá que usar el FQDN de su grupo de servidores front-end o, si hace esto para un único servidor, para su servidor de front-end o servidor Standard Edition.

5.  También necesitará confirmar que existe un registro de host A (AAAA para IPv6) para su servicio Web externo nombre de dominio completo (FQDN) para el grupo front-end (como lyncwebextpool01.contoso.com), o un FQDN para su FQDN de servidor único si no tiene ningún grupo de servidores front-end. Tal y como se indicó en el paso anterior, necesitará lo siguiente si no tiene un grupo de directores.

6.  Ahora, en el formato adecuado para su proveedor de DNS externo, elija la opción para crear un **nuevo alias (CNAME)** (puede ser una opción de menú o un vínculo, según el formato del proveedor DNS).

7.  Debe haber alguna forma de cuadro de texto **nombre de alias** como con el DNS interno, debe escribir lyncdiscover como nombre de host para la dirección URL del servicio de detección automática externa.

8.  También debe haber alguna forma de un **nombre de dominio completo (FQDN) para** el cuadro de texto de host de destino, aquí es donde debe especificar el FQDN de los servicios web externos para el grupo de directores (por ejemplo, lyncwebexdir01.contoso.com) y, a continuación, hacer clic en aceptar o tomar lo que haya acción en el DNS externo para aceptar la creación de esta entrada. Como se mencionó anteriormente en el paso 4, si no tiene un grupo de directores, tendrá que usar el FQDN del grupo de servidores front-end o el FQDN de servidor único que ha configurado, según corresponda.

9.  Tendrá que crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Crear un registro DNS interno A

1.  Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red con una cuenta de dominio que sea miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.

2.  Abra el complemento administrativo DNS: haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.

3.  Para un registro DNS interno, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory (por ejemplo, contoso. local) donde esté instalado el grupo de directores de Lync Server 2013 y el grupo front-end.

4.  Compruebe si existe un registro A (AAAA para IPv6) para el grupo de directores para un registro DNS interno, debe existir un registro A host para el nombre de dominio completo (FQDN) del servicio Web interno para el grupo de directores (por ejemplo, lyncwebdir01. contoso. local). Si no está aquí, es posible que no esté usando un grupo de directores y tendrá que usar la dirección IP del grupo de servidores front-end o incluso una dirección IP del servidor, si se trata de la configuración.

5.  Teniendo esto en cuenta, compruebe si existe un registro A (AAAA para IPv6) para el grupo de servidores front-end para un registro DNS interno, debe existir un registro de host A (o AAAA) para el FQDN de los servicios Web internos para el grupo front-end (por ejemplo , lyncwebpool01. contoso. local). Si no es así, tendrá que tomar nota de la dirección IP del servidor front-end o del servidor Standard Edition.

6.  Una vez que sepa qué registros de host A (o AAAA) existen, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).

7.  Haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, haga clic en **nuevo host (A o aaaa)**.

8.  En **nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio de detección automática.

9.  En **dirección IP**, escriba la dirección IP de los servicios Web internos del Director (o bien, si usa un equilibrador de carga, escriba la dirección IP virtual (VIP) del equilibrador de carga del Director). Como se mencionó anteriormente en el paso 4, si no está usando un director, es posible que tenga que escribir la dirección IP del servidor front-end o el servidor Standard Edition o, si usa un equilibrador de carga, escriba la VIP del equilibrador de carga del grupo de servidores front-end.

10. Haga clic en **Agregar host**y, a continuación, en **Aceptar**.

11. Para crear un registro A o AAAA adicional, repita los pasos 8 a 10, teniendo en cuenta que tendrá que crear nuevos registros A o AAAA de detección automática en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync Server 2013.

12. Cuando haya terminado de crear un registro (para IPv6, AAAA), haga clic en **listo**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Crear un registro DNS externo

1.  Para crear un registro DNS externo, conéctese a su proveedor de DNS público y, a continuación, siga nuestros pasos. No podemos describir exactamente dónde va a estar en el entorno de su proveedor de DNS, ya que puede haber diferentes formas de administrar su DNS externo, pero esperamos que estos pasos le ayuden.

2.  Tendrá que haber iniciado sesión como una cuenta que puede crear registros DNS en ese entorno.

3.  Para un registro DNS externo, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com). Para un registro DNS externo, en el árbol de consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).

4.  Ya debería ver un registro host A (AAAA para IPv6) para el grupo de directores (como lyncwebexdir01.contoso.com), por lo que debe confirmar que está allí y cuál es la dirección IP. De lo contrario, es posible que no esté usando un grupo de directores. Si ese es el caso, tendrá que usar la dirección IP de su grupo de servidores front-end o, si lo hace para un único servidor, para su servidor de front-end o servidor Standard Edition. Tenga en cuenta que los servidores también pueden estar detrás de un equilibrador de carga o con un proxy inverso. Anote las direcciones IP también para seguir los pasos que se indican a continuación.

5.  También necesitará confirmar que existe un registro de host A (AAAA para IPv6) para su servicio Web externo nombre de dominio completo (FQDN) para el grupo de front-end (como lyncwebextpool01.contoso.com) o una dirección IP para su instalación de Lync de servidor único si no tienen Grupo front-end. Tal y como se indicó en el paso anterior, necesitará lo siguiente si no tiene un grupo de directores.

6.  Ahora, en el formato adecuado para su proveedor de DNS externo, elija la opción para crear un **nuevo host a o AAAA** (puede ser una opción de menú o un vínculo, según el formato del proveedor DNS).

7.  Debe haber un lugar para escribir un **nombre**, escriba lyncdiscover como nombre de host para la dirección URL del servicio de detección automática externa.

8.  También debe haber un cuadro de texto **dirección IP** , aquí es donde debe especificar la dirección IP de su grupo de directores (por ejemplo, lyncwebexdir01.contoso.com) o, posiblemente, la IP del equilibrador de carga del grupo (o una IP de proxy invertida que lleva a la misma) y, a continuación, haga clic en Aceptar o tomar cualquier acción en el DNS externo para aceptar la creación de esta entrada. Como se mencionó anteriormente en el paso 4, si no tiene un grupo de directores, tendrá que usar la dirección IP del grupo de servidores front-end o la dirección IP del servidor único que haya configurado, según corresponda.

9.  Tendrá que crear un nuevo registro de detección automática A o AAAA en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

