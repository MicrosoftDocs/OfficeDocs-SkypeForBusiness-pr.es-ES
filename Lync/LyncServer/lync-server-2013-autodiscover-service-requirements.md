---
title: "Lync Server 2013 : Conf. requise pour le service de découverte automatique"
TOCTitle: Requisitos del servicio Detección automática
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48274386
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos del servicio Detección automática para Lync Server 2013

 

_**Última modificación del tema:** 2013-02-25_

El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en los servidores director y grupo de servidores front-end, y cuando se publica en DNS, los dispositivos móviles que ejecutan Lync Mobile pueden usarlo para localizar servicios de movilidad. Antes de que los dispositivos móviles que ejecutan Lync Mobile puedan aprovechar la detección automática, hay que modificar las listas de nombres alternativos de sujeto de certificados en cualquier Director y Servidor front-end que ejecute el servicio Detección automática. Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.

Para obtener más información acerca de las entradas de nombres alternativos de sujeto que son necesarios para directores, servidores front-end y proxies inversos, vea [Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) en Planeación de movilidad.

La decisión de usar listas de nombres alternativos de sujeto en proxies inversos se basa en si se publica el servicio Detección automática en el puerto 80 o en el puerto 443:

  - **Publicado en el puerto 80**   No son necesarios cambios de certificado si la consulta inicial al servicio Detección automática se produce en el puerto 80. Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 de forma externa y, a continuación, se redirigirán a un Director o Servidor front-end en el puerto 8080 de forma interna. Para obtener más información, vea la sección “Proceso de detección automática inicial usando el puerto 80” más adelante en este tema.

  - **Publicado en el puerto 443**   La lista de nombres alternativos de sujeto en certificados usada por la regla de publicación de servicios web externos debe contener una entrada *lyncdiscover.\<sipdomain\>* para cada dominio SIP de su organización.

La reemisión de certificados usando una entidad de certificación interna suele ser un proceso sencillo, pero para certificados públicos usados en la regla de publicación de servicios web, puede resultar caro agregar varias entradas de nombres alternativos de sujeto. Para solucionar este problema, es posible la conexión de detección automática inicial a través del puerto 80, que a continuación se redirige al puerto 8080 en el Director o Servidor front-end.

Por ejemplo, supongamos que un cliente móvil que ejecuta Lync Mobile está configurado para iniciar sesión en Lync Server 2013 mediante la característica de detección automática usando HTTP para la solicitud inicial.

## Proceso de detección automática inicial para dispositivos móviles usando el puerto 80

1.  El dispositivo móvil que ejecuta Lync Mobile busca lyncdiscover.contoso.com usando DNS, donde hay un registro A.

2.  El DNS externo devuelve la dirección IP para los servicios web externos al cliente.

3.  El dispositivo móvil que ejecuta Lync Mobile envía la solicitud http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com al proxy inverso.

4.  La regla de publicación de web conectará la solicitud del puerto 80 de forma externa al puerto 8080 de forma interna, que la enrutará a un Director o Servidor front-end.
    
    Puesto que la solicitud es HTTP y no HTTPS, no es necesaria ninguna modificación en el certificado de la regla de publicación de los servicios web externos para admitir el servicio Detección automática.

5.  El servicio Detección automática devuelve las direcciones URL del servicio web externo (en formato HTTPS).

6.  El dispositivo móvil que ejecuta Lync Mobile puede volverse a conectar al proxy inverso en el puerto 443 y redirigirse a través del puerto 4443 al servicio de movilidad que se ejecuta en el grupo de servidores principales del usuario.
    
    Puesto que la consulta HTTPS es a la dirección URL de servicios web externos frente a la dirección URL del servicio Detección automática, se realiza correctamente porque el certificado ya deberá contener entradas de nombres alternativos de sujeto para los FQDN de servicios web externos.
    
    En este escenario, no hay cambios de certificado necesarios para admitir la movilidad.
    

    > [!NOTE]
    > Si el servidor web de destino tiene un certificado que no tiene un valor coincidente para lyncdiscover.contoso.com como valor de lista de nombres alternativos de sujeto:<BR>a. El servidor web responde con un saludo de servidor y sin certificado.<BR>b. El dispositivo móvil que ejecuta Lync Mobile termina inmediatamente la sesión.<BR>Si el servidor web de destino tiene un certificado que incluye lyncdiscover.contoso.com como valor de lista de nombres alternativos de sujeto:<BR>a. El servidor web responde con un saludo de servidor y un certificado.<BR>b. El dispositivo móvil que ejecuta Lync Mobile valida el certificado y completa el protocolo de enlace.



Para admitir una conexión inicial al servicio Detección automática usando el puerto 80 en su servidor proxy inverso, puede crear una regla de publicación http similar a este ejemplo para una regla de publicación de web de proxy inverso de Forefront Threat Management Gateway 2010:

1.  Crear una nueva regla de publicación de web (por ejemplo, **Detección automática de Lync Server (HTTP)** ).

2.  En **Nombre público**, escriba lyncdiscover.contoso.com.

3.  En la ficha **Protocolo de puente**, seleccione solo la opción para conectar solicitudes del puerto 80 al puerto 8080.

4.  En la ficha **Autenticación**, seleccione **Sin autenticación** y **El cliente no se puede autenticar directamente**.

5.  Confirme los cambios y mueva la regla al principio de la lista de reglas de Lync (primera en orden de procesamiento).

## Movilidad para la implementación de dominio dividido

Un espacio de direcciones SIP compartido, también conocido como un *dominio dividido* o una *implementación híbrida* es una configuración en la que los usuarios se implementan en toda una implementación local y en un entorno en línea. El resultado deseado es tener un usuario, independientemente de dónde se encuentre su servidor principal (in situ o en línea), para iniciar sesión en la implementación y redirigirse a la ubicación de su servidor principal. Para lograr esto, la función Detección automática de Microsoft Lync Server 2013 se utiliza para redireccionar al usuario en línea hacia la topología en línea. Esto se lleva a cabo configurando el localizador uniforme de recursos (URL) de Detección automática utilizando el Shell de administración de Lync Server y los cmdlets **Get-CsHostingProvider** y **Set-CsHostingProvider**.

Necesitará recopilar y registrar los siguientes atributos implementados:

  - Del Shell de administración de Lync Server, escriba
    
        Get-CsHostingProvider

  - En los resultados, encuentre el proveedor en línea que tenga el atributo **ProxyFQDN**. Por ejemplo, sipfed.online.lync.com

  - Registre el valor del ProxyFQDN

  - Habilite la federación en el Panel de control de Lync Server local, permitiendo la federación con el proveedor en línea

  - Habilite la federación para el proveedor en línea. De manera predeterminada, todos los usuarios en línea están habilitados para la federación de dominios y pueden comunicarse con todos los dominios

  - Si desea definir dominios restringidos y permitidos, determine de manera explícita los dominios que permitirá y los que restringirá

  - Para la federación en línea, debe planificar registros host (A o AAAA, si utiliza IPv6) de DNS, certificados y excepciones de firewall. Asimismo, debe configurar las directivas de federación. Para obtener información detallada, consulte [Planeación de federación de Lync Server y Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

