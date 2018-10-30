---
title: "Lync Server 2013: Creación de registros DNS para el servicio Detección automática"
TOCTitle: Creación de registros DNS para el servicio Detección automática
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48274915
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación de registros DNS para el servicio Detección automática en Lync Server 2013

 

_**Última modificación del tema:** 2014-06-20_

Los usuarios de Lync Mobile le necesitarán para que active la detección automática y, una parte de eso, afecta a la creación de algunos registros del sistema de nombres de dominio (DNS). Dependiendo de sus necesidades, necesitará lo siguiente:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.

  - Un registro DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet

¿Por qué ambos? Necesita crear un registro DNS interno y un registro DNS externo para cada dominio SIP.

Los registros DNS que cree pueden ser registros A (host) o registros CNAME. Para ayudarle, veremos cómo crear estos registros DNS internos y externos a continuación. Si necesita lecturas adicionales sobre los requisitos de DNS para usuarios móviles, puede consultar [Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

## Creación de un registro CNAME de DNS interno

1.  Para crear un registro DNS interno, tendrá que iniciar sesión en un servidor DNS de la red con una cuenta de dominio que sea miembro del grupo Admins. del dominio o miembro del grupo DnsAdmins.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  En el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** del dominio de Active Directory donde están instalados Lync Server 2013Grupo de directores y Grupo de servidores front-end, (por ejemplo, contoso.local).

4.  Compruebe y vea si existe un registro de host A (AAAA para IPv6) en Grupo de directores para un registro de DNS interno, debe existir un registro de host A para el nombre de dominio completo (FQDN) de los servicios web internos del Grupo de directores (por ejemplo, lyncwebdir01.contoso.local). Si no está, no puede usar un Grupo de directores, y tendrá que usar el FQDN de su Grupo de servidores front-end o incluso un FQDN de un servidor único, si esa es su configuración.

5.  Tenga eso en cuenta, compruebe y vea si existe un registro de host A (AAAA para IPv6) en Grupo de servidores front-end para un registro de DNS interno, debe existir un registro de host A para el nombre de dominio completo (FQDN) de los servicios web internos para Grupo de servidores front-end (por ejemplo, lyncwebpool01.contoso.local). Si no existe, tendrá que tener en cuenta el FQDN para el Servidor front-end o el Servidor Standard Edition.

6.  Una vez que sabe que existen registros de host A (o AAAA), en el árbol de la consola del servidor DNS, expanda**Zonas de búsqueda directa** del dominio SIP (por ejemplo, contoso.com).

7.  Haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo alias (CNAME)**.

8.  En **Nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.

9.  En **Nombre de dominio completo (FQDN) para el host de destino**, escriba o busque el FQDN interno de servicios web del Grupo de directores (por ejemplo, lyncwebdir01.contoso.local) y luego haga clic en **Aceptar**.

10. Debe crear un nuevo registro CNAME de Detección automática en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.

## Creación de un registro CNAME de DNS externo

1.  Para crear un registro CNAME de DNS externo, tendrá que conectarse con su proveedor de DNS público y luego seguir estos pasos. No se puede describir exactamente dónde entrará en el entorno del proveedor de DNS ya puede haber diferentes formas de administrar los DNS externos, pero esperamos que estos pasos le ayuden.

2.  Inicie sesión en su proveedor de DNS externo con una cuenta que puede crear registros de DNS en ese entorno.

3.  Ya debe tener un dominio SIP creado para este entorno. Expanda la **Zona de búsqueda directa** de este dominio SIP domain o, de lo contrario, selecciónelo dependiendo de la interfaz externa de DNS que vaya a utilizar.

4.  Ya debería ver un registro de host A (AAAA para IPv6) en Grupo de directores (como lyncwebexdir01.contoso.com), así que confirme que está ahí. Si no, es posible que no pueda utililizar un Grupo de directores. Si es el caso, necesitará utilizar el FQDN de su grupo de servidores front-end o, si está haciendo esto en un servidor único, en su servidor front-end o en Standard Edition.

5.  También necesitará confirmar que existe un registro de host A (AAAA para IPv6) para el nombre de dominio completo (FQDN) de los servicios web externos de el grupo de front-end (como lyncwebextpool01.contoso.com) o un FQDN para el FQDN del servidor único si no tiene un grupo de front-end. Como se indicó en el paso anterior, necesitará lo siguiente si no tiene un grupo Director.

6.  Ahora, en el formato adecuado para su proveedor DNS externo, elija la opción para crear un **Nuevo alias (CNAME)** (esto puede ser una opción de menú o un vínculo, dependiendo del formato del proveedor de DNS).

7.  Debería haber algún formulario del cuadro de texto de **Nombre de alias** como con el DNS interno, debería introducir lyncdiscover como el nombre de host para la dirección URL externa del servicio Detección automática.

8.  También debería haber algún formulario del cuadro de texto de **Nombre de dominio completo (FQDN) para el host de destino**, aquí es donde introducirá el FQDN de los servicios web externos del Grupo de directores (por ejemplo, lyncwebexdir01.contoso.com) y luego haga clic en Aceptar o realice cualquier acción en el DNS externo para aceptar la creación de esta entrada. Como se indicó en el Paso 4 anterior, si no tiene un Grupo de directores, necesitará utilizar el FQDN del grupo de front-end o el FQDN del servidor único que ha configurado, según corresponda.

9.  Tendrá que crear un nuevo registro CNAME de Detección automática en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync 2013.

## Creación de un registro A de DNS interno

1.  Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red con una cuenta de dominio que sea miembro del grupo Admins. del dominio o miembro del grupo DnsAdmins.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  En el caso de un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** de su dominio de Active Directory (por ejemplo, contoso.local) donde están instalados el grupo de Lync Server 2013Director y Grupo de servidores front-end.

4.  Compruebe y vea si existe un registro de host A (AAAA para IPv6) en Grupo de directores para un registro de DNS interno, debe existir un registro de host A para el nombre de dominio completo (FQDN) de los servicios web internos del Grupo de directores (por ejemplo, lyncwebdir01.contoso.local). Si no está, no puede usar un Grupo de directores, y tendrá que usar la dirección IP de su grupo front-end o incluso la dirección IP de un servidor único, si esa es su configuración.

5.  Tenga eso en cuenta, compruebe y vea si existe un registro de host A (AAAA para IPv6) en Grupo de servidores front-end para un registro de DNS interno, debe existir un registro de host A para el nombre de dominio completo (FQDN) de los servicios web internos del Grupo de servidores front-end (por ejemplo, lyncwebpool01.contoso.local). Si no existe, tendrá que tener en cuenta la dirección IP del Servidor front-end o el Servidor Standard Edition.

6.  Una vez que sabe que existen registros de host A (o AAAA), en el árbol de la consola del servidor DNS, expanda**Zonas de búsqueda directa** del dominio SIP (por ejemplo, contoso.com).

7.  Haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo host (A o AAAA)**.

8.  En **Nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.

9.  En **IP Address**, escriba la dirección IP interna de servicios web del Director (o, si usa un equilibrador de carga, escriba la IP virtual (VIP) del equilibrador de carga del Director). Como se indicó en el Paso 4 anterior, si no usa un Director, puede que tenga que introducir la dirección IP del Servidor front-end o el Servidor Standard Edition o, si usa un equilibrador de carga, escriba la dirección VIP del equilibrador de carga del Grupo de servidores front-end.

10. Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

11. Para crear un registro A o AAAA adicional, repita los pasos 8 a 10, teniendo en cuenta que tendrá que crear nuevos registros de Detección automática A o AAAA en la zona de búsqueda directa de cada dominio SIP que ha admitido en su entorno de Lync Server 2013.

12. Cuando termine de crear registros A (para IPv6, AAAA), haga clic en **Listo**.

## Creación de un registro A de DNS externo

1.  Para crear un registro de DNS externo, conéctese con su proveedor de DNS público y luego seguir estos pasos. No se puede describir exactamente dónde entrará en el entorno del proveedor de DNS ya puede haber diferentes formas de administrar los DNS externos, pero esperamos que estos pasos le ayuden.

2.  Tendrá que iniciar con una cuenta que puede crear registros de DNS en ese entorno.

3.  En el caso de un registro DNS externo, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** de su dominio SIP (por ejemplo, contoso.com). En el caso de un registro DNS externo, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** de su dominio SIP (por ejemplo, contoso.com).

4.  Ya debería ver un registro de host A (AAAA para IPv6) en Grupo de directores (como lyncwebexdir01.contoso.com), así que confirme que está ahí y cuál es la dirección IP. Si no, es posible que no pueda utililizar un Grupo de directores. ISi es el caso, necesitará utilizar la dirección IP de su grupo de servidores front-end o, si está haciendo esto en un servidor único, en su servidor front-end o en Standard Edition. Tenga en cuenta que los servidores también pueden estar detrás de un equilibrador de carga o utilizar a un proxy inverso. Anote también las direcciones IP para realizar los pasos siguientes.

5.  También necesitará confirmar que existe un registro de host A (AAAA para IPv6) para el nombre de dominio completo (FQDN) de los servicios web externos de el grupo de front-end (como lyncwebextpool01.contoso.com) o una dirección IP para la instalación de Lync del servidor único si no tiene un grupo de front-end. Como se indicó en el paso anterior, necesitará lo siguiente si no tiene un grupo Director.

6.  Ahora, en el formato adecuado para su proveedor DNS externo, elija la opción para crear un **Nuevo host A o AAAA** (esto puede ser una opción de menú o un vínculo, dependiendo del formato del proveedor de DNS).

7.  Debería haber un lugar para introducir un **Nombre**, escriba lyncdiscover como el nombre de host en la dirección URL externa del servicio Detección automática.

8.  También debería haber un cuadro de texto de **Dirección IP Address**, aquí es donde introducirá la dirección IP del Grupo de directores (por ejemplo, lyncwebexdir01.contoso.com) o posiblemente la dirección IP del equilibrador de carga del grupo (o una dirección Ip de proxy inverso que le lleve al mismo) y luego haga clic en Aceptar o realice cualquier acción en el DNS externo para aceptar la creación de esta entrada. Como se indicó en el Paso 4 anterior, si no tiene un Grupo de directores, necesitará utilizar la dirección IP del grupo de front-end o la dirección IP del servidor único que ha configurado, según corresponda.

9.  Tendrá que crear un nuevo registro A o AAAA de Detección automática en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Lync 2013.

