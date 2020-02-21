---
title: Calculadora de planeación de capacidad 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b920f7fd0325c3232abb5670a2da66fc98352d38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Uso de la calculadora de planeación de capacidad para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-21_

La calculadora de planeación de capacidad de Microsoft® Lync™ Server 2013 está <https://www.microsoft.com/download/details.aspx?id=36828>disponible para su descarga en. Está diseñado para ayudarle a determinar los requisitos del servidor en función de las cantidades de usuarios y las modalidades de comunicación que están habilitadas en su organización. Escriba el perfil de su organización y la calculadora le proporcionará recomendaciones que le ayudarán a planear la topología.

Las recomendaciones creadas por la calculadora son solo para fines de planeación. La simulación de carga real es necesaria para garantizar que Lync Server 2013 se haya aprovisionado correctamente. Para realizar pruebas de esfuerzo con una carga simulada, use la [herramienta de esfuerzo y rendimiento de Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724).

Una vez que haya determinado el perfil de usuario y las modalidades que desea habilitar para los usuarios, es el momento de usar la calculadora para planear el número de servidores, la memoria y el ancho de banda que necesita. Esta versión de la calculadora no proporciona instrucciones sobre los requisitos de e/s de disco.

Esta calculadora complementa a [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) y [Microsoft Lync Server](lync-server-2013-planning.md). Use la calculadora una vez que haya revisado la guía y haya creado una topología recomendada mediante la herramienta de planeación.

Puede beneficiarse de la calculadora si tiene información precisa y detallada sobre su perfil de usuario específico. Por ejemplo, el porcentaje de usuarios habilitados para voz, promedio de llamadas por usuario y hora, duración de las llamadas y el porcentaje de usuarios simultáneos en conferencias puede hacer una gran diferencia en los requisitos del servidor. La precisión de las recomendaciones que crea la calculadora depende de la exactitud de la información proporcionada.

<div>

## <a name="using-the-capacity-calculator"></a>Uso de la calculadora de capacidad

La calculadora es una hoja de cálculo de Microsoft Excel®. Las celdas de color naranja son para su entrada. Se especifican los valores predeterminados (80.000 usuarios en un grupo con doce servidores front-end), pero puede cambiar estos valores según las necesidades de su organización.

El modelo de uso contiene las siguientes secciones. Para calcular los requisitos de capacidad, escriba los datos como se describe:

**Mensajería instantánea y presencia**

  - En número de usuarios, escriba el número de usuarios que van a iniciar sesión de forma simultánea. Este número suele ser el 80% del número total de usuarios aprovisionados. En la mayoría de los casos, el 100% de los usuarios simultáneos estará habilitado para mensajería instantánea y presencia. El valor predeterminado es 80.000.

  - Número medio de contactos en la lista de contactos indica el número de contactos que estamos usando para validar los requisitos del sistema. Este número no es modificable.

**Telefonía IP empresarial**

  - En usuarios habilitados para telefonía IP empresarial, escriba el porcentaje de usuarios que están habilitados para telefonía IP empresarial. El valor predeterminado es 60%.

  - En número medio de llamadas por usuario por hora (máximo), escriba el número de llamadas por hora que se espera que el usuario medio participe durante los períodos de carga máxima. El valor predeterminado es 4.

  - En porcentaje de llamadas que usan la omisión de medios, escriba el porcentaje de llamadas realizadas por los usuarios que pasarán por alto el servidor de mediación. El valor predeterminado es 65%.

  - En porcentaje de los usuarios de voz implicados en las llamadas de UC a RTC, escriba el porcentaje de llamadas de su organización que son llamadas telefónicas de UC a RTC. El valor predeterminado es 60%.

  - En porcentaje de los usuarios de voz implicados en las llamadas de UC a UC se muestra el porcentaje de usuarios que están habilitados para telefonía IP empresarial que solo se habilitarán para las llamadas de comunicaciones unificadas. Este número se calcula en función de lo que se especifique para el porcentaje de usuarios de voz habilitados para llamadas de UC a RTC.

**Conferencia**

  - En porcentaje de usuarios en conferencias simultáneas, escriba el porcentaje de usuarios que se participarán simultáneamente en conferencias. El valor predeterminado es el 5%.

  - En porcentaje de conferencias con sólo mensajería instantánea del grupo (sin voz), escriba el porcentaje de conferencias cuyas conferencias implicarán únicamente mensajería instantánea; es decir, que no incluyen un componente de audio. El valor predeterminado es el 10%.

  - En porcentaje de usuarios que usan la Conferencia de acceso telefónico local, escriba el porcentaje de participantes simultáneos en conferencias que utilizarán la Conferencia de acceso telefónico local. El valor predeterminado es el 15%.

  - En porcentaje de conferencias con voz, escriba el porcentaje de conferencias que incluirán un componente de audio.
    
      - Si el 20% de las conferencias de voz también incluirá vídeo normal, seleccione la casilla de verificación incluir vídeo (sin vista múltiple).
    
      - Si el 20% de las conferencias también incluirá vídeo con varias vistas, active la casilla de verificación incluir varias vistas.
    
      - Si el 50% de las conferencias de voz también incluirá el uso compartido de aplicaciones, active la casilla incluir uso compartido de aplicaciones.
    
      - Si el 20% de las conferencias de voz incluye cargas de datos, como presentaciones de Microsoft PowerPoint®, active la casilla de verificación incluir conferencia Web.

**Movilidad**

  - En porcentaje de usuarios habilitados para movilidad, escriba el porcentaje de usuarios que se habilitarán para conectarse a Lync Server mediante dispositivos móviles. El valor predeterminado es 40%.

Una vez que haya introducido toda la información necesaria, la calculadora de capacidad estima sus requisitos. Las celdas amarillas muestran los valores calculados para los requisitos de CPU, memoria y ancho de banda en función de las pruebas realizadas en los laboratorios de rendimiento de Lync Server 2013. Los números se proporcionan como instrucciones, no se comprueba y valida cada variación única. Se calculan los siguientes valores:

  - CPU front-end: porcentaje de uso de la CPU si la carga completa se administraba a través de un servidor front-end de las mismas especificaciones que el servidor que se usaba en las pruebas de Microsoft.

  - Red en Mbps: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.

  - Memoria en GB: memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.

Las celdas verdes muestran recomendaciones para el modelo de uso que se ha especificado.

  - Total de servidores front-end: el número de servidores físicos necesarios se basa en servidores dedicados que ejecutan Lync Server 2013 con dos procesadores, HEX-Core, con 2.260 megaciclos.

  - Tenga en cuenta que se recomienda habilitar el hyperthreading y que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio y vídeo.

  - Servidores perimetrales: número de servidores perimetrales necesarios, en función del 30% de todos los usuarios simultáneos que se comunican a través de los servidores perimetrales. Este porcentaje no se puede cambiar en la calculadora.

  - Almacén de servicios y registro detallado de llamadas/calidad de la experiencia almacén: el número de almacenes necesarios para las características de archivado o supervisión, si están habilitados en la organización.

  - Se requiere servidor de base de datos back-end (grupos requeridos): el número de servidores de base de datos back-end necesarios para admitir la carga de trabajo seleccionada.

Además, en la fila junto a total de servidores front-end, se proporciona más información acerca de la carga de los servidores y la red para todas las cargas de trabajo previstas combinadas.

  - Carga de CPU media: el uso medio de CPU por servidor front-end.

  - Red en Mbps: la asignación de ancho de banda necesaria para admitir el modelo de uso que ha escrito.

  - Memoria en GB: memoria, en gigabytes, necesaria para cada servidor front-end.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Ajustar para sus procesadores

Todas las cifras de uso de la CPU de la hoja de cálculo suponen que cada servidor tiene un procesador dual, HEX-Core con 2,26 GHz, al menos 32 GB de memoria y 8 o más unidades de disco duro 10.000-RPM con al menos 72 GB de espacio libre en disco.

Si los servidores tienen distintos procesadores, puede ajustar las cifras para que se ajusten a su hardware.

</div>

</div>

<span> </span>

</div>

</div>

</div>

