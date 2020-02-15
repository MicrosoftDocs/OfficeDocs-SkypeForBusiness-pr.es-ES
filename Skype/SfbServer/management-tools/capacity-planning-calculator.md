---
title: Calculadora de planeación de capacidad de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Resumen: Cómo usar la herramienta calculadora de capacidad.'
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031084"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de planeación de capacidad de Skype empresarial Server
 
**Resumen:** Cómo usar la herramienta calculadora de capacidad.

> [!NOTE]
> Este artículo hace referencia a descargas de Skype empresarial Server 2015, pero se aplica a:
> - Skype empresarial Server 2019.
> - Skype empresarial Server 2015.
  
La calculadora de capacidad de [Skype empresarial server 2015](https://www.microsoft.com/download/details.aspx?id=51196) y la [calculadora de capacidad de skype empresarial Server 2019](https://www.microsoft.com/download/details.aspx?id=57509) amplían la [herramienta de planeación de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=50357) y la documentación de implementación ([planeación de la implementación de Skype empresarial Server 2015](../plan-your-deployment/plan-your-deployment.md) y [planeación de la implementación de Skype empresarial Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) , respectivamente). Use la calculadora una vez que haya revisado la guía y haya creado una topología recomendada mediante la herramienta de planeación.
  
La calculadora de capacidad de Skype empresarial Server le ayuda a determinar los requisitos del servidor en función del número de usuarios y las herramientas de comunicación que usa su organización. Una vez que haya determinado el perfil de usuario y las funciones que desea habilitar para los usuarios, use la calculadora para determinar el número de servidores, memoria y ancho de banda que necesitará. Esta versión de la calculadora no proporciona instrucciones sobre los requisitos de e/s de disco.
  
Puede beneficiarse de la calculadora si tiene información precisa y detallada sobre su perfil de usuario específico. Por ejemplo, el porcentaje de usuarios habilitados para voz, promedio de llamadas por usuario y hora, duración de las llamadas y el porcentaje de usuarios simultáneos en conferencias puede hacer una gran diferencia en los requisitos del servidor. La precisión de las recomendaciones que crea la calculadora depende de la exactitud de la información proporcionada.
  
Una vez que haya usado la herramienta de planeación y la calculadora de planeación de capacidad, debe simular la carga propuesta y planeada para asegurarse de que Skype empresarial Server se aprovisionará adecuadamente. Para realizar pruebas de esfuerzo en una carga simulada, use la [herramienta de esfuerzo y rendimiento de Skype empresarial Server](https://www.microsoft.com/download/details.aspx?id=50367) que se documenta en la [herramienta de esfuerzo y rendimiento de Skype empresarial Server](https://technet.microsoft.com/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Uso de la calculadora de capacidad

La calculadora es una hoja de cálculo de Microsoft Excel. Las celdas de entrada son de color naranja. Los valores predeterminados se escriben en las celdas (para los usuarios de Skype empresarial Server 2015, 80.000 en un grupo con doce servidores front-end, mientras que Skype empresarial Server 2019, 106.000 los usuarios en un grupo con dieciséis servidores front-end), pero debe cambiar estos valores a hacer coincidir con las necesidades de su organización.
  
El modelo de uso contiene las siguientes secciones. Para calcular los requisitos de capacidad, escriba los datos tal y como se describen comenzando en la parte superior de la hoja y trabajando hacia abajo fila por fila: 
  
 **Mensajería instantánea y presencia**
  
- En **número de usuarios**, escriba el número de usuarios que se iniciarán sesión a la vez. Este número suele ser el 80% del número total de usuarios aprovisionados. En la mayoría de los casos, el 100% de los usuarios simultáneos estará habilitado para mensajería instantánea y presencia. El valor predeterminado es 80.000 para Skype empresarial Server 2015 y 106.000 usuarios para Skype empresarial Server 2019.
    
- **Número medio de contactos en la lista** de contactos indica el número de contactos que estamos usando para validar los requisitos del sistema. Este número es fijo y no es algo que deba cambiar.
    
  **Telefonía IP empresarial**
  
- En **usuarios habilitados para telefonía IP empresarial**, escriba el porcentaje de usuarios habilitados para telefonía IP empresarial. El valor predeterminado es 60%. 
    
- En **número medio de llamadas por usuario por hora (máximo)**, escriba el número de llamadas por hora que se espera que el usuario medio participe durante los períodos de carga máxima. El valor predeterminado es 4. 
    
- En **porcentaje de llamadas que usan la omisión de medios**, escriba el porcentaje de llamadas realizadas por los usuarios que pasarán por alto el servidor de mediación. El valor predeterminado es 65%, pero podría ser menor si está disperso geográficamente o tiene un gran porcentaje de usuarios que trabajan desde casa.
    
- En **porcentaje de los usuarios de voz implicados en las llamadas de UC a RTC**, escriba el porcentaje de llamadas de su organización que son llamadas telefónicas de UC a RTC. El valor predeterminado es 60%.
    
- **Porcentaje de usuarios de voz implicados en las llamadas de UC a UC** muestra el porcentaje de usuarios que están habilitados para telefonía IP empresarial que solo se habilitarán para las llamadas de comunicaciones unificadas. Este número se calcula en función de lo que se especifique para el **porcentaje de usuarios de voz habilitados para llamadas de UC a RTC**. 
    
  **Conferencia**
  
- En **porcentaje de usuarios en conferencias simultáneas**, escriba el porcentaje de usuarios que participarán en conferencias al mismo tiempo. El valor predeterminado es el 5%. 
    
- En **porcentaje de conferencias con sólo mensajería instantánea del grupo (sin voz)**, escriba el porcentaje de conferencias que implicarán sólo mensajería instantánea y no incluyen audio. El valor predeterminado es el 10%.
    
- En **porcentaje de usuarios que usan la Conferencia de acceso telefónico local**, escriba el porcentaje de participantes en conferencias que usarán conferencias de acceso telefónico local al mismo tiempo. El valor predeterminado es el 15%.
    
- En **porcentaje de conferencias con voz**, escriba el porcentaje de conferencias que incluirán audio. 
    
  - Si el 20% de las conferencias de voz también incluirá vídeo normal, seleccione la casilla de verificación **incluir vídeo (sin vista múltiple)** .
    
  - Si el 20% de las conferencias también incluirá vídeo con varias vistas, active la casilla de verificación **incluir varias vistas** .
    
  - Si el 50% de las conferencias de voz también incluirá el uso compartido de aplicaciones, active la casilla **incluir uso compartido de aplicaciones** .
    
  - Si el 20% de las conferencias de voz incluye cargas de datos, como presentaciones de PowerPoint, active la casilla de verificación **incluir conferencia web** .
    
  **Movilidad**
  
- En **porcentaje de usuarios habilitados para movilidad**, escriba el porcentaje de usuarios que se habilitarán para conectarse a Skype empresarial Server mediante dispositivos móviles. El valor predeterminado es 40%. 
    
Una vez que haya introducido toda la información necesaria, la calculadora de capacidad estima sus requisitos. Las celdas amarillas muestran los valores calculados para los requisitos de CPU, memoria y ancho de banda en función de las pruebas realizadas en los laboratorios de rendimiento de Skype empresarial Server. Los números se proporcionan como instrucciones, no se comprueba y valida cada variación única. Se calculan los siguientes valores: 
  
- **CPU front-end**: porcentaje de uso de la CPU si la carga completa se administraba a través de un servidor front-end de las mismas especificaciones que el servidor usado en las pruebas (vea la descripción al final de este artículo).
    
- **Red en Mbps**: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.
    
- **Memoria en GB**: memoria necesaria en GIGABYTES (GB) para la carga de trabajo correspondiente.
    
Las celdas verdes muestran recomendaciones para el modelo de uso que se ha especificado. 
  
- **Total de servidores front-end**: el número de servidores físicos necesarios se basa en servidores dedicados que ejecutan Skype empresarial Server 2015 con procesador dual, HEX-Core, con 2.260 megaciclos o Skype empresarial Server 2019 con Intel Xeon E5-2673 V3, procesador dual, HEX-Core.
    
    Tenga en cuenta que se recomienda habilitar el hyperthreading y que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio y vídeo.
    
- **Servidores perimetrales**: número de servidores perimetrales necesarios, en función del 30% de todos los usuarios simultáneos que se comunican a través de los servidores perimetrales. Este porcentaje no se puede cambiar en la calculadora. 
    
- **Almacén de servicios y registro detallado de llamadas/calidad de la experiencia almacén**: el número de almacenes necesarios para las características de archivado o supervisión, si están habilitados en la organización.
    
- Se **requiere servidor de base de datos back-end (grupos requeridos)**: el número de servidores de base de datos back-end necesarios para admitir la carga de trabajo seleccionada.
    
Además, en la fila junto a total de servidores front-end, se proporciona más información acerca de la carga de los servidores y la red para todas las cargas de trabajo previstas combinadas.
  
- **Carga de CPU media**: el uso medio de CPU por servidor front-end.
    
- **Red en Mbps**: la asignación de ancho de banda necesaria para admitir el modelo de uso que ha escrito.
    
- **Memoria en GB**: memoria, en gigabytes, necesaria para cada servidor front-end.
    
### <a name="adjusting-for-your-processors"></a>Ajustar para sus procesadores

Todas las cifras de uso de la CPU de la hoja de cálculo suponen que cada servidor de Skype empresarial Server 2015 tiene un procesador dual, HEX-Core con 2,26 GHz, al menos 32 GB de memoria y 8 o más unidades de disco duro 10.000-RPM con al menos 72 GB de espacio libre en disco. Para cada servidor de Skype empresarial Server 2019, todas las cifras de uso de la CPU de la hoja de cálculo suponen que cada servidor tiene un procesador dual, HEX-Core con Intel Xeon E5-2673 V3, al menos 64 GB de memoria y 8 o más unidades de disco duro 10.000-RPM con al menos 72 GB de disco libre ritmo.
  
Si los servidores tienen distintos procesadores, puede ajustar las cifras para que se ajusten a su hardware.
  
