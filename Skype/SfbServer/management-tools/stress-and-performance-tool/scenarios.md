---
title: Escenarios de rendimiento para el Skype para Business Server 2015 Stress y la herramienta de rendimiento
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tareas que debe realizar para configurar Skype para Business Server 2015 rendimiento y pruebas de carga mediante la herramienta de rendimiento y esfuerzo.
ms.openlocfilehash: 6b60d403e0a440e544874a8ed877a0b98e3e92ae
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Escenarios de rendimiento para el Skype para Business Server 2015 Stress y la herramienta de rendimiento
 
Tareas que debe realizar para configurar Skype para Business Server 2015 rendimiento y pruebas de carga mediante la herramienta de rendimiento y esfuerzo.
  
Para ejecutar el Skype para Business Server 2015 herramienta Stress and Performance (LyncPerfTool), primero debe configurarse el Skype para Business Server 2015 topología para escenarios relevantes para usted. Si Skype para Business Server 2015 no está configurado o no está configurado correctamente, es muy probable que un error la simulación de carga. Con Skype para Business Server 2015 Stress y la herramienta de rendimiento, ofrecemos ejemplo Skype para secuencias de comandos de Shell de administración de servidor de negocios y archivos de recursos básicos como parte de la [descarga de la herramienta](https://www.microsoft.com/download/details.aspx?id=50367). Estos pueden utilizarse como punto de partida para configurar su Skype para la implementación de Business Server. Este artículo describe los ejemplos de Windows PowerShell proporcionados.
  
> [!NOTE]
> Este tema no le ayudará a describir cómo configurar Skype para Business Server 2015 generalmente, tenemos otros temas de planificación e implementación para eso. Para obtener más información acerca de cómo trabajar con Windows PowerShell en Skype para Business Server 2015, consulte el Skype para la documentación del Shell de administración de servidor empresarial en Insertar aquí la introducción. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Acerca de cómo ejecutar Skype para administración de Business Server secuencias de comandos de shell

Nos permite proporcionar secuencias de comandos de PowerShell de ejemplo que puede utilizar para preparar sus simulaciones de carga. Debido a estas secuencias de comandos están destinados a la simulación de carga, encontrará que son simples y permisiva. Puede que no sea adecuado para su entorno de producción. Nuevo se hace hincapié en que estas secuencias de comandos son ejemplos, debe revisarlos y en muchos casos hacer cambios relevantes para el entorno antes de poder hacer un uso práctico de ellos. Como mínimo, esperaríamos que necesitará modificar la secuencia de comandos de grupo de servicio de respuesta (RSG) con la topología en mente (para especificar a los agentes asignados a los grupos de agente). Pero no tienes que ejecutar, si no es necesario.
  
> [!CAUTION]
> Por favor, tenga cuidado al revisar y comprender estos ejemplos. Las secuencias de comandos sobrescribirá cualquier configuración existente en la topología cuando ejecuta. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Herramienta de carga y rendimiento nombres de versión de cliente

Debe configurar la directiva de comprobación de versión del cliente si previamente ha cambiado la configuración de los valores predeterminados. Si no está seguro acerca de esto, consulte la [documentación de comprobación de versión del cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
La herramienta Stress and Performance utiliza las siguientes versiones de agente de usuario de forma predeterminada cuando se comunica con Skype para Business Server 2015:
  
- LSPT/15.0.0.0 (Skype para Business Server 2015 Stress y la herramienta de rendimiento)
    
- OCPHONE/.0.522
    
Para el cliente de movilidad (UCWA) en LyncPerfTool:
  
- Conferencia UCWA Web de la herramienta rendimiento
    
- Herramienta de rendimiento UCWA/móvil
    

