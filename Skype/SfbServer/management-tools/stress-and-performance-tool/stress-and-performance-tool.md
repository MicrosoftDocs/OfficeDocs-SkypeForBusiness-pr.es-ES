---
title: Skype Empresarial Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 381e6178994ce8d4ce2f3558bd075cf6fc3b6d43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611899"
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
  
|||
|:-----|:-----|
|Mensajería instantánea (MI) y presencia  <br/> |Audioconferencia  <br/> |
|Uso compartido de aplicaciones  <br/> |Simulación de voz sobre IP (VoIP), incluida la simulación de red telefónica conmutada (PTSN)  <br/> |
|Conferencias de cliente de Web Access  <br/> |Operador automático de conferencia  <br/> |
|Grupos de respuesta  <br/> |Expansión de listas de distribución  <br/> |
|Descarga de libreta de direcciones y consulta de libreta de direcciones  <br/> |Llamadas mejoradas 911 (E911) y perfil de ubicación (plan de marcado)  <br/> |
|MultiView  <br/> |Colaboración de datos  <br/> |
|Movilidad  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicaciones y archivos incluidos con la Skype Empresarial Server de esfuerzo y rendimiento de 2015

Estas aplicaciones forman parte de la Skype Empresarial Server de esfuerzo y rendimiento:
  
|**Herramienta**|**Descripción**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Esta herramienta se usa para crear usuarios y contactos.  <br/> |
|UserProfileGenerator.exe  <br/> |Se usa para configurar las características de la carga de usuario que está simulando.  <br/> |
|LyncPerfTool.exe  <br/> |La herramienta que simula la carga del usuario.  <br/> |
|Default.tmx  <br/> |Necesario para usar la Skype Empresarial Server de registro de 2015.  <br/> |
|Ejemplos de script de aprovisionamiento  <br/> |Se usa para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos. Es probable que deba modificarlos para que sean relevantes para su entorno en particular.  <br/> |
   
## <a name="topics-in-this-section"></a>Temas de esta sección

Debe revisar los siguientes artículos si necesita saber más:
  
- [Requisitos previos y configuración de la Skype para la herramienta de rendimiento y esfuerzo de Busines](prerequisites-and-setup.md)
    
- [Escenarios de rendimiento para la Skype Empresarial Server de esfuerzo y rendimiento de 2015](scenarios.md)
    
  - [Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento](provisioning-the-topology-to-run-load.md)
    
  - [Configuración de directivas para la Skype Empresarial Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [Uso de la Skype Empresarial Server de esfuerzo y rendimiento de 2015](using-the-tool.md)
    
- [Faq for the Skype Empresarial Server 2015 Stress and Performance Tool](faq.md)
    

