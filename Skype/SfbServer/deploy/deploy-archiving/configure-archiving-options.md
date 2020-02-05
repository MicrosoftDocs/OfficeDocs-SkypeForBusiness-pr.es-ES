---
title: Configurar opciones de archivado para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar las opciones iniciales de archivado de Skype empresarial Server. Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.'
ms.openlocfilehash: f663b310d4c82594976f2f0fc99b8ddd9baf035f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769203"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurar opciones de archivado para Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar las opciones iniciales de archivado para Skype empresarial Server. Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.
  
Para configurar las configuraciones iniciales de archivado, use el panel de control de Skype empresarial Server para especificar lo siguiente:
  
- Configuración de nivel global que se crea de forma predeterminada al implementar Skype empresarial Server
    
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
  
Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md). Para obtener detalles sobre cómo administrar las configuraciones después de la implementación mediante el panel de control o mediante Windows PowerShell, consulte [administrar las opciones de archivado en Skype empresarial Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurar las opciones de archivado en el ámbito global

Cuando agrega un archivo a su topología y publica la topología, Skype empresarial Server crea una configuración global para el archivado. De forma predeterminada, no se habilita ninguna opción de archivado en la configuración global. La configuración global controla qué opciones se habilitan para toda la implementación, a menos que realice configuraciones de sitio o de grupo, que omiten la configuración global.
  
Para configurar las opciones de archivado en el ámbito global:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea (MI)**
    
   - **Archivar sesiones de mensajería instantánea (MI) y conferencias web**
    
6. Además, en la página **Editar configuración de archivado global** , haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
7. Haga clic en **Confirmar**.
    
## <a name="configure-site-level-archiving-options"></a>Configurar las opciones de archivado en el sitio

Puede especificar opciones de archivado para un sitio específico. Una configuración de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración del sitio. 
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, en **Configuración de sitio**.
    
5. En **Seleccionar un sitio**, seleccione el sitio que necesita configurar para el archivado.
    
6. En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
   - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
   - Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) y las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
   - A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.
    
7. Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
8. Haga clic en **Confirmar**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurar las opciones de archivado en el grupo

Puede especificar las opciones de archivado para un grupo específico. Una configuración de grupo reemplaza la configuración global y de sitio, pero solo para el grupo especificado en la configuración de grupo.
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, haga clic en **Configuración de grupo**.
    
5. En **Seleccionar un servicio**, seleccione el grupo que desea configurar para el archivado.
    
6. En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:
    
   - **Deshabilitar archivado**
    
   - **Archivar sesiones de mensajería instantánea (MI)**
    
   - **Archivar sesiones de mensajería instantánea (MI) y conferencias web**
    
7. Además, en la página **Nueva configuración de archivado**, haga lo siguiente:
    
   - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
   - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .
    
   - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
    
   - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
    
   - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
8. Haga clic en **Confirmar**.
    

