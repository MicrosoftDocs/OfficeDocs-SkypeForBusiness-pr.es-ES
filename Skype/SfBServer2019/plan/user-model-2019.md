---
title: Planeación de capacidad para Skype Empresarial Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: Los temas de esta sección le ayudarán a comprender cómo planear e implementar Skype Empresarial Server de modo que pueda planear adecuadamente el número de usuarios de su organización y planear la carga del servidor que generan sus actividades.
ms.openlocfilehash: aaa34d4ec935735215da36d888ab3c5155f158b89fd366546eac14b3f6259482
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277645"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Planeación de capacidad para Skype Empresarial Server 2019

En este artículo se proporcionan instrucciones sobre cuántos servidores necesita en un sitio para el número de usuarios en ese sitio, de acuerdo con el uso descrito en Modelos de [usuario en Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Plataforma de hardware probada

Hemos realizado nuestras pruebas de rendimiento en el hardware descrito en la tabla siguiente. Todas nuestras recomendaciones y resultados se basan en este hardware. Si decide probar a usar hardware menos eficaz que el que se muestra aquí, tenga en cuenta que puede tener problemas de funcionalidad o un rendimiento deficiente.

**Hardware usado en pruebas de rendimiento**

|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior.  <br/> Los procesadores Intel Itanium no son compatibles Skype Empresarial Server funciones de 2019.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |CUALQUIERA DE LAS DOS:  <br/> • 8 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (dos de los discos que usan RAID 1 y 6 con RAID 10).  <br/> O  <br/> • Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 8 unidades de disco mecánicas de 10000 RPM.  <br/> |
|Red  <br/> |1 adaptador de red de doble puerto, 1 Gbps o superior (se pueden usar 2 adaptadores de red, pero deben estar asociados con una sola dirección MAC y una única dirección IP).  <br/> Las configuraciones duales o  multialod no son compatibles con servidores front-end, servidores back-end y servidores Standard Edition cliente. <br/> Siempre que no estén expuestos al sistema operativo y se estén utilizando para supervisar y administrar el hardware del servidor, puede tener sistemas de administración fuera de banda, como DRAC o ILO. Este escenario no constituye un servidor multialocución y es compatible.  <br/> |

## <a name="summary-of-results"></a>Resumen de resultados

En la tabla siguiente se resumen nuestras recomendaciones.

|**Rol del servidor**|**Cantidad máxima de usuarios admitidos**|
|:-----|:-----|
|Grupo de servidores front-end con dieciséis servidores front-end y servidor back-end o un par de servidores back-end con SQL AlwaysOn para alta disponibilidad.  <br/> |106 000 usuarios únicos iniciaron sesión simultáneamente, más un 50 % de varios puntos de presencia (MPOP) que representan instancias que no son móviles, más el 40 % de los usuarios habilitados para Mobility para un total de 210 000 puntos de conexión.  <br/> |
|Conferencia A/V  <br/> |El servicio de conferencia A/V proporcionado por un grupo de servidores front-end admite las conferencias del grupo suponiendo un tamaño máximo de conferencia de 250 usuarios y solo una conferencia tan grande que se ejecute a la vez.  <br/> **Nota:** Además, puede admitir grandes conferencias de entre 250 y 1000 usuarios mediante la implementación de un grupo de servidores front-end independiente con dos servidores front-end para hospedar las grandes conferencias. Para obtener más información, vea [Plan for large meetings in Skype Empresarial Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Un servidor perimetral  <br/> |18.000 usuarios remotos simultáneos.  <br/> |
|Un director  <br/> |18.000 usuarios remotos simultáneos.  <br/> |
|Supervisión y archivado  <br/> |Los servicios front-end de supervisión y archivado se ejecutan en cada servidor front-end, en lugar de en roles de servidor independientes.  <br/> La supervisión y el archivado aún requieren sus propios almacenes de bases de datos. Si también ejecuta Exchange 2013 o posterior, puede mantener los datos de archivado en Exchange, en lugar de en una base de datos SQL dedicada.  <br/> |
|Un servidor de mediación  <br/> |El servidor de mediación asociado con el servidor front-end se ejecuta en todos los servidores front-end de un grupo de servidores y debe proporcionar suficiente capacidad para los usuarios del grupo. Para el servidor de mediación independiente, vea la sección "Servidor de mediación" más adelante en este tema.  <br/> |
|Un servidor Standard Edition  <br/> |Se recomienda encarecidamente que si usa servidores Standard Edition para hospedar usuarios, siempre use dos servidores, emparejados con las recomendaciones de Planeación de alta disponibilidad y recuperación [ante desastres.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery) Cada servidor del par puede hospedar hasta 2.500 usuarios y, si se produce un error en un servidor, el servidor restante puede admitir 5.000 usuarios en un escenario de conmutación por error.  <br/>  Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede sufrir más de 2.500 usuarios por servidor. En este caso, debe considerar agregar más servidores Standard Edition o pasar a Skype Empresarial Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Servidor front-end

> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.

En un grupo de servidores front-end, debe tener un servidor front-end por cada 6.660 usuarios que se alojen en el grupo, suponiendo que el hyper-threading está habilitado en todos los servidores del grupo, que está usando SQL Server Express Edition y que el hardware del servidor cumple las recomendaciones de Requisitos del servidor para [Skype Empresarial Server 2019](system-requirements.md). El número máximo de usuarios de un grupo de servidores front-end es 106.000, suponiendo de nuevo que el hyper-threading está habilitado y SQL Server Express Edition se usa en todos los servidores del grupo. Si tiene más de 106 000 usuarios en un sitio, puede implementar más de un grupo de servidores front-end.

Al tener en cuenta el número de usuarios de un grupo de servidores front-end, incluya los usuarios que se encuentran en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia en sucursales asociadas a este grupo de servidores front-end.

Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente a los demás servidores del grupo. En un escenario donde tiene 30.000 usuarios y cinco servidores front-end, si un servidor no está disponible, las conexiones de 6000 de los usuarios deben transferirse a los otros cuatro servidores restantes. A continuación, estos cuatro servidores restantes tendrán 7500 usuarios, lo que es un número mayor del recomendado.

Si en su lugar había comenzado con seis servidores front-end para sus 30.000 usuarios y uno deja de estar disponible, un total de 5.000 usuarios deben moverse a los cinco servidores restantes. A continuación, estos cinco servidores restantes hospedarán a 6000 usuarios, que se encuentra en el rango recomendado.

El número máximo de usuarios de un grupo de servidores front-end es de 106 000. El número máximo de servidores front-end de un grupo de servidores es 16.

Para un grupo de servidores front-end con 80.000 usuarios, 16 servidores front-end serán buenos para el rendimiento, en implementaciones típicas que siguen los modelos de usuario de [Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/user-models.md). Las implementaciones diseñadas para admitir la conmutación por error de recuperación ante desastres suponen que se puede hospedar un máximo de 53.000 usuarios en cada uno de los dos grupos de servidores front-end emparejados, en los que cada grupo de servidores tiene suficientes servidores front-end para contener a los usuarios de ambos grupos, en caso de que un grupo de servidores necesite conmutarse por error al otro.

El número de usuarios admitidos con buen rendimiento por un grupo de servidores front-end determinado puede diferir de estos números por los siguientes motivos:

- El hardware de los servidores front-end no cumple las recomendaciones.
- En lugar de usar SQL Server Express Edition, usa otra SQL Server Edition, puede hospedar usuarios adicionales en cada grupo de servidores front-end.
- El uso de su organización es muy diferente de los modelos de usuario, por ejemplo, si tiene mucho más tráfico de conferencia.

En la tabla siguiente se muestra el ancho de banda promedio para mensajería instantánea y presencia, dado el modelo de usuario, tal como se define en Modelos de [usuario en Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

|**Ancho de banda medio por usuario**|**Requisitos de ancho de banda por servidor front-end con 6.660 usuarios**|
|:-----|:-----|
|3-3,75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> Para mejorar el rendimiento multimedia de la funcionalidad de servidor de mediación y conferencia A/V en los servidores front-end, debe habilitar el escalado del lado de recepción (RSS) en los adaptadores de red de los servidores front-end. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, [consulte Receive Side Scaling (RSS) en la Windows Server 2012 de datos](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)). Para obtener más información sobre cómo habilitar RSS, deberá consultar la documentación del adaptador de red.

## <a name="conferencing-maximums"></a>Máximos de conferencia

Dado el modelo de usuario que el 5 % de los usuarios de un grupo puede estar en una conferencia en cualquier momento, un grupo de 106.000 usuarios podría tener unos 5.300 usuarios en conferencias simultáneamente. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de MI; otras, de MI con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay un límite difícil para el número real de conferencias permitidas y el uso real determina el rendimiento real. Por ejemplo, si su organización tiene muchas más conferencias en modo mixto de las que se suponen en el modelo de usuario, es posible que deba implementar más servidores front-end o servidores de conferencia A/V que las recomendaciones que se encuentran en este artículo. Para obtener información detallada sobre los supuestos del modelo de usuario, vea [Modelos de usuario en Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

El tamaño máximo de conferencia admitido hospedado por un grupo de servidores Skype Empresarial Server cliente que también hospeda usuarios es de 250 participantes. Mientras se está produciendo una conferencia de 250 usuarios, el grupo de servidores también admite otras conferencias, de forma que un total del 5 % de los usuarios del grupo están en conferencias simultáneas. Por ejemplo, en un grupo de 16 servidores front-end y 106.000 usuarios, mientras se está produciendo la conferencia de 250 usuarios, Skype Empresarial Server admite a otros 5.050 usuarios que participan en conferencias más pequeñas.

Independientemente del número de usuarios que se hospedan en el grupo de servidores front-end o en el servidor Standard Edition, Skype Empresarial Server admite un mínimo de 125 usuarios que participan en conferencias más pequeñas en el mismo grupo o servidor que hospeda una conferencia de 250 usuarios.

Para habilitar conferencias con entre 250 y 1000 usuarios, puede configurar un grupo de servidores front-end independiente solo para hospedar esas conferencias. Este grupo de servidores front-end no hospedará ningún usuario. Para obtener más información, consulte [Plan for large meetings in Skype Empresarial Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md).

Si su organización tiene muchas más conferencias en modo mixto de las que se suponen en el modelo de usuario, es posible que deba implementar más servidores front-end de los recomendados en este documento (hasta un límite de 16 servidores front-end). Para obtener información detallada sobre los supuestos del modelo de usuario, vea [Modelos de usuario en Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>Servidor perimetral

> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.

Debe implementar un servidor perimetral por cada 18.000 usuarios remotos que accederán a un sitio simultáneamente. Como mínimo, se recomienda el uso de dos servidores perimetrales para obtener alta disponibilidad. Estas recomendaciones suponen que el hardware de los servidores perimetrales cumple las recomendaciones de [Plataformas de hardware de servidor](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

Cuando calcule el número de usuarios de los servidores perimetrales, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.

> [!NOTE]
> Para mejorar el rendimiento del servicio de conferencia A/V en los servidores perimetrales, debe habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de los servidores perimetrales. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, [compruebe Receive Side Scaling (RSS) en Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)). Para obtener más información sobre cómo habilitar RSS, deberá consultar la documentación del adaptador de red.

## <a name="director"></a>Director

> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.

Si implementa el rol de servidor Director, se recomienda implementar un director por cada 18.000 usuarios remotos que tendrán acceso a un sitio al mismo tiempo. Como mínimo, se recomienda el uso de dos directores para obtener alta disponibilidad. Estas recomendaciones suponen que el hardware de los servidores perimetrales cumple las recomendaciones de [Plataformas de hardware de servidor](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

Cuando calcule el número de usuarios de los directores, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.

## <a name="mediation-server"></a>Servidor de mediación

> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.

Si se asocia el servidor de mediación con el servidor front-end, el servidor de mediación se ejecuta en todos los servidores front-end del grupo de servidores y debe proporcionar suficiente capacidad para los usuarios del grupo.

Si implementa un grupo de servidores de mediación independiente, el número de servidores de mediación que se va a implementar depende de muchos factores, incluido el hardware usado para el servidor de mediación, el número de usuarios VoIP que tiene, el número de servidores del mismo nivel de puerta de enlace que controla cada grupo de servidores de mediación, el tráfico de horas ocupadas a través de esas puertas de enlace y el porcentaje de llamadas con medios que omite el servidor de mediación.

En las tablas siguientes se proporciona una guía sobre cuántas llamadas simultáneas puede controlar un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumple los requisitos de las plataformas de [hardware](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) de servidor y que el hiperprocesamiento está habilitado. Para obtener más información sobre la escalabilidad del servidor de mediación, vea [Estimating voice usage and traffic for Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) and Deployment guidelines for Mediation Server in [Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Todas las tablas siguientes suponen el uso tal como se resume en [Modelos de usuario en Skype Empresarial Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

**Capacidad del servidor de mediación independiente: 70 % usuarios internos, 30 % usuarios externos con capacidad de llamada sin desvío (transcodificación de medios realizada por el servidor de mediación)**

|**Hardware del servidor**|**Número máximo de llamadas**|**Número máximo de líneas T1**|**Número máximo de líneas E1**|
|:-----|:-----|:-----|:-----|
|Procesador dual Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior con **hyper-threading** deshabilitado, con 64 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Procesador dual Intel Xeon E5-2673 v3, de 6 núcleos, 2,4 gigahercios (GHz) o superior, con 64 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Aunque se usaron servidores con 64 GB de memoria para pruebas de rendimiento, los servidores con 32 GB de memoria son compatibles con el servidor de mediación independiente y son suficientes para proporcionar el rendimiento que se muestra en esta tabla.

**Capacidad del servidor de mediación (servidor de mediación con servidor front-end) 70 % usuarios internos, 30 % usuarios externos, capacidad de llamada sin desvío (procesamiento de medios realizado por el servidor de mediación)**

|**Hardware del servidor**|**Número máximo de llamadas**|
|:-----|:-----|
|Procesador dual Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior. Con 64 GB de memoria y 2 tarjetas de adaptador de red de 1 GB.  <br/> |200  <br/> |

> [!NOTE]
> Este número es mucho menor que los números del servidor de mediación independiente. Esto se debe a que el servidor front-end tiene que controlar otras características y funciones para los 6600 usuarios que se alojen en él, además de la transcodificación necesaria para las llamadas de voz.

> [!NOTE]
> Para mejorar el rendimiento del servidor de mediación, debe habilitar el escalado del lado de recepción (RSS) en los adaptadores de red de los servidores de mediación. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, vea "[Receive-Side Scaling in Windows Server 2012".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Para obtener más información sobre cómo habilitar RSS, deberá consultar la documentación del adaptador de red.

## <a name="back-end-server"></a>Servidor back-end

Aunque gran parte de la información de la base de datos se almacena principalmente en los servidores front-end, debe asegurarse de que los servidores back-end cumplan las recomendaciones de hardware enumeradas anteriormente en esta sección y en Plataformas de [hardware de servidor.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Para proporcionar alta disponibilidad del servidor back-end, se recomienda implementar grupos de disponibilidad AlwaysOn o creación de reflejos del servidor. Para obtener más información, [vea Back End Server high availability in Skype Empresarial Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Supervisión y archivado

Si implementa supervisión o archivado, la funcionalidad front-end de estos servicios se ejecuta en los servidores front-end, cada uno de ellos usa su propio almacén de bases de datos, independiente del almacén back-end. Como alternativa, si Exchange 2013 implementado, puede almacenar datos de archivado de mensajes instantáneos en Exchange en lugar de en un almacén de SQL dedicado.

En la tabla siguiente se indica aproximadamente cuánto almacenamiento de bases de datos se requiere por usuario y día para los datos de supervisión y archivado.

||**CDR (supervisión)** <br/> |**QoE (supervisión)** <br/> |**Archivado** <br/> |
|:-----|:-----|:-----|:-----|
|Espacio en disco necesario por usuario y día  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft usó el hardware de la tabla siguiente para el servidor de bases de datos para la supervisión y el archivado durante las pruebas de rendimiento. Las pruebas recopilaron los datos de dos grupos de servidores front-end, cada uno de los cuales contenía 80.000 usuarios.

**Hardware usado en pruebas de rendimiento de archivado y supervisión**

|**Componente de hardware**|**Recomendada**|
|:-----|:-----|
|CPU  <br/> |Procesador dual Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahercios (GHz) o superior.  <br/> |
|Memoria  <br/> |48 GB  <br/> |
|Disco  <br/> | CUALQUIERA DE LAS DOS:<br/> • 4 o más unidades de disco duro de 10000 RPM con al menos 72 GB de espacio libre en disco (los discos deben estar en una configuración de 2x RAID 1). <br/>O <br/>• Unidades de estado sólido (SSD) capaces de proporcionar el mismo espacio libre y un rendimiento similar a 4 unidades de disco mecánicas de 10000 RPM.   <br/> |
|Red  <br/> | 1 adaptador de red de doble puerto, 1 Gbps o superior (2 recomendado, lo que requiere la asociación con una sola dirección MAC y una sola dirección IP).  <br/> |

**Configuraciones de disco recomendadas**

|**Drive** <br/> |**Configuración de RAID** <br/> |**Número de discos** <br/> |
|:-----|:-----|:-----|
|Cdr, QoE y archivos de datos de base de datos de archivado, en una sola unidad  <br/> |1+0  <br/> |16   <br/> |
|El archivo de registro de la base de datos CDR  <br/> |1  <br/> |2  <br/> |
|El archivo de registro de la base de datos QoE  <br/> |1  <br/> |2  <br/> |
|Archivo de registro de base de datos de archivado  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Capacidad del servidor de interoperabilidad de vídeo

Si implementa el servidor de interoperabilidad de vídeo y necesita determinar la capacidad, consulte el número máximo de sistemas de teleconferencia de vídeo (VTC) que estarán en llamadas simultáneas. Por ejemplo, si tiene 250 VTC en su organización y su modelo de usuario calcula que, como máximo, el 20 % de ellos podrían estar en llamadas simultáneas, basará la planeación de capacidad en 50 VTC simultáneos.