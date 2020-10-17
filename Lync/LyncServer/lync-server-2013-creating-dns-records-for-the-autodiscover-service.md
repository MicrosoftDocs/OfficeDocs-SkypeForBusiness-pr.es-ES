---
title: 'Lync Server 2013: creación de registros DNS para el servicio Detección automática'
description: 'Lync Server 2013: creación de registros DNS para el servicio Detección automática.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563106"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Creación de registros DNS para el servicio Detección automática en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-20_

Los usuarios de Lync Mobile deberán habilitar la detección automática, y una parte de esto implicará la creación de algunos registros del sistema de nombres de dominio (DNS). Según sus necesidades, necesitará lo siguiente:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de la organización.

  - Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet

¿Por qué? Debe crear un registro DNS interno y un registro DNS externo para cada dominio SIP.

Los registros DNS que cree pueden ser registros A (host) o registros CNAME. Para ayudarle, analizaremos cómo crear estos registros DNS internos y externos a continuación. Si necesita más información sobre los requisitos de DNS para los usuarios móviles, puede consultar [los requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Crear un registro CNAME de DNS interno

1.  Para crear un registro DNS interno, tendrá que iniciar sesión en un servidor DNS de la red con una cuenta de dominio que sea miembro del grupo administradores de dominio o que pertenezca al grupo DnsAdmins.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  En el árbol de la consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory en el que está instalado el grupo de directores de Lync Server 2013 y el grupo de servidores front-end. (por ejemplo, contoso. local).

4.  Compruebe si existe un registro de host A (AAAA para IPv6) para el grupo de directores para un registro DNS interno, debe haber un registro de host A para el nombre de dominio completo (FQDN) de servicios Web internos del grupo de directores (por ejemplo, lyncwebdir01. contoso. local). Si no es así, es posible que no esté usando un grupo de directores, por lo que necesitará usar el FQDN del grupo de servidores front-end o incluso un FQDN de servidor único, si es su configuración.

5.  Teniendo esto en cuenta, compruebe si existe un registro de host A (AAAA para IPv6) para el grupo de servidores front-end para un registro DNS interno, debe haber un registro de host A (o AAAA) para el FQDN de servicios Web internos del grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local). Si no es así, tendrá que anotar el FQDN del servidor front-end o del servidor Standard Edition.

6.  Una vez que sepa qué registros de host A (o AAAA) existen, en el árbol de la consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).

7.  Haga clic con el botón secundario del mouse en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo alias (CNAME)**.

8.  En **nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.

9.  En **nombre de dominio completo (FQDN) para el host de destino**, escriba o busque el FQDN de servicios Web internos del grupo de directores (por ejemplo, lyncwebdir01. contoso. local) y, a continuación, haga clic en **Aceptar**.

10. Debe crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Crear un registro CNAME de DNS externo

1.  Para crear un registro CNAME de DNS externo, necesitará conectarse a su proveedor de DNS público y, a continuación, seguir los pasos que se indican a continuación. No podemos describir exactamente dónde vas a trabajar en el entorno del proveedor de DNS, ya que puede haber distintas formas de administrar su DNS externo, pero esperamos que estos pasos le ayuden.

2.  Inicie sesión en el proveedor de DNS externo con una cuenta que pueda crear registros DNS en ese entorno.

3.  Ya debe tener un dominio SIP creado para este entorno. Expanda la **zona de búsqueda directa** para este dominio SIP o seleccione en función de la interfaz DNS externa que se use.

4.  Ya debería ver un registro de host A (AAAA para IPv6) para el grupo de directores (por ejemplo, lyncwebexdir01.contoso.com), por lo que debe confirmar que está ahí. Si no es así, es posible que no use un grupo de directores. Si ese es el caso, deberá usar el FQDN del grupo de servidores front-end o, si lo hace para un único servidor, para el servidor de Front-End Server o Standard Edition.

5.  También necesitará confirmar que existe un registro de host A (AAAA para IPv6) para el nombre de dominio completo (FQDN) de servicios web externos del grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com) o un FQDN para el FQDN de servidor único si no tiene ningún grupo de servidores front-end. Como se indicó en el paso anterior, necesitará lo siguiente si no tiene un grupo de directores.

6.  Ahora, en el formato adecuado para su proveedor de DNS externo, elija la opción para crear un **nuevo alias (CNAME)** (puede ser una opción de menú o un vínculo, según el formato del proveedor DNS).

7.  Debe haber algún tipo de cuadro de texto **nombre de alias** como con el DNS interno, escriba lyncdiscover como nombre de host para la dirección URL externa del servicio Detección automática.

8.  También debe haber una forma de un **nombre de dominio completo (FQDN) para el cuadro de texto de host de destino** , aquí es donde escribirá el FQDN de servicios web externos para el grupo de directores (por ejemplo, lyncwebexdir01.contoso.com) y, a continuación, haga clic en aceptar o realice cualquier acción en el DNS externo para aceptar la creación de esta entrada. Como se indicó en el paso 4 anterior, si no tiene un grupo de directores, deberá usar el FQDN del grupo de servidores front-end o el FQDN de servidor único que haya configurado, según corresponda.

9.  Deberá crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Creación de un registro A de DNS interno

1.  Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red con una cuenta de dominio que sea miembro del grupo administradores del dominio o de un miembro del grupo DnsAdmins.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  Para un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **zonas de búsqueda directa** para el dominio de Active Directory (por ejemplo, contoso. local) donde esté instalado el grupo de directores de Lync Server 2013 y el grupo de servidores front-end.

4.  Compruebe si existe un registro de host A (AAAA para IPv6) para el grupo de directores para un registro DNS interno, debe haber un registro de host A para el nombre de dominio completo (FQDN) de servicios Web internos del grupo de directores (por ejemplo, lyncwebdir01. contoso. local). Si no es así, es posible que no esté usando un grupo de directores, por lo que tendrá que usar la dirección IP de su grupo de servidores front-end o incluso una dirección IP de servidor única, si es su configuración.

5.  Teniendo esto en cuenta, compruebe si existe un registro de host A (AAAA para IPv6) para el grupo de servidores front-end para un registro DNS interno, debe haber un registro de host A (o AAAA) para el FQDN de servicios Web internos del grupo de servidores front-end (por ejemplo, lyncwebpool01. contoso. local). Si no es así, tendrá que anotar la dirección IP del servidor front-end o del servidor Standard Edition.

6.  Una vez que sepa qué registros de host A (o AAAA) existen, en el árbol de la consola del servidor DNS, expanda **zonas de búsqueda directa** para su dominio SIP (por ejemplo, contoso.com).

7.  Haga clic con el botón secundario del mouse en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo host (A o AAAA)**.

8.  En **nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.

9.  En **dirección IP**, escriba la dirección IP de los servicios Web internos del Director (o bien, si usa un equilibrador de carga, escriba la IP virtual (VIP) del equilibrador de carga del Director). Como se indicó en el paso 4 anterior, si no usa un director, es posible que tenga que escribir la dirección IP del servidor front-end o del servidor Standard Edition o bien, si usa un equilibrador de carga, escriba la VIP del equilibrador de carga del grupo de servidores front-end.

10. Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

11. Para crear un registro A o AAAA adicional, repita los pasos 8 a 10, teniendo en cuenta que tendrá que crear nuevos registros A o AAAA de detección automática en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync Server 2013.

12. Cuando acabe de crear registros A (para IPv6, AAAA), haga clic en **Listo**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Creación de un registro A de DNS externo

1.  Para crear un registro DNS externo, conéctese a su proveedor de DNS público y, a continuación, siga los pasos que se indican a continuación. No podemos describir exactamente dónde vas a trabajar en el entorno del proveedor de DNS, ya que puede haber distintas formas de administrar su DNS externo, pero esperamos que estos pasos le ayuden.

2.  Debe iniciar sesión como una cuenta que puede crear registros DNS en ese entorno.

3.  Para un registro DNS externo, en el árbol de la consola del servidor DNS, expanda  **Zonas de búsqueda directa**para su dominio SIP (por ejemplo, contoso.com). Para un registro DNS externo, en el árbol de la consola del servidor DNS, expanda  **Zonas de búsqueda directa**para su dominio SIP (por ejemplo, contoso.com).

4.  Ya debería ver un registro de host A (AAAA para IPv6) para el grupo de directores (como lyncwebexdir01.contoso.com), por lo que debe confirmar que está ahí y cuál es la dirección IP. Si no es así, es posible que no use un grupo de directores. Si ese es el caso, tendrá que usar la dirección IP del grupo de servidores front-end o, si está haciendo esto para un único servidor, para el servidor de Front-End o servidor Standard Edition. Tenga en cuenta que los servidores también pueden estar detrás de un equilibrador de carga o mediante un proxy inverso. Tome nota de las direcciones IP también para seguir los pasos que se indican a continuación.

5.  También necesitará confirmar que existe un registro de host A (AAAA para IPv6) para el nombre de dominio completo (FQDN) de servicios web externos del grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com) o una dirección IP para la instalación de Lync de servidor único si no tiene ningún grupo de servidores front-end. Como se indicó en el paso anterior, necesitará lo siguiente si no tiene un grupo de directores.

6.  Ahora, en el formato adecuado para su proveedor de DNS externo, elija la opción para crear un **nuevo host a o AAAA** (puede ser una opción de menú o un vínculo, según el formato del proveedor DNS).

7.  Debe haber un punto para escribir un **nombre**, escriba lyncdiscover como nombre de host para la dirección URL externa del servicio Detección automática.

8.  También debe haber un cuadro de texto **dirección IP** ; aquí puede especificar la IP de su grupo de directores (por ejemplo, lyncwebexdir01.contoso.com) o posiblemente la IP del equilibrador de carga del grupo de servidores (o una IP de proxy inverso que conduce al mismo) y, a continuación, haga clic en aceptar o realice alguna acción en el DNS externo para aceptar la creación de esta entrada. Como se indicó en el paso 4 anterior, si no tiene un grupo de directores, tendrá que usar la dirección IP del grupo de servidores front-end o la dirección IP de un único servidor que haya configurado, según corresponda.

9.  Deberá crear un nuevo registro de detección automática A o AAAA en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

