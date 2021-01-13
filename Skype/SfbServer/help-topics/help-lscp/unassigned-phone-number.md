---
title: Número de teléfono sin asignar
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826890"
---
# <a name="unassigned-phone-number"></a>Número de teléfono sin asignar

Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien, con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.

> [!IMPORTANT]
> Antes de configurar la tabla de números sin asignar, debe haber definido uno o más anuncios o haber establecido un operador automático de mensajería unificada de Exchange.

La página **Número no asignado** muestra una lista de todos los intervalos de números sin asignar definidos para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas desde la página **Número no asignado**:

- Crear un intervalo numérico sin asignar nuevo

- Cambiar un intervalo numérico sin asignar existente

- Eliminar un intervalo numérico sin asignar

- Cambiar el orden de intervalos numéricos sin asignar para determinar qué acción debe aplicarse primero a una llamada entrante que coincida con un número sin asignar.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia un nuevo intervalo de números sin signo.

- **Editar** Abre el intervalo de números sin signo seleccionado para su edición, selecciona todos los intervalos de números sin signo de la lista o elimina el intervalo de números sin signo seleccionado.

- **Subir** Mueve el intervalo de números sin signo seleccionado hacia arriba en la lista para que Skype Empresarial Server lo encuentre antes y aplique la acción especificada antes de aplicar las acciones especificadas para otros intervalos de la lista.

    > [!NOTE]
    > Skype Empresarial Server busca en la tabla de números sin signo de arriba abajo y usa el primer intervalo que coincide con el número sin signo. Por ejemplo, si tiene un intervalo que especifique una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.

- **Bajar** Mueve el intervalo de números sin signo seleccionado hacia abajo en la lista.

- **Confirmar todo** Guarda todos los cambios realizados en intervalos de números sin signo.

    > [!IMPORTANT]
    > Este comando guarda todos los cambios realizados en la página **Nuevo número sin asignar** y en la página **Editar número sin asignar**.

- **Actualizar** Actualiza la lista de intervalos de números sin signo.

En la siguiente lista se describen los campos de la página.

- **Nombre** Nombre único que identifica el intervalo de números sin signo.

- **Estado** Muestra qué intervalos de números se han guardado en la base de datos y cuáles no.

- **Intervalo de inicio** Número inicial del intervalo de números sin signo.

- **Intervalo de finalización** Número final del intervalo de números sin signo.

- **Destino** El identificador de servicio del servicio de aplicación que hospeda la aplicación anuncio que controlará las llamadas entrantes a este intervalo de números sin signo.

- **Anuncio** Anuncio que se reproducirá para este intervalo de números sin signo.

Para obtener más información sobre las características y capacidades de anuncio, consulte [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación sobre planeación. Para obtener más detalles sobre cómo trabajar con rangos de números sin asignar, vea [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.


