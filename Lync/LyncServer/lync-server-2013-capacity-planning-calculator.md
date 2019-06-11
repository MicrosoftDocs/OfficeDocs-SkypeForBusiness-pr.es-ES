---
title: Calculadora de planeación de capacidad 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 385127f1686c2a4fa5beaf33f02d2eec6ba19500
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Usar la calculadora de planeación de capacidad para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-21_

La calculadora de planeación de capacidad de Microsoft® Lync™ Server 2013 está <http://www.microsoft.com/en-us/download/details.aspx?id=36828>disponible para su descarga en. Está diseñado para ayudarle a determinar los requisitos del servidor en función de los números de usuarios y las modalidades de comunicación que están habilitadas en su organización. Escriba el perfil de su organización y la calculadora le ofrece recomendaciones que le ayudarán a planear su topología.

Las recomendaciones creadas por la calculadora son solo para fines de planificación. La simulación de carga real es necesaria para garantizar que Lync Server 2013 se haya aprovisionado correctamente. Para realizar pruebas de estrés bajo una carga simulada, use la [herramienta Lync Server 2013 de estrés y rendimiento](http://go.microsoft.com/fwlink/?linkid=282724).

Una vez que haya determinado el perfil de usuario y las modalidades que quiere habilitar para los usuarios, es el momento de usar la calculadora para planear el número de servidores, la memoria y el ancho de banda que necesita. Esta versión de la calculadora no ofrece instrucciones sobre los requisitos de I/O de disco.

Esta calculadora complementa [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) y [Microsoft Lync Server](lync-server-2013-planning.md). Use la calculadora después de que haya revisado la guía y haya creado una topología recomendada mediante el uso de la Herramienta de planeación.

Para sacar el máximo partido de la calculadora necesitará información precisa y detallada sobre el perfil de usuario específico. Por ejemplo, datos como el porcentaje de usuarios habilitados para voz, la media de llamadas por usuario por hora, la duración de las llamadas y el porcentaje de usuarios simultáneos en las conferencias pueden suponer una gran diferencia en cuanto a requisitos de servidor. La precisión de las recomendaciones de la calculadora dependerá de la precisión de la información que se le suministre.

<div>

## <a name="using-the-capacity-calculator"></a>Uso de la calculadora de capacidad

La calculadora es una hoja de cálculo de Microsoft Excel®. Las celdas de color naranja son para el usuario. Se escriben valores predeterminados (80.000 usuarios en un grupo con doce servidores frontales), pero puede cambiar estos valores según las necesidades de la organización.

El modelo de uso contiene las secciones siguientes. Para calcular los requisitos de capacidad, escriba los datos según se describe:

**Mensajería instantánea y presencia**

  - En número de usuarios, escriba el número de usuarios que van a iniciar sesión de forma simultánea. Por lo general, este número asciende al 80 % del número total de usuarios especificado. En muchas ocasiones, el 100 % de los usuarios simultáneos estarán habilitados para mensajería instantánea y presencia. El valor predeterminado es 80 000.

  - El número medio de contactos de la Lista de contactos es el número de contactos que deberá usar para validar los requisitos del sistema. Este número no es modificable.

**Telefonía IP empresarial**

  - En usuarios habilitados para telefonía IP empresarial, escriba el porcentaje de usuarios que están habilitados para telefonía IP empresarial. El valor predeterminado es el 60 %.

  - En número promedio de llamadas por usuario por hora (máximo), escriba el número de llamadas por hora que espera que el usuario promedio participe en los períodos de carga máxima. El valor predeterminado es 4.

  - En Porcentaje de llamadas que usan el desvío de medios, escriba el porcentaje de llamadas realizadas por sus usuarios que desviarán el Servidor de mediación. El valor predeterminado es 65%.

  - En Porcentaje de usuarios de voz en llamadas de UC a RTC, escriba el porcentaje de llamadas de la organización que son llamadas telefónicas de UC a RTC. El valor predeterminado es 60%.

  - En porcentaje de usuarios de voz implicados en las comunicaciones UC-UC se muestra el porcentaje de usuarios que están habilitados para telefonía IP empresarial que solo se habilitará para llamadas UC-UC. Este número se calcula en función del dato que se ha especificado en Porcentaje de usuarios de voz en llamadas de UC a RTC.

**Conferencia**

  - En porcentaje de usuarios en conferencias simultáneas, escriba el porcentaje de usuarios que participarán de forma simultánea en las conferencias. El valor predeterminado es el 5 %.

  - En un porcentaje de conferencias con sólo mensajería instantánea (sin voz), escriba el porcentaje de conferencias cuyas conferencias implicarán únicamente mensajería instantánea; es decir, que no incluyen un componente de audio. El valor predeterminado es el 10 %.

  - En porcentaje de usuarios con conferencias de acceso telefónico local, escriba el porcentaje de participantes simultáneos en conferencias que usarán conferencias de acceso telefónico local. El valor predeterminado es el 15 %.

  - En porcentaje de conferencias con voz, escriba el porcentaje de conferencias que incluirán un componente de audio.
    
      - Si el 20 % de las conferencias de voz incluirán también vídeos comunes, active la casilla Incluye vídeo (sin vista múltiple).
    
      - Si el 20 % de las conferencias incluirán también vídeos en vista múltiple, active la casilla Incluye vista múltiple.
    
      - Si el 50 % de las conferencias de voz incluirán también el uso compartido de aplicaciones, active la casilla Incluye uso compartido de aplicaciones.
    
      - Si el 20% de las conferencias de voz incluye cargas de datos, como presentaciones de Microsoft PowerPoint®, active la casilla de verificación Incluir conferencias web.

**Movilidad**

  - En porcentaje de usuarios habilitados para movilidad, escriba el porcentaje de usuarios que se habilitarán para conectarse a Lync Server mediante dispositivos móviles. El valor predeterminado es el 40 %.

Cuando se especifique toda la información necesaria, la calculadora de capacidad calculará los requisitos. Las celdas amarillas muestran valores calculados para los requisitos de CPU, memoria y ancho de banda según las pruebas realizadas en los laboratorios de rendimiento de Lync Server 2013. Las cifras se ofrecen a título orientativo (no se han comprobado y validado todas las variaciones individuales posibles). Se han calculado los valores siguientes:

  - CPU front-end: porcentaje de uso de CPU si un servidor front-end estaba manejando toda la carga con las mismas especificaciones que el servidor que se usó en las pruebas de Microsoft.

  - Red en Mbps: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.

  - Memoria en GB: memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.

Las celdas verdes contienen recomendaciones para el modelo de uso que se ha especificado.

  - Total de servidores front-end: el número de servidores físicos necesarios se basa en servidores dedicados que ejecutan Lync Server 2013 con dos procesadores, HEX-Core, con 2.260 megaciclos.

  - Tenga en cuenta que se recomienda habilitar el hyperthreading ya que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio o vídeo.

  - Servidores perimetrales: número de servidores perimetrales necesarios calculado a partir del 30 % de todos los usuarios simultáneos que usan estos servidores para comunicarse. Este porcentaje de la calculadora no se puede modificar.

  - Almacén de los servicios de archivado/registro detallado de llamadas/calidad de la experiencia: número de almacenes necesarios para las características de archivado o supervisión (si se han habilitado en la organización).

  - Servidores de base de datos back-end necesarios (grupos necesarios): número de servidores de base de datos back-end necesarios para la carga de trabajo que se ha seleccionado.

En la fila situada junto a Número total de servidores front-end, también se facilita información sobre la carga de los servidores y la red para todas las cargas de trabajo combinadas.

  - Carga media de CPU: uso medio de la CPU por servidor front-end.

  - Red en Mbps: asignación de ancho de banda necesario para el modelo de uso que se ha especificado.

  - Memoria en GB: memoria en gigabytes necesaria para cada servidor front-end.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Ajustar para sus procesadores

Todas las cifras de uso de CPU de la hoja de cálculo presuponen que todos los servidores cuentan con un procesador dual, 6 núcleos con 2,26 GHz, un mínimo de 32 GB de memoria, 8 unidades de disco duro de 10.000 RPM y 72 GB de espacio libre en disco.

Si los servidores tienen distintos procesadores, puede ajustar las cifras a las de su hardware.

</div>

</div>

<span> </span>

</div>

</div>

</div>

