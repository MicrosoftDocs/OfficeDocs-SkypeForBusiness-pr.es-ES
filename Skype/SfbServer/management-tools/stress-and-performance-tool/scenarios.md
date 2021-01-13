---
title: Escenarios de rendimiento para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
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
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814710"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Escenarios de rendimiento para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
 
Tareas que deberá realizar para configurar Skype Empresarial Server 2015 para realizar pruebas de carga y rendimiento con la Herramienta de esfuerzo y rendimiento.
  
Para ejecutar la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 (LyncPerfTool), la topología de Skype Empresarial Server 2015 debe configurarse primero para escenarios relevantes para usted. Si Skype Empresarial Server 2015 no está configurado o no está configurado correctamente, es muy probable que la simulación de carga falle. Con la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, proporcionamos scripts del Shell de administración de Skype Empresarial Server y archivos de recursos básicos como parte de la descarga de la [herramienta.](https://www.microsoft.com/download/details.aspx?id=50367) Se pueden usar como punto de partida para configurar la implementación de Skype Empresarial Server. En este artículo se describen Windows PowerShell ejemplos proporcionados.
  
> [!NOTE]
> Este tema no le ayudará a describir cómo configurar Skype Empresarial Server 2015 en general, tenemos otros temas de planeación e implementación para ello. Para obtener más información sobre cómo Windows PowerShell en Skype Empresarial Server 2015, consulte la documentación del Shell de administración de Skype Empresarial Server en Insert introduction HERE. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Acerca de cómo ejecutar scripts de shell de administración de Skype Empresarial Server

Proporcionamos scripts de PowerShell de ejemplo que puede usar para prepararse para las simulaciones de carga. Dado que estos scripts están diseñados para la simulación de carga, encontrará que son simples y permisivos. Es posible que no sea adecuado para su entorno de producción. Una vez más, destacamos que estos scripts son ejemplos, tendrá que revisarlos y, en muchos casos, realizar cambios relevantes para su entorno antes de poder usarlos de forma práctica. Como mínimo, esperamos que tenga que modificar el script de Grupo de servicio de respuesta (RSG) pensando en su topología (para especificar los agentes asignados a los grupos de agentes). Pero no es necesario ejecutarlo, si no es necesario.
  
> [!CAUTION]
> Tenga cuidado de revisar y comprender estos ejemplos. Los scripts sobrescribirán las configuraciones existentes en la topología cuando se ejecuten. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nombres de versión de cliente de stress and Performance Tool

Es posible que deba configurar la directiva de comprobación de versión de cliente si ha cambiado previamente la configuración de los valores predeterminados. Si no está seguro de esto, consulte la documentación de comprobación de [versión de cliente.](https://msdn.microsoft.com/vsto/jj923060)
  
La herramienta Stress and Performance usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Skype Empresarial Server 2015:
  
- LSPT/15.0.0.0 (Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015)
    
- OCPHONE/.0.522
    
Para el cliente de movilidad (UCWA) en LyncPerfTool:
  
- Herramienta ucwa perf/conferencia web
    
- UCWA Perf Tool/Mobile
    

