---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: La herramienta de estrés y rendimiento de Skype empresarial Server 2015 se usa durante la planificación de la capacidad y en el ajuste del rendimiento en entornos ajenos a la producción o pruebas.
ms.openlocfilehash: efc3ed6cc7f24acc5fda7a7ae2ae818df5b43393
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816159"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
La herramienta de estrés y rendimiento de Skype empresarial Server 2015 se usa durante la planificación de la capacidad y en el ajuste del rendimiento en entornos ajenos a la producción o pruebas.
  
La herramienta de estrés y rendimiento de Skype empresarial Server 2015 incluye herramientas que simplificarán la planificación de la capacidad de Skype empresarial Server 2015. La herramienta de estrés y rendimiento de Skype empresarial Server 2015 le ayudará a:
  
- Simplificar la planificación de hardware para Skype empresarial Server
    
- Obtener un mayor conocimiento y procedimientos recomendados para ajustar el rendimiento
    
- Medir el rendimiento de las implementaciones de Skype empresarial Server
    
Normalmente usaría esta herramienta después de usar la herramienta de [planeación de Skype empresarial Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y refinar la topología con la calculadora de [planeación de capacidad de Skype empresarial 2015](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Esta herramienta no se actualizará en Skype empresarial Server 2019.
  
## <a name="tests"></a>Pruebas

La herramienta estrés and performance puede simular estos tipos de carga de usuarios:
  
|||
|:-----|:-----|
|Mensajería instantánea (mi) y presencia  <br/> |Audioconferencia  <br/> |
|Uso compartido de aplicaciones  <br/> |Voz sobre IP (VoIP), incluida una simulación de red de telefonía pública conmutada (RTC)  <br/> |
|Conferencia de cliente de Web Access  <br/> |Operador automático de la Conferencia  <br/> |
|Grupos de respuesta  <br/> |Expansión de la lista de distribución  <br/> |
|Consulta de la libreta de direcciones y descarga de la libreta de direcciones  <br/> |Llamadas y perfiles de ubicación de 911 (E911) mejorados (plan de marcado)  <br/> |
|Multivista  <br/> |Colaboración de datos.  <br/> |
|Movilidad  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicaciones y archivos incluidos con la herramienta de estrés y rendimiento de Skype empresarial Server 2015

Estas aplicaciones forman parte de la herramienta de estrés y rendimiento de Skype empresarial Server:
  
|**Utilidad**|**Descripción**|
|:-----|:-----|
|UserProvisioningTool. exe  <br/> |Esta herramienta se usa para crear usuarios y contactos.  <br/> |
|UserProfileGenerator. exe  <br/> |Se usa para configurar las características de la carga de usuarios que se está simulando.  <br/> |
|LyncPerfTool. exe  <br/> |La herramienta que simula la carga de usuarios.  <br/> |
|Default. TMX  <br/> |Necesario para usar la herramienta de registro de Skype empresarial Server 2015.  <br/> |
|Ejemplos de scripts de aprovisionamiento  <br/> |Se usa para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos. Es probable que deba modificarlos para que sean relevantes para su entorno en particular.  <br/> |
   
## <a name="topics-in-this-section"></a>Temas de esta sección

Debe revisar los artículos siguientes si necesita más información:
  
- [Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial](prerequisites-and-setup.md)
    
- [Escenarios de rendimiento para la herramienta de estrés y rendimiento de Skype empresarial Server 2015](scenarios.md)
    
  - [Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento](provisioning-the-topology-to-run-load.md)
    
  - [Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015](configuring-policies.md)
    
- [Usar la herramienta de estrés y rendimiento de Skype empresarial Server 2015](using-the-tool.md)
    
- [Preguntas más frecuentes sobre la herramienta de estrés y rendimiento de Skype empresarial Server 2015](faq.md)
    

