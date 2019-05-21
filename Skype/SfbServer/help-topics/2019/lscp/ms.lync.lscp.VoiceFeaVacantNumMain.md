---
title: Número de teléfono sin asignar
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 684519d29177b9daf4be57c650e811f00945adfb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290034"
---
# <a name="unassigned-phone-number"></a>Número de teléfono sin asignar

> [!NOTE]
> La mensajería unificada de Exchange sigue disponible en Skype empresarial Server 2019 al integrar la 2019 de Skype empresarial con Exchange 2013 o Exchange 2016. Debido a cambios en el soporte técnico de Exchange 2019, la integración de mensajería unificada de Exchange se subraya en favor del buzón de voz de nube y las características del operador automático de la nube.

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

- **Nuevo** Inicia un nuevo intervalo de números sin asignar.

- **Editar** Abre el intervalo de números seleccionado sin asignar para editar, selecciona todos los intervalos de números sin asignar de la lista o elimina el intervalo de números sin asignar seleccionado.

- **Subir** Mueve el intervalo de número no asignado seleccionado hacia arriba en la lista para que Skype empresarial Server lo encuentre antes de aplicar las acciones especificadas para otros rangos de la lista.

    > [!NOTE]
    > Skype empresarial Server busca la tabla de números sin asignar de arriba a abajo y usa el primer rango que coincida con el número sin asignar. Por ejemplo, si tiene un intervalo que especifique una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.

- **Bajar** Mueve el intervalo de número no asignado seleccionado hacia abajo en la lista.

- **Confirmar todo** Guarda todos los cambios realizados en intervalos de números sin asignar.

    > [!IMPORTANT]
    > Este comando guarda todos los cambios realizados en las páginas **Nuevo número sin asignar** y **Editar número sin asignar**.

- **Actualizar** Actualiza la lista de intervalos de números no asignados.

En la siguiente lista se describen los campos de la página.

- **Nombre** Nombre único que identifica el intervalo de números sin asignar.

- **Estado** Muestra los intervalos de números que se han guardado en la base de datos y cuáles no.

- **Intervalo de inicio** El número inicial del intervalo de números sin asignar.

- **Finalizar rango** El número final del intervalo de números sin asignar.

- **Destino** El identificador de servicio del servicio de aplicación que hospeda la aplicación de anuncio que controlará las llamadas entrantes a este intervalo de números no asignados.

- **Anuncio** El anuncio que se reproducirá para este rango de números no asignados.

Para obtener más información sobre las características y capacidades del anuncio, consulte [planear la aplicación de anuncios en Skype empresarial](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación. Para más detalles sobre cómo trabajar con intervalos de números sin asignar, mire [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.


