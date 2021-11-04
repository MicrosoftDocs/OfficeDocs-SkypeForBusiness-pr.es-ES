---
title: Calculadora de planeamiento de capacidad de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Resumen: Cómo usar la herramienta calculadora de capacidad.'
ms.openlocfilehash: bfceeb643f9043053c70670f19cbc91b325acbb4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745926"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de planeamiento de capacidad de Skype Empresarial Server
 
**Resumen:** Cómo usar la herramienta calculadora de capacidad.

> [!NOTE]
> Este artículo hace referencia Skype Empresarial Server descargas de 2015, pero se aplica a:
> - Skype Empresarial Server 2019.
> - Skype Empresarial Server 2015.
  
La calculadora de capacidad de [Skype Empresarial Server 2015](https://www.microsoft.com/download/details.aspx?id=51196) y la calculadora de capacidad de [Skype Empresarial Server 2019](https://www.microsoft.com/download/details.aspx?id=57509) aumentan la herramienta de planeación de [Skype Empresarial](https://www.microsoft.com/download/details.aspx?id=50357) y la documentación de implementación ( Plan for your[Skype Empresarial Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and Plan for your Skype Empresarial Server [2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively). Use la calculadora después de revisar la guía y crear una topología recomendada mediante la Herramienta de planeación.
  
La Skype Empresarial Server de capacidad le ayuda a determinar los requisitos del servidor en función del número de usuarios y las herramientas de comunicación que usa su organización. Después de determinar el perfil de usuario y las funciones que desea habilitar para los usuarios, use la calculadora para determinar el número de servidores, memoria y ancho de banda que necesitará. Esta versión de la calculadora no proporciona instrucciones para los requisitos de E/S de disco.
  
Puedes beneficiarte más de la calculadora si tienes información precisa y detallada sobre tu perfil de usuario específico. Por ejemplo, el porcentaje de usuarios habilitados para voz, el promedio de llamadas por usuario por hora, la duración de la llamada y el porcentaje de usuarios simultáneos en conferencias pueden marcar una gran diferencia en los requisitos del servidor. La precisión de las recomendaciones creadas por la calculadora depende de la precisión de la información que proporcione.
  
Una vez que haya usado la Herramienta de planeación y la calculadora de planeación de capacidad, debe simular la carga propuesta y planeada para asegurarse de que Skype Empresarial Server se aprovisionará adecuadamente. Para realizar pruebas de esfuerzo bajo una carga simulada, use la herramienta Skype Empresarial Server [stress and performance documentada](https://www.microsoft.com/download/details.aspx?id=50367) en [Skype Empresarial Server Stress and Performance Tool](./stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="using-the-capacity-calculator"></a>Uso de la calculadora de capacidad

La calculadora es una Microsoft Excel hoja de cálculo. Las celdas de entrada son de color naranja. Los valores predeterminados se introducen en las celdas (para Skype Empresarial Server 2015, 80 000 usuarios en un grupo con doce servidores front-end, mientras que para Skype Empresarial Server 2019, 106 000 usuarios en un grupo con dieciséis servidores front-end), pero debe cambiar estos valores para que coincidan con las necesidades de su organización.
  
El modelo de uso contiene las secciones siguientes. Para calcular los requisitos de capacidad, escriba los datos como se describe a partir de la parte superior de la hoja y trabajando fila por fila: 
  
 **Mensajería instantánea y presencia**
  
- En **Número de usuarios**, escriba el número de usuarios que van a haber iniciado sesión a la vez. Este número suele ser el 80 % del número total de usuarios aprovisionados. En la mayoría de las situaciones, el 100 % de los usuarios simultáneos estarán habilitados para mensajería instantánea y presencia. El valor predeterminado es 80 000 para Skype Empresarial Server 2015 y 106 000 usuarios para Skype Empresarial Server 2019.
    
- **El número promedio de contactos en la lista** de contactos indica el número de contactos que estamos usando para validar los requisitos del sistema. Este número es fijo y no es algo que debería cambiar.
    
  **Telefonía IP empresarial**
  
- En **Usuarios habilitados para Telefonía IP empresarial**, escriba el porcentaje de los usuarios habilitados para Telefonía IP empresarial. El valor predeterminado es 60 %. 
    
- En Promedio de llamadas por usuario por hora **(pico),** escriba el número de llamadas por hora en las que espera que el usuario promedio participe durante las horas de carga máxima. El valor predeterminado es 4. 
    
- En **Porcentaje de llamadas que usan desvío** de medios , escriba el porcentaje de llamadas realizadas por los usuarios que omitirán el servidor de mediación. El valor predeterminado es el 65 %, pero podría ser menor si está distribuido geográficamente o tiene un gran porcentaje de usuarios que trabajan desde casa.
    
- En **Porcentaje de usuarios de voz** implicados en llamadas RTC UC , escriba el porcentaje de llamadas de su organización que son llamadas de teléfono UC-RTC. El valor predeterminado es 60 %.
    
- El porcentaje de usuarios de voz implicados en llamadas **UC-UC** muestra el porcentaje de usuarios que están habilitados para Telefonía IP empresarial que se habilitarán solo para las llamadas UC-UC. Este número se calcula en función de lo que se introduzca para porcentaje de usuarios de voz habilitados **para llamadas RTC UC.** 
    
  **Conferencia**
  
- En **Porcentaje de usuarios en conferencias simultáneas,** escriba el porcentaje de usuarios que participarán en conferencias al mismo tiempo. El valor predeterminado es 5%. 
    
- En Porcentaje de conferencias con mensajería instantánea de grupo **solo (sin voz),** escriba el porcentaje de conferencias que implicarán mensajería instantánea únicamente y no incluirán audio. El valor predeterminado es 10%
    
- En **Porcentaje de usuarios** que usan conferencias de acceso telefónico local , escriba el porcentaje de participantes en conferencias que usarán conferencias de acceso telefónico local a la vez. El valor predeterminado es 15%.
    
- En **Porcentaje de conferencias con voz,** escriba el porcentaje de conferencias que incluirán audio. 
    
  - Si el 20 % de las conferencias de voz también incluirán vídeo normal, active la casilla Incluir **vídeo (sin vista** múltiple).
    
  - Si el 20 % de las conferencias también incluirá vídeo de vista múltiple, active la casilla **Incluir vista** múltiple.
    
  - Si el 50 % de las conferencias de voz también incluirán uso compartido de aplicaciones, active la casilla Incluir uso **compartido** de aplicaciones.
    
  - Si el 20 % de las conferencias de voz incluyen cargas  de datos, como PowerPoint presentaciones, active la casilla Incluir conferencias web.
    
  **Movilidad**
  
- En **Porcentaje de usuarios habilitados para Movilidad,** escriba el porcentaje de usuarios que se habilitarán para conectarse a Skype Empresarial Server con dispositivos móviles. El valor predeterminado es el 40 %. 
    
Cuando haya especificado toda la información necesaria, la calculadora de capacidad calcula sus requisitos. Las celdas amarillas muestran valores calculados para los requisitos de CPU, memoria y ancho de banda en función de las pruebas realizadas en Skype Empresarial Server de rendimiento. Los números se proporcionan como una directriz, no todas las variaciones se prueban y validan. Se calculan los siguientes valores: 
  
- **CPU front-end:** porcentaje de uso de CPU si la carga completa estaba siendo manejada por un servidor front-end con las mismas especificaciones que el servidor que se usó en las pruebas (vea la descripción al final de este artículo).
    
- **Red en Mbps:** requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.
    
- **Memoria en GB:** memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.
    
Las celdas verdes muestran recomendaciones para el modelo de uso que ha especificado. 
  
- **Servidores front-end** totales: el número de servidores físicos necesarios se basa en servidores dedicados que ejecutan Skype Empresarial Server 2015 con procesador dual, núcleo hexadecimal, con 2.260 megaciclos o Skype Empresarial Server 2019 con Intel Xeon E5-2673 v3, procesador dual, hex-core.
    
    Tenga en cuenta que se recomienda habilitar el hyperthreading y se ha demostrado que mejora el rendimiento de los servidores que admiten audio y vídeo.
    
- **Servidores perimetrales:** el número de servidores perimetrales necesarios, en función del 30 % de todos los usuarios simultáneos que se comunican a través de los servidores perimetrales. Este porcentaje no se puede cambiar en la calculadora. 
    
- Almacén de servicios de archivado/registro detallado de **llamadas/Calidad** de la experiencia: el número de almacenes necesarios para las características de archivado o supervisión, si están habilitadas en la organización.
    
- Servidor de base de datos **back-end requerido (grupos necesarios):** el número de servidores de bases de datos back-end necesarios para admitir la carga de trabajo seleccionada.
    
Además, en la fila junto a Servidores front-end totales, se proporciona más información sobre la carga en los servidores y la red para todas las cargas de trabajo planeadas combinadas.
  
- **Carga media de CPU:** el uso promedio de CPU por servidor front-end.
    
- **Red en Mbps:** la asignación de ancho de banda necesaria para admitir el modelo de uso especificado.
    
- **Memoria en GB:** memoria, en gigabytes, necesaria para cada servidor front-end.
    
### <a name="adjusting-for-your-processors"></a>Ajustar para sus procesadores

Todas las cifras de uso de CPU de la hoja de cálculo suponen que cada servidor de Skype Empresarial Server 2015 tiene un procesador dual, núcleo hexadecimal con 2,26 GHz, al menos 32 GB de memoria y 8 o más unidades de disco duro de 10.000 RPM con al menos 72 GB de espacio libre en disco. Para cada servidor de Skype Empresarial Server 2019, todas las cifras de uso de CPU de la hoja de cálculo suponen que cada servidor tiene un procesador dual, un núcleo hexadecimal con Intel Xeon E5-2673 v3, al menos 64 GB de memoria y 8 o más unidades de disco duro de 10 000 RPM con al menos 72 GB de espacio libre en disco.
  
Si los servidores tienen procesadores diferentes, puede ajustar las cifras para que coincidan con el hardware.
