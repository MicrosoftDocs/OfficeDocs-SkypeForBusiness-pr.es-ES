---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Se usa el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento durante la planeación de la capacidad y la optimización del rendimiento en entornos de prueba o que no sea de producción.
ms.openlocfilehash: 7705e92c8389e0377e805bd7d8e09aee454d9160
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904576"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Se usa el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento durante la planeación de la capacidad y la optimización del rendimiento en entornos de prueba o que no sea de producción.
  
El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento incluye herramientas que simplifican la capacidad de Skype para Business Server 2015. El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento le ayudará a:
  
- Simplificar el hardware de planeación de Skype para Business Server
    
- Le proporcionan mayor conocimiento y procedimientos recomendados para el ajuste del rendimiento
    
- Medir el rendimiento de su Skype para las implementaciones de Business Server
    
Normalmente, deberá usar esta herramienta después de utilizar el [Skype para la herramienta de planeación de Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y perfeccionamiento de la topología con el [Skype para Calculadora de planeación de capacidad de Business Server 2015](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Esta herramienta no se actualizarán para Skype para Business Server 2019.
  
## <a name="tests"></a>Pruebas

La herramienta de rendimiento y esfuerzo pueden simular estos tipos de carga de usuarios:
  
|||
|:-----|:-----|
|Instant Messaging (IM) y presencia  <br/> |Audioconferencia  <br/> |
|Uso compartido de aplicaciones  <br/> |Voz sobre IP (VoIP), incluida la red telefónica conmutada simulación (PTSN)  <br/> |
|Conferencia de acceso cliente Web  <br/> |Operador automático de conferencia  <br/> |
|Grupos de respuesta  <br/> |Expansión de la lista de distribución  <br/> |
|Descarga de la libreta de direcciones y consulta de la libreta de direcciones  <br/> |Enhanced 911 (E911) las llamadas y perfil de ubicación (plan de marcado)  <br/> |
|MultiView  <br/> |Colaboración de datos.  <br/> |
|Movilidad  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Las aplicaciones y los archivos incluidos con la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento

Estas aplicaciones son una parte de la Skype para Business Server Stress and Performance Tool:
  
|**Herramienta**|**Descripción**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Esta herramienta se utiliza para crear usuarios y contactos.  <br/> |
|UserProfileGenerator.exe  <br/> |Se usa para configurar las características de la carga del usuario que está simulando.  <br/> |
|LyncPerfTool.exe  <br/> |La herramienta que simula la carga de usuarios.  <br/> |
|Default.TMX  <br/> |Necesarios para usar el Skype para la herramienta de registro de Business Server 2015.  <br/> |
|Ejemplos de scripts de aprovisionamiento  <br/> |Se usa para configurar la topología para la ejecución de las pruebas de carga, basadas en escenarios específicos. Es probable que necesitará modificarlos para que sean relevantes para su entorno particular.  <br/> |
   
## <a name="topics-in-this-section"></a>Temas de esta sección

Si necesita saber más debe revisar los siguientes artículos:
  
- [Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial](prerequisites-and-setup.md)
    
- [Escenarios de rendimiento para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento](scenarios.md)
    
  - [Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento](provisioning-the-topology-to-run-load.md)
    
  - [Configuración de directivas para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento](configuring-policies.md)
    
- [Uso de la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento](using-the-tool.md)
    
- [Preguntas más frecuentes para la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento](faq.md)
    

