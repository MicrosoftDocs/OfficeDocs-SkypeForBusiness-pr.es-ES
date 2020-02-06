---
title: Escenarios de rendimiento para la herramienta de estrés y rendimiento de Skype empresarial Server 2015
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
description: Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar el rendimiento y las pruebas de carga, con la herramienta estrés and performance.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803880"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Escenarios de rendimiento para la herramienta de estrés y rendimiento de Skype empresarial Server 2015
 
Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar el rendimiento y las pruebas de carga, con la herramienta estrés and performance.
  
Para ejecutar la herramienta Skype empresarial Server 2015 stress and Performance (LyncPerfTool), la topología de Skype empresarial Server 2015 debe estar configurada en primer lugar para los escenarios relevantes para usted. Si Skype empresarial Server 2015 no está configurado o no está configurado correctamente, es muy probable que la simulación de carga no se realice correctamente. Con la herramienta de estrés y rendimiento de Skype empresarial Server 2015, proporcionamos ejemplos de scripts del shell de administración de Skype empresarial y archivos de recursos básicos como parte de la descarga de la [herramienta](https://www.microsoft.com/download/details.aspx?id=50367). Se pueden usar como punto de partida para configurar la implementación de Skype empresarial Server. En este artículo se describen los ejemplos de Windows PowerShell proporcionados.
  
> [!NOTE]
> En general, este tema no le ayudará a describir cómo configurar Skype empresarial Server 2015, tenemos otros temas de planificación e implementación para eso. Para obtener más información sobre cómo trabajar con Windows PowerShell en Skype empresarial Server 2015, consulte la documentación del shell de administración de Skype empresarial en Insertar aquí. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Acerca de la ejecución de scripts de Shell de administración de Skype empresarial

Proporcionamos scripts de PowerShell de ejemplo que puede usar para prepararse para sus simulaciones de carga. Debido a que estas secuencias de comandos se han diseñado para la simulación de carga, los encontrarás como simples y permisivos. Es posible que no sea adecuado para su entorno de producción. Nuevamente, hacemos hincapié en que estas secuencias de comandos son muestras, necesitarás revisarlas y, en muchos casos, hacer cambios relevantes para tu entorno antes de poder hacer uso práctico de ellas. Como mínimo, esperamos que necesite modificar el script de grupo de servicio de respuesta (RSG) con su topología en mente (para especificar los agentes asignados a los grupos de agentes). Pero no tiene que hacerlo, si no lo necesita.
  
> [!CAUTION]
> Ten cuidado al revisar y comprender estas muestras. Las secuencias de comandos sobrescribirán cualquier configuración existente en la topología cuando se ejecute. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nombres de versión del cliente de la herramienta de estrés y rendimiento

Es posible que tenga que configurar la Directiva de comprobación de versión del cliente si ha cambiado previamente la configuración de los valores predeterminados. Si no está seguro de esto, Compruebe la documentación de comprobación de la [versión del cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
La herramienta de carga y rendimiento usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Skype empresarial Server 2015:
  
- LSPT/15.0.0.0 (herramienta de estrés y rendimiento de Skype empresarial Server 2015)
    
- OCPHONE/.0.522
    
Para el cliente de movilidad (UCWA) en LyncPerfTool:
  
- Herramienta de rendimiento de UCWA y conferencia Web
    
- Herramienta de Perf de UCWA/móvil
    

