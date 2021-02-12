---
title: Agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumen: lea este tema para obtener información sobre cómo agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015.'
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825110"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015.
  
Después de instalar el software necesario para requisitos previos en cada servidor en el que planea implementar el servidor de chat persistente, use topology Builder para: 
  
- Actualizar la topología para incluir el servidor de chat persistente
    
- Publicar la topología actualizada
    
> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Actualizar la topología para incluir el servidor de chat persistente

Realice los siguientes pasos para instalar un único grupo de servidores de chat persistente sin una configuración de recuperación ante desastres. For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Para implementar varios grupos de servidores de chat persistente, repita el mismo proceso para cada grupo.
  
1. En un equipo que ejecute Skype Empresarial Server o en el que estén instaladas las herramientas administrativas de Skype Empresarial Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, necesaria para instalar Skype  Empresarial Server, debe usar una cuenta que sea miembro del grupo Administradores de dominio y del grupo **RTCUniversalServerAdmins,** y que tenga permisos de control total (lectura, escritura y modificación) en el almacén de archivos que vaya a usar para el almacén de archivos del servidor de chat persistente (para que topology Builder pueda configurar las DACL necesarias) o una cuenta con derechos equivalentes.
  
2. Inicie el Generador de topologías.
    
3. En el árbol de consola, vaya al nodo Grupos de **chat** persistente y expándalo para seleccionar un grupo de Servidores de Skype Empresarial o haga clic con el botón secundario en el nodo y seleccione Nuevo grupo **de chat persistente.** Debe definir el nombre de dominio completo (FQDN) del grupo de servidores e indicar si el grupo será un grupo de un solo servidor o una implementación de grupo de varios servidores.
    
    Puede elegir un **Grupo de varios PC** o **Grupo de un PC**. Elija el primero si tiene previsto tener más de un servidor front-end en el grupo de servidores de chat persistente. Realice esta elección ahora, o luego, debido a que después de crear un solo grupo de PC no podrá agregar servidores adicionales más adelante. Si elige un grupo de varios equipos, escriba los nombres de los servidores front-end individuales que conforman el grupo.
    
    > [!IMPORTANT]
    > Si el rol de servidor de chat persistente se está instalando en un servidor Standard Edition, el FQDN debe coincidir con el FQDN del servidor Standard Edition. 
  
4. Defina un nombre para **mostrar simple para** el grupo de servidores de chat persistente. Los clientes personalizados pueden usar el nombre para mostrar, especialmente cuando hay varios grupos de servidores de chat persistente para diferenciar los salas.
    
5. Defina el puerto usado por el servidor de chat persistente para comunicarse con los servidores front-end de Skype Empresarial Server. El puerto predeterminado es 5041.
    
6. Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento**. Si se elige, el servicio de cumplimiento del servidor de chat persistente se instala en el mismo equipo que el servidor front-end del servidor de chat persistente. Más adelante, se le pedirá que seleccione SQL Server servidor back-end para el cumplimiento del servidor de chat persistente.
    
7. Asignar afinidad de sitio para el grupo de servidores de chat persistente. Active **la \<SiteName\>** casilla Usar este grupo  como predeterminado para el sitio o Use este grupo como predeterminado para que todos los sitios designe este grupo de servidores de chat persistente como el grupo predeterminado para el sitio actual o para todos los sitios. Cuando el cliente de Skype Empresarial se usa para crear y administrar salas, la experiencia de creación y administración de salas usa el grupo predeterminado asociado con el sitio del usuario para que pueda enrutar las operaciones de administración y creación de salas a ese grupo. Esto solo se aplica cuando tiene varios grupos de servidores de chat persistente implementados y desea usar las características de creación y administración de salas del servidor de chat persistente.
    
    > [!IMPORTANT]
    > Puede personalizar las características de creación y administración de salas mediante el Kit de desarrollo de software (SDK) del servidor de chat persistente. 
  
8. Defina el SQL para el back-end del servidor de chat persistente (donde se almacena el contenido del salón de **chat)** mediante una de las siguientes acciones:
    
   - Para usar un almacén de SQL Server existente, en la lista desplegable, haga clic en el nombre del almacén de SQL Server que desea usar.
    
   - Para especificar una nueva base SQL Server datos, haga clic en Nuevo y, en Definir nuevo **SQL almacén,** realice lo siguiente:
    
   - En **SQL Server FQDN,** especifique el FQDN de la SQL Server en la que desea crear la nueva base SQL Server datos.
    
   - Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, a continuación, especifique la instancia que desee utilizar.
    
     > [!NOTE]
     > Para obtener más información sobre cómo configurar bases de datos de copia de seguridad de SQL Server para la recuperación ante desastres, consulte Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en [Skype Empresarial Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
9. Defina el almacén SQL Server cumplimiento si habilitó El cumplimiento.
    
    > [!IMPORTANT]
    > Para obtener más información sobre cómo configurar reflejos de SQL Server para alta disponibilidad para la base de datos del servidor de chat persistente y la base de datos de cumplimiento del servidor de chat persistente, consulte Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en [Skype Empresarial Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
10. Defina el almacén de archivos. Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos, por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en una de chat. En el caso de una topología de servidor de chat persistente de varios servidores, debe ser una ruta de acceso UNC (Convención de nomenclatura universal); y para una topología de servidor de chat persistente de un solo servidor, puede ser una ruta de acceso de archivo local.
    
    Para utilizar un almacén de archivos existente, realice los siguientes pasos:
    
    - En **el FQDN del servidor de** archivos, especifique el FQDN del equipo en el que desea crear el nuevo almacén de archivos.
    
    - En **Recurso compartido de archivos**, especifique el almacén de archivos que desee utilizar.
    
      > [!IMPORTANT]
      > Puede definir el almacén de archivos en el Generador de topologías antes de crear el almacén de archivos, pero debe crear el almacén de archivos en la ubicación definida antes de publicar la topología. Si el almacén de archivos no existe, se producirá un error al intentar publicar la topología. 
  
11. Seleccione el grupo de servidores front-end que se usará como próximo salto para este grupo de servidores de chat persistente. Este es el grupo de servidores front-end que podrá enrutar las solicitudes del servidor de chat persistente a este grupo.
    
12. Para guardar la configuración, haga clic en **Finalizar**. El grupo de servidores de chat persistente aparece en el Generador de topologías acompañado de la configuración de grupo específica.
    
    Para publicar la topología actualizada a la que ha agregado el servidor de chat persistente, consulte Publicar la topología actualizada.
    
    > [!NOTE]
    > Con el Generador de topologías ya abierto, puede continuar con el paso 3 en Publicar la topología actualizada para empezar a publicar la topología actualizada. 
  
## <a name="publish-the-updated-topology"></a>Publicar la topología actualizada
<a name="BKMK_PublishTopology"> </a>

Después de actualizar la topología en el Generador de topologías, debe publicarla en el almacén de administración central para poder configurar y usar Skype Empresarial Server. Las copias de solo lectura de los datos se replican a todos los servidores de la topología para que todos los servidores permanezcan sincronizados con la topología y otros cambios de configuración.
  
Antes de publicar la topología, instale las bases de datos para el servidor de chat persistente. Use topology Builder para instalar bases de datos seleccionando **Acción** e **Instalar base de datos.**
  
1. En un equipo que ejecute Skype Empresarial Server o en el que estén instaladas las herramientas administrativas de  Skype Empresarial Server, inicie sesión con una cuenta que sea miembro del grupo Administradores de dominio y del grupo **RTCUniversalServerAdmins,** y que tenga permisos de control total (lectura, escritura y modificación) en el almacén de archivos que se usará para el almacén de archivos del servidor de chat persistente (para que el Generador de topologías pueda configurar las listas de control de acceso discrecional (DACL) necesarias o una cuenta con derechos de usuario equivalentes.
    
2. Inicie el Generador de topologías. Seleccione **Abrir topología en un archivo local** si lo guardó localmente.
    
3. En el árbol de la consola, haga clic con el botón secundario en **Skype Empresarial Server 2015** y, a continuación, haga clic **en Publicar topología.**
    
4. En la página **Publicar topología**, haga clic en **Siguiente**.
    
5. En la página **Asistente de publicación completado**, compruebe que la topología se haya publicado correctamente y, a continuación, haga clic en **Finalizar**.
    

