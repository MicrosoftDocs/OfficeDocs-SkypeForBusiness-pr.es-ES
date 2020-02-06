---
title: Planificación de capacidad de uso de modelo de usuario para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Este artículo proporciona instrucciones sobre cuántos servidores necesita en un sitio para el número de usuarios de ese sitio, según el uso descrito en modelos de usuario en Skype empresarial Server.
ms.openlocfilehash: 401dcb06940f9ae0735107f533d609481e3b3182
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816049"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Planificación de capacidad de uso de modelo de usuario para Skype empresarial Server

Este artículo proporciona instrucciones sobre cuántos servidores necesita en un sitio para el número de usuarios de ese sitio, según el uso descrito en modelos de [usuario en Skype empresarial Server](user-models.md).

> [!NOTE]
> Todas las recomendaciones de este artículo dan por supuesto que en sus servidores tiene instalado Skype Empresarial con la actualización acumulativa de noviembre de 2015 (o una versión posterior).

## <a name="tested-hardware-platform"></a>Plataforma de hardware probada

Hemos finalizado nuestras pruebas de rendimiento en el hardware que se describe en la tabla siguiente. Todas las recomendaciones y los resultados se basan en este hardware. Si decide usar un hardware de menor capacidad al que se indica aquí, tenga en cuenta que puede tener problemas de rendimiento o de funcionamiento. Estas recomendaciones de hardware son las mismas que las de Lync Server 2013, si es útil (y en escenarios de actualización, puede ser).

**Hardware usado en pruebas de rendimiento**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, seis núcleos y 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de servidor de Skype empresarial Server.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |8 o más unidades de disco duro de 10 000 RPM con al menos 72 GB de espacio libre en disco. Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.  <br/> O BIEN  <br/>Unidades de estado sólido (SSDs) que proporcionan un rendimiento similar a las unidades de disco mecánicas de 8 10.000 a RPM. <br/> |
|Red  <br/> |1 adaptador de red de puerto doble, 1 Gbps o superior (recomendado: 2, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).  <br/> |

## <a name="summary-of-results"></a>Resumen de los resultados

En la tabla siguiente se resumen nuestras recomendaciones.

|**Rol de servidor**|**Cantidad máxima de usuarios admitidos**|
|:-----|:-----|
|Grupo front-end con doce servidores front-end y un servidor back-end o un par espejeado de servidores back end.  <br/> |80.000 usuarios únicos con sesión iniciada simultáneamente, más un 50% de múltiples puntos de presencia (MPOP) que representan instancias no móviles, más un 40% de los usuarios habilitados para movilidad, lo que hace un total de 152.000 extremos.  <br/> |
|Conferencia A/V  <br/> |El servicio de conferencia A/V suministrado por un grupo de servidores front-end admite las conferencias de la agrupación suponiendo un tamaño máximo de conferencia de usuarios de 250 y solo una de estas conferencias de gran tamaño.  <br/> **Nota:** Además, puede admitir conferencias grandes de usuarios de 250 y 1000 implementando un grupo de servidores front-end independiente con dos servidores front-end para hospedar las grandes conferencias. Para obtener más información, vea [planear reuniones grandes en Skype empresarial Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Un servidor perimetral  <br/> |12 000 usuarios remotos simultáneos.  <br/> |
|Un director  <br/> |12 000 usuarios remotos simultáneos.  <br/> |
|Supervisión y archivado  <br/> |Los servicios front-end de supervisión y archivado se ejecutan en cada servidor front-end, en lugar de en roles de servidor diferentes.  <br/> Los servicios de supervisión y archivado aún necesitan sus propios almacenes de base de datos. Si también ejecuta Exchange 2013 o una versión posterior, puede mantener los datos de archivado en Exchange, en lugar de en una base de datos SQL dedicada.  <br/> |
|Un servidor de mediación  <br/> |El servidor de mediación en el servidor front-end se ejecuta en todos los servidores front end de un grupo y debe proporcionar la capacidad suficiente para los usuarios del grupo. Para el servidor de mediación independiente, consulte la sección "servidor de media", más adelante en este mismo tema.  <br/> |
|Un servidor Standard Edition  <br/> |Recomendamos encarecidamente que si usa servidores Standard Edition para hospedar usuarios, siempre use dos servidores, emparejados con las recomendaciones de [planeación de alta disponibilidad y recuperación ante desastres](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Cada servidor del par puede hospedar hasta 2500 usuarios y, si uno de los servidores produce errores, el otro servidor puede admitir 5000 usuarios en un escenario de conmutación por error.  <br/>  Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede verse afectado con más de 2500 usuarios por servidor. En este caso, debe considerar la posibilidad de agregar servidores Standard Edition o de ir a Skype empresarial Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Servidor front-end

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

En un grupo de servidores front-end, debe disponer de un servidor front-end para cada 6.660 usuarios alojados en su grupo, suponiendo que Hyper-Threading está habilitado en todos los servidores del grupo, y que el hardware del servidor cumpla con las recomendaciones de [servidor para Skype empresarial server 2015](../requirements-for-your-environment/server-requirements.md) o [requisitos del sistema para skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md). La cantidad máxima de usuarios de un grupo de servidores front-end es de 80.000, suponiendo que Hyper-Threading está habilitado en todos los servidores de su grupo. Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores front-end.

Si tiene en cuenta el número de usuarios de un grupo de servidores front-end, incluya a los usuarios alojados en los equipos de las sucursales y los servidores de sucursal que sean revivientes y que estén asociados a este grupo de servidores front-end.

Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente al resto de los servidores del grupo. En un escenario en el que haya 30.000 usuarios y cinco servidores front-end, si un servidor no está disponible, las conexiones de 6000 de los usuarios deberán transferirse a los otros cuatro servidores restantes. Cada uno de los cuatro servidores restantes tendrá 7500 usuarios, un número superior al recomendado.

Si en su lugar ha empezado con seis servidores front-end para los usuarios de 30.000 y uno no está disponible, un total de 5000 usuarios deben ir a los cinco servidores restantes. Cada uno de estos cinco servidores hospedará 6000 usuarios, dentro del intervalo recomendado.

El número máximo de usuarios en un grupo de servidores front-end es de 80.000. La cantidad máxima de servidores frontales en un grupo es de 12.

En el caso de un grupo de servidores front-end con usuarios de 80.000, doce servidores front-end serán buenos para el rendimiento, en las implementaciones típicas que siguen los [modelos de usuario de Skype empresarial Server](user-models.md). Las implementaciones diseñadas para admitir la conmutación por error de recuperación ante desastres suponen que se puede hospedar un máximo de 40.000 usuarios en cada uno de los dos grupos de aplicaciones para usuario emparejados, en el que cada grupo tiene suficientes servidores front-end para contener los usuarios de ambos grupos, en caso de que un grupo necesite realizar una migración tras error o la otra.

El número de usuarios admitidos por un buen rendimiento de un grupo de servidores front-end determinado puede diferir de estos números por los siguientes motivos:

- El hardware de los servidores de aplicaciones para el usuario no cumple con las recomendaciones.

- El uso de su organización es muy diferente de los modelos de usuario, por ejemplo, si tiene mucho más tráfico de conferencia.

En la tabla siguiente se muestra el ancho de banda medio para mensajería instantánea y presencia, dado el modelo de usuario, según se define en [modelos de usuario en Skype empresarial Server](user-models.md).

|**Ancho de banda medio por usuario**|**Requisitos de ancho de banda por servidor front-end con usuarios de 6.660**|
|:-----|:-----|
|1,3 Kbps  <br/> |13 Mbps  <br/> |

> [!NOTE]
> Para mejorar el rendimiento de los medios de la funcionalidad de servidor de mediación y conferencias A/V, en los servidores front-end, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores front-end. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte [Receive Side Scaling (RSS) en la documentación de Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.

## <a name="conferencing-maximums"></a>Máximos de conferencia

Como el modelo de usuario que establece que el 5 % de los usuarios de un grupo puede estar en una conferencia en cualquier momento, un grupo de 80 000 usuarios podría tener unos 4000 usuarios en conferencias de forma simultánea. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de mensajería instantánea; otras, de mensajería instantánea con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay ningún límite fijo para el número real de conferencias permitidas y el uso real determinará el rendimiento real. Por ejemplo, si su organización tiene muchas más conferencias de modo mixto de lo que se supone en el modelo de usuario, es posible que tenga que implementar más servidores front-end o servidores de conferencia A/V con las recomendaciones de este artículo. Para obtener más información sobre los supuestos en el modelo de usuario, consulte [modelos de usuario en Skype empresarial Server](user-models.md).

El máximo tamaño admitido de conferencia hospedado por un grupo de servidores front-end de Skype empresarial normal, que también hospeda usuarios, es de 250 participantes. Mientras se celebra una conferencia de 250 usuarios, el grupo puede admitir también otras conferencias, con un total del 5 % de los usuarios del grupo en conferencias simultáneas. Por ejemplo, en un grupo de doce servidores front-end y usuarios de 80.000, mientras se celebra la Conferencia 250-User, Skype empresarial Server admite 3.750 usuarios que participen en conferencias más pequeñas.

Independientemente del número de usuarios alojados en el grupo de servidores front-end o del servidor Standard Edition, Skype empresarial Server admite un mínimo de 125 otros usuarios que participan en conferencias más pequeñas en el mismo Pool o servidor que hospeda una conferencia 250-usuario.

Para habilitar las conferencias que tienen entre 250 y 1000 usuarios, puede configurar un grupo de servidores front-end independiente solo para hospedar esas conferencias. Este grupo de servidores front-end no alojará ningún usuario. Para obtener más información, vea [plan para reuniones grandes en Skype empresarial Server](../../plan-your-deployment/conferencing/large-meetings.md).

Si su organización tiene muchas más conferencias de modo mixto de lo que se supone en el modelo de usuario, es posible que tenga que implementar más servidores front-end de los que recomendamos en este documento (hasta un límite de 12 servidores front-end). Para obtener más información sobre los supuestos en el modelo de usuario, consulte [modelos de usuario en Skype empresarial Server](user-models.md).

## <a name="edge-server"></a>Servidor perimetral

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

Debe implementar un servidor perimetral para cada 12.000 usuarios remotos que tengan acceso a un sitio al mismo tiempo. Como mínimo, recomendamos dos servidores perimetrales para una alta disponibilidad. En estas recomendaciones se supone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Cuando tenga en cuenta el número de usuarios de los servidores perimetrales, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y los servidores de sucursal con la supervivencia que están asociados a un grupo de servidores front-end en este sitio.

> [!NOTE]
> Para mejorar el rendimiento del servicio perimetral de conferencia A/V en los servidores perimetrales, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores perimetrales. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte "[recibir escala de la cara (RSS) en Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.

## <a name="director"></a>Director

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

Si implementa el rol de servidor Director, se recomienda implementar un director por cada 12.000 usuarios remotos que tengan acceso a un sitio al mismo tiempo. Como mínimo, recomendamos dos directores para una alta disponibilidad. En estas recomendaciones se supone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Cuando tenga en cuenta la cantidad de usuarios para los directores, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y en los servidores de sucursal con la supervivencia que están asociados a un grupo de servidores front-end en este sitio.

## <a name="mediation-server"></a>Servidor de mediación

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor.

Si Collocate Server Mediation with front end Server, Media Server se ejecuta en todos los servidores front end del grupo y debe proporcionar la capacidad suficiente para los usuarios del grupo.

Si implementa un grupo de servidores de mediación independiente, entonces la cantidad de servidores de mediación que se van a implementar depende de muchos factores, incluido el hardware usado para el servidor de mediación, el número de usuarios de VoIP que tiene, el número de puertas de enlace y el número de puertas de enlace de cada grupo de servidores de mediación controles, el tráfico de horas ocupado a través de estas puertas de enlace y el porcentaje de llamadas con medios que omiten el servidor de mediación.

En las siguientes tablas se ofrecen instrucciones sobre cuántas llamadas simultáneas puede controlar un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumpla los requisitos de las [plataformas de hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) y que la tecnología Hyper-Threading esté habilitada. Para obtener más información sobre la escalabilidad del servidor de mediación, consulte [estimar el uso de voz y el tráfico de Skype empresarial Server](estimating-voice-traffic.md) y las [pautas de implementación para el servidor de mediación en Skype empresarial Server](mediation-server-deployment-guidelines.md).

En todas las tablas siguientes se supone que el uso está resumido en [modelos de usuario en Skype empresarial Server](user-models.md).

**Capacidad de servidor de mediación independiente: 70% usuarios internos, 30% usuarios externos con capacidad de llamada sin derivación (transcodificación multimedia realizada por el servidor de mediación)**

|**Hardware de servidor**|**Número máximo de llamadas.**|**Número máximo de líneas T1**|**Número máximo de líneas E1**|
|:-----|:-----|:-----|:-----|
|Procesador dual, seis núcleos, CPU con Hyper-Threading a 2,26 GHz **con la tecnología Hyper-Threading deshabilitada**, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Aunque los servidores con 32 GB de memoria se usan para pruebas de rendimiento, los servidores con 16 GB de memoria son compatibles con el servidor de mediación independiente y son suficientes para proporcionar el rendimiento que se muestra en esta tabla.

**Capacidad del servidor de mediación (servidor de mediación en el servidor front-end) 70% usuarios internos, 30% de los usuarios externos, capacidad de llamada sin omisión (procesamiento de multimedia realizado por el servidor de mediación)**

|**Hardware de servidor**|**Número máximo de llamadas.**|
|:-----|:-----|
|Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y 4 tarjetas adaptadoras de red de 1 GB.  <br/> |150  <br/> |

> [!NOTE]
> Este número es mucho menor que los números para el servidor de mediación independiente. Esto se debe a que el servidor front-end tiene que manejar otras características y funciones para los usuarios de 6600 alojados en ella, además de la transcodificación necesaria para las llamadas de voz.

> [!NOTE]
> Para mejorar el rendimiento del servidor de mediación, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores de mediación. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte "[escala del lado de recepción en Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.

## <a name="back-end-server"></a>Servidor back-end

Aunque gran parte de la información de la base de datos se almacena principalmente en los servidores de aplicaciones para el usuario, debe asegurarse de que los servidores de servicios de fondo cumplen las recomendaciones de hardware enumeradas anteriormente en esta sección y en [plataformas de hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Para ofrecer una alta disponibilidad de su servidor back-end, se recomienda implementar los grupos de disponibilidad AlwaysOn o el reflejo de servidor. Para más información, vea [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Supervisión y archivado

Si implementa la supervisión o el archivado, la funcionalidad front-end de estos servicios se ejecuta en los servidores front-end, la supervisión y el archivado usan su propia tienda de bases de datos, independiente de la tienda back-end. Como alternativa, si tiene Exchange 2013 implementado, puede almacenar datos de archivado de mensajes instantáneos en Exchange en lugar de en una tienda SQL dedicada.

En la tabla siguiente se indica cuánto almacenamiento de base de datos se necesita aproximadamente por usuario y por día para los datos de supervisión y archivado.

||**CDR (Supervisión)** <br/> |**QoE (Supervisión)** <br/> |**Archivado** <br/> |
|:-----|:-----|:-----|:-----|
|Espacio en disco necesario por usuario y por día  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Durante las pruebas de rendimiento, Microsoft usó el hardware de la tabla siguiente para el servidor de bases de datos de supervisión y archivado. Las pruebas recopilaron los datos de dos grupos de servidores front-end, cada uno de los cuales contiene 80.000 usuarios.

**Hardware utilizado en las pruebas de rendimiento de supervisión y archivado**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior  <br/> |
|Memoria  <br/> |48 gigabytes (GB).  <br/> |
|Disco  <br/> |unidades de disco duro de 25 10.000 a RPM con 300 GB en cada disco, con la configuración de la tabla siguiente  <br/> |
|Red  <br/> | 1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).  <br/> |

**Configuraciones de disco recomendadas**

|**Unidad** <br/> |**Configuración RAID** <br/> |**Número de discos** <br/> |
|:-----|:-----|:-----|
|Archivos de datos de las bases de datos de CDR, QoE y archivado, en una sola unidad  <br/> |1+0  <br/> |apartado  <br/> |
|Archivo de registro de la base de datos CDR  <br/> |1  <br/> |1  <br/> |
|Archivo de registro de la base de datos QoE  <br/> |1  <br/> |1  <br/> |
|Archivo de registro de la base de datos de archivado  <br/> |1  <br/> |1  <br/> |

## <a name="video-interop-server-capacity"></a>Capacidad del servidor de interoperabilidad de vídeo

Si implementas el servidor de interoperabilidad de vídeo y necesitas determinar la capacidad, puedes observar la cantidad máxima de sistemas de videoconferencias de video (VTCs) que estarán en llamadas simultáneas. Por ejemplo, si tiene 250 VTC en su organización y el modelo de usuario calcula que, como máximo, el 20 % de ellos estarán en llamadas simultáneas, tome como base el planeamiento de capacidad en 50 VTC simultáneos.


