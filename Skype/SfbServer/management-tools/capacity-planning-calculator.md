---
title: Calculadora de planeamiento de capacidad de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Resumen: Cómo utilizar la herramienta Calculadora de capacidad.'
ms.openlocfilehash: 5d94dab15b104703efc76b227e6e9dd1286f9955
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-capacity-planning-calculator"></a>Calculadora de planeamiento de capacidad de Skype Empresarial Server 2015
 
**Resumen:** cómo usar la herramienta de calculadora de capacidad.
  
[Skype para Business Server 2015 capacidad calculadora](https://www.microsoft.com/en-us/download/details.aspx?id=51196) aumenta el [Skype para la herramienta de planificación de negocios 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357) y la documentación en [planear su Skype para la implementación de Business Server 2015](https://technet.microsoft.com/en-us/library/dn951427). Use la calculadora después de que haya revisado la guía y haya creado una topología recomendada mediante el uso de la Herramienta de planeación.
  
El Skype para Business Server 2015 capacidad calculadora le ayuda a usted determinar requisitos del servidor en función del número de usuarios y las herramientas de comunicación que utiliza su organización. Tras determinar el perfil de usuario y las funciones que desea habilitar para los usuarios, use la calculadora para determinar el número de servidores, la memoria y el ancho que necesitará. Esta versión de la calculadora no ofrece instrucciones sobre los requisitos de I/O de disco.
  
Para sacar el máximo partido de la calculadora necesitará información precisa y detallada sobre el perfil de usuario específico. Por ejemplo, datos como el porcentaje de usuarios habilitados para voz, la media de llamadas por usuario por hora, la duración de las llamadas y el porcentaje de usuarios simultáneos en las conferencias pueden suponer una gran diferencia en cuanto a requisitos de servidor. La precisión de las recomendaciones de la calculadora dependerá de la precisión de la información que se le suministre.
  
Una vez que se ha utilizado la herramienta de planeación y la calculadora de planeamiento de capacidad, debe simular la carga propuesta y planificada para garantizar que se suministrará adecuadamente Skype para Business Server 2015. Para realizar pruebas bajo una carga simulada de esfuerzo, utilice el [Skype para Business Server 2015 Stress y la herramienta de rendimiento](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documentado en [Skype para Business Server 2015 Stress y la herramienta de rendimiento](https://technet.microsoft.com/en-us/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Uso de la calculadora de capacidad

La calculadora es una hoja de cálculo de Microsoft Excel. Las celdas que escribe se colorean de naranja. Valores predeterminados se especifican en las celdas (por ejemplo, 80.000 usuarios en un grupo con doce servidores frontales), pero debe cambiar estos valores para que coincida con las necesidades de su organización. 
  
El modelo de uso contiene las secciones siguientes. Para calcular los requisitos de capacidad, escriba los datos tal y como se describen a partir de la parte superior de la hoja y siguiendo hacia abajo fila por fila: 
  
 **Mensajería instantánea y presencia**
  
- Bajo **Número de usuarios**, escriba el número de usuarios que iniciarán sesión a la vez. Por lo general, este número asciende al 80 % del número total de usuarios especificado. En muchas ocasiones, el 100 % de los usuarios simultáneos estarán habilitados para mensajería instantánea y presencia. El valor predeterminado es 80 000.
    
- **El número medio de contactos de la Lista de contactos** es el número de contactos que deberá usar para validar los requisitos del sistema. Este número es fijo y no debería modificarse.
    
 **Telefonía IP empresarial**
  
- En **Usuarios habilitados para Telefonía IP empresarial**, escriba el porcentaje de los usuarios que se han habilitado para este tipo de telefonía. El valor predeterminado es el 60 %. 
    
- En **Número medio de llamadas por usuario por hora (pico)**, escriba el número de llamadas por hora en las que calcula que participará el usuario medio durante las horas de pico de carga. El valor predeterminado es 4. 
    
- En **Porcentaje de llamadas que usan el desvío de medios**, escriba el porcentaje de llamadas realizadas por sus usuarios que desviarán el Servidor de mediación. El valor predeterminado es del 65 % pero podría ser más bajo si se encuentran repartidos geográficamente o si tiene un porcentaje más grande de usuarios que trabajan desde casa.
    
- **Porcentaje de usuarios de voz implicados en las llamadas PSTN de UC**, escriba el porcentaje de llamadas de su organización que son llamadas de teléfono PSTN de comunicaciones unificadas. El valor predeterminado es el 60 %.
    
- **Porcentaje de usuarios de voz en llamadas de UC a UC** muestra el porcentaje de usuarios habilitados para Telefonía IP empresarial que solo podrán realizar llamadas de UC a UC. Este número se calcula en función del dato que se ha especificado en **Porcentaje de usuarios de voz en llamadas de UC a RTC**. 
    
 **Conferencias **
  
- En **Porcentaje de usuarios en conferencias simultáneas**, escriba el porcentaje de usuarios que participarán en conferencias de forma simultánea. El valor predeterminado es el 5 %. 
    
- En **Porcentaje de conferencias solo con sesión de mensajería instantánea en grupo (sin voz)**, escriba el porcentaje de conferencias en las que solo se usará mensajería instantánea sin incluir componentes de audio. El valor predeterminado es el 10 %.
    
- En **Porcentaje de usuarios con conferencia de acceso telefónico local**, escriba el porcentaje de participantes en conferencias que usarán este tipo de conferencia a la vez. El valor predeterminado es el 15 %.
    
- En **Porcentaje de conferencias con voz**, escriba el porcentaje de conferencias que incluirán audio. 
    
  - Si el 20 % de las conferencias de voz incluirán también vídeos comunes, active la casilla **Incluye vídeo (sin vista múltiple)**.
    
  - Si el 20 % de las conferencias incluirán también vídeos en vista múltiple, active la casilla **Incluye vista múltiple**.
    
  - Si el 50% de la conferencia de voz incluirá también el uso compartido de aplicaciones, active la casilla de verificación **incluido el uso compartido de aplicaciones** .
    
  - Si el 20 % de las conferencias de voz incluirán también cargas de datos, como las presentaciones de PowerPoint, active la casilla **Incluye conferencia web**.
    
 **Movilidad**
  
- En **porcentaje de los usuarios habilitados para la movilidad**, escriba el porcentaje de los usuarios que se habilitará para conectarse a Skype para Business Server mediante dispositivos móviles. El valor predeterminado es el 40 %. 
    
Cuando se especifique toda la información necesaria, la calculadora de capacidad calculará los requisitos. Las celdas en amarillas mostrar valores calculados para la CPU, la memoria y los requisitos de ancho de banda basados en pruebas realizadas en Skype para los laboratorios de rendimiento Business Server. Las cifras se ofrecen a título orientativo (no se han comprobado y validado todas las variaciones individuales posibles). Se han calculado los valores siguientes: 
  
- **Front-end CPU**: porcentaje de uso de la CPU si la carga completa se estaba controlando mediante un servidor front-end de las mismas especificaciones que el servidor que se usó en las pruebas (consulte la descripción al final de este artículo).
    
- **Red en Mbps**: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.
    
- **Memoria en GB**: memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.
    
Las celdas verdes contienen recomendaciones para el modelo de uso que se ha especificado. 
  
- **Número total de servidores front-end**: número de servidores físicos necesarios basados en servidores dedicados que ejecutan Skype Empresarial Server 2015 con procesador dual, 6 núcleos y 2260 megaciclos.
    
    Tenga en cuenta que se recomienda habilitar el hyperthreading ya que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio o vídeo.
    
- **Servidores perimetrales**: número de servidores perimetrales necesarios calculado a partir del 30 % de todos los usuarios simultáneos que usan estos servidores para comunicarse. Este porcentaje de la calculadora no se puede modificar. 
    
- **Almacén de los servicios de archivado/registro detallado de llamadas/calidad de la experiencia**: número de almacenes necesarios para las características de archivado o supervisión (si se han habilitado en la organización).
    
- **Servidores de base de datos back-end necesarios (grupos necesarios)**: número de servidores de base de datos back-end necesarios para la carga de trabajo que se ha seleccionado.
    
En la fila situada junto a Número total de servidores front-end, también se facilita información sobre la carga de los servidores y la red para todas las cargas de trabajo combinadas.
  
- **Carga media de CPU**: uso medio de la CPU por servidor front-end.
    
- **Red en Mbps**: asignación de ancho de banda necesario para el modelo de uso que se ha especificado.
    
- **Memoria en GB**: memoria en gigabytes necesaria para cada servidor front-end.
    
### <a name="adjusting-for-your-processors"></a>Ajustar para sus procesadores

Todas las cifras de uso de CPU de la hoja de cálculo presuponen que todos los servidores cuentan con un procesador dual, 6 núcleos con 2,26 GHz, un mínimo de 32 GB de memoria, 8 unidades de disco duro de 10.000 RPM y 72 GB de espacio libre en disco. 
  
Si los servidores tienen distintos procesadores, puede ajustar las cifras a las de su hardware.
  

