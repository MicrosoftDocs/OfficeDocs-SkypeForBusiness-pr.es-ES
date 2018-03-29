---
title: Uso de modelo de usuario de planeamiento de capacidad para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Este artículo proporciona orientación sobre cuántos servidores necesitan en un sitio para el número de usuarios en ese sitio, según el uso que se describe en los modelos de usuario en Skype para Business Server 2015.
ms.openlocfilehash: b8395e1fdec1a9d4ed100a911fccd6177b03c665
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server-2015"></a>Uso de modelo de usuario de planeamiento de capacidad para Skype Empresarial Server 2015
 
Este artículo proporciona orientación sobre cuántos servidores necesitan en un sitio para el número de usuarios en ese sitio, según el uso que se describe en [los modelos de usuario Skype para Business Server 2015](user-models.md).
  
> [!NOTE]
> Todas las recomendaciones de este artículo dan por supuesto que en sus servidores tiene instalado Skype Empresarial con la actualización acumulativa de noviembre de 2015 (o una versión posterior). 
  
## <a name="tested-hardware-platform"></a>Plataforma de hardware probada

Hemos finalizado nuestras pruebas de rendimiento en el hardware que se describe en la tabla siguiente. Todas las recomendaciones y los resultados se basan en este hardware. Si decide usar un hardware de menor capacidad al que se indica aquí, tenga en cuenta que puede tener problemas de rendimiento o de funcionamiento. Estas recomendaciones de hardware son los mismos que Lync Server 2013, si eso es útil (y en escenarios de actualización, puede ser).
  
**Hardware utilizado en las pruebas de rendimiento**

|**Componente de hardware**|**Recomienda**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, seis núcleos y 2,26 gigahercios (GHz) o superior.  <br/> Procesadores Intel Itanium no son compatibles para Skype para funciones de servidor de Business Server.  <br/> |
|Memoria  <br/> |32 gigabytes (GB).  <br/> &bull;&nbsp;&nbsp;espacio 8 o 10.000 RPM más unidades de disco duro con al menos 72 GB de espacio libre en disco.  <br/> Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.  <br/> O BIEN   <br/> &bull;&nbsp;&nbsp;Unidades de estado sólido (SSD) que proporcionan un rendimiento similar a 8 unidades de disco mecánicas de 10.000 RPM.  <br/> |
|Disco  <br/> ||
|Red  <br/> |&bull;&nbsp;&nbsp;1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendado, lo que requiere trabajo en equipo con una única dirección MAC y la dirección IP única).  <br/> |
   
## <a name="summary-of-results"></a>Resumen de los resultados

En la tabla siguiente se resumen nuestras recomendaciones.
  
|**Función de servidor**|**Número máximo de usuarios admitidos**|
|:-----|:-----|
|Grupo de servidores frontal con doce servidores frontales y un nuevo servidor o un par espejeado detrás de servidores de fondo.  <br/> |80.000 usuarios únicos con sesión iniciada simultáneamente, más un 50% de múltiples puntos de presencia (MPOP) que representan instancias no móviles, más un 40% de los usuarios habilitados para movilidad, lo que hace un total de 152.000 extremos.  <br/> |
|Conferencia A/V  <br/> |El servicio de conferencias audiovisuales proporcionado por un grupo de servidores Front-End admite conferencias de la piscina suponiendo un tamaño máximo de conferencia de 250 usuarios y solo dichas conferencias ejecutar a la vez.  <br/> **Nota:** Además, se pueden admitir grandes conferencias de entre 250 y 1000 usuarios al implementar un grupo distinto de Front-End con dos servidores frontales para alojar las conferencias de gran tamaño. Para obtener información detallada, consulte [Plan de grandes reuniones en Skype para Business Server 2015](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Servidor de uno de los bordes  <br/> |12 000 usuarios remotos simultáneos.  <br/> |
|Un Director  <br/> |12 000 usuarios remotos simultáneos.  <br/> |
|Supervisión y archivado  <br/> |Los servicios front-end de archivado y de supervisión ejecutar en cada servidor de extremo frontal, en lugar de en los roles de servidor independiente.  <br/> Los servicios de supervisión y archivado aún necesitan sus propios almacenes de base de datos. Si también ejecuta Exchange 2013 o posterior, puede mantener los datos de Archiving en Exchange, en lugar de en una base de datos SQL dedicado.  <br/> |
|Un servidor de mediación  <br/> |Servidor de mediación en combinación con el servidor Front-End se ejecuta en cada servidor Front-End en un grupo y debe proporcionar la suficiente capacidad para los usuarios en el grupo. Para el servidor de mediación de independiente, consulte la sección "Servidor de mediación" más adelante en este tema.  <br/> |
|Un servidor Standard Edition  <br/> |Recomendamos encarecidamente que si utiliza servidores Standard Edition para alojar usuarios, utilice siempre dos servidores, emparejados siguiendo las recomendaciones de [diseño para alta disponibilidad y recuperación ante desastres](http://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Cada servidor del par puede hospedar hasta 2500 usuarios y, si uno de los servidores produce errores, el otro servidor puede admitir 5000 usuarios en un escenario de conmutación por error.  <br/>  Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede verse afectado con más de 2500 usuarios por servidor. En este caso, puede agregar más servidores Standard Edition o mover a Skype para Business Server Enterprise Edition. <br/> |
   
## <a name="front-end-server"></a>Servidor front-end

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor. 
  
En un grupo de servidores Front-End, debera haber un que servidor Front-End para cada 6,660 usuarios alojado en el grupo, suponiendo que hyper-threading está habilitada en todos los servidores en el grupo y que el hardware del servidor cumple las recomendaciones en [Plataformas de Hardware de servidor](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). El número máximo de usuarios en un grupo de servidores Front-End es nuevo 80.000, suponiendo que hyper-threading está habilitada en todos los servidores de su grupo. Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores Front-End. 
  
Cuando se tiene en cuenta para el número de usuarios en un grupo de servidores Front-End, se incluyen todos los usuarios alojados en equipos de sucursales que sobreviven y que sobreviven rama servidores de sucursales que están asociados con este grupo de servidores Front-End.
  
Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente al resto de los servidores del grupo. En un escenario donde hay 30.000 usuarios y cinco servidores frontales, si un servidor no está disponible, las conexiones de 6000 usuarios deben transferirse a los otros cuatro servidores restantes. Cada uno de los cuatro servidores restantes tendrá 7500 usuarios, un número superior al recomendado.
  
Si en su lugar había comenzado con seis servidores frontales para los 30.000 usuarios y uno deja de estar disponible, un total de 5.000 usuarios que necesite mover a los demás servidores de cinco. Cada uno de estos cinco servidores hospedará 6000 usuarios, dentro del intervalo recomendado.
  
El número máximo de usuarios en un grupo de servidores Front-End es 80.000. El número máximo de servidores frontales de un grupo es 12. 
  
Para un grupo Front-End con 80.000 usuarios, será útil para el rendimiento, en las implementaciones típicas que siguen los [modelos de usuario en Skype para Business Server 2015](user-models.md)doce servidores frontales. Se supone que se puede alojar un máximo de 40000 usuarios en cada uno de los dos grupos de Front-End emparejados, en la que cada grupo tiene suficientes servidores frontales para incluir a los usuarios de ambos grupos, un grupo es necesario que se haga failover t implementaciones diseñadas para soportar failover de recuperación ante desastres o el otro.
  
El número de usuarios admitidos con buen rendimiento por un determinado conjunto de Front-End puede diferir de estas cifras por las siguientes razones:
  
- El hardware de los servidores frontales no cumple las recomendaciones de [Plataformas de Hardware de servidor](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
    
- Uso de su organización es muy diferente de los modelos de usuario, por ejemplo, si tiene mucho más tráfico de conferencia.
    
La siguiente tabla muestra el ancho de banda medio para mensajería instantánea y presencia, dado el modelo de usuario, tal como se define en [los modelos de usuario Skype para Business Server 2015](user-models.md).
  
|**Ancho de banda promedio por usuario**|**Requisitos de ancho de banda por servidor Front-End con 6,660 usuarios**|
|:-----|:-----|
|1,3 Kbps  <br/> |13 Mbps  <br/> |
   
> [!NOTE]
> Para mejorar el rendimiento de los medios de comparten ubicación A / funcionalidad de conferencias audiovisuales y servidor de mediación en los servidores frontales, debe habilitar el lado de recepción (RSS) de escala en los adaptadores de red en los servidores frontales. La RSS permite que varios procesadores en el servidor gestionen los paquetes entrantes. Para obtener más información, consulte [Recibir escalamiento lateral (RSS) en la documentación de Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red. 
  
## <a name="conferencing-maximums"></a>Máximos de conferencia

Como el modelo de usuario que establece que el 5 % de los usuarios de un grupo puede estar en una conferencia en cualquier momento, un grupo de 80 000 usuarios podría tener unos 4000 usuarios en conferencias de forma simultánea. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de mensajería instantánea; otras, de mensajería instantánea con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay ningún límite fijo para el número real de conferencias permitidas y el uso real determinará el rendimiento real. Por ejemplo, si la organización tiene muchas más conferencias de modo mixto que se supone que en el modelo de usuario, puede que necesite implementar más servidores frontales o A / V servidores de conferencia que las recomendaciones que se encuentran en este artículo. Para obtener más información acerca de los supuestos en el modelo de usuario, vea [modelos de usuario en Skype para Business Server 2015](user-models.md).
  
El tamaño máximo de conferencia admitidas alojado por un Skype para el grupo de negocio de servidor Front-End que también aloja usuarios regular es de 250 participantes. Mientras se celebra una conferencia de 250 usuarios, el grupo puede admitir también otras conferencias, con un total del 5 % de los usuarios del grupo en conferencias simultáneas. Por ejemplo, en un grupo de servidores frontales doce y 80.000 usuarios, durante la conferencia de 250 usuarios, Skype para Business Server admite 3.750 otros usuarios participen en conferencias más pequeñas.
  
Independientemente del número de usuarios alojados en el grupo de servidores frontales o el servidor Standard Edition, Skype para Business Server admite un mínimo de 125 otros usuarios participen en conferencias más pequeñas en el mismo grupo o servidor que aloja una conferencia de 250 usuarios. 
  
Para habilitar conferencias que tienen entre 250 y 1000 usuarios, puede configurar un grupo distinto de Front-End para alojar las conferencias. Este grupo de servidores Front-End no aloja usuarios. Para obtener información detallada, consulte [Plan de grandes reuniones en Skype para Business Server 2015](../../plan-your-deployment/conferencing/large-meetings.md).
  
Si su organización tiene mucho más conferencias de modo mixto que se supone que en el modelo de usuario, puede que necesite implementar más servidores frontales que nos recomendación en este documento (hasta un máximo de 12 servidores frontales). Para obtener más información acerca de los supuestos en el modelo de usuario, vea [modelos de usuario en Skype para Business Server 2015](user-models.md).
  
## <a name="edge-server"></a>Servidor perimetral

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor. 
  
Debe implementar un servidor perimetral para cada 12.000 usuarios remotos tengan acceso simultáneamente a un sitio. Como mínimo se recomiendan dos servidores perimetrales para alta disponibilidad. Estas recomendaciones se supone que el hardware de sus servidores perimetrales cumple las recomendaciones de [Plataformas de Hardware de servidor](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Cuando se tiene en cuenta para el número de usuarios para los servidores perimetrales, se incluyen los usuarios alojados en equipos de sucursales que sobreviven y que sobreviven rama servidores de sucursales que están asociados con un grupo de servidores Front-End en este sitio.
  
> [!NOTE]
> Para mejorar el rendimiento de la A / V conferencia borde servicio en sus servidores perimetrales, debe habilitar el lado de recepción escala (RSS) de los adaptadores de red en los servidores de borde. La RSS permite que varios procesadores en el servidor gestionen los paquetes entrantes. Para obtener más información, consulte "[Mejoras escala en lado de recepción en Windows Server 20081](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red. 
  
## <a name="director"></a>Director

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor. 
  
Si implementa la función de servidor Director, recomendamos implementar un Director para cada 12.000 usuarios remotos tengan acceso simultáneamente a un sitio. Como mínimo se recomiendan dos directores para alta disponibilidad. Estas recomendaciones se supone que el hardware de sus servidores perimetrales cumple las recomendaciones de [Plataformas de Hardware de servidor](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Cuando se tiene en cuenta para el número de usuarios para los directores, se incluyen los usuarios alojados en equipos de sucursales que sobreviven y que sobreviven rama servidores de sucursales que están asociados con un grupo de servidores Front-End en este sitio.
  
## <a name="mediation-server"></a>Servidor de mediación

> [!NOTE]
> Los grupos extendidos no son compatibles con este rol del servidor. 
  
Si coloca el servidor de mediación con el servidor Front-End, servidor de mediación se ejecuta en cada servidor Front-End en el grupo y debe proporcionar la suficiente capacidad para los usuarios en el grupo. 
  
Si implementa un conjunto de servidor de mediación de independiente y, a continuación, ¿cuántos servidores de mediación implementar depende de muchos factores, incluido el hardware utilizado para el servidor de mediación, el número de usuarios de VoIP tiene, el número de puerta de enlace de mismo nivel que cada grupo de servidor de mediación Controla el tráfico de horas ocupadas a través de las puertas de enlace y el porcentaje de llamadas con los medios de comunicación que pasa por alto el servidor de mediación. 
  
Las siguientes tablas proporcionan una guía para cuántos puede controlar las llamadas simultáneas a un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumpla los requisitos de [Las plataformas de Hardware de servidor](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) y que hyper-threading está habilitada. Para obtener más información acerca de la escalabilidad del servidor de mediación, consulte [uso de la voz de estimación y tráfico de Skype para Business Server 2015](estimating-voice-traffic.md) y [directrices de implementación para el servidor de mediación en Skype para Business Server 2015](mediation-server-deployment-guidelines.md).
  
Las siguientes tablas supone uso como se resume en [los modelos de usuario Skype para Business Server 2015](user-models.md).
  
**Capacidad de servidor de mediación independiente: 70% de los usuarios internos, 30% de los usuarios externos con no derivación llamada capacidad (servidor de mediación realizada la transcodificación de medios)**

|**Hardware del servidor**|**Número máximo de llamadas.**|**Número máximo de líneas T1**|**Número máximo de líneas E1**|
|:-----|:-----|:-----|:-----|
|Procesador dual, seis núcleos, CPU con Hyper-Threading a 2,26 GHz **con la tecnología Hyper-Threading deshabilitada**, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.  <br/> |1500  <br/> |63  <br/> |47  <br/> |
   
> [!NOTE]
> Aunque se utilizaron servidores con 32 GB de memoria para pruebas de rendimiento, servidores con 16 GB de memoria son compatibles con el servidor de mediación de independiente y son suficientes para proporcionar el rendimiento que se muestra en esta tabla. 
  
**Capacidad del servidor de mediación (servidor de mediación en combinación con el servidor Front-End) los usuarios internos de 70%, 30% de los usuarios externos, no omitir llamada capacidad (procesamiento de medios realizado por servidor de mediación)**

|**Hardware del servidor**|**Número máximo de llamadas.**|
|:-----|:-----|
|Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y 4 tarjetas adaptadoras de red de 1 GB.  <br/> |150  <br/> |
   
> [!NOTE]
> Este número es mucho menor que los números para el servidor de mediación de independiente. Eso es porque el servidor Front-End tiene que controlar otras características y funciones para los 6600 usuarios alojados en él, además de la transcodificación necesaria para llamadas de voz. 
  
> [!NOTE]
> Para mejorar el rendimiento del servidor de mediación, debe habilitar el lado de recepción escala (RSS) de los adaptadores de red en los servidores de mediación. La RSS permite que varios procesadores en el servidor gestionen los paquetes entrantes. Para obtener más información, consulte "[Mejoras escala en lado de recepción en Windows Server 2008](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red. 
  
## <a name="back-end-server"></a>Servidor back-end

Aunque gran parte de la información de la base de datos se almacena principalmente en los servidores frontales, debe asegurarse de que los servidores de fondo Atrás cumple las recomendaciones de hardware enumeradas anteriormente en esta sección y en [Las plataformas de Hardware de servidor](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Para proporcionar alta disponibilidad de su servidor de fondo detrás, recomendamos implementar grupos de disponibilidad AlwaysOn o reflejo de servidores. Para obtener más información, vea el [nuevo servidor de alta disponibilidad en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  
## <a name="monitoring-and-archiving"></a>Supervisión y archivado

Si se implementa archivado o supervisión, la funcionalidad de front-end de estos servicios se ejecuta en los servidores de fondo de la parte delantera, supervisión y archivado utilizan su propio almacén de base de datos independiente del almacén de Back End. O bien, si tienes 2013 Exchange implementado, puede almacenar datos de archivado de mensajería instantánea de Exchange en lugar de en un almacén SQL dedicado.
  
En la tabla siguiente se indica cuánto almacenamiento de base de datos se necesita aproximadamente por usuario y por día para los datos de supervisión y archivado.
  
|||||
|:-----|:-----|:-----|:-----|
||**CDR (Supervisión)** <br/> |**QoE (Supervisión)** <br/> |**Archivado** <br/> |
|Espacio en disco necesario por usuario y por día  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |
   
Durante las pruebas de rendimiento, Microsoft usó el hardware de la tabla siguiente para el servidor de bases de datos de supervisión y archivado. Las pruebas, recopilan los datos de dos grupos de Front-End, cada uno de los cuales contenía 80.000 usuarios.
  
**Hardware utilizado en la supervisión y pruebas de rendimiento de Archiving**

|**Componente de hardware**|**Recomienda**|
|:-----|:-----|
|CPU  <br/> |Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior  <br/> |
|Memoria  <br/> |48 gigabytes (GB).  <br/> |
|Disco  <br/> |25 a 10.000 RPM y unidades de disco duro con 300 GB en cada disco, con la configuración en la tabla siguiente  <br/> |
|Red  <br/> | 1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).  <br/> |
   
**Configuraciones de disco recomendadas**

||||
|:-----|:-----|:-----|
|**Unidad** <br/> |**Configuración RAID** <br/> |**Número de discos** <br/> |
|Archivos de datos de las bases de datos de CDR, QoE y archivado, en una sola unidad  <br/> |1+0  <br/> |16  <br/> |
|Archivo de registro de la base de datos CDR  <br/> |1  <br/> |2  <br/> |
|Archivo de registro de la base de datos QoE  <br/> |1  <br/> |2  <br/> |
|Archivo de registro de la base de datos de archivado  <br/> |1  <br/> |2  <br/> |
   
## <a name="video-interop-server-capacity"></a>Capacidad de interoperabilidad servidor de vídeo

Si implementar servidor de interoperabilidad de vídeo y es necesario determinar la capacidad, mire el número máximo de los sistemas de teleconferencia por vídeo (VTCs) que estarán en llamadas simultáneas. Por ejemplo, si tiene 250 VTC en su organización y el modelo de usuario calcula que, como máximo, el 20 % de ellos estarán en llamadas simultáneas, tome como base el planeamiento de capacidad en 50 VTC simultáneos.
  

