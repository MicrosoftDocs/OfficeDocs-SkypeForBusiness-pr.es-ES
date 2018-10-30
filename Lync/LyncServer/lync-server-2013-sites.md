---
title: Sitios de Lync Server 2013
TOCTitle: Sitios
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48274243
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sitios de Lync Server para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-16_

En Lync Server, define *sitios* en la red que contienen componentes de Lync Server. Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad. Tenga en cuenta que los sitios de Lync Server son un concepto independiente de los sitios de Servicios de dominio de Active Directory y los sitios de Microsoft Exchange Server. Sus sitios de Lync Server no tienen que corresponder con sus sitios de Active Directory.

## Tipos de sitio

Cada uno de los sitios es un *sitio central* que contiene, como mínimo, un Grupo de servidores front-end o un Servidor Standard Edition, o bien una *sucursal* . Cada una de las sucursales está asociada exactamente a un sitio central, y los usuarios del sitio central obtienen la mayoría de sus funciones de Lync Server de los servidores del sitio central asociado.

Cada una de las sucursales contiene uno de los siguientes elementos:

  - Una *aplicación de sucursal con funciones de supervivencia (SBA)* , que es un servidor blade estándar del sector con un servidor de registrador y mediación de Lync Server que se ejecuta en Windows Server. La Aplicación de sucursal con funciones de supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). La Aplicación de sucursal con funciones de supervivencia está diseñada para sitios de sucursal con un número comprendido entre 25 y 1000 usuarios.

  - Un *servidor de sucursal con funciones de supervivencia (SBS)* , que es un servidor que ejecuta Windows Server que cumple requisitos de hardware específicos, y que tiene el software del servidor de mediación y registrador Lync Server instalado. Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos. El servidor de sucursal con funciones de supervivencia está diseñado para sucursales de entre 1.000 y 5.000 usuarios.

  - Una puerta de enlace RTC y, opcionalmente, un *servidor de mediación* . Para obtener detalles sobre este y otros roles de servidor, vea [Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md).

Una sucursal con un vínculo de red de área extensa (WAN) resistente hacia un sitio central puede usar la tercera opción: una puerta de enlace RTC y, opcionalmente, un servidor de mediación. Los sitios de sucursal con vínculos menos resistentes deberán usar una Aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, lo que le proporcionará resistencia en los momentos en que la red de área extensa falle. Por ejemplo, en un sitio con una Aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia instalado, los usuarios pueden seguir realizando y recibiendo llamadas de Enterprise Voice si la WAN que conecta la sucursal con el sitio central está fuera de servicio. Para obtener más información acerca de la Aplicación de sucursal con funciones de supervivencia, el servidor de sucursal con funciones de supervivencia y la resistencia, consulte [Planear la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) en la documentación de planeación.

## Topología de sitios

La implementación debe incluir un sitio central como mínimo, y puede incluir de ninguna a muchas sucursales. Cada una de las sucursales está afiliada a un sitio central. El sitio central proporciona a la sucursal los servicios de Lync Server que no se hospedan localmente en la sucursal, como, por ejemplo, de presencia y de conferencia.

Si tiene varios sitios, puede emparejar los grupos de servidores de front-end en diferentes sitios para habilitar capacidades de recuperación ante desastres. Para obtener detalles, vea [Compatibilidad entre la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

## Vea también

#### Conceptos

[Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md)  
[Compatibilidad entre la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  

#### Otros recursos

[Planear la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

