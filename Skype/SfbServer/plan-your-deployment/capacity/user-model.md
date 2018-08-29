---
title: Planificación de capacidad uso del modelo de usuario de Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: En este artículo se proporciona orientación sobre cuántos servidores necesita en un sitio para el número de usuarios en ese sitio, según el uso descrito en modelos de usuario de Skype para Business Server.
ms.openlocfilehash: 3a1838200e4590649fd290530a50fba3015b670f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261605"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Planificación de capacidad uso del modelo de usuario de Skype para Business Server

En este artículo se proporciona orientación sobre cuántos servidores necesita en un sitio para el número de usuarios en ese sitio, según el uso descrito en [modelos de usuario de Skype para Business Server](user-models.md).

> [!NOTE]
> Todas las recomendaciones de este artículo dan por supuesto que en sus servidores tiene instalado Skype Empresarial con la actualización acumulativa de noviembre de 2015 (o una versión posterior).

## <a name="tested-hardware-platform"></a>Plataforma de hardware probada

Hemos finalizado nuestras pruebas de rendimiento en el hardware que se describe en la tabla siguiente. Todas las recomendaciones y los resultados se basan en este hardware. Si decide usar un hardware de menor capacidad al que se indica aquí, tenga en cuenta que puede tener problemas de rendimiento o de funcionamiento. Estas recomendaciones de hardware son los mismos que Lync Server 2013, si es útil que (y en escenarios de actualización, puede ser).

**Hardware usado en pruebas de rendimiento**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, seis núcleos y 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no se admiten para Skype para funciones de servidor de Business Server.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> &bull;&nbsp;&nbsp;unidades de disco duro 8 o más de 10.000 RPM con al menos 72 GB de espacio libre de espacio en disco.  <br/> Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.  <br/> O BIEN   <br/> &bull;&nbsp;&nbsp;Unidades de estado sólido (SSD) que proporcionan un rendimiento similar a 8 unidades de disco mecánicas de 10.000 RPM.  <br/> |
|Disco  <br/> ||
|Red  <br/> |&bull;&nbsp;&nbsp;1 adaptador de red de doble puerto, 1 Gbps o superior (se recomiendan 2 unidades, lo que requiere la formación de equipos con una sola dirección MAC y una única dirección IP).  <br/> |

## <a name="summary-of-results"></a>Resumen de los resultados

En la tabla siguiente se resumen nuestras recomendaciones.

|**Rol de servidor**|**Cantidad máxima de usuarios admitidos**|
|:-----|:-----|
|Servidor front-end con doce servidores Front-End y un servidor Back-End o un par reflejado de servidores Back-End.  <br/> |80.000 usuarios únicos con sesión iniciada simultáneamente, más un 50% de múltiples puntos de presencia (MPOP) que representan instancias no móviles, más un 40% de los usuarios habilitados para movilidad, lo que hace un total de 152.000 extremos.  <br/> |
|Conferencia A/V  <br/> |El servicio de conferencia A/v proporcionado por un grupo de servidores Front-End admite las conferencias del grupo suponiendo un tamaño máximo de conferencia de 250 usuarios y sólo una conferencia grande al mismo tiempo.  <br/> **Nota:** Además, puede admitir grandes conferencias de entre 250 y 1000 usuarios mediante la implementación de un grupo de servidores Front-End independiente con dos servidores de Front-End para hospedar las conferencias de gran tamaño. Para obtener información detallada, consulte [Plan para reuniones grandes en Skype para Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Un servidor perimetral  <br/> |12 000 usuarios remotos simultáneos.  <br/> |
|Un Director  <br/> |12 000 usuarios remotos simultáneos.  <br/> |
|Supervisión y archivado  <br/> |Los servicios front-end de supervisión y archivado ejecutar en cada servidor Front-End, en lugar de hacerlo en roles de servidor independiente.  <br/> Los servicios de supervisión y archivado aún necesitan sus propios almacenes de base de datos. Si también ejecuta Exchange 2013 o posterior, puede conservar los datos de archivado en Exchange, en lugar de en una base de datos dedicada de SQL.  <br/> |
|Un servidor de mediación  <br/> |Servidor de mediación se combina con el servidor Front-End de ejecuciones en cada servidor Front-End en un grupo de servidores y debe proporcionar capacidad suficiente para los usuarios del grupo de servidores. Para un servidor de mediación independiente, vea la sección "Servidor de mediación" más adelante en este tema.  <br/> |
|Un servidor Standard Edition  <br/> |Recomendamos encarecidamente que si usa los servidores Standard Edition a los usuarios de host, utilice siempre dos servidores, emparejados siguiendo las recomendaciones de [planeación de alta disponibilidad y recuperación ante desastres](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Cada servidor del par puede hospedar hasta 2500 usuarios y, si uno de los servidores produce errores, el otro servidor puede admitir 5000 usuarios en un escenario de conmutación por error.  <br/>  Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede verse afectado con más de 2500 usuarios por servidor. En este caso, debe tener en cuenta agregando más servidores Standard Edition o moviendo a Skype para Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Servidor front-end

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

En un grupo de servidores Front-End, debe tener uno que servidor Front-End por cada 6.660 usuarios alojado en el grupo de servidores, suponiendo que la tecnología hyper-threading está habilitada en todos los servidores en el grupo de servidores y que el hardware del servidor cumple las recomendaciones de los requisitos de [Server de Skype para 2015 de servidor empresarial](../requirements-for-your-environment/server-requirements.md) o [requisitos del sistema para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). El número máximo de usuarios en un grupo de servidores Front-End es nuevo 80.000, suponiendo que la tecnología hyper-threading está habilitada en todos los servidores en el grupo de servidores. Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores Front-End.

Cuando calcule el número de usuarios en un grupo de servidores Front-End, incluir todos los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia en sucursales que están asociadas con este grupo de servidores Front-End.

Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente al resto de los servidores del grupo. En un escenario donde hay 30.000 usuarios y cinco servidores Front-End, si un servidor no está disponible, las conexiones de 6000 de los usuarios deben transferirse a los otros cuatro servidores restantes. Cada uno de los cuatro servidores restantes tendrá 7500 usuarios, un número superior al recomendado.

Si en su lugar había iniciado con seis servidores Front-End para los 30.000 usuarios y uno deja de estar disponible, un total de 5000 usuarios tenga que mover a los cinco servidores restantes. Cada uno de estos cinco servidores hospedará 6000 usuarios, dentro del intervalo recomendado.

El número máximo de usuarios en un grupo de servidores Front-End es 80.000. El número máximo de servidores Front-End en un grupo de servidores es 12.

Para un grupo de servidores Front-End con 80.000 usuarios, será útil para el rendimiento, en las implementaciones típicas que siga los [modelos de usuario de Skype para Business Server](user-models.md)doce servidores Front-End. Las implementaciones que se ha diseñado para admitir la conmutación por error de recuperación de desastres, se suponen que se puede hospedar un máximo de 40.000 usuarios en cada uno de los dos grupos de Front-End emparejados, en la que cada grupo de servidores tiene suficientes servidores Front-End para que contenga los usuarios de ambos grupos, si necesita un grupo de servidores se conmutan por error t o la otra.

El número de usuarios admitidos con un buen rendimiento por un determinado grupo de servidores Front-End puede diferir a estas cifras por los motivos siguientes:

- El hardware de los servidores Front-End no cumple las recomendaciones.

- Uso de la organización es muy diferente de los modelos de usuario, por ejemplo, si tiene mucho más tráfico de conferencia.

En la siguiente tabla se muestra el ancho de banda medio para mensajería instantánea y presencia, dado el modelo de usuario, según se define en [modelos de usuario de Skype para Business Server](user-models.md).

|**Ancho de banda medio por usuario**|**Requisitos de ancho de banda por cada servidor Front-End con 6.660 usuarios**|
|:-----|:-----|
|1,3 Kbps  <br/> |13 Mbps  <br/> |

> [!NOTE]
> Para mejorar el rendimiento de medios de la co-autoría encuentra A / funcionalidad de conferencia A/v y el servidor de mediación en los servidores Front-End, debe habilitar el lado de recepción (RSS) de escala en los adaptadores de red en los servidores Front-End. La RSS permite que varios procesadores en el servidor gestionen los paquetes entrantes. Para obtener información detallada, vea [Recibir del ajuste de escala (RSS) en la documentación de Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.

## <a name="conferencing-maximums"></a>Máximos de conferencia

Como el modelo de usuario que establece que el 5 % de los usuarios de un grupo puede estar en una conferencia en cualquier momento, un grupo de 80 000 usuarios podría tener unos 4000 usuarios en conferencias de forma simultánea. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de mensajería instantánea; otras, de mensajería instantánea con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay ningún límite fijo para el número real de conferencias permitidas y el uso real determinará el rendimiento real. Por ejemplo, si su organización tiene muchas más conferencias de modo mixto que se supone que en el modelo de usuario, es posible que necesite implementar más servidores Front-End o un / servidores de conferencia A/v que las recomendaciones que se encuentran en este artículo. Para obtener información detallada sobre las suposiciones en el modelo de usuario, vea [modelos de usuario de Skype para Business Server](user-models.md).

El tamaño máximo de conferencia admitidos hospedado por un Skype regular para el grupo de negocio de servidor Front-End que también hospeda a los usuarios es 250 participantes. Mientras se celebra una conferencia de 250 usuarios, el grupo puede admitir también otras conferencias, con un total del 5 % de los usuarios del grupo en conferencias simultáneas. Por ejemplo, en un grupo de servidores de doce servidores Front-End y 80.000 usuarios mientras se está realizando la conferencia de 250 usuarios, Skype para Business Server admite 3.750 otros usuarios que participan en las conferencias más pequeñas.

Independientemente del número de usuarios alojados en el grupo de servidores Front-End o un servidor Standard Edition, Skype para Business Server admite un mínimo de 125 otros usuarios que participan en las conferencias más pequeñas en el mismo grupo de servidores o el servidor que hospeda una conferencia de 250 usuarios.

Para habilitar las conferencias que tienen entre 250 y 1000 usuarios, puede configurar un grupo de servidores Front-End independiente para hospedar dichas conferencias. Este grupo de servidores Front-End no hospede a ningún usuario. Para obtener información detallada, vea [planear reuniones grandes en Skype para Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Si su organización tiene mucho más de modo mixto de conferencias que se supone que en el modelo de usuario, es posible que necesite implementar más servidores de Front-End que nos recomendación en este documento (hasta un máximo de 12 servidores Front-End). Para obtener información detallada sobre las suposiciones en el modelo de usuario, vea [modelos de usuario de Skype para Business Server](user-models.md).

## <a name="edge-server"></a>Servidor perimetral

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

Debe implementar un servidor perimetral para cada 12.000 usuarios remotos tengan acceso simultáneamente a un sitio. Como mínimo se recomienda dos servidores perimetrales para una alta disponibilidad. Estas recomendaciones se suponen que el hardware para los servidores perimetrales cumple las recomendaciones de [Plataformas de Hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Cuando calcule el número de usuarios para los servidores perimetrales, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia en sucursales que están asociadas con un grupo de servidores Front-End en este sitio.

> [!NOTE]
> Para mejorar el rendimiento del servicio perimetral de conferencia en los servidores perimetrales, debe habilitar el lado de recepción escala (RSS) en los adaptadores de red en los servidores perimetrales. La RSS permite que varios procesadores en el servidor gestionen los paquetes entrantes. Para obtener información detallada, consulte "[Recibir del ajuste de escala (RSS) en Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.

## <a name="director"></a>Director

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

Si implementa la función de servidor Director, se recomienda implementar un Director para cada 12.000 usuarios remotos tengan acceso simultáneamente a un sitio. Como mínimo se recomienda dos directores para alta disponibilidad. Estas recomendaciones se suponen que el hardware para los servidores perimetrales cumple las recomendaciones de [Plataformas de Hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Cuando calcule el número de usuarios para los directores, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia en sucursales que están asociadas con un grupo de servidores Front-End en este sitio.

## <a name="mediation-server"></a>Servidor de mediación

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

Si instala el servidor de mediación con el servidor Front-End, servidor de mediación se ejecuta en cada servidor Front-End del grupo de servidores y debe proporcionar capacidad suficiente para los usuarios del grupo de servidores.

Si implementa un grupo de servidores de mediación independiente y, a continuación, ¿cuántos servidores de mediación implementar depende de muchos factores, como el hardware usado para el servidor de mediación, el número de usuarios de VoIP tiene, el número de puerta de enlace de mismo nivel que cada grupo de servidores de mediación controles, el tráfico de hora punta a través de las puertas de enlace y el porcentaje de llamadas con medios que omite el servidor de mediación.

Las siguientes tablas proporcionan una guía para cuántos puede controlar las llamadas simultáneas a un servidor de mediación, suponiendo que el hardware para los servidores de mediación cumple los requisitos en [Plataformas de Hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) y que esté habilitada la tecnología hyper-threading. Para obtener información detallada acerca de la escalabilidad del servidor de mediación, vea [uso de voz de Estimating y el tráfico de Skype para Business Server](estimating-voice-traffic.md) e [instrucciones de implementación para el servidor de mediación en Skype para Business Server](mediation-server-deployment-guidelines.md).

Las siguientes tablas suponen uso como se resume en los [modelos de usuario de Skype para Business Server](user-models.md).

**Capacidad del servidor de mediación independiente: 70% de los usuarios internos, 30% de los usuarios externos con sin desvío capacidad de llamadas (transcodificación multimedia realizada por el servidor de mediación)**

|**Hardware de servidor**|**Número máximo de llamadas.**|**Número máximo de líneas T1**|**Número máximo de líneas E1**|
|:-----|:-----|:-----|:-----|
|Procesador dual, seis núcleos, CPU con Hyper-Threading a 2,26 GHz **con la tecnología Hyper-Threading deshabilitada**, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Aunque se utilizaron servidores con 32 GB de memoria para las pruebas de rendimiento, los servidores con 16 GB de memoria son compatibles con el servidor de mediación independiente y son suficientes para proporcionar el rendimiento que se muestra en esta tabla.

**Capacidad del servidor de mediación (servidor de mediación se combina con el servidor Front-End) capacidad de 70% usuarios internos, 30% de los usuarios externos, sin desvío de llamadas (procesamiento multimedia realizado por el servidor de mediación)**

|**Hardware de servidor**|**Número máximo de llamadas.**|
|:-----|:-----|
|Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y 4 tarjetas adaptadoras de red de 1 GB.  <br/> |150  <br/> |

> [!NOTE]
> Este número es mucho menor que los números para el servidor de mediación independiente. Que es debido a que el servidor Front-End tiene que controlar otras características y funciones para los 6600 usuarios hospedados en él, además de la transcodificación necesario para las llamadas de voz.

> [!NOTE]
> Para mejorar el rendimiento del servidor de mediación, debe habilitar el lado de recepción escala (RSS) en los adaptadores de red en los servidores de mediación. La RSS permite que varios procesadores en el servidor gestionen los paquetes entrantes. Para obtener información detallada, vea "[Receive-Side Scaling en Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.

## <a name="back-end-server"></a>Servidor back-end

Aunque gran parte de la información de la base de datos se almacena principalmente en los servidores Front-End, debe asegurarse de que los servidores Back-End cumple las recomendaciones de hardware enumeradas anteriormente en esta sección y en [Plataformas de Hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Para proporcionar una alta disponibilidad de su servidor Back-End, se recomienda implementar grupos de disponibilidad AlwaysOn o la creación de reflejo de servidor. Para obtener más información, vea [servidor Back-End de alta disponibilidad en Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Supervisión y archivado

Si implementa supervisión o archivado, la funcionalidad de front-end de estos servicios se ejecuta en Front End Servers, supervisión y archivado usan su propio almacén de base de datos de forma independiente desde el almacén de Back-End. Como alternativa, si dispone de Exchange 2013 implementado, puede almacenar datos de archivado de mensajería instantánea de Exchange en lugar de en un almacén de SQL dedicado.

En la tabla siguiente se indica cuánto almacenamiento de base de datos se necesita aproximadamente por usuario y por día para los datos de supervisión y archivado.

||**CDR (Supervisión)** <br/> |**QoE (Supervisión)** <br/> |**Archivado** <br/> |
|:-----|:-----|:-----|:-----|
|Espacio en disco necesario por usuario y por día  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Durante las pruebas de rendimiento, Microsoft usó el hardware de la tabla siguiente para el servidor de bases de datos de supervisión y archivado. Las pruebas, recopilan los datos de dos grupos de servidores Front-End, cada uno de los cuales contenía 80.000 usuarios.

**Hardware utilizado en las pruebas de rendimiento de supervisión y archivado**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior  <br/> |
|Memoria  <br/> |48 gigabytes (GB).  <br/> |
|Disco  <br/> |25 a 10.000 RPM unidades de disco duro con 300 GB en cada disco, con la configuración en la siguiente tabla  <br/> |
|Red  <br/> | 1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).  <br/> |

**Configuraciones de disco recomendadas**

|**Unidad** <br/> |**Configuración RAID** <br/> |**Número de discos** <br/> |
|:-----|:-----|:-----|
|Archivos de datos de las bases de datos de CDR, QoE y archivado, en una sola unidad  <br/> |1+0  <br/> |16  <br/> |
|Archivo de registro de la base de datos CDR  <br/> |1  <br/> |2  <br/> |
|Archivo de registro de la base de datos QoE  <br/> |1  <br/> |2  <br/> |
|Archivo de registro de la base de datos de archivado  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Capacidad del servidor de interoperabilidad vídeo

Si implementar servidor de interoperabilidad de vídeo y necesita determinar la capacidad, examine el número máximo de sistemas de teleconferencia de vídeo (VTCs) que se incluirá en llamadas simultáneas. Por ejemplo, si tiene 250 VTC en su organización y el modelo de usuario calcula que, como máximo, el 20 % de ellos estarán en llamadas simultáneas, tome como base el planeamiento de capacidad en 50 VTC simultáneos.


