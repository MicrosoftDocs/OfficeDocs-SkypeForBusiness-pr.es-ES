---
title: Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumen: Leer este tema para aprender a agregar servidor de Chat persistentes a su Skype para Business Server 2015 topología.'
ms.openlocfilehash: 3d00e24dbe8f25b2a1887b8c1c79a63bda3471f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015
 
**Resumen:** Lea este tema para aprender a agregar servidor de Chat persistentes a su Skype para Business Server 2015 topología.
  
Después de instalar el software necesario en cada servidor en el que planea implementar servidor de Chat persistente, utilice el generador de topología para: 
  
- Actualizar la topología para incluir el servidor de chat persistente
    
- Publicar la topología actualizada
    
## <a name="update-your-topology-to-include-persistent-chat-server"></a>Actualizar la topología para incluir el servidor de chat persistente

Realice los pasos siguientes para instalar un único repositorio de servidor de charla persistente sin una configuración de recuperación ante desastres. Para configurar un grupo de servidor de charla persistente extendido para alta disponibilidad y recuperación ante desastres, consulte [configurar alta disponibilidad y recuperación ante desastres para el servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Para implementar varios grupos de servidor de charla persistente, repita el mismo proceso para cada grupo.
  
1. En un equipo que está ejecutando Skype para Business Server o en el que el Skype para herramientas administrativas Business Server están instaladas, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios local, pero para publicar una topología, que es necesario para instalar Skype para Business Server, debe utilizar una cuenta que sea miembro del grupo **Administradores** del dominio y la ** RTCUniversalServerAdmins** group y que tenga permisos de control total (leer, escribir y modificar) en el almacén de archivos que se van a utilizar para el almacén de archivos de servidor de charla persistente (por lo que el generador de topología puede configurar las DACL necesarias), o una cuenta con derechos equivalentes.
  
2. Iniciar el generador de topología.
    
3. En el árbol de consola, desplácese hasta el nodo **Grupos de Chat persistentes** y expándalo para seleccionar un Skype para el grupo de servidores empresariales, o haga clic en el nodo y seleccione **Nuevo grupo de Chat persistentes**. Debe definir el nombre del grupo de dominio completo (FQDN) e indicar si el grupo estará formado un grupo de servidor único o una implementación de grupo de varios servidores.
    
    Puede elegir un **Grupo de varios equipos** o **Grupo de un solo equipo**. Elija la primera si piensa tener más de un servidor de Front-End en la agrupación de servidor de charla persistente. Realice esta elección ahora, porque después de crear un grupo de un solo equipo no le podrá agregar servidores adicionales más adelante. Si elige un grupo de equipo múltiple, escriba los nombres de los servidores de extremo frontal individuales que componen el grupo.
    
    > [!IMPORTANT]
    > Si la función de servidor de charla persistente se está instalando en un servidor Standard Edition, el FQDN debe coincidir con el FQDN del servidor Standard Edition. 
  
4. Defina un **Nombre para mostrar** sencillo para el grupo de servidor de charla persistente. El nombre para mostrar puede utilizarse por los clientes personalizados, especialmente cuando hay varios grupos de servidor de charla persistente para diferenciar las habitaciones.
    
5. Definir el puerto utilizado por el servidor de charla persistente para comunicarse con Skype para Business Server servidores frontales. El puerto predeterminado es 5041.
    
6. Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento**. Si elige esta opción, el servicio de cumplimiento de servidor de charla persistente está instalado en el mismo equipo que el persistente Chat Server servidor Front-End. Le pedirá que seleccione un servidor de SQL Server nuevo fondo para el cumplimiento de servidor de Chat persistentes más adelante.
    
7. Asignar afinidad de sitios para el grupo de servidor de charla persistente. Seleccione el **utilizar este grupo como predeterminado para el sitio \<SiteName\> ** casilla de verificación o **utilizar este grupo como predeterminada para todos los sitios** para designar este grupo de servidores de charla persistentes como el grupo predeterminado para el sitio actual o todos los sitios. Cuando se utiliza el Skype para cliente de negocio para crear y administrar las salas, el grupo predeterminado asociado con el sitio del usuario se utiliza por la experiencia de creación y administración de la sala para que pueden enrutar las operaciones de creación y administración de sala a ese grupo. Esto sólo se aplica cuando se ha implementado varios grupos de servidor de charla persistente y desea utilizar las características de creación y administración de sala de servidor de charla persistente.
    
    > [!IMPORTANT]
    > Puede personalizar las características de creación y administración de sala utilizando el persistente Chat Server Software Development Kit (SDK). 
  
8. Defina el **almacén de SQL para la persistente Chat Server Back End (donde se almacena el contenido del salón de chat)** siguiendo uno de estos procedimientos:
    
   - Para utilizar un almacén de SQL Server existente, en la lista desplegable, haga clic en el nombre del almacén de SQL Server que desea utilizar.
    
   - Para especificar una base de datos de SQL Server, haga clic en **nuevo**y en **Definir nuevo almacén de SQL**, haga lo siguiente:
    
   - En el **FQDN de SQL Server**, especifique el FQDN de la de SQL Server en el que desea crear la nueva base de datos de SQL Server.
    
   - Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, luego, especifique la instancia que desee utilizar.
    
    > [!NOTE]
    > Para obtener más información acerca de cómo configurar las bases de datos de copia de seguridad de SQL Server para recuperación ante desastres, consulte [configurar alta disponibilidad y recuperación ante desastres para el servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Definir el almacén de cumplimiento de SQL Server si se ha habilitado el cumplimiento de normas.
    
    > [!IMPORTANT]
    > Para obtener más información acerca de cómo configurar los reflejos de SQL Server para alta disponibilidad de la base de datos del servidor de charla persistente y la base de datos de servidor de charla persistente cumplimiento, consulte [configurar alta disponibilidad y recuperación ante desastres para servidor persistente Chat de Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Defina el almacén de archivos. Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos (por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en un salón de chat). En el caso de una topología de servidor de Chat persistente de varios servidores, esto debe ser una ruta de convención de nomenclatura Universal (UNC, Universal Naming Convention); y para una topología de servidor único persistente Chat Server, puede ser una ruta de acceso local.
    
    Para utilizar un almacén de archivos existente, haga lo siguiente:
    
    - En **FQDN del servidor de archivos**, especifique el FQDN del equipo en el que desee crear el almacén de archivos.
    
    - En **Recurso compartido de archivos**, especifique el almacén de archivos que desee utilizar.
    
     > [!IMPORTANT]
     > Puede definir el almacén de archivos en el generador de topología antes de crear el almacén de archivos, pero debe crear el almacén de archivos en la ubicación definida que definir antes de publicar la topología. Si el almacén de archivos aún no existe, no se podrá publicar la topología. 
  
11. Seleccione el grupo de servidor Front-End que se utilizará como próximo salto para este grupo de servidores de charla persistente. Se trata del grupo de servidor Front-End que será capaz de enrutar las solicitudes de servidor de charla persistente a este grupo.
    
12. Para guardar la configuración, haga clic en **Finalizar**. El grupo del servidor de Chat persistentes aparece generador de topología acompañado por la configuración de grupo específico.
    
    Para publicar su topología actualizados a que ha agregado el servidor de charla persistente, consulte publicar la topología actualizados.
    
    > [!NOTE]
    > Con el generador de topología ya está abierto, puede continuar con el paso 3 en publicar la topología actualizados para empezar a publicar su topología actualizados. 
  
## <a name="publish-the-updated-topology"></a>Publicar la topología actualizada
<a name="BKMK_PublishTopology"> </a>

Después de actualizar la topología de generador de topología, debe publicar la topología en el almacén de Administración Central para poder configurar y utilizar Skype para Business Server. Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios en la topología y en otras opciones de configuración.
  
Antes de publicar la topología, instalar las bases de datos para el servidor de charla persistente. Utilice el generador de topología para instalar las bases de datos seleccionando la **acción** e **Instalar la base de datos**.
  
1. En un equipo que está ejecutando Skype para Business Server o en el que el Skype para herramientas administrativas Business Server están instaladas, inicie sesión con una cuenta que sea miembro del grupo **Administradores** del dominio y del grupo **RTCUniversalServerAdmins** , y que tiene permisos de control total (leer, escribir y modificar) en el almacén de archivos que se utilizará para el almacén de archivos de servidor de charla persistente (por lo que el generador de topología puede configurar las listas de control de acceso discrecional (DACL)), o una cuenta de usuario equivalente derechos.
    
2. Iniciar el generador de topología. Seleccione **Abrir la topología desde un archivo local**, si la ha guardado de forma local.
    
3. En el árbol de consola, haga clic derecho en **Skype para Business Server 2015**y, a continuación, haga clic en **Publicar la topología**.
    
4. En la página **Publicar la topología**, haga clic en **Siguiente**.
    
5. En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    

