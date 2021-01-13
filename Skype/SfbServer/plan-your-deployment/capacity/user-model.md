---
title: Uso del modelo de usuario de planeación de capacidad para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: En este artículo se proporcionan instrucciones sobre cuántos servidores necesita en un sitio para el número de usuarios de ese sitio, de acuerdo con el uso descrito en modelos de usuario en Skype Empresarial Server.
ms.openlocfilehash: e0b145ddfc766ba7db9012d4f3aaa7333f4f5d72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827640"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Uso del modelo de usuario de planeación de capacidad para Skype Empresarial Server

En este artículo se proporcionan instrucciones sobre cuántos servidores necesita en un sitio para el número de usuarios de ese sitio, de acuerdo con el uso descrito en modelos de usuario en [Skype Empresarial Server.](user-models.md)

> [!NOTE]
> Todas las recomendaciones de este artículo suponen que ha instalado la actualización acumulativa de Skype Empresarial, noviembre de 2015 o posterior en sus servidores.

## <a name="tested-hardware-platform"></a>Plataforma de hardware probada

Hemos realizado nuestras pruebas de rendimiento en el hardware que se describe en la tabla siguiente. Todas nuestras recomendaciones y resultados se basan en este hardware. Si decides usar un hardware menos eficaz que el que aparece aquí, ten en cuenta que puedes enfrentarte a problemas de funcionalidad o a un rendimiento deficiente. Estas recomendaciones de hardware son las mismas que lync Server 2013, si es útil (y en escenarios de actualización, puede ser).

**Hardware usado en las pruebas de rendimiento**

|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, núcleo hexadecimal, 2,26 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles con los roles de servidor de Skype Empresarial Server.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |8 o más unidades de disco duro de 10 000 RPM con al menos 72 GB de espacio libre en disco. Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.  <br/> O bien: <br/>Unidades de estado sólido (SSD) que proporcionan un rendimiento similar a 8 unidades de disco mecánicas de 10 000 RPM. <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se recomienda 2, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).  <br/> |

## <a name="summary-of-results"></a>Resumen de resultados

En la tabla siguiente se resumen nuestras recomendaciones.

|**Rol del servidor**|**Cantidad máxima de usuarios admitidos**|
|:-----|:-----|
|Grupo de servidores front-end con doce servidores front-end y un servidor back-end o un par reflejado de servidores back-end.  <br/> |80 000 usuarios únicos iniciaron sesión simultáneamente, más el 50 % de varios puntos de presencia (MPOP) que representan instancias no móviles, más el 40 % de los usuarios habilitados para movilidad para un total de 152 000 puntos de conexión.  <br/> |
|Conferencia A/V  <br/> |El servicio de conferencia A/V proporcionado por un grupo de servidores front-end admite las conferencias del grupo suponiendo un tamaño máximo de conferencia de 250 usuarios y solo una conferencia tan grande ejecutándose a la vez.  <br/> **Nota:** Además, puede admitir conferencias grandes de entre 250 y 1000 usuarios implementando un grupo de servidores front-end independiente con dos servidores front-end para hospedar las conferencias grandes. Para obtener más información, consulte [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Un servidor perimetral  <br/> |12.000 usuarios remotos simultáneos.  <br/> |
|Un director  <br/> |12.000 usuarios remotos simultáneos.  <br/> |
|Supervisión y archivado  <br/> |Los servicios front-end de supervisión y archivado se ejecutan en cada servidor front-end, en lugar de en roles de servidor independientes.  <br/> La supervisión y el archivado aún requieren sus propios almacenes de bases de datos. Si también ejecuta Exchange 2013 o posterior, puede mantener los datos de archivado en Exchange, en lugar de en una base de datos de SQL dedicada.  <br/> |
|Un servidor de mediación  <br/> |El servidor de mediación junto con el servidor front-end se ejecuta en todos los servidores front-end de un grupo de servidores y debe proporcionar suficiente capacidad a los usuarios del grupo. Para el servidor de mediación independiente, consulte la sección "Servidor de mediación" más adelante en este tema.  <br/> |
|Un servidor Standard Edition  <br/> |Se recomienda encarecidamente que si usa servidores Standard Edition para hospedar usuarios, use siempre dos servidores, emparejados con las recomendaciones de Planeación de alta disponibilidad y recuperación [ante desastres.](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx) Cada servidor del par puede hospedar hasta 2.500 usuarios y, si se produce un error en un servidor, el servidor restante puede admitir 5.000 usuarios en un escenario de conmutación por error.  <br/>  Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede sufrir más de 2.500 usuarios por servidor. En este caso, considere la posibilidad de agregar más servidores Standard Edition o de pasar a Skype Empresarial Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Servidor front-end

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol de servidor.

En un grupo de servidores front-end, debe tener un servidor front-end por cada 6.660 usuarios que se alojen en el grupo, suponiendo que el hyperproceso esté habilitado en todos los servidores del grupo y que el hardware del servidor cumpla las recomendaciones de los requisitos del servidor para [Skype Empresarial Server 2015](../requirements-for-your-environment/server-requirements.md) o los requisitos del sistema para [Skype Empresarial Server 2019.](../../../SfBServer2019/plan/system-requirements.md) El número máximo de usuarios de un grupo de servidores front-end es de 80.000, suponiendo de nuevo que el hyperproceso esté habilitado en todos los servidores del grupo. Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores front-end.

Al tener en cuenta el número de usuarios de un grupo de servidores front-end, incluya los usuarios que estén en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia en las sucursales asociadas a este grupo de servidores front-end.

Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente a los demás servidores del grupo. En un escenario en el que tiene 30.000 usuarios y cinco servidores front-end, si un servidor no está disponible, las conexiones de 6000 de los usuarios deben transferirse a los otros cuatro servidores restantes. A continuación, estos cuatro servidores restantes tendrán 7500 usuarios, lo que es un número mayor del recomendado.

Si, en su lugar, empezó con seis servidores front-end para los 30.000 usuarios y uno deja de estar disponible, un total de 5000 usuarios necesita moverse a los cinco servidores restantes. A continuación, estos cinco servidores restantes hospedarán a 6000 usuarios, que se encuentra en el intervalo recomendado.

La cantidad máxima de usuarios en un grupo de servidores front-end es 80.000. El número máximo de servidores front-end de un grupo de servidores es 12.

Para un grupo de servidores front-end con 80.000 usuarios, doce servidores front-end serán buenos para el rendimiento, en implementaciones típicas que siguen los modelos de usuario de [Skype Empresarial Server.](user-models.md) Las implementaciones diseñadas para admitir la conmutación por error de recuperación ante desastres suponen que se puede hospedar un máximo de 40 000 usuarios en cada uno de los dos grupos de servidores front-end emparejados, en los que cada grupo de servidores tiene suficientes servidores front-end para contener a los usuarios de ambos grupos, en caso de que un grupo de servidores necesite conmutarse por error al otro.

El número de usuarios admitidos con un buen rendimiento por un grupo de servidores front-end determinado puede diferir de estos números por las siguientes razones:

- El hardware de los servidores front-end no cumple las recomendaciones.

- El uso de su organización es muy diferente de los modelos de usuario, por ejemplo, si tiene mucho más tráfico de conferencias.

En la tabla siguiente se muestra el ancho de banda promedio para mensajería instantánea y presencia, dado el modelo de usuario, tal como se define en los modelos de usuario [en Skype Empresarial Server.](user-models.md)

|**Ancho de banda medio por usuario**|**Requisitos de ancho de banda por servidor front-end con 6.660 usuarios**|
|:-----|:-----|
|1,3 Kbps  <br/> |13 Mbps  <br/> |

> [!NOTE]
> Para mejorar el rendimiento multimedia de la funcionalidad de servidor de mediación y conferencia A/V en los servidores front-end, debe habilitar el ajuste de escala del lado de recepción (RSS) en los adaptadores de red de los servidores front-end. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, consulte El ajuste de escala del lado de recepción [(RSS) en la documentación de Windows Server 2012.](https://go.microsoft.com/fwlink/p/?LinkId=620365) Para obtener más información sobre cómo habilitar RSS, deberá consultar la documentación del adaptador de red.

## <a name="conferencing-maximums"></a>Máximos de conferencia

Dado el modelo de usuario según el que el 5 % de los usuarios de un grupo de servidores puede estar en una conferencia en cualquier momento, un grupo de 80 000 usuarios podría tener unos 4.000 usuarios en conferencias simultáneamente. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de MI; otras, de MI con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay un límite máximo para el número real de conferencias permitidas y el uso real determina el rendimiento real. Por ejemplo, si su organización tiene muchas más conferencias en modo mixto de las que se suponen en el modelo de usuario, es posible que necesite implementar más servidores front-end o servidores de conferencia A/V que las recomendaciones que se encuentran en este artículo. Para obtener más información sobre las suposiciones en el modelo de usuario, consulte [Modelos de usuario en Skype Empresarial Server.](user-models.md)

El tamaño máximo de conferencia admitido hospedado por un grupo de servidores front-end normal de Skype Empresarial Server que también hospeda usuarios es de 250 participantes. Mientras se está produciendo una conferencia de 250 usuarios, el grupo de servidores también admite otras conferencias, de forma que un total del 5 % de los usuarios del grupo están en conferencias simultáneas. Por ejemplo, en un grupo de doce servidores front-end y 80.000 usuarios, mientras se está produciendo la conferencia de 250 usuarios, Skype Empresarial Server admite la participación de otros 3.750 usuarios en conferencias más pequeñas.

Independientemente del número de usuarios que se hospedan en el grupo de servidores front-end o en el servidor Standard Edition, Skype Empresarial Server admite como mínimo la participación de otros 125 usuarios en conferencias más pequeñas en el mismo grupo o servidor que hospeda una conferencia de 250 usuarios.

Para habilitar conferencias con entre 250 y 1000 usuarios, puede configurar un grupo de servidores front-end independiente solo para hospedar esas conferencias. Este grupo de servidores front-end no hospedará ningún usuario. Para obtener más información, consulte [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Si su organización tiene muchas más conferencias en modo mixto de las que se suponen en el modelo de usuario, es posible que necesite implementar más servidores front-end de los recomendados en este documento (hasta un límite de 12 servidores front-end). Para obtener más información sobre las suposiciones en el modelo de usuario, consulte [Modelos de usuario en Skype Empresarial Server.](user-models.md)

## <a name="edge-server"></a>Servidor perimetral

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol de servidor.

Debe implementar un servidor perimetral por cada 12.000 usuarios remotos que tendrán acceso a un sitio simultáneamente. Como mínimo, se recomienda el uso de dos servidores perimetrales para obtener alta disponibilidad. Estas recomendaciones suponen que el hardware de los servidores perimetrales cumple las recomendaciones de [las plataformas de hardware de servidor.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Cuando calcule el número de usuarios de los servidores perimetrales, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.

> [!NOTE]
> Para mejorar el rendimiento del servicio de conferencia A/V en los servidores perimetrales, debe habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de los servidores perimetrales. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, compruebe " Ajuste de escala del lado de recepción[(RSS) en Windows Server 2012".](https://go.microsoft.com/fwlink/p/?linkId=268731) Para obtener más información sobre cómo habilitar RSS, deberá consultar la documentación del adaptador de red.

## <a name="director"></a>Director

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol de servidor.

Si implementa el rol de servidor Director, se recomienda implementar un director por cada 12.000 usuarios remotos que tendrán acceso a un sitio simultáneamente. Como mínimo, se recomienda el uso de dos directores para obtener alta disponibilidad. Estas recomendaciones suponen que el hardware de los servidores perimetrales cumple las recomendaciones de [las plataformas de hardware de servidor.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Cuando calcule el número de usuarios de los directores, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.

## <a name="mediation-server"></a>Servidor de mediación

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol de servidor.

Si se coloca el servidor de mediación con el servidor front-end, el servidor de mediación se ejecuta en todos los servidores front-end del grupo de servidores y debe proporcionar suficiente capacidad a los usuarios del grupo.

Si implementa un grupo de servidores de mediación independiente, el número de servidores de mediación que se va a implementar depende de muchos factores, incluido el hardware usado para el servidor de mediación, el número de usuarios VoIP que tiene, el número de puertas de enlace del mismo nivel que controla cada grupo de servidores de mediación, el tráfico de horas punta a través de esas puertas de enlace y el porcentaje de llamadas con medios que omite el servidor de mediación.

En las tablas siguientes se proporcionan instrucciones sobre cuántas llamadas simultáneas puede controlar un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumple los requisitos de las plataformas de [hardware](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) de servidor y que el hyperproceso está habilitado. Para obtener más información sobre la escalabilidad del servidor de mediación, consulte [Estimating voice usage and traffic for Skype for Business Server](estimating-voice-traffic.md) and Deployment guidelines for Mediation Server in Skype for Business [Server](mediation-server-deployment-guidelines.md).

Todas las tablas siguientes suponen el uso tal y como se resume en [modelos de usuario en Skype Empresarial Server.](user-models.md)

**Capacidad del servidor de mediación independiente: 70 % usuarios internos, 30 % usuarios externos con capacidad de llamada sin desvío (transcodificación de medios realizada por el servidor de mediación)**

|**Hardware del servidor**|**Número máximo de llamadas**|**Número máximo de líneas T1**|**Número máximo de líneas E1**|
|:-----|:-----|:-----|:-----|
|Procesador dual, núcleo hexadecimal, CPU hiperproceso a 2,26 GHz con **hyperproceso** deshabilitado, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Procesador dual, núcleo hexadecimal, CPU hiperproceso a 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Aunque se utilizaron servidores con 32 GB de memoria para la prueba, se pueden utilizar servidores con 16 GB de memoria como servidores de mediación independientes y son suficientes para ofrecer el rendimiento mostrado en esta tabla.

**Capacidad del servidor de mediación (servidor de mediación con servidor front-end) 70 % usuarios internos, 30 % usuarios externos, capacidad de llamada sin desvío (procesamiento de medios realizado por el servidor de mediación)**

|**Hardware del servidor**|**Número máximo de llamadas**|
|:-----|:-----|
|Procesador dual, núcleo hexadecimal, CPU hiperproceso a 2,26 GHz, con 32 GB de memoria y 2 tarjetas adaptadoras de red de 1 GB.  <br/> |150  <br/> |

> [!NOTE]
> Este número es mucho menor que los números del servidor de mediación independiente. Esto se debe a que el servidor front-end tiene que controlar otras características y funciones para los 6600 usuarios que se alojen en él, además de la transcodificación necesaria para las llamadas de voz.

> [!NOTE]
> Para mejorar el rendimiento del servidor de mediación, debe habilitar el ajuste de escala del lado de recepción (RSS) en los adaptadores de red de los servidores de mediación. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, consulte "Ajuste de escala[del lado de recepción en Windows Server 2012".](https://go.microsoft.com/fwlink/p/?linkId=268731) Para obtener más información sobre cómo habilitar RSS, deberá consultar la documentación del adaptador de red.

## <a name="back-end-server"></a>Servidor back-end

Aunque gran parte de la información de la base de datos se almacena principalmente en los servidores front-end, debe asegurarse de que los servidores back-end cumplen las recomendaciones de hardware indicadas anteriormente en esta sección y en plataformas de [hardware](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)de servidor.

Para proporcionar alta disponibilidad del servidor back-end, se recomienda implementar grupos de disponibilidad AlwaysOn o creación de reflejos del servidor. Para obtener más información, vea alta disponibilidad [del servidor back-end en Skype Empresarial Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

## <a name="monitoring-and-archiving"></a>Supervisión y archivado

Si implementa supervisión o archivado, la funcionalidad front-end de estos servicios se ejecuta en los servidores front-end, y cada uno de ellos usa su propio almacén de bases de datos, independiente del almacén back-end. Como alternativa, si ha implementado Exchange 2013, puede almacenar datos de archivado de mensajes instantáneos en Exchange en lugar de en un almacén de SQL dedicado.

En la tabla siguiente se indica aproximadamente cuánto almacenamiento de base de datos se necesita por usuario y día para los datos de supervisión y archivado.

||**CDR (supervisión)** <br/> |**QoE (supervisión)** <br/> |**Archivado** <br/> |
|:-----|:-----|:-----|:-----|
|Espacio en disco necesario por usuario y día  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft usó el hardware de la tabla siguiente para el servidor de bases de datos para supervisión y archivado durante las pruebas de rendimiento. Las pruebas recopilaron los datos de dos grupos de servidores front-end, cada uno de los cuales contenía 80 000 usuarios.

**Hardware usado en las pruebas de rendimiento de archivado y supervisión**

|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior.  <br/> |
|Memoria  <br/> |48 gigabytes (GB)  <br/> |
|Disco  <br/> |25 unidades de disco duro de 10 000 RPM con 300 GB en cada disco, con la configuración de la tabla siguiente  <br/> |
|Red  <br/> | 1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).  <br/> |

**Configuraciones de disco recomendadas**

|**Drive** <br/> |**Configuración de RAID** <br/> |**Número de discos** <br/> |
|:-----|:-----|:-----|
|Archivos de datos de cdr, QoE y base de datos de archivado, en una sola unidad  <br/> |1+0  <br/> |16   <br/> |
|El archivo de registro de la base de datos CDR  <br/> |1   <br/> |2   <br/> |
|El archivo de registro de la base de datos QoE  <br/> |1   <br/> |2   <br/> |
|Archivo de registro de base de datos de archivado  <br/> |1   <br/> |2   <br/> |

## <a name="video-interop-server-capacity"></a>Capacidad del servidor de interoperabilidad de vídeo

Si implementa el servidor de interoperabilidad de vídeo y necesita determinar la capacidad, consulte el número máximo de sistemas de teleconferencia de vídeo (VTC) que estarán en llamadas simultáneas. Por ejemplo, si tiene 250 VTC en su organización y su modelo de usuario calcula que, como máximo, el 20 % de ellos puede estar en llamadas simultáneas, basa su planeación de capacidad en 50 VTC simultáneos.


