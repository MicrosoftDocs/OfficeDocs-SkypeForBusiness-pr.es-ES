---
title: Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 se usa durante la planeación de capacidad y el ajuste del rendimiento en entornos de prueba o no producción.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814930"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
 
La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 se usa durante la planeación de capacidad y el ajuste del rendimiento en entornos de prueba o no producción.
  
La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 incluye herramientas que simplificarán la planeación de la capacidad para Skype Empresarial Server 2015. La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 le ayudará a:
  
- Simplificar la planeación del hardware para Skype Empresarial Server
    
- Proporcionar mayor conocimiento y procedimientos recomendados para el ajuste del rendimiento
    
- Medir el rendimiento de las implementaciones de Skype Empresarial Server
    
Normalmente, esta herramienta se usa después de usar la Herramienta de planeación de Skype Empresarial [Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y refinar la topología con la calculadora de planeación de capacidad de [Skype Empresarial Server 2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Esta herramienta no se actualizará para Skype Empresarial Server 2019.
  
## <a name="tests"></a>Pruebas

La herramienta Stress and Performance puede simular estos tipos de carga de usuario:
  
|||
|:-----|:-----|
|Mensajería instantánea (MI) y presencia  <br/> |Audioconferencia  <br/> |
|Uso compartido de aplicaciones  <br/> |Voz sobre IP (VoIP), incluida la simulación de red telefónica conmutada (PTSN)  <br/> |
|Conferencia de cliente de acceso web  <br/> |Operador automático de conferencia  <br/> |
|Grupos de respuesta  <br/> |Expansión de listas de distribución  <br/> |
|Descarga de libreta de direcciones y consulta de libreta de direcciones  <br/> |Perfil de ubicación y llamadas mejoradas al 911 (E911) (plan de marcado)  <br/> |
|MultiView  <br/> |Colaboración de datos  <br/> |
|Movilidad  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicaciones y archivos incluidos con la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015

Estas aplicaciones forman parte de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server:
  
|**Herramienta**|**Descripción**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Esta herramienta se usa para crear usuarios y contactos.  <br/> |
|UserProfileGenerator.exe  <br/> |Se usa para configurar las características de la carga de usuario que está simulando.  <br/> |
|LyncPerfTool.exe  <br/> |Herramienta que simula la carga de usuarios.  <br/> |
|Default.tmx  <br/> |Necesario para usar la herramienta de registro de Skype Empresarial Server 2015.  <br/> |
|Ejemplos de script de aprovisionamiento  <br/> |Se usa para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos. Es probable que deba modificarlos para que sean relevantes para su entorno en particular.  <br/> |
   
## <a name="topics-in-this-section"></a>Temas de esta sección

Debe revisar los siguientes artículos si necesita más información:
  
- [Requisitos previos y configuración de la Herramienta de esfuerzo y rendimiento de Skype Empresarial](prerequisites-and-setup.md)
    
- [Escenarios de rendimiento para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015](scenarios.md)
    
  - [Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento](provisioning-the-topology-to-run-load.md)
    
  - [Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015](configuring-policies.md)
    
- [Uso de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015](using-the-tool.md)
    
- [Preguntas más frecuentes sobre la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015](faq.md)
    

