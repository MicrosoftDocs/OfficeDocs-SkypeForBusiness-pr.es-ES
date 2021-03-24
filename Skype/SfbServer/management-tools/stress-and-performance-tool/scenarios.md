---
title: Escenarios de rendimiento para la herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Tareas que deberá realizar para configurar Skype Empresarial Server 2015 para realizar pruebas de carga y rendimiento con la Herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105376"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Escenarios de rendimiento para la herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
 
Tareas que deberá realizar para configurar Skype Empresarial Server 2015 para realizar pruebas de carga y rendimiento con la Herramienta de esfuerzo y rendimiento.
  
Para ejecutar la herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 (LyncPerfTool), la topología de Skype Empresarial Server 2015 debe configurarse primero para escenarios relevantes para usted. Si Skype Empresarial Server 2015 no está configurado o está configurado incorrectamente, es muy probable que la simulación de carga falle. Con la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, proporcionamos scripts del Shell de administración de Skype Empresarial Server y archivos de recursos básicos como parte de la descarga de la [herramienta](https://www.microsoft.com/download/details.aspx?id=50367). Se pueden usar como punto de partida para configurar la implementación de Skype Empresarial Server. En este artículo se describen los Windows PowerShell ejemplos proporcionados.
  
> [!NOTE]
> Este tema no le ayudará a describir cómo configurar Skype Empresarial Server 2015 en general, tenemos otros temas de planeación e implementación para eso. Para obtener más información sobre cómo Windows PowerShell en Skype Empresarial Server 2015, vea la documentación del Shell de administración de Skype Empresarial Server en Insertar introducción AQUÍ. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Acerca de cómo ejecutar scripts de shell de administración de Skype Empresarial Server

Proporcionamos scripts de PowerShell de ejemplo que puede usar para preparar las simulaciones de carga. Dado que estos scripts están diseñados para la simulación de carga, encontrará que son simples y permisivos. Puede que no sea apropiado para el entorno de producción. Una vez más, subrayamos que estos scripts son ejemplos, deberá revisarlos y, en muchos casos, realizar cambios relevantes para su entorno antes de poder hacer un uso práctico de ellos. Como mínimo, esperaríamos que deba modificar el script de grupo de servicio de respuesta (RSG) con la topología en mente (para especificar los agentes asignados a los grupos de agentes). Pero no es necesario ejecutarlo, si no es necesario.
  
> [!CAUTION]
> Tenga cuidado en revisar y comprender estas muestras. Los scripts sobrescribirán cualquier configuración existente en la topología cuando se ejecute. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nombres de versión de cliente de la herramienta de esfuerzo y rendimiento

Es posible que deba configurar la directiva de comprobación de versiones de cliente si ha cambiado anteriormente la configuración de los valores predeterminados. Si no está seguro acerca de esto, consulte la documentación [de comprobación de versión de cliente](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).
  
La Herramienta de esfuerzo y rendimiento usa las siguientes versiones del agente de usuario de forma predeterminada al comunicarse con Skype Empresarial Server 2015:
  
- LSPT/15.0.0.0 (Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015)
    
- OCPHONE/.0.522
    
Para el cliente de movilidad (UCWA) en LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
