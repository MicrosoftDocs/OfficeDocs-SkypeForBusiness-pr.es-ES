---
title: Escenarios de rendimiento para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar pruebas de carga y rendimiento, mediante la herramienta stress and performance.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983855"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Escenarios de rendimiento para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015
 
Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar pruebas de carga y rendimiento, mediante la herramienta stress and performance.
  
Para ejecutar la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015 (LyncPerfTool), la topología de Skype empresarial Server 2015 debe estar configurada primero para los escenarios que le resulten relevantes. Si Skype empresarial Server 2015 no está configurado o no está configurado correctamente, es muy probable que la simulación de carga falle. Con la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015, proporcionamos ejemplos de secuencias de comandos del shell de administración de Skype empresarial Server y archivos de recursos básicos como parte de la descarga de la [herramienta](https://www.microsoft.com/download/details.aspx?id=50367). Se pueden usar como punto de partida para configurar su implementación de Skype empresarial Server. En este artículo se describen los ejemplos de Windows PowerShell proporcionados.
  
> [!NOTE]
> En este tema no se describe cómo configurar Skype empresarial Server 2015 en general, tenemos otros temas de planeación e implementación para ello. Para obtener información detallada sobre cómo trabajar con Windows PowerShell en Skype empresarial Server 2015, consulte la documentación del shell de administración de Skype empresarial Server en Insert Introduction aquí. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Acerca de la ejecución de scripts del shell de administración de Skype empresarial Server

Proporcionamos scripts de PowerShell de ejemplo que puede usar para preparar sus simulaciones de carga. Como estos scripts están diseñados para la simulación de carga, los encontrará sencillos y permisivos. Es posible que no sea adecuado para su entorno de producción. De nuevo, resalte que estos scripts son ejemplos, necesitará revisarlos y, en muchos casos, realizar cambios relevantes para su entorno antes de poder hacer un uso práctico de ellos. Como mínimo, esperamos que deba modificar el script de grupo de servicio de respuesta (RSG) con la topología teniendo en cuenta (para especificar los agentes asignados a los grupos de agentes). Pero no es necesario que lo ejecute, si no lo necesita.
  
> [!CAUTION]
> Tenga cuidado en la revisión y comprensión de estos ejemplos. Los scripts sobrescribirán cualquier configuración existente en la topología cuando se ejecute. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nombres de versión de cliente de la herramienta stress and Performance

Es posible que deba configurar la Directiva de comprobación de versión de cliente si ha cambiado previamente la configuración de los valores predeterminados. Si no está seguro de esto, consulte la documentación de comprobación de la [versión de cliente](https://msdn.microsoft.com/vsto/jj923060).
  
La herramienta stress and Performance usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Skype empresarial Server 2015:
  
- LSPT/15.0.0.0 (herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015)
    
- OCPHONE/.0.522
    
Para el cliente de movilidad (UCWA) en LyncPerfTool:
  
- Conferencia de rendimiento de UCWA Tool/Web
    
- Herramienta de Perf de UCWA/móvil
    

