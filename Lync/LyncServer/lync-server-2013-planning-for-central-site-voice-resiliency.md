---
title: 'Lync Server 2013: Planeación de resistencia de voz de sitio central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbeda869c078e6adfce18088545428170b356980
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planeación de resistencia de voz de sitio central en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-30_

Cada vez más, las empresas tienen varios sitios diseminados por todo el mundo. El mantenimiento de los servicios de emergencia, el acceso al Departamento de soporte técnico y la capacidad de realizar tareas críticas empresariales cuando un sitio central está fuera de servicio es esencial para cualquier solución de resiliencia de telefonía empresarial. Cuando un sitio central deja de estar disponible, se deben cumplir las condiciones siguientes:

  - Debe proporcionarse la conmutación por error.

  - Los usuarios que normalmente se registran con el grupo de servidores front-end en el sitio central deben poder registrarse con un grupo de servidores front-end alternativo. Esto puede hacerse creando varios registros SRV de DNS, cada uno de los cuales se resuelve en un grupo de directores o grupo de servidores front-end en cada uno de sus sitios centrales. Puede ajustar la prioridad y los pesos de los registros SRV para que los usuarios atendidos por ese sitio central obtengan el director y el grupo de servidores front-end correspondiente antes que los de otros registros SRV.

  - Las llamadas entre usuarios que se encuentren en otros sitios deben ser redirigidas a la RTC.

En este tema se describe la solución recomendada para proteger la resistencia de voz del sitio central.

<div>

## <a name="architecture-and-topology"></a>Arquitectura y topología

La planificación de resistencia de voz en un sitio central requiere un conocimiento básico del rol central que desempeña el registrador de Lync Server 2013 registrador en habilitar la conmutación por error de voz. El registrador de Lync Server es un rol de servidor que permite la autenticación y el registro de clientes, y proporciona servicios de enrutamiento. Se encuentra junto con otros componentes en un servidor Standard Edition, un servidor front-end, un director o un equipo de sucursales con la supervivencia. Un grupo de registradores consta de registrar servicios que se ejecutan en el grupo de servidores front-end y que residen en el mismo sitio. El grupo de servidores front-end debe tener equilibrio de carga. Se recomienda el equilibrio de carga de DNS, pero el equilibrio de carga de hardware es aceptable. Un cliente de Lync detecta el grupo de servidores front-end mediante el siguiente mecanismo de detección:

1.  Registro SRV de DNS

2.  Servicio Web de descubrimiento automático (nuevo en Lync Server 2013)

3.  Opción de DHCP 120

Después de que el cliente Lync se conecte al grupo de servidores front-end, lo dirigirá el equilibrador de carga a uno de los servidores front-end en el grupo. Ese servidor front-end, a su vez, redirige al cliente a un registrador preferido en el grupo.

Cada usuario habilitado para telefonía IP se asigna a un grupo de registrador concreto, que se convierte en el grupo de registrador principal de ese usuario. En un sitio determinado, cientos o miles de usuarios suelen compartir un único grupo de servidores principal. Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios de un sitio de sucursal que dependen del sitio central para la presencia, la Conferencia o la conmutación por error, le recomendamos que considere a cada usuario del sitio de sucursal como si el usuario fuera un usuario registrado con el sitio central. Por el momento, no hay límites en el número de usuarios de la sucursal, incluidos los registrados en un equipo de sucursales con la supervivencia.

Para garantizar la resistencia de voz en el caso de que se produzca un error en un sitio central, el grupo de registrador principal debe tener un único grupo de registrador de copia de seguridad ubicado en otro sitio. La copia de seguridad se puede configurar con la configuración de resistencia del generador de topología. Suponiendo un vínculo WAN resistente entre los dos sitios, los usuarios cuyo grupo principal ya no esté disponible se dirigen automáticamente al grupo de registro de la copia de seguridad.

Los pasos siguientes describen el proceso de detección y registro de clientes:

1.  Un cliente Descubre Lync Server a través de registros SRV de DNS. En Lync Server 2013, los registros SRV de DNS se pueden configurar para que devuelvan más de un FQDN a la consulta SRV de DNS. Por ejemplo, si Enterprise Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia Pacífico) y un grupo de directores en cada sitio central, los registros SRV de DNS pueden apuntar a los FQDN del grupo de directores en cada una de las tres ubicaciones. Siempre que el grupo de directores esté disponible en una de las ubicaciones, el cliente puede conectarse al primer salto de Lync Server.
    
    <div>
    

    > [!NOTE]  
    > El uso de un grupo de directores es opcional. En su lugar, se puede usar un grupo de servidores front-end.

    
    </div>

2.  El grupo de directores informa al cliente de Lync sobre el grupo de registradores principal del usuario y el grupo de registro de la copia de seguridad.

3.  En primer lugar, el cliente de Lync intenta conectarse al grupo de registrador principal del usuario. Si el registrador principal está disponible, el registrador acepta el registro. Si el registrador principal del registrador no está disponible, el cliente de Lync intenta conectarse al grupo de registro de la copia de seguridad. Si el grupo de registro de la copia de seguridad está disponible y ha determinado que el registrador principal del usuario no está disponible (al detectar la falta de latido para un intervalo de conmutación por error especificado) el grupo de registro de la copia de seguridad acepta el registro del usuario. Después de que el registrador de la copia de seguridad detecta que el registrador principal está de nuevo disponible, el grupo de registro de la copia de seguridad redirigirá los clientes de Lync a su grupo principal.

La siguiente ilustración muestra la topología recomendada para garantizar una resistencia de sitio central. Los dos sitios están conectados mediante un vínculo WAN resistente. Si el sitio central no está disponible, los usuarios asignados a ese grupo se dirigen al sitio de copia de seguridad para su registro.

**Topología recomendada para resistencia de voz de sitio central**

![Topología de resistencia de voz para sitio central](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topología de resistencia de voz para sitio central")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Los siguientes requisitos y recomendaciones para implementar la resistencia de voz de sitio central son adecuados para la mayoría de las organizaciones:

  - Los sitios en los que residen los grupos principal y de registro de la entidad de seguridad deben conectarse con un vínculo WAN resistente.

  - Cada sitio central debe contener un grupo de registradores formado por uno o varios registradores.

  - Cada grupo de registrador debe tener equilibrio de carga mediante el equilibrio de carga de DNS, el equilibrio de carga de hardware o ambos. Para obtener información detallada sobre cómo planear la configuración del equilibrio de carga, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Cada usuario debe estar asignado a un grupo de registrador principal mediante el cmdlet **de Shell Set-CsUser** del shell de administración de Lync Server o el panel de control de Lync Server.

  - El grupo de registrador principal debe tener un único grupo de registradores de copia de seguridad ubicado en un sitio central diferente.

  - El grupo de registrador principal debe configurarse para conmutar por error al grupo de registro de la copia de seguridad. De forma predeterminada, el registrador principal se establece para migrar tras un intervalo de 300 segundos. Puede cambiar este intervalo mediante el generador de topología de Lync Server 2013.

  - Configure una ruta de conmutación por error, como se describe en el tema "[configuración de una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" en la documentación de planificación. Al configurar la ruta, especifique una puerta de enlace que se encuentre en un sitio diferente de la puerta de enlace especificada en la ruta principal.

  - Si el sitio central contenía su servidor de administración principal y es probable que el sitio esté inactiva durante un período prolongado, tendrá que volver a instalar las herramientas de administración en el sitio de copia de seguridad. de lo contrario, no podrá cambiar ninguna configuración de administración.

</div>

<div>

## <a name="dependencies"></a>Dependencias

Lync Server depende de los siguientes componentes de infraestructura y software para garantizar la resistencia de la voz:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Componente</strong></p></td>
<td><p><strong>Funcionan</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Resolver registros SRV y A para la conectividad de servidor-servidor y servidor-cliente</p></td>
</tr>
<tr class="odd">
<td><p>Exchange y Exchange Web Services (EWS)</p></td>
<td><p>Almacenamiento de contactos; datos de calendario</p></td>
</tr>
<tr class="even">
<td><p>Mensajería unificada de Exchange y servicios Web de Exchange</p></td>
<td><p>Registros de llamadas, lista de correo de voz, correo de voz</p></td>
</tr>
<tr class="odd">
<td><p>Opciones de DHCP 120</p></td>
<td><p>Si SRV de DNS no está disponible, el cliente intentará usar la opción 120 de DHCP para descubrir el registrador. Para que esto funcione, se debe configurar un servidor DHCP o Lync Server 2013 DHCP debe estar habilitado. Para obtener más información, vea requisitos de hardware y software para la resistencia a sitios de sucursal en <a href="lync-server-2013-branch-site-resiliency-requirements.md">la sección requisitos de resistencia de sitios de sucursales para Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Características de voz revivientes

Si se han implementado los requisitos y las recomendaciones anteriores, el grupo de registro de la copia de seguridad proporcionará las siguientes características de voz:

  - Llamadas RTC salientes

  - Llamadas RTC entrantes, si el proveedor de servicios de telefonía admite la posibilidad de migrar por error a un sitio de copia de seguridad

  - Llamadas empresariales entre usuarios en el mismo sitio y entre dos sitios diferentes

  - Manejo básico de llamadas, que incluye la llamada en espera, la recuperación y la transferencia

  - Mensajería instantánea de dos participantes y uso compartido de audio y vídeo entre usuarios del mismo sitio

  - Desvío de llamadas, llamadas simultáneas a puntos de conexión, Delegación de llamadas y servicios de llamada de equipo, pero solo si las dos partes para llamar a la delegación o todos los miembros del equipo, se configuran en el mismo sitio.

  - Los teléfonos y clientes existentes siguen funcionando.

  - Registro detallado de llamadas (CDR)

  - Autenticación y autorización

Según el modo en que estén configuradas, las siguientes características de voz pueden funcionar o no cuando un sitio central principal está fuera de servicio:

  - Depósito y recuperación de correo de voz
    
    Si desea que la mensajería unificada de Exchange esté disponible cuando el sitio central principal está fuera de servicio, debe realizar una de las siguientes acciones:
    
      - Cambie los registros SRV de DNS para que los servidores de mensajería unificada de Exchange en el sitio central apunten a la copia de seguridad de los servidores MU de otro sitio.
    
      - Configure el plan de marcado de MU de Exchange de cada usuario para incluir servidores MU de Exchange en el sitio central y en el sitio de copia de seguridad, pero designe los servidores de Exchange UM como deshabilitados. Si el sitio primario no está disponible, el administrador de Exchange tiene que marcar los servidores de mensajería unificada de Exchange en el sitio de copia de seguridad como habilitado.
    
    Si ninguna de las soluciones anteriores es posible, la mensajería unificada de Exchange no estará disponible en caso de que el sitio central deje de estar disponible.

  - Conferencias de todos los tipos
    
    Un usuario que conmuta por error a un sitio de copia de seguridad puede unirse a una conferencia creada o hospedada por un organizador cuyo grupo está disponible, pero no puede crear ni hospedar una conferencia en su propio grupo principal, que ya no está disponible. De forma similar, otros usuarios no pueden unirse a conferencias hospedadas en el grupo primario del usuario afectado.

Las siguientes características de voz no funcionan cuando un sitio central principal está fuera de servicio:

  - Operador automático de conferencia

  - Presencia y enrutamiento basado en DND

  - Actualización de la configuración del desvío de llamadas

  - Servicio de grupo de respuesta y Parque de llamadas

  - Aprovisionamiento de nuevos teléfonos y clientes

  - Búsqueda en Internet de la libreta de direcciones

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificar la resistencia de voz en sitios de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

