---
title: Calculadora de planeamiento de capacidad de Skype Empresarial Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Resumen: cómo usar la herramienta de calculadora de capacidad.'
ms.openlocfilehash: 9ec15c4bdcfee98e2f018a443c84384ebde8aaeb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888727"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de planeamiento de capacidad de Skype Empresarial Server
 
**Resumen:** cómo usar la herramienta de calculadora de capacidad.

> [!NOTE]
> En este artículo se hace referencia a Skype para descargas de Business Server 2015, pero se aplica al:
> - Skype para Business Server 2019.
> - Skype para Business Server 2015.
  
El [Skype para Calculadora de capacidad de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196) y [Skype para Calculadora de capacidad de Business Server 2019](https://www.microsoft.com/en-us/download/details.aspx?id=57509) aumentan la [Skype para la herramienta de planeación de negocio](https://www.microsoft.com/en-us/download/details.aspx?id=50357) y la documentación de implementación ([Plan para su Skype para la empresa Implementación de servidor 2015](../plan-your-deployment/plan-your-deployment.md) y [planear su Skype para la implementación empresarial Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectivamente). Use la calculadora después de que haya revisado la guía y haya creado una topología recomendada mediante el uso de la Herramienta de planeación.
  
El Skype para ayuda a la calculadora de capacidad de servidor empresarial se determinar los requisitos de servidor en función del número de usuarios y las herramientas de comunicación que usa la organización. Tras determinar el perfil de usuario y las funciones que desea habilitar para los usuarios, use la calculadora para determinar el número de servidores, la memoria y el ancho que necesitará. Esta versión de la calculadora no ofrece instrucciones sobre los requisitos de I/O de disco.
  
Para sacar el máximo partido de la calculadora necesitará información precisa y detallada sobre el perfil de usuario específico. Por ejemplo, datos como el porcentaje de usuarios habilitados para voz, la media de llamadas por usuario por hora, la duración de las llamadas y el porcentaje de usuarios simultáneos en las conferencias pueden suponer una gran diferencia en cuanto a requisitos de servidor. La precisión de las recomendaciones de la calculadora dependerá de la precisión de la información que se le suministre.
  
Una vez que ha usado la herramienta de planeación y la calculadora de capacidad de planeación, debe simular la carga propuesta y planeada para asegurarse de que se va a aprovisionar adecuadamente Skype para Business Server. Para realizar pruebas en una carga simulada de esfuerzo, use el [Skype para Business Server Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documentadas en [Skype para Business Server Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Uso de la calculadora de capacidad

La calculadora es una hoja de cálculo de Microsoft Excel. Las celdas que escribe se colorean de naranja. Los valores predeterminados se escriben en las celdas (de Skype para Business Server 2015, 80.000 usuarios en un grupo de servidores con doce servidores Front-End, mientras que para Skype para Business Server 2019, 106,000 a los usuarios en un grupo de servidores con dieciséis servidores Front-End), pero debe cambiar estos valores para coincidir con las necesidades de su organización.
  
El modelo de uso contiene las secciones siguientes. Para calcular los requisitos de capacidad, escriba los datos tal y como se describen a partir de la parte superior de la hoja y siguiendo hacia abajo fila por fila: 
  
 **Mensajería instantánea y presencia**
  
- Bajo **Número de usuarios**, escriba el número de usuarios que iniciarán sesión a la vez. Por lo general, este número asciende al 80 % del número total de usuarios especificado. En muchas ocasiones, el 100 % de los usuarios simultáneos estarán habilitados para mensajería instantánea y presencia. El valor predeterminado es 80.000 para Skype para Business Server 2015 y 106,000 a los usuarios de Skype para Business Server 2019.
    
- **El número medio de contactos de la Lista de contactos** es el número de contactos que deberá usar para validar los requisitos del sistema. Este número es fijo y no debería modificarse.
    
  **Telefonía IP empresarial**
  
- En **Usuarios habilitados para Telefonía IP empresarial**, escriba el porcentaje de los usuarios que se han habilitado para este tipo de telefonía. El valor predeterminado es el 60 %. 
    
- En **Número medio de llamadas por usuario por hora (pico)**, escriba el número de llamadas por hora en las que calcula que participará el usuario medio durante las horas de pico de carga. El valor predeterminado es 4. 
    
- En **Porcentaje de llamadas que usan el desvío de medios**, escriba el porcentaje de llamadas realizadas por sus usuarios que desviarán el Servidor de mediación. El valor predeterminado es del 65 % pero podría ser más bajo si se encuentran repartidos geográficamente o si tiene un porcentaje más grande de usuarios que trabajan desde casa.
    
- En el **porcentaje de usuarios de voz que participan en llamadas UC-RTC**, escriba el porcentaje de llamadas de la organización que son llamadas de teléfono UC-RTC. El valor predeterminado es el 60 %.
    
- **Porcentaje de usuarios de voz en llamadas de UC a UC** muestra el porcentaje de usuarios habilitados para Telefonía IP empresarial que solo podrán realizar llamadas de UC a UC. Este número se calcula en función del dato que se ha especificado en **Porcentaje de usuarios de voz en llamadas de UC a RTC**. 
    
  **Conferencias **
  
- En **Porcentaje de usuarios en conferencias simultáneas**, escriba el porcentaje de usuarios que participarán en conferencias de forma simultánea. El valor predeterminado es el 5 %. 
    
- En **Porcentaje de conferencias solo con sesión de mensajería instantánea en grupo (sin voz)**, escriba el porcentaje de conferencias en las que solo se usará mensajería instantánea sin incluir componentes de audio. El valor predeterminado es el 10 %.
    
- En **Porcentaje de usuarios con conferencia de acceso telefónico local**, escriba el porcentaje de participantes en conferencias que usarán este tipo de conferencia a la vez. El valor predeterminado es el 15 %.
    
- En **Porcentaje de conferencias con voz**, escriba el porcentaje de conferencias que incluirán audio. 
    
  - Si el 20 % de las conferencias de voz incluirán también vídeos comunes, active la casilla **Incluye vídeo (sin vista múltiple)**.
    
  - Si el 20 % de las conferencias incluirán también vídeos en vista múltiple, active la casilla **Incluye vista múltiple**.
    
  - Si el 50% de las conferencias de voz también se incluye el uso compartido de aplicaciones, seleccione la casilla de verificación **incluido el uso compartido de aplicaciones** .
    
  - Si el 20 % de las conferencias de voz incluirán también cargas de datos, como las presentaciones de PowerPoint, active la casilla **Incluye conferencia web**.
    
  **Movilidad**
  
- En **porcentaje de los usuarios habilitados para movilidad**, escriba el porcentaje de los usuarios que se habilitará para conectarse a Skype para Business Server mediante dispositivos móviles. El valor predeterminado es el 40 %. 
    
Cuando se especifique toda la información necesaria, la calculadora de capacidad calculará los requisitos. Las celdas en amarillas, muestran valores calculados de CPU, memoria y requisitos de ancho de banda en función de pruebas realizadas en Skype para laboratorios de rendimiento de Business Server. Las cifras se ofrecen a título orientativo (no se han comprobado y validado todas las variaciones individuales posibles). Se han calculado los valores siguientes: 
  
- **Front-end CPU**: porcentaje de uso de la CPU si la carga completa se estaba controlando mediante un servidor front-end de las mismas especificaciones que el servidor que se usó en las pruebas (consulte la descripción al final de este artículo).
    
- **Red en Mbps**: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.
    
- **Memoria en GB**: memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.
    
Las celdas verdes contienen recomendaciones para el modelo de uso que se ha especificado. 
  
- **Total servidores Front-End**: el número de servidores físicos requeridos se basa en servidores dedicados que ejecuten Skype para Business Server 2015 con procesador dual, seis núcleos, con 2,260 megaciclos o Skype para Business Server 2019 con Intel Xeon E5-2673 v3, dual seis núcleos de procesador.
    
    Tenga en cuenta que se recomienda habilitar el hyperthreading ya que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio o vídeo.
    
- **Servidores perimetrales**: número de servidores perimetrales necesarios calculado a partir del 30 % de todos los usuarios simultáneos que usan estos servidores para comunicarse. Este porcentaje de la calculadora no se puede modificar. 
    
- **Almacén de los servicios de archivado/registro detallado de llamadas/calidad de la experiencia**: número de almacenes necesarios para las características de archivado o supervisión (si se han habilitado en la organización).
    
- **Servidores de base de datos back-end necesarios (grupos necesarios)**: número de servidores de base de datos back-end necesarios para la carga de trabajo que se ha seleccionado.
    
En la fila situada junto a Número total de servidores front-end, también se facilita información sobre la carga de los servidores y la red para todas las cargas de trabajo combinadas.
  
- **Carga media de CPU**: uso medio de la CPU por servidor front-end.
    
- **Red en Mbps**: asignación de ancho de banda necesario para el modelo de uso que se ha especificado.
    
- **Memoria en GB**: memoria en gigabytes necesaria para cada servidor front-end.
    
### <a name="adjusting-for-your-processors"></a>Ajustar para sus procesadores

Todas las cifras de uso de CPU en la hoja de cálculo se suponen que cada Skype para Business Server 2015 server tiene un procesador dual, seis núcleos con 2,26 GHz, al menos 32 GB de memoria, y libre de unidades de disco duro 8 o más de 10.000 RPM con al menos 72 GB de espacio en disco. Para cada Skype para server Business Server 2019, todas las cifras de uso de CPU en la hoja de cálculo se suponen que cada servidor tiene un procesador dual, seis núcleos con Intel Xeon E5-2673 v3, al menos 64 GB de memoria, y unidades de disco duro 8 o más de 10.000 RPM con al menos 72 GB libre de disco s ritmo.
  
Si los servidores tienen distintos procesadores, puede ajustar las cifras a las de su hardware.
  
