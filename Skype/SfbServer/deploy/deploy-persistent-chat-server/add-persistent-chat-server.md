---
title: Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumen: Lea este tema para obtener información sobre cómo agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server.'
ms.openlocfilehash: 733d75e954c75cecfab38e0a2f1294c6e20984c1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794118"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server.
  
Después de instalar el software necesario en cada servidor en el que tiene previsto implementar un servidor de chat persistente, use el generador de topología para: 
  
- Actualizar la topología para incluir el servidor de chat persistente
    
- Publicar la topología actualizada
    
> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Actualizar la topología para incluir el servidor de chat persistente

Siga estos pasos para instalar un único grupo de servidores de chat persistente sin una configuración de recuperación ante desastres. Para configurar un grupo de servidores de chat persistente ampliado para una alta disponibilidad y recuperación ante desastres, consulte [configurar la alta disponibilidad y la recuperación ante desastres para un servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Para implementar varios grupos de servidores de chat persistentes, repita el mismo proceso para cada grupo.
  
1. En un equipo que ejecuta Skype empresarial Server o en el que están instaladas las herramientas administrativas de Skype empresarial Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para instalar Skype empresarial Server,, debe usar una cuenta que sea miembro del grupo de **administradores de dominio** y el grupo **RTCUniversalServerAdmins** , y que tenga permisos de control total (lectura, escritura y modificación) en el almacén de archivos que va a usar para el almacén de archivos del servidor de chat persistente (de modo que topología pueda configurar las DACL requeridas) o una cuenta con un equivalente Rights.
  
2. Iniciar el generador de topología.
    
3. En el árbol de consola, vaya al nodo **grupos de chats persistentes** y expándalo para seleccionar un grupo de servidores de Skype empresarial, o haga clic con el botón derecho en el nodo y seleccione **nuevo grupo de chats persistentes**. Debe definir el nombre de dominio completo (FQDN) de la agrupación e indicar si el grupo será un grupo de un solo servidor o una implementación de grupo de varios servidores.
    
    Puede elegir un **Grupo de varios equipos** o **Grupo de un solo equipo**. Elija el primero si planea tener más de un servidor front-end en el grupo de servidores de chat persistente. Realice esta elección ahora, porque después de crear un grupo de un solo equipo no le podrá agregar servidores adicionales más adelante. Si elige un grupo de varios equipos, escriba los nombres de los servidores front-end individuales que componen el grupo.
    
    > [!IMPORTANT]
    > Si el rol de servidor de chat persistente se instala en un servidor Standard Edition, el FQDN debe coincidir con el FQDN del servidor Standard Edition. 
  
4. Defina un **nombre para mostrar** simple para el grupo de servidores de chat persistente. El nombre para mostrar puede ser usado por clientes personalizados, especialmente cuando hay varios grupos de servidores de chat persistentes para diferenciar las habitaciones.
    
5. Defina el puerto que usa el servidor de chat persistente para comunicarse con los servidores front-end de Skype empresarial Server. El puerto predeterminado es 5041.
    
6. Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento**. Si se elige, el servicio de cumplimiento de servidor de chat persistente se instala en el mismo equipo que el servidor de front-end del servidor de chat persistente. Se le pedirá que seleccione un servidor Back End SQL Server para el cumplimiento del servidor de chat persistente más adelante.
    
7. Asigne afinidad de sitio para el grupo de servidores de chat persistente. Active la casilla de verificación **usar este grupo como \<predeterminado\> para el sitio siteName** o **use este grupo como predeterminado para que todos los sitios** designen este grupo de servidores de chat persistente como el grupo predeterminado para el sitio actual o todos los sitios. Cuando se usa el cliente de Skype empresarial para crear y administrar salas, la experiencia de creación y administración de la sala usa el grupo predeterminado asociado al sitio del usuario para que pueda dirigir las operaciones de administración y creación de salas a ese grupo. Esto solo se aplica cuando se han implementado varios grupos de servidores de chat persistentes y desea usar las características de creación y administración de la sala de un servidor de chat persistente.
    
    > [!IMPORTANT]
    > Puede personalizar las características de creación y administración de la sala con el kit de desarrollo de software (SDK) del servidor de chat persistente. 
  
8. Defina el **almacén SQL para el back-end del servidor de chat persistente (donde se almacena el contenido del salón de chat)** mediante uno de los siguientes procedimientos:
    
   - Para usar un almacén de SQL Server existente, en la lista desplegable, haga clic en el nombre del almacén de SQL Server que desea usar.
    
   - Para especificar una nueva base de datos de SQL Server, haga clic en **nuevo**y, en **definir nueva tienda SQL**, realice lo siguiente:
    
   - En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear la nueva base de datos de SQL Server.
    
   - Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, luego, especifique la instancia que desee utilizar.
    
     > [!NOTE]
     > Para obtener más información sobre cómo configurar las bases de datos de copia de seguridad de SQL Server para recuperación ante desastres, consulte [configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Defina el almacén de cumplimiento de SQL Server si ha habilitado la compatibilidad.
    
    > [!IMPORTANT]
    > Para obtener más información sobre cómo configurar las duplicaciones de SQL Server para una alta disponibilidad de la base de datos del servidor de chat persistente y la base de datos de cumplimiento del servidor de chat persistente, consulte [configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Defina el almacén de archivos. Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos (por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en un salón de chat). En el caso de una topología de servidor de chat persistente de varios servidores, debe ser una ruta de acceso UNC (Convención de nomenclatura universal); para una topología de servidor de chat persistente de un solo servidor, puede ser una ruta de acceso de archivo local.
    
    Para utilizar un almacén de archivos existente, haga lo siguiente:
    
    - En **FQDN del servidor de archivos**, especifique el FQDN del equipo en el que desee crear el almacén de archivos.
    
    - En **Recurso compartido de archivos**, especifique el almacén de archivos que desee utilizar.
    
      > [!IMPORTANT]
      > Puede definir el almacén de archivos en el generador de topología antes de crear el almacén de archivos, pero debe crear el almacén de archivos en la ubicación definida que defina antes de publicar la topología. Si el almacén de archivos aún no existe, no se podrá publicar la topología. 
  
11. Seleccione el grupo de servidores front-end que se usará como próximo salto para este grupo de servidores de chat persistente. Este es el grupo de servidores front-end que podrá enrutar solicitudes de servidor de chat persistentes a este grupo.
    
12. Para guardar la configuración, haga clic en **Finalizar**. El grupo de servidores de chat persistente aparece en el generador de topología junto con la configuración específica de la agrupación.
    
    Para publicar la topología actualizada a la que ha agregado el servidor de chat persistente, vea publicar la topología actualizada.
    
    > [!NOTE]
    > Con el generador de topología ya abierto, puede continuar con el paso 3 en publicar la topología actualizada para empezar a publicar su topología actualizada. 
  
## <a name="publish-the-updated-topology"></a>Publicar la topología actualizada
<a name="BKMK_PublishTopology"> </a>

Después de actualizar su topología en el generador de topología, debe publicarla en el almacén de administración central para poder configurar y usar Skype empresarial Server. Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios en la topología y en otras opciones de configuración.
  
Antes de publicar su topología, instale las bases de datos para el servidor de chat persistente. Use el generador de topología para instalar bases de datos seleccionando **acción** e **instalar base de datos**.
  
1. En un equipo que ejecuta Skype empresarial Server o en el que están instaladas las herramientas administrativas de Skype empresarial Server, inicie sesión con una cuenta que sea miembro del grupo de **administradores del dominio** y del grupo **RTCUniversalServerAdmins** , y que tenga permisos de control total (lectura, escritura y modificación) en el almacén de archivos para que se pueda usar en el almacén de archivos del servidor de chat persistente (para que topología pueda configurar las listas de control de acceso discrecional (DACL) obligatorias) o una cuenta con un usuario equivalente Rights.
    
2. Iniciar el generador de topología. Seleccione **Abrir la topología desde un archivo local**, si la ha guardado de forma local.
    
3. En el árbol de consola, haga clic con el botón secundario en **Skype empresarial Server 2015**y, a continuación, haga clic en **publicar topología**.
    
4. En la página **Publicar la topología**, haga clic en **Siguiente**.
    
5. En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    

