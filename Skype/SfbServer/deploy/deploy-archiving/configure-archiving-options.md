---
title: Configurar las opciones de archivado para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar las opciones de archivado iniciales de Skype para Business Server. Se configura inicialmente las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar las configuraciones de después de la implementación.'
ms.openlocfilehash: 58dd94cb5d42e3d0dabb845acbb5b72e7e90d8bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895928"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurar las opciones de archivado para Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar las opciones de archivado iniciales de Skype para Business Server. Se configura inicialmente las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar las configuraciones de después de la implementación.
  
Para configurar inicial de archivado de las configuraciones, se usa Skype para el Panel de Control de servidor empresarial para especificar lo siguiente:
  
- Configuración de nivel global que se crea de forma predeterminada al implementar Skype para Business Server
    
- En la configuración de sitio opcional, que especifica cómo se implementa el archivado para un sitio específico
    
- Configuraciones opcionales de nivel de grupo de servidores que especifican cómo se implementa el archivado para un grupo de servidores específico
    
Necesitará configurar las opciones para determinar lo siguiente:
  
- Si desea habilitar o deshabilitar el archivado
    
- Si desea archivar las sesiones de mensajería instantánea (MI)
    
- Si desea archivar las sesiones de conferencias web
    
- Si desea bloquear la actividad cuando el archivado no está disponible
    
- Si desea utilizar la integración de Exchange
    
- Cómo configurar la purga y la exportación de datos
    
> [!NOTE]
> Es preciso que especifique todas las opciones adecuadas antes de habilitar el archivado. 
  
Para obtener información detallada acerca de cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de archivado de las configuraciones, vea [Plan for archiving en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md). Para obtener información detallada sobre cómo administrar las configuraciones de después de la implementación mediante el Panel de Control o mediante el uso de Windows PowerShell, vea [administrar las opciones de archivado en Skype para Business Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurar las opciones de archivado en el ámbito global

Al agregar el archivado a la topología y publique la topología, Skype para Business Server crea una configuración global para el archivado. De forma predeterminada, no se habilita ninguna opción de archivado en la configuración global. La configuración global controla qué opciones se habilitan para toda la implementación, a menos que realice configuraciones de sitio o de grupo, que omiten la configuración global.
  
Para configurar las opciones de archivado en el ámbito global:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea (MI)**
    
   - **Archivar sesiones de mensajería instantánea (MI) y conferencias web**
    
6. También en la página **Editar configuración de archivado - Global** , haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-site-level-archiving-options"></a>Configurar las opciones de archivado en el sitio

Puede especificar opciones de archivado para un sitio específico. Una configuración de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración del sitio. 
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, en **Configuración de sitio**.
    
5. En **Seleccionar un sitio**, seleccione el sitio que necesita configurar para el archivado.
    
6. En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
   - Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) y las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.
    
7. Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
8. Haga clic en **Confirmar**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurar las opciones de archivado en el grupo

Puede especificar las opciones de archivado para un grupo específico. Una configuración de grupo reemplaza la configuración global y de sitio, pero solo para el grupo especificado en la configuración de grupo.
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, haga clic en **Configuración de grupo**.
    
5. En **Seleccionar un servicio**, seleccione el grupo que desea configurar para el archivado.
    
6. En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea (MI)**
    
   - **Archivar sesiones de mensajería instantánea (MI) y conferencias web**
    
7. Además, en la página **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
8. Haga clic en **Confirmar**.
    

