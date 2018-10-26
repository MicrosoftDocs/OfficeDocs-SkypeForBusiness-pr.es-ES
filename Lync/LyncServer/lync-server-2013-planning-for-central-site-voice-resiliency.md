---
title: 'Lync Server 2013: Planeación de resistencia de voz de sitio central'
TOCTitle: Planeación de resistencia de voz de sitio central
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48275271
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación de resistencia de voz de sitio central en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada día con mayor frecuencia, las empresas tienen varios sitios distribuidos por todo el mundo. El mantenimiento de servicios de emergencia, el acceso al departamento de soporte técnico y la capacidad de realizar tareas empresariales fundamentales cuando un sitio central está fuera de servicio son esenciales para una solución de resistencia de Telefonía IP empresarial. Cuando un sitio central no está disponible, es necesario que se cumplan las siguientes condiciones:

  - Debe proporcionar conmutación por error de voz.

  - Los usuarios que normalmente se registran con el Grupo de servidores front-end en el sitio central deben poder registrarse con un Grupo de servidores front-end alternativo. Esto se puede lograr mediante la creación de varios registros de servidor DNS, cada uno de los cuales se resuelve en un Grupo de directores o un Grupo de servidores front-end de cada uno de los sitios centrales. Puede ajustar la prioridad y el peso de los registros SRV, de forma que los usuarios que reciben servicio mediante el sitio central obtengan el Director y Grupo de servidores front-end correspondiente antes que los de otros registros SRV.

  - Las llamadas realizadas a usuarios o desde usuarios ubicados en otros sitios se deben enrutar a través de la RTC.

En este tema se describe la solución recomendada para garantizar la resistencia de voz del sitio central.

## Arquitectura y topología

La planificación de la resistencia de voz en un sitio central requiere una comprensión básica del rol central que cumple el registrador de Lync Server 2013 al habilitar la conmutación por error de voz. El registrador de Lync Server es un rol de servidor que permite el registro y la autenticación de clientes y proporciona servicios de enrutamiento. Se encuentra, junto a otros componentes, en un Servidor Standard Edition, Servidor front-end, Director o Aplicación de sucursal con funciones de supervivencia. Un grupo de registrador está formado por servicios de registrador que se ejecutan en el Grupo de servidores front-end y que residen en el mismo sitio. El Grupo de servidores front-end debe estar equilibrado. Se recomienda un equilibrio de carga de DNS, aunque también es aceptable un equilibrio de carga de hardware. Un cliente de Lync detecta el Grupo de servidores front-end a través del siguiente mecanismo de detección.

1.  Registro DNS SRV

2.  Servicio web de detección automática (nuevo en Lync Server 2013)

3.  Opción 120 de DHCP

Después de que el cliente de Lync se conecta al Grupo de servidores front-end, el equilibrador de carga lo dirige a uno de los Servidores front-end del grupo. Ese Servidor front-end redirige al cliente a un registrador preferido del grupo.

Cada uno de los usuarios habilitados para Telefonía IP empresarial se asigna a un grupo de registrador concreto, que pasa a ser el grupo de registrador principal del usuario. En un sitio determinado, cientos o miles de usuarios normalmente comparten un único grupo de registrador principal. Para tener en cuenta el consumo de los recursos del sitio central a través de los usuarios de cualquier sitio de sucursal que confíen en el sitio central para fines de presencia, conferencia o conmutación por error, se aconseja considerar cada usuario de sitio de sucursal teniendo en cuenta que el usuario es un usuario registrado en el sitio central. Actualmente no hay límites con respecto al número de usuarios de sitios de sucursal, incluidos los usuarios registrados con una Aplicación de sucursal con funciones de supervivencia.

Para garantizar la resistencia de voz en caso de error en el sitio central, el grupo de registrador principal debe tener un solo grupo de registrador de reserva designado ubicado en otro sitio. Este grupo de reserva se puede configurar mediante los ajustes de resistencia de Generador de topologías. Dando por supuesto que existe un vínculo WAN resistente entre los dos sitios, los usuarios cuyo grupo de registrador primario ya no está disponible se direccionan automáticamente al grupo de registrador de reserva.

En los pasos siguientes se describe el proceso de detección y registro de clientes:

1.  Un cliente descubre Lync Server a través de registros del servidor DNS. En Lync Server 2013, los registros del servidor DNS se pueden configurar para que devuelvan más de un FQDN para la consulta del servidor DNS. Por ejemplo, si la empresa Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia-Pacífico) y un grupo de directores en cada sitio central, los registros del servidor DNS pueden orientarse a los FQDN de los grupos de directores de cada una de las tres ubicaciones. Mientras que el grupo de directores de una de las ubicaciones esté disponible, el cliente se puede conectar al primer salto Lync Server.
    

    > [!NOTE]
    > La utilización de un Grupo de directores es opcional. En su lugar puede usar un Grupo de servidores front-end.



2.  El Grupo de directores informa al cliente de Lync sobre el grupo de registrador principal del usuario y el grupo de registrador de reserva.

3.  El cliente de Lync intenta conectarse en primer lugar al grupo de registrador principal del usuario. Si el grupo de registrador principal está disponible, el registrador acepta el registro. Si no lo está, el cliente de Lync intenta conectarse al grupo de registrador de reserva. Si el grupo de registrador de reserva está disponible y ha determinado que el grupo de registrador principal del usuario no está disponible (mediante la detección de una ausencia de latido durante un intervalo de conmutación por error determinado), el grupo de registrador de reserva acepta el registro del usuario. Cuando el registrador de reserva detecta que el registrador principal vuelve a estar disponible, el grupo de registrador de reserva redirecciona los clientes de Lync de conmutación por error al grupo principal.

La figura siguiente muestra la topología recomendada para garantizar la resistencia de un sitio central. Los dos sitios están conectados mediante un vínculo WAN resistente. Si el sitio central deja de estar disponible, los usuarios asignados a dicho grupo se dirigen al sitio de reserva para su registro.

**Topología recomendada para resistencia de voz de sitio central**

![Topología de resistencia de voz para sitio central](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topología de resistencia de voz para sitio central")

## Requisitos y recomendaciones

A continuación se muestran los requisitos y las recomendaciones para implementar una resistencia de voz de sitio central adecuados para la mayoría de las organizaciones:

  - Los sitios en los que se encuentren los grupos de registrador principal y de reserva deberán estar conectados mediante un vínculo WAN resistente.

  - Cada sitio central debe contener un grupo de registrador formado por uno o varios registradores.

  - Cada grupo de registradores debe tener la carga equilibrada mediante el equilibrio de carga de DNS, el equilibrio de carga de hardware o ambos. Para obtener información detallada sobre la planeación de su configuración del equilibrio de carga, vea [Requisitos del equilibrio de carga de Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Cada usuario debe estar asignado a un grupo de registrador principal mediante el cmdlet **set-CsUser** del Shell de administración de Lync Server o desde el Panel de control de Lync Server.

  - El grupo de registrador principal debe tener un único grupo de registrador de reserva en otro sitio central.

  - El grupo de registrador principal se debe configurar para realizar la conmutación por error para el grupo de registrador de reserva. De forma predeterminada, el registrador principal se configura para realizar la conmutación por error para el grupo de registrador de reserva después de un intervalo de 300 segundos. Puede modificar este intervalo a través del Generador de topologías de Lync Server 2013.

  - Configure una ruta de conmutación por error tal como se describe en el tema " [Configurar una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md) de la documentación referente a la planeación. Al configurar la ruta, especifique una puerta de enlace que se encuentre en un sitio diferente al de la puerta de enlace especificada en la ruta principal.

  - Si el sitio central contenía el servidor de administración principal y es probable que el sitio no esté operativo durante un período de tiempo prolongado, tendrá que volver a instalar las herramientas de administración en el sitio de reserva; de no hacerlo así, no podrá modificar la configuración de administración.

## Dependencias

Lync Server depende de los siguientes componentes de software e infraestructura para garantizar la resistencia de voz:


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
<td><p>Si el servidor DNS no está disponible, el cliente intentará usar Opción de DHCP 120 para descubrir el registrador. Para esta tarea, debe haber configurado un servidor DHCP o Lync Server 2013 DHCP tiene que estar habilitado. Para más información, vea Requisitos de hardware y software para resistencia de sitios de sucursal en la sección <a href="lync-server-2013-branch-site-resiliency-requirements.md">Requisitos de resistencia de sitios de sucursal para Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


## Características de voz con funciones de supervivencia

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
    
      - Configurar el plan de marcado de Mensajería unificada de Exchange de cada usuario para que incluya servidores de Mensajería unificada de Exchange en el sitio central y en el sitio de reserva, pero designar los servidores de Mensajería unificada de Exchange de reserva como deshabilitados. Si el sitio principal deja de estar disponible, el administrador de Exchange tiene que marcar como habilitados los servidores de Mensajería unificada de Exchange del sitio de reserva.
    
    Si no se puede aplicar ninguna de las soluciones anteriores, Mensajería unificada de Exchange no estará disponible en el caso de que el sitio central deje de estar disponible.

  - Conferencias de todos los tipos
    
    Un usuario que ha experimentado una conmutación por error a un sitio de copia de seguridad se puede unir a una conferencia creada u hospedada por un organizador cuyo grupo esté disponible, pero no puede crear ni hospedar una conferencia en su propio grupo principal, que ya no está disponible. Del mismo modo, otros usuarios no se pueden unir a conferencias hospedadas en el grupo principal del usuario afectado.

Las características de voz que se indican a continuación no funcionan cuando un sitio central principal está fuera de servicio:

  - Operador automático de conferencia

  - Enrutamiento basado en DNS y presencia

  - Actualización de la configuración del desvío de llamadas

  - Servicio de grupo de respuesta y estacionamiento de llamadas

  - Aprovisionamiento de nuevos teléfonos y clientes

  - Búsqueda en la web de la libreta de direcciones

## Vea también

#### Otros recursos

[Planificar la resistencia de voz en sitios de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

