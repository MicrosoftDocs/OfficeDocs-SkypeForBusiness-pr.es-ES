---
title: Skype Empresarial Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: La Skype Empresarial Server de esfuerzo y rendimiento de 2015 se usa durante la planeación de capacidad y la optimización del rendimiento en entornos de prueba o no de producción.
ms.openlocfilehash: 140ca0d169c9863fe3104837dae294ee49bc0f48
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839862"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype Empresarial Server 2015 Stress and Performance Tool
 
La Skype Empresarial Server de esfuerzo y rendimiento de 2015 se usa durante la planeación de capacidad y la optimización del rendimiento en entornos de prueba o no de producción.
  
La Skype Empresarial Server 2015 Stress and Performance Tool incluye herramientas que simplificarán la planeación de capacidad para Skype Empresarial Server 2015. La Skype Empresarial Server de esfuerzo y rendimiento de 2015 le ayudará a:
  
- Simplifique la planeación de hardware Skype Empresarial Server
    
- Proporcionar mayor conocimiento y procedimientos recomendados para la optimización del rendimiento
    
- Medir el rendimiento de las Skype Empresarial Server implementación
    
Normalmente, esta herramienta se usa después de usar la herramienta de planeación de [Skype Empresarial Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y refinar la topología con la calculadora de planeación de capacidad de [Skype Empresarial Server 2015](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Esta herramienta no se actualizará para Skype Empresarial Server 2019.
  
## <a name="tests"></a>Pruebas

La Herramienta de esfuerzo y rendimiento puede simular estos tipos de carga de usuario:
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Mensajería instantánea (MI) y presencia   |Audioconferencia   |
|Uso compartido de aplicaciones   |Simulación de voz sobre IP (VoIP), incluida la simulación de red telefónica conmutada (PTSN)   |
|Conferencias de cliente de Web Access   |Operador automático de conferencia   |
|Grupos de respuesta   |Expansión de listas de distribución   |
|Descarga de libreta de direcciones y consulta de libreta de direcciones   |Llamadas mejoradas 911 (E911) y perfil de ubicación (plan de marcado)   |
|MultiView   |Colaboración de datos   |
|Movilidad   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicaciones y archivos incluidos con la Skype Empresarial Server de esfuerzo y rendimiento de 2015

Estas aplicaciones forman parte de la Skype Empresarial Server de esfuerzo y rendimiento:
  
|Herramienta|Descripción|
|:-----|:-----|
|UserProvisioningTool.exe   |Esta herramienta se usa para crear usuarios y contactos.   |
|UserProfileGenerator.exe   |Se usa para configurar las características de la carga de usuario que está simulando.   |
|LyncPerfTool.exe   |La herramienta que simula la carga del usuario.   |
|Default.tmx   |Necesario para usar la Skype Empresarial Server de registro de 2015.   |
|Ejemplos de script de aprovisionamiento   |Se usa para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos. Es probable que deba modificarlos para que sean relevantes para su entorno en particular.   |
   
## <a name="topics-in-this-section"></a>Temas de esta sección

Debe revisar los siguientes artículos si necesita saber más:
  
- [Requisitos previos y configuración de la Skype para la herramienta de rendimiento y esfuerzo de Busines](prerequisites-and-setup.md)
    
- [Escenarios de rendimiento para la Skype Empresarial Server de esfuerzo y rendimiento de 2015](scenarios.md)
    
  - [Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento](provisioning-the-topology-to-run-load.md)
    
  - [Configuración de directivas para la Skype Empresarial Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [Uso de la Skype Empresarial Server de esfuerzo y rendimiento de 2015](using-the-tool.md)
    
- [Faq for the Skype Empresarial Server 2015 Stress and Performance Tool](faq.md)
    

