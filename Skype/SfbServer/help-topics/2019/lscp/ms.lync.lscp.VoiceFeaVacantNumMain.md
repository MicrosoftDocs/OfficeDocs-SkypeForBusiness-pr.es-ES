---
title: Número de teléfono sin asignar
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 71b6fa44d088bb73a1253555d1e5c9601d889767
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005171"
---
# <a name="unassigned-phone-number"></a>Número de teléfono sin asignar
 
Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
  
La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar, o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en ese momento. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.
  
> [!IMPORTANT]
> Antes de configurar la tabla de números sin asignar, tiene que haber definido uno o más anuncios o haber establecido un operador automático de mensajería unificada de Exchange. 
  
La página **Número no asignado** muestra una lista de todos los intervalos de números sin asignar definidos en la organización.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Número no asignado** puede realizar las siguientes tareas:
  
- Crear un intervalo de números sin asignar
    
- Cambiar un intervalo de números sin asignar existente
    
- Eliminar un intervalo de números sin asignar
    
- Cambiar el orden de los intervalos de números sin asignar para determinar qué acción necesita aplicarse primero a una llamada entrante que coincida con un número sin asignar. 
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.
  
- **Nuevo** Inicia un nuevo intervalo numérico sin asignar.
    
- **Editar** Se abre el intervalo numérico sin asignar seleccionado para su edición, selecciona todos los intervalos numéricos sin asignar de la lista o elimina el intervalo numérico sin asignar seleccionado.
    
- **Mover hacia arriba** Mueve el intervalo numérico sin asignar seleccionado copia de seguridad en la lista de modo que Skype para Business Server encuentra antes y aplica la acción especificada antes de aplicar las acciones especificadas para otros rangos de la lista.
    
    > [!NOTE]
    > Skype para Business Server busca en la tabla de números sin asignar de arriba a abajo y usa el primer rango que coincida con el número sin asignar. Por ejemplo, si tiene un intervalo que especifique una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista. 
  
- **Mover hacia abajo** Mueve el intervalo numérico sin asignar seleccionado hacia abajo en la lista.
    
- **Confirmar todos** Guarda todos los cambios realizados a intervalos numéricos sin asignar.
    
    > [!IMPORTANT]
    > Este comando guarda todos los cambios realizados en las páginas **Nuevo número sin asignar** y **Editar número sin asignar**.
  
- **Actualizar** Actualiza la lista de intervalos numéricos sin asignar.
    
En la siguiente lista se describen los campos de la página.
  
- **Nombre** El nombre único que identifica el intervalo de números sin asignar.
    
- **Estado** Muestra qué intervalos numéricos se han guardado en la base de datos y cuáles no.
    
- **Intervalo de inicio** El número inicial del intervalo numérico sin asignar.
    
- **Intervalo de finalización** El número final del intervalo numérico sin asignar.
    
- **Destino** El identificador de servicio de la aplicación que hospeda la aplicación de anuncio que controlará las llamadas entrantes a este intervalo de números sin asignar.
    
- **Anuncio** El anuncio que se reproducirá para este intervalo de números sin asignar.
    
Para obtener información detallada sobre las capacidades y características de anuncio, consulte [Plan para la aplicación de anuncio en Skype para la empresa](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación. Para obtener información detallada sobre cómo trabajar con intervalos numéricos sin asignar, vea [Configurar el enrutamiento de sin asignar números de teléfono](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación sobre operaciones.
  

