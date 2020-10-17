---
title: 'Lync Server 2013: Planeación de resistencia de voz de sitio central'
description: 'Lync Server 2013: Planeación de resistencia de voz de sitio central.'
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
ms.openlocfilehash: dd41943212459311abdb64b3ed77c918539d082d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567386"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planeación de resistencia de voz de sitio central en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-30_

Cada día con mayor frecuencia, las empresas tienen varios sitios distribuidos por todo el mundo. El mantenimiento de los servicios de emergencia, el acceso al Departamento de soporte técnico y la capacidad de llevar a cabo tareas empresariales críticas cuando un sitio central está fuera de servicio es esencial para cualquier solución de resistencia de telefonía IP empresarial. Cuando un sitio central no está disponible, es necesario que se cumplan las siguientes condiciones:

  - Debe proporcionar conmutación por error de voz.

  - Los usuarios que normalmente se registran con el grupo de servidores front-end en el sitio central deben poder registrarse con un grupo de servidores front-end alternativo. Esto puede hacerse creando varios registros SRV de DNS, cada uno de los cuales se resuelve en un grupo de directores o grupo de servidores front-end en cada uno de los sitios centrales. Puede ajustar la prioridad y los pesos de los registros SRV para que los usuarios atendidos por ese sitio central obtengan el director y el grupo de servidores front-end correspondientes antes que los de otros registros SRV.

  - Las llamadas realizadas a usuarios o desde usuarios ubicados en otros sitios se deben enrutar a través de la RTC.

En este tema se describe la solución recomendada para garantizar la resistencia de voz del sitio central.

<div>

## <a name="architecture-and-topology"></a>Arquitectura y topología

La planeación de la resistencia de voz en un sitio central requiere un conocimiento básico de la función central que desempeña el registrador de Lync Server 2013 registrador en habilitar la conmutación por error de voz. El registrador de Lync Server es un rol de servidor que permite el registro y la autenticación de clientes, y proporciona servicios de enrutamiento. Reside junto con otros componentes en un servidor Standard Edition, servidor front-end, director o aplicación de sucursal con funciones de supervivencia. Un grupo de registradores consta de los servicios de registrador que se ejecutan en el grupo de servidores front-end y residen en el mismo sitio. El grupo de servidores front-end debe tener carga equilibrada. Se recomienda un equilibrio de carga de DNS, aunque también es aceptable un equilibrio de carga de hardware. Un cliente de Lync detecta el grupo de servidores front-end mediante el siguiente mecanismo de detección:

1.  Registro DNS SRV

2.  Servicio Web de detección automática (nuevo en Lync Server 2013)

3.  Opción 120 de DHCP

Una vez que el cliente Lync se conecta al grupo de servidores front-end, el equilibrador de carga lo dirige a uno de los servidores front-end del grupo. Ese servidor front-end, a su vez, redirige al cliente a un registrador preferido del grupo.

Cada usuario habilitado para telefonía IP empresarial se asigna a un grupo de registrador concreto, que se convierte en el grupo de registrador principal del usuario. En un sitio determinado, cientos o miles de usuarios normalmente comparten un único grupo de registrador principal. Para tener en cuenta el consumo de los recursos del sitio central a través de los usuarios de cualquier sitio de sucursal que confíen en el sitio central para fines de presencia, conferencia o conmutación por error, se aconseja considerar cada usuario de sitio de sucursal teniendo en cuenta que el usuario es un usuario registrado en el sitio central. Actualmente no hay ningún límite en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con una aplicación de sucursal con funciones de supervivencia.

Para garantizar la resistencia de voz en caso de error en el sitio central, el grupo de registrador principal debe tener un solo grupo de registrador de reserva designado ubicado en otro sitio. La copia de seguridad se puede configurar mediante la configuración de resistencia del generador de topologías. Dando por supuesto que existe un vínculo WAN resistente entre los dos sitios, los usuarios cuyo grupo de registrador primario ya no está disponible se direccionan automáticamente al grupo de registrador de reserva.

En los pasos siguientes se describe el proceso de detección y registro de clientes:

1.  Un cliente detecta Lync Server a través de registros SRV de DNS. En Lync Server 2013, los registros DNS SRV se pueden configurar para que devuelvan más de un FQDN a la consulta SRV de DNS. Por ejemplo, si la empresa Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia-Pacífico) y un grupo de directores en cada sitio central, los registros del servidor DNS pueden orientarse a los FQDN de los grupos de directores de cada una de las tres ubicaciones. Siempre y cuando el grupo de directores de una de las ubicaciones esté disponible, el cliente puede conectarse al primer salto de Lync Server.
    
    <div>
    

    > [!NOTE]  
    > El uso de un grupo de directores es opcional. En su lugar, se puede usar un grupo de servidores front-end.

    
    </div>

2.  El grupo de servidores Director informa al cliente de Lync sobre el grupo de registrador principal del usuario y el grupo de registrador de reserva.

3.  El cliente de Lync intenta conectarse primero al grupo de registrador principal del usuario. Si el grupo de registrador principal está disponible, el registrador acepta el registro. Si el grupo de registrador principal no está disponible, el cliente de Lync intenta conectarse al grupo de registrador de reserva. Si el grupo de registrador de reserva está disponible y ha determinado que el grupo de registrador principal del usuario no está disponible (mediante la detección de una ausencia de latido durante un intervalo de conmutación por error determinado), el grupo de registrador de reserva acepta el registro del usuario. Una vez que el registrador de copia de seguridad detecta que el registrador principal vuelve a estar disponible, el grupo de registrador de reserva redirige los clientes de Lync de conmutación por error a su grupo principal.

La figura siguiente muestra la topología recomendada para garantizar la resistencia de un sitio central. Los dos sitios están conectados mediante un vínculo WAN resistente. Si el sitio central deja de estar disponible, los usuarios asignados a dicho grupo se dirigen al sitio de reserva para su registro.

**Topología recomendada para resistencia de voz de sitio central**

![Topología para resistencia de voz de sitio central](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topología para resistencia de voz de sitio central")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

A continuación se muestran los requisitos y las recomendaciones para implementar una resistencia de voz de sitio central adecuados para la mayoría de las organizaciones:

  - Los sitios en los que se encuentren los grupos de registrador principal y de reserva deberán estar conectados mediante un vínculo WAN resistente.

  - Cada sitio central debe contener un grupo de registrador formado por uno o varios registradores.

  - Cada grupo de registrador debe tener equilibrio de carga mediante el equilibrio de carga de DNS, el equilibrio de carga de hardware o ambos. Para obtener información detallada acerca de la planeación de la configuración del equilibrio de carga, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Cada usuario debe estar asignado a un grupo de registrador principal mediante el cmdlet **set-CsUser** del shell de administración de Lync Server o el panel de control de Lync Server.

  - El grupo de registrador principal debe tener un único grupo de registrador de reserva en otro sitio central.

  - El grupo de registrador principal se debe configurar para realizar la conmutación por error para el grupo de registrador de reserva. De forma predeterminada, el registrador principal se configura para realizar la conmutación por error para el grupo de registrador de reserva después de un intervalo de 300 segundos. Puede cambiar este intervalo mediante el generador de topologías de Lync Server 2013.

  - Configure una ruta de conmutación por error, como se describe en el tema sobre[Cómo configurar una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)en la documentación referente a la planeación. Al configurar la ruta, especifique una puerta de enlace que se encuentre en un sitio diferente al de la puerta de enlace especificada en la ruta principal.

  - Si el sitio central contenía el servidor de administración principal y es probable que el sitio no esté operativo durante un período de tiempo prolongado, tendrá que volver a instalar las herramientas de administración en el sitio de reserva; de no hacerlo así, no podrá modificar la configuración de administración.

</div>

<div>

## <a name="dependencies"></a>Dependencias

Lync Server depende de los siguientes componentes de infraestructura y software para garantizar la resistencia de voz:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Componente</strong></p></td>
<td><p><strong>Funcional</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Resolver registros de servidor y registros A para conectividad de servidor a servidor y de servidor a cliente</p></td>
</tr>
<tr class="odd">
<td><p>Exchange y servicios Web Exchange (EWS)</p></td>
<td><p>Almacenamiento de contactos; datos de calendario</p></td>
</tr>
<tr class="even">
<td><p>Mensajería unificada de Exchange y servicios Web Exchange</p></td>
<td><p>Registros de llamadas, lista de correo de voz y correo de voz</p></td>
</tr>
<tr class="odd">
<td><p>Opciones de DHCP 120</p></td>
<td><p>Si el servidor DNS no está disponible, el cliente intentará usar Opción de DHCP 120 para descubrir el registrador. Para que esto funcione, es necesario configurar un servidor DHCP o Lync Server 2013 DHCP debe estar habilitado. Para obtener más información, vea requisitos de hardware y software para Branch-Site resistencia en <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resistencia de sitios de sucursal para la sección de Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Características de voz con funciones de supervivencia

Si ha implementado los requisitos y recomendaciones anteriores, el grupo de registrador de reserva ofrecerá las siguientes características de voz:

  - Llamadas RTC realizadas

  - Llamadas RTC entrantes, si el proveedor de servicios de telefonía ofrece la posibilidad de conmutar por error a un sitio secundario.

  - Llamadas de empresa entre usuarios del mismo sitio y entre dos sitios diferentes

  - Administración básica de llamadas, incluida la retención, recuperación y transferencia de llamadas.

  - Mensajería instantánea entre dos participantes y uso compartido de audio y vídeo entre usuarios del mismo sitio

  - Servicios de desvío de llamadas, llamadas simultáneas de extremos, delegación de llamadas y llamada de equipo, pero solo si están configuradas en el mismo sitio ambas partes para la delegación de llamadas, o todos los miembros del equipo.

  - Los teléfonos y clientes existentes siguen funcionando.

  - Registro de detalles de llamadas (CDR)

  - Autenticación y autorización

En función de cómo estén configuradas, las características de voz que se indican a continuación pueden funcionar o no cuando un sitio central principal está fuera de servicio:

  - Depósito y recuperación de correos de voz
    
    Si desea hacer que la mensajería unificada de Exchange esté disponible cuando el sitio central principal esté fuera de servicio, deberá realizar una de las acciones siguientes:
    
      - Cambiar los registros de servidor DNS para que los servidores de mensajería unificada de Exchange del sitio central apunten hacia los servidores de mensajería unificada de Exchange de reserva de otro sitio.
    
      - Configure el plan de marcado de mensajería unificada de Exchange de cada usuario para incluir los servidores de MU de Exchange en el sitio central y en el sitio de copia de seguridad, pero designar los servidores de mensajería unificada de Exchange como deshabilitados. Si el sitio principal deja de estar disponible, el administrador de Exchange tiene que marcar los servidores de mensajería unificada de Exchange en el sitio de copia de seguridad como habilitado.
    
    Si ninguna de las soluciones anteriores es posible, la mensajería unificada de Exchange no estará disponible en el caso de que el sitio central deje de estar disponible.

  - Conferencias de todos los tipos
    
    Un usuario que ha experimentado una conmutación por error a un sitio de copia de seguridad se puede unir a una conferencia creada u hospedada por un organizador cuyo grupo esté disponible, pero no puede crear ni hospedar una conferencia en su propio grupo principal, que ya no está disponible. Del mismo modo, otros usuarios no se pueden unir a conferencias hospedadas en el grupo principal del usuario afectado.

Las características de voz que se indican a continuación no funcionan cuando un sitio central principal está fuera de servicio:

  - Operador automático de conferencia

  - Enrutamiento basado en DNS y presencia

  - Actualización de la configuración del desvío de llamadas

  - Servicio de grupo de respuesta y estacionamiento de llamadas

  - Aprovisionamiento de nuevos teléfonos y clientes

  - Búsqueda en la web de la libreta de direcciones

</div>

<div>

## <a name="see-also"></a>Consulte también


[Planeación de la resistencia de voz en sitios de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

