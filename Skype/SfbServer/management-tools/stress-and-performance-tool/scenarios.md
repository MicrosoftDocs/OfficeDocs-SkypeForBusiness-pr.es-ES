---
title: Escenarios de rendimiento para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tareas que necesitará realizar para configurar Skype para Business Server 2015 hacer pruebas de rendimiento y carga-, mediante la herramienta de rendimiento y esfuerzo.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874594"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Escenarios de rendimiento para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
 
Tareas que necesitará realizar para configurar Skype para Business Server 2015 hacer pruebas de rendimiento y carga-, mediante la herramienta de rendimiento y esfuerzo.
  
Para ejecutar la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento (LyncPerfTool), en primer lugar debe configurarse la Skype para topología empresarial Server 2015 para escenarios relevantes para usted. Si Skype para Business Server 2015 no está configurado o no está configurado correctamente, es muy probable que se lleve a cabo la simulación de carga. Con Skype para Business Server 2015 herramienta de esfuerzo y rendimiento, ofrecemos ejemplo Skype para las secuencias de comandos de Shell de administración de servidor empresarial y archivos de recursos básicos como parte de la [descarga de la herramienta](https://www.microsoft.com/download/details.aspx?id=50367). Estos se pueden usar como punto de partida para configurar su Skype para la implementación de Business Server. En este artículo se describe los ejemplos de Windows PowerShell proporcionados.
  
> [!NOTE]
> En este tema no le ayudará a describen cómo configurar Skype para Business Server 2015, por lo general, tenemos otros temas de planeación e implementación para. Para obtener información detallada sobre cómo trabajar con Windows PowerShell en Skype para Business Server 2015, vea el Skype para la documentación del Shell de administración de servidor empresarial en Insertar aquí la introducción. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Acerca de la ejecución de Skype para la administración de Business Server secuencias de comandos de shell

Nos permite proporcionar scripts de PowerShell de ejemplo que puede usar para preparar sus simulaciones de carga. Debido a que estas secuencias de comandos están diseñados para la simulación de carga, encontrará que sean sencilla y permissive. Puede que no sea apropiado para su entorno de producción. Vuelva a se hace hincapié en que estas secuencias de comandos son ejemplos, que necesitará para revisarlos y en muchos casos realice cambios relevantes para su entorno antes de poder hacer un uso práctico de ellos. Como mínimo, que esperábamos que necesita modificar la secuencia de comandos del grupo de servicio de respuesta (RSG) con su topología en cuenta (para especificar a los agentes asignados a los grupos de agentes). Pero no es necesario ejecutar, si no es necesario.
  
> [!CAUTION]
> Por favor, tenga cuidado al revisar y descripción de estos ejemplos. Las secuencias de comandos sobrescribe cualquier configuración existente en la topología cuando ejecuta. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Herramienta de esfuerzo y rendimiento nombres de versión de cliente

Es posible que necesite configurar la directiva de comprobación de la versión de cliente si anteriormente se ha cambiado la configuración de los valores predeterminados. Si no está seguro acerca de esto, consulte la [documentación de comprobación de la versión de cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
La herramienta Stress and Performance utiliza las siguientes versiones de agente de usuario de forma predeterminada cuando se comunica con Skype para Business Server 2015:
  
- LSPT/15.0.0.0 (Skype para Business Server 2015 herramienta de esfuerzo y rendimiento)
    
- OCPHONE/.0.522
    
Para el cliente de movilidad (UCWA) en LyncPerfTool:
  
- Conferencia Web de la herramienta rendimiento UCWA
    
- Herramienta de rendimiento UCWA o móvil
    

