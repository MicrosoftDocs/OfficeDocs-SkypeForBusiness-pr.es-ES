---
title: Calculadora de planeamiento de capacidad de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: ca7266f5a18e21dbb964f18a791de9b8903a7f0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803000"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de planeamiento de capacidad de Skype Empresarial Server
 
**Resumen:** Cómo usar la herramienta calculadora de capacidad.

> [!NOTE]
> En este artículo se hace referencia a las descargas de Skype Empresarial Server 2015, pero se aplica a:
> - Skype Empresarial Server 2019.
> - Skype Empresarial Server 2015.
  
La Calculadora de capacidad de Skype Empresarial [Server 2015](https://www.microsoft.com/download/details.aspx?id=51196) y la Calculadora de capacidad de Skype Empresarial [Server 2019](https://www.microsoft.com/download/details.aspx?id=57509) aumentan la Herramienta de planeación de [Skype](https://www.microsoft.com/download/details.aspx?id=50357) Empresarial y la documentación de implementación (planifique su implementación de Skype Empresarial[Server 2015](../plan-your-deployment/plan-your-deployment.md) y planifique su implementación de [Skype Empresarial Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectivamente). Use la calculadora después de haber revisado la guía y creado una topología recomendada mediante la Herramienta de planeación.
  
La Calculadora de capacidad de Skype Empresarial Server le ayuda a determinar los requisitos del servidor en función del número de usuarios y las herramientas de comunicación que usa su organización. Una vez que haya determinado el perfil de usuario y las funciones que desea habilitar para los usuarios, use la calculadora para determinar el número de servidores, memoria y ancho de banda que necesitará. Esta versión de la calculadora no proporciona instrucciones para los requisitos de E/S de disco.
  
Puede beneficiarse más de la calculadora si tiene información precisa y detallada sobre su perfil de usuario específico. Por ejemplo, el porcentaje de usuarios habilitados para voz, las llamadas promedio por usuario y hora, la duración de las llamadas y el porcentaje de usuarios simultáneos en conferencias pueden marcar una gran diferencia en los requisitos del servidor. La precisión de las recomendaciones creadas por la calculadora depende de la precisión de la información que proporcione.
  
Una vez que haya usado la Herramienta de planeación y la Calculadora de planeación de capacidad, debe simular la carga propuesta y planeada para garantizar que Skype Empresarial Server se aprovisionará adecuadamente. Para realizar pruebas de esfuerzo bajo una carga simulada, use la Herramienta de esfuerzo y rendimiento de Skype Empresarial [Server](https://www.microsoft.com/download/details.aspx?id=50367) documentada en la Herramienta de esfuerzo y rendimiento de Skype Empresarial [Server.](https://technet.microsoft.com/library/mt631400.aspx)
  
## <a name="using-the-capacity-calculator"></a>Uso de la calculadora de capacidad

La calculadora es una hoja de cálculo de Microsoft Excel. Las celdas de entrada tienen un color naranja. Los valores predeterminados se introducen en las celdas (para Skype Empresarial Server 2015, 80 000 usuarios en un grupo con doce servidores front-end, mientras que para Skype Empresarial Server 2019, 106 000 usuarios en un grupo con dieciséis servidores front-end), pero debe cambiar estos valores para que se ajusten a las necesidades de su organización.
  
El modelo de uso contiene las siguientes secciones. Para calcular los requisitos de capacidad, escriba los datos como se describe empezando por la parte superior de la hoja y trabajando fila por fila: 
  
 **Mensajería instantánea y presencia**
  
- En **Número de usuarios,** escriba el número de usuarios que van a haber iniciado sesión a la vez. Este número suele ser el 80 % del número total de usuarios aprovisionados. En la mayoría de las situaciones, el 100 % de los usuarios simultáneos estará habilitado para mensajería instantánea y presencia. El valor predeterminado es 80 000 para Skype Empresarial Server 2015 y 106 000 usuarios para Skype Empresarial Server 2019.
    
- **El número medio de contactos en la lista** de contactos indica el número de contactos que estamos usando para validar los requisitos del sistema. Este número es fijo y no es algo que debería cambiar.
    
  **Telefonía IP empresarial**
  
- En **Usuarios habilitados para Telefonía IP empresarial**, escriba el porcentaje de los usuarios habilitados para Telefonía IP empresarial. El valor predeterminado es 60 %. 
    
- En Promedio de llamadas por usuario por hora **(pico),** escriba el número de llamadas por hora en las que espera que participe el usuario medio durante las horas de carga máxima. El valor predeterminado es 4. 
    
- En Porcentaje de llamadas que usan la omisión **de medios,** escriba el porcentaje de llamadas realizadas por los usuarios que omitirán el servidor de mediación. El valor predeterminado es el 65 %, pero podría ser inferior si está distribuido geográficamente o si tiene un gran porcentaje de usuarios que trabajan desde casa.
    
- En **Porcentaje de usuarios de** voz que participan en llamadas DE UC a RTC, escriba el porcentaje de llamadas de su organización que son llamadas telefónicas DE UC a RTC. El valor predeterminado es 60 %.
    
- **El porcentaje de usuarios de** voz que participan en llamadas de UC a UC muestra el porcentaje de usuarios que están habilitados para Telefonía IP empresarial que solo se habilitarán para llamadas de UC a UC. Este número se calcula en función de lo que se introduzca para el porcentaje de usuarios de voz habilitados para llamadas **DE UC a RTC.** 
    
  **Conferencia**
  
- En **Porcentaje de usuarios en conferencias simultáneas,** escriba el porcentaje de usuarios que participarán en conferencias al mismo tiempo. El valor predeterminado es 5%. 
    
- En Porcentaje de conferencias con mensajería instantánea de grupo solo **(sin voz),** escriba el porcentaje de conferencias que implicarán solo mensajería instantánea y no incluirán audio. El valor predeterminado es 10 %
    
- En **Porcentaje de usuarios** que usan conferencias de acceso telefónico local, escriba el porcentaje de participantes en conferencias que usarán las conferencias de acceso telefónico local a la vez. El valor predeterminado es 15 %.
    
- En **Porcentaje de conferencias con voz,** escriba el porcentaje de conferencias que incluirán audio. 
    
  - Si el 20 % de las conferencias de voz también incluirán vídeo normal, active la casilla Incluir **vídeo (sin vista** múltiple).
    
  - Si el 20 % de las conferencias también incluirá vídeo de varias vistas, active la casilla Incluir **vista** múltiple.
    
  - Si el 50 % de las conferencias de voz también incluirán uso compartido de aplicaciones, active la casilla Incluir uso **compartido** de aplicaciones.
    
  - Si el 20 % de las conferencias de voz incluye cargas de datos, como presentaciones de PowerPoint, active la casilla Incluir conferencia **web.**
    
  **Movilidad**
  
- En **Porcentaje de usuarios habilitados para** movilidad, escriba el porcentaje de usuarios que se habilitarán para conectarse a Skype Empresarial Server con dispositivos móviles. El valor predeterminado es 40 %. 
    
Cuando haya especificado toda la información necesaria, la calculadora de capacidad calcula sus requisitos. Las celdas amarillas muestran valores calculados para los requisitos de CPU, memoria y ancho de banda en función de las pruebas realizadas en los laboratorios de rendimiento de Skype Empresarial Server. Los números se proporcionan como una directriz, no todas las variaciones se prueban y validan. Se calculan los siguientes valores: 
  
- **CPU front-end:** porcentaje de uso de CPU si la carga completa estaba siendo manejada por un servidor front-end con las mismas especificaciones que el servidor que se usó en las pruebas (vea la descripción al final de este artículo).
    
- **Red en Mbps:** requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.
    
- **Memoria en GB:** memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.
    
Las celdas verdes muestran recomendaciones para el modelo de uso que escribió. 
  
- Total de servidores **front-end:** el número de servidores físicos necesarios se basa en servidores dedicados que ejecutan Skype Empresarial Server 2015 con procesador dual, núcleo hexadecimal, con 2.260 megaciclos o Skype Empresarial Server 2019 con Intel Xeon E5-2673 v3, procesador dual, núcleo hexadecimal.
    
    Ten en cuenta que se recomienda habilitar hyperthreading y se ha demostrado que mejora el rendimiento de los servidores que admiten audio y vídeo.
    
- **Servidores perimetrales:** número de servidores perimetrales necesarios, en función del 30 % de todos los usuarios simultáneos que se comunican a través de los servidores perimetrales. Este porcentaje no se puede cambiar en la calculadora. 
    
- **Almacén de servicios de archivado,registro** detallado de llamadas/calidad de la experiencia: el número de almacenes necesarios para las características de archivado o supervisión, si están habilitados en la organización.
    
- **Servidor de base de datos back-end requerido (grupos necesarios):** el número de servidores de bases de datos back-end necesarios para admitir la carga de trabajo seleccionada.
    
Además, en la fila junto a Total Front End Servers, se proporciona más información sobre la carga en los servidores y la red de todas las cargas de trabajo planeadas combinadas.
  
- **Carga media de CPU:** uso medio de CPU por servidor front-end.
    
- **Red en Mbps:** la asignación de ancho de banda necesaria para admitir el modelo de uso especificado.
    
- **Memoria en GB:** memoria, en gigabytes, necesaria para cada servidor front-end.
    
### <a name="adjusting-for-your-processors"></a>Ajustar para sus procesadores

Todas las cifras de uso de CPU de la hoja de cálculo suponen que cada servidor de Skype Empresarial Server 2015 tiene un procesador dual, un núcleo hexadecimal con 2,26 GHz, al menos 32 GB de memoria y 8 o más unidades de disco duro de 10 000 RPM con al menos 72 GB de espacio libre en disco. Para cada servidor de Skype Empresarial Server 2019, todas las cifras de uso de CPU de la hoja de cálculo suponen que cada servidor tiene un procesador dual, un núcleo hexadecimal con Intel Xeon E5-2673 v3, al menos 64 GB de memoria y 8 o más unidades de disco duro de 10 000 RPM con al menos 72 GB de espacio libre en disco.
  
Si los servidores tienen procesadores diferentes, puede ajustar las cifras para que coincidan con el hardware.
  
