---
title: Configurar las opciones de archivado para Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumen: Leer este tema para aprender a configurar las opciones de archivado iniciales de Skype para Business Server 2015. Configurar inicialmente archivado configuraciones al implementar archiving, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.'
ms.openlocfilehash: 38923d436f2fc5543158dfce6f8bebde27c7c911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-for-skype-for-business-server-2015"></a>Configurar las opciones de archivado para Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a configurar las opciones de archivado iniciales de Skype para Business Server 2015. Configurar inicialmente archivado configuraciones al implementar archiving, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.
  
Para configurar inicial de archiving configuraciones, es utilizar Skype para Business Server Control Panel para especificar lo siguiente:
  
- Configuración de nivel global por defecto se crea al implementar Skype para Business Server
    
- En la configuración de sitio opcional, que especifica cómo se implementa el archivado para un sitio específico
    
- Configuraciones de nivel de grupo opcionales que especifican cómo se implementa el archivado para un grupo específico
    
Necesitará configurar las opciones para determinar lo siguiente:
  
- Si desea habilitar o deshabilitar el archivado
    
- Si desea archivar las sesiones de mensajería instantánea (MI)
    
- Si desea archivar las sesiones de conferencias web
    
- Si desea bloquear la actividad cuando el archivado no está disponible
    
- Si desea utilizar la integración de Exchange
    
- Cómo configurar la purga y la exportación de datos
    
> [!NOTE]
> Es preciso que especifique todas las opciones adecuadas antes de habilitar el archivado. 
  
Para obtener más información acerca de cómo se implementan las configuraciones de archivado, incluyendo qué opciones se pueden especificar y la jerarquía del archiving de configuraciones, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md). Para obtener más información acerca de cómo administrar las configuraciones después de la implementación mediante el Panel de Control o mediante el uso de Windows PowerShell, consulte [Administrar opciones de archivado en Skype para Business Server 2015](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurar las opciones de archivado en el ámbito global

Al agregar archivado en su topología y publicar la topología, Skype para Business Server crea una configuración global para archivado. De forma predeterminada, no se habilita ninguna opción de archivado en la configuración global. La configuración global controla qué opciones se habilitan para toda la implementación, a menos que realice configuraciones de sitio o de grupo, que omiten la configuración global.
  
Para configurar las opciones de archivado en el ámbito global:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea (MI)**
    
   - **Archivar sesiones de mensajería instantánea y conferencias web**
    
6. También en la página **Editar archivado configuración - Global** , realice lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para utilizar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-site-level-archiving-options"></a>Configurar las opciones de archivado en el sitio

Puede especificar opciones de archivado para un sitio específico. Una configuración de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración del sitio. 
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, en **Configuración de sitio**.
    
5. En **Seleccionar un sitio**, seleccione el sitio que necesita configurar para el archivado.
    
6. En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
   - Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) y las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.
    
7. Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para utilizar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
8. Haga clic en **Confirmar**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurar las opciones de archivado en el grupo

Puede especificar las opciones de archivado para un grupo específico. Una configuración de grupo reemplaza la configuración global y de sitio, pero solo para el grupo especificado en la configuración de grupo.
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, haga clic en **Configuración de grupo**.
    
5. En **Seleccionar un servicio**, seleccione el grupo que desea configurar para el archivado.
    
6. En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea (MI)**
    
   - **Archivar sesiones de mensajería instantánea (MI) y conferencias web**
    
7. Además, en la página **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para utilizar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
8. Haga clic en **Confirmar**.
    

