---
title: Estacionamiento de llamadas
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Cuando una llamada está estacionada, se transfiere a un número temporal donde se mantiene la llamada hasta que alguien recupera o se agota el tiempo. Debe configurar una tabla con los rangos de números de extensión que desea reservar para las llamadas aparcadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación llamada Park puede tener uno o más rangos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: 710d923ae9c1e44320438334ad42a89d9d14062f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="call-park"></a>Estacionamiento de llamadas
 
Cuando una llamada está estacionada, se transfiere a un número temporal donde se mantiene la llamada hasta que alguien recupera o se agota el tiempo. Debe configurar una tabla con los rangos de números de extensión que desea reservar para las llamadas aparcadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación llamada Park puede tener uno o más rangos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.
  
El ** llamada Park ** página muestra una lista de todos los intervalos número parque de llamada que se definen para su organización.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Estacionamiento de llamadas** puede realizar las siguientes tareas:
  
- Crear un intervalo de números
    
- Cambiar un intervalo de números existente
    
- Eliminar un intervalo de números
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.
  
- **Nuevo** Inicia un nuevo intervalo de número de llamada Park.
    
- **Editar** Abre el intervalo seleccionado para su edición, selecciona todos los intervalos de números en la lista o elimina el intervalo seleccionado.
    
- **Actualizar** Actualiza la lista de intervalos numéricos.
    
En la siguiente lista se describen los campos de la página.
  
- **Nombre** El nombre único que identifica el intervalo de números.
    
- **Inicio de intervalo** El número inicial del rango.
    
- **Intervalo final** El número final del rango.
    
- **Destino** El nombre de dominio completo (FQDN) de nombre o identificador del servicio de aplicación que hospeda la aplicación llamada Park para el intervalo de números de servicio.
    
Para obtener detalles acerca de llamada Park características y capacidades, consulte [Plan para el parque de llamada en Skype para negocios 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener más información sobre cómo trabajar con intervalos numéricos llamada Park, vea [Configurar las extensiones de número de teléfono para llamadas de estacionamiento](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).
  

