---
title: Directiva de ubicación
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: fa1ca0907d3316066e2ca6e1fcf8a1d09a9c315a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy"></a>Directiva de ubicación
 
Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos. 
  
Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:
  
- **Directiva global:** De forma predeterminada, se crea la directiva global. Puede editar la directiva global, pero no puede eliminarlo. Si intenta quitar la directiva global, todos los valores se restablecen a los valores predeterminados.
    
- **Sitio de directivas (opcionales):** Puede crear uno o más sitios ubicación directivas, cada una de ellas se aplica a un sitio específico. Directivas de sitio anulan la directiva global.
    
- **Las directivas de usuario (opcionales):** Puede crear uno o varios ubicación directivas de usuario, cada uno de los cuales se aplica a un usuario o grupo específico de usuarios. Directivas de usuario anulan la directiva global y las políticas del sitio.
    
> [!NOTE]
> También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes. Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario. Para obtener más información acerca de cómo asignar directivas de ubicación a los sitios de la red mediante cmdlets, vea [Agregar una directiva de ubicación en un sitio de red en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Para obtener más información acerca de cómo utilizar Skype para Panel de Control de servidor empresarial para asignar una directiva de ubicación en un sitio de red, consulte [Configuración de sitios de red](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx). 
  
La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas en la organización.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Directiva de ubicación** puede realizar las siguientes tareas:
  
- Crear una directiva de ubicación de sitio o de ubicación de usuario
    
- Cambiar la directiva global o una directiva de sitio o de usuario existente
    
- Eliminar una directiva de sitio o de usuario
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.
  
- **Nuevo** Inicia una nueva política de ubicación de sitio o ubicación usuario.
    
- **Editar** Abre la directiva de la ubicación seleccionada para modificarlo, selecciona todas las políticas de ubicación de la lista o elimina la política de sitio seleccionado o usuario.
    
    > [!NOTE]
    > En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.
  
- **Actualizar** Actualiza la lista de las directivas de ubicación.
    
En la siguiente lista se describen los campos de la página.
  
- **Nombre** Identifica la ubicación de directiva.
    
- **Ámbito de aplicación** Identifica el ámbito de la política de ubicación: global, sitio o usuario.
    
- **E9-1-1** Comprueba si están habilitados los usuarios asignados a esta directiva de ubicación para E9-1-1.
    
- **Ubicación** Especifica si se pide a los usuarios para escribir información de ubicación cuando su cliente se registra con Skype para Business Server en una nueva ubicación, y si ven una renuncia si cerrar el símbolo del sistema sin introducir información de ubicación.
    
- **Uso PSTN** Especifica el uso de telefónica pública conmutada (RTC) de la red que se utiliza para determinar la ruta de voz utilizada para enrutar las llamadas de emergencia de los clientes con este perfil.
    
- **Número de E9-1-1** Especifica el número que se marca para llegar a los servicios de emergencia.
    
- **Máscara de E9-1-1** Especifica un número que llama a un usuario y, a continuación, se convierte en el número de acceso telefónico de emergencia.
    
Para obtener más información acerca de capacidades y características de Telefonía IP empresarial servicio de emergencia, vea [Resumen de E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planeamiento. Para obtener más información acerca de cómo trabajar con las políticas de ubicación, vea [Configurar la directiva de ubicación](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) en la documentación de las operaciones.
  

