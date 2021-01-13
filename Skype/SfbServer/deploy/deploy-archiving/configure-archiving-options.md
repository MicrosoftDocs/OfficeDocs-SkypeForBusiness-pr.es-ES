---
title: Configurar las opciones de archivado para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumen: lea este tema para obtener información sobre cómo configurar las opciones de archivado iniciales para Skype Empresarial Server. Las configuraciones de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.'
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815540"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurar las opciones de archivado para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar las opciones de archivado iniciales para Skype Empresarial Server. Las configuraciones de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.
  
Para configurar las configuraciones de archivado iniciales, use el Panel de control de Skype Empresarial Server para especificar lo siguiente:
  
- Configuración de nivel global que se crea de forma predeterminada al implementar Skype Empresarial Server
    
- Configuraciones de nivel de sitio opcionales que especifican cómo se implementa el archivado para un sitio específico
    
- Configuraciones opcionales de nivel de grupo que especifican cómo se implementa el archivado para un grupo específico
    
Tendrá que configurar las opciones para lo siguiente:
  
- Si se habilita o deshabilita el archivado
    
- Si se archivarán las sesiones de mensajería instantánea
    
- Si se archivarán las sesiones de conferencia web
    
- Si se va a bloquear la actividad cuando el archivado no está disponible
    
- Si se va a usar la integración de Exchange
    
- Cómo configurar la purga y exportación de datos
    
> [!NOTE]
> Debe especificar todas las opciones adecuadas antes de habilitar el archivado. 
  
Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Para obtener más información sobre cómo administrar las configuraciones después de la implementación mediante el Panel de control o mediante Windows PowerShell, consulte Administrar las opciones de archivado [en Skype Empresarial Server.](../../manage/archiving/options.md)
  
## <a name="configure-global-level-archiving-options"></a>Configurar las opciones de archivado de nivel global

Cuando agrega archivado a la topología y publica la topología, Skype Empresarial Server crea una configuración global para el archivado. De forma predeterminada, no hay opciones de archivado habilitadas en la configuración global. La configuración global controla qué opciones se habilitan para su completa implementación, a menos que realice configuraciones de sitio o grupo de servidores, que omiten la configuración global.
  
Para configurar las opciones de archivado en el nivel global:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Global**, **Editar** y **Mostrar detalles**.
    
5. En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea**
    
   - **Archivar mensajería instantánea y sesiones de conferencias web**
    
6. También en la **página Editar configuración de archivado - Global,** haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
   - Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de **integración de Microsoft Exchange.**
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
    
   - Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-site-level-archiving-options"></a>Configurar las opciones de archivado de nivel de sitio

Puede especificar opciones de archivado para un sitio específico. Una configuración de sitio invalida la configuración global, pero solo para el sitio especificado en la configuración del sitio. 
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. En la página **Configuración de** archivado, haga clic **en Nuevo** y, a continuación, en Configuración **del sitio.**
    
5. En **Seleccionar un sitio**, seleccione el sitio que debe configurarse para el archivado.
    
6. En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea**.
    
   - Para habilitar el archivado para sesiones de mensajería instantánea y conferencias, haga clic en Archivar sesiones de mensajería instantánea **y conferencia web.**
    
   - Para deshabilitar el archivado para la directiva, haga clic en **Deshabilitar archivado**.
    
7. Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
   - Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de **integración de Microsoft Exchange.**
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
    
   - Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.
    
8. Haga clic en **Confirmar**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurar las opciones de archivado de nivel de grupo

Puede especificar las opciones de archivado para un grupo específico. La configuración de un grupo de servidores anula la configuración global y de sitio, pero únicamente para el grupo de servidores especificad en la configuración del grupo de servidores.
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y en **Directiva de grupo**.
    
5. En **Seleccione un servicio**, seleccione el grupo de servidores que desea configurar para el archivado.
    
6. En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea**
    
   - **Archivar sesiones de MI y conferencias**
    
7. Además, en la página **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla  **Bloquear las sesiones de mensajería instantánea (MI) o conferencias si se produce algún error en el archivado**.
    
   - Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de **integración de Microsoft Exchange.**
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
    
   - Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.
    
8. Haga clic en **Confirmar**.
    

