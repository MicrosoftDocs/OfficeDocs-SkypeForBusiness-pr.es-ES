---
title: Directiva de ubicación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: 133fd96bbceab7971196147d604ed582d5584f1a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891134"
---
# <a name="location-policy"></a>Directiva de ubicación

Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.

Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:

- **Directiva global:** De forma predeterminada, se crea la directiva global. Puede editar la directiva global, pero no puede eliminar. Si se intenta quitar la directiva global, se restablecen todas las opciones a los valores predeterminados.

- **(Opcionales) de directivas de sitio:** Puede crear uno o varios sitios directivas de ubicación, cada uno de los cuales se aplica a un sitio específico. Las directivas de sitio invalidar la directiva global.

- **Las directivas de usuario (opcionales):** Puede crear uno o varios usuarios directivas de ubicación, cada uno de los cuales se aplica a un usuario específico o grupo de usuarios. Las directivas de usuario reemplazan las directivas globales y las directivas de sitio.

> [!NOTE]
> También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes. Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario. Para obtener información detallada acerca de cómo asignar directivas de ubicación a sitios de red mediante el uso de cmdlets, consulte [Agregar una directiva de ubicación en un sitio de red de Skype para Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Para obtener información detallada acerca del uso de Skype para el Panel de Control de servidor empresarial para asignar una directiva de ubicación a un sitio de red, consulte [Configuración de sitios de red](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas en la organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Directiva de ubicación** puede realizar las siguientes tareas:

- Crear una directiva de ubicación de sitio o de ubicación de usuario

- Cambiar la directiva global o una directiva de sitio o de usuario existente

- Eliminar una directiva de sitio o de usuario

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva directiva de ubicación de sitio o directiva de ubicación del usuario.

- **Editar** Se abre la directiva de ubicación seleccionada para editarla, selecciona todas las directivas de ubicación en la lista o elimina la directiva de sitio seleccionado o la directiva de usuario.

    > [!NOTE]
    > En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de directivas de ubicación.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la directiva de ubicación.

- **Ámbito** Identifica el ámbito de la directiva de ubicación: global, sitio o usuario.

- **E9-1-1** Comprueba si los usuarios asignados a esta directiva de ubicación están habilitados para E9-1-1.

- **Ubicación** Especifica si los usuarios se le pide que escriba información de ubicación cuando su cliente registra con Skype para Business Server en una ubicación nueva, y si puede ver una renuncia de responsabilidad si cierre el símbolo del sistema sin tener que especificar información de ubicación.

- **Uso de RTC** Especifica el uso de telefónica conmutada (RTC) que se utiliza para determinar la ruta de voz que se usa para enrutar las llamadas de emergencia desde clientes que usen este perfil.

- **Número E9-1-1** Especifica el número que se marca para llegar a los servicios de emergencia.

- **Máscara E9-1-1** Especifica un número que llama a un usuario y, a continuación, se convierte en el número de marcado de emergencia.

Para obtener información detallada sobre las características de servicios de emergencia de Enterprise Voice y funciones, vea [información general de E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planeación. For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.


