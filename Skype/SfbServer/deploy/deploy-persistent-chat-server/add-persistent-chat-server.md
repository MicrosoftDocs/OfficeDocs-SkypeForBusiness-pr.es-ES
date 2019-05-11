---
title: Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumen: Lea este tema para obtener información sobre cómo agregar servidores de Chat persistente a su Skype para topología empresarial Server 2015.'
ms.openlocfilehash: edd04ce781c3f91190b2c7baf9e0575f6dba5b1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894503"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo agregar servidores de Chat persistente a su Skype para topología empresarial Server 2015.
  
Después de instalar el software necesario como requisito previo en cada servidor en el que planea implementar servidor de Chat persistente, use el generador de topología para: 
  
- Actualizar la topología para incluir el servidor de chat persistente
    
- Publicar la topología actualizada
    
> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Actualizar la topología para incluir el servidor de chat persistente

Realice los pasos siguientes para instalar un único grupo de servidores de servidor de Chat persistente sin una configuración de recuperación ante desastres. Para configurar un grupo de servidores de Chat persistente de alta disponibilidad y recuperación ante desastres, vea [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Para implementar varios grupos de servidores de Chat persistente, repita el mismo proceso para cada grupo de servidores.
  
1. En un equipo que ejecuta Skype para Business Server o en el que el Skype para instaladas las herramientas administrativas de Business Server, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología mediante una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesario para instalar Skype para Business Server, debe usar una cuenta que sea miembro del grupo **Administradores** del dominio y el ** RTCUniversalServerAdmins** grupo y que tiene permisos de control total (leer, escribir y modificar) en el almacén de archivos que se va a usar para el almacén de archivos de servidor de Chat persistente (por lo que el generador de topología puede configurar las DACL necesarias), o una cuenta con derechos equivalentes.
  
2. Iniciar el generador de topología.
    
3. En el árbol de consola, navegue hasta el nodo **Grupos de servidores de Chat persistente** y expándalo para seleccionar un Skype para el grupo de servidores empresariales, o haga clic en el nodo y seleccione **Nuevo grupo de Chat persistente**. Debe definir el nombre del grupo de servidores de dominio completo (FQDN) e indicar si el grupo de servidores será un grupo de servidores de un solo servidor o la implementación del grupo de varios servidores.
    
    Puede elegir un **Grupo de varios equipos** o **Grupo de un solo equipo**. Elija los antiguos si planea tener más de un servidor Front-End de su grupo de servidores de Chat persistente. Realice esta elección ahora, porque después de crear un grupo de un solo equipo no le podrá agregar servidores adicionales más adelante. Si elige un grupo de varios equipos, escriba los nombres de la individuales servidores Front-End que conforman el grupo de servidores.
    
    > [!IMPORTANT]
    > Si se va a instalar el rol de servidor de Chat persistente en un servidor Standard Edition, el FQDN debe coincidir con el FQDN del servidor Standard Edition. 
  
4. Definir un **Nombre para mostrar** sencillo para el grupo de servidores de Chat persistente. El nombre para mostrar se puede usar por los clientes personalizados, especialmente cuando hay varios grupos de servidores de Chat persistente para diferenciar los salones.
    
5. Definir el puerto usado por el servidor de Chat persistente para comunicarse con Skype para servidores Front-End de Business Server. El puerto predeterminado es 5041.
    
6. Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento**. Si selecciona esta opción, el servicio de cumplimiento de servidor de Chat persistente está instalado en el mismo equipo que el Persistent Chat Server servidor Front-End. Le pedirá que seleccione un servidor de SQL Server Back End para cumplimiento de servidor de Chat persistente más adelante.
    
7. Asignar afinidad de sitios para el grupo de servidores de Chat persistente. Seleccione el **utilizar este grupo de servidores como predeterminado para el sitio \<SiteName\> ** casilla de verificación o **utilizar este grupo de servidores como predeterminado para todos los sitios** para designar este grupo de servidores de servidor de Chat persistente como el grupo predeterminado para el sitio actual o todos los sitios. Cuando se usa el Skype para cliente de negocio para crear y administrar las salas, se usa el grupo predeterminado asociado con el sitio del usuario por la experiencia de creación y administración de salón para que pueden enrutar las operaciones de creación y administración de sala a ese grupo. Esto sólo se aplica cuando tiene varios grupos de servidores de Chat persistente implementados y desea usar las características de creación y administración de sala de servidor de Chat persistente.
    
    > [!IMPORTANT]
    > Puede personalizar las características de creación y administración de sala utilizando la persistente Chat Server Software Development Kit (SDK). 
  
8. Defina el **almacén de SQL para la Persistent Chat Server Back-End (donde se almacena el contenido del salón de chat)** realizando una de las siguientes:
    
   - Para usar un almacén de SQL Server existente, en la lista desplegable, haga clic en el nombre del almacén de SQL Server que desea usar.
    
   - Para especificar una nueva base de datos de SQL Server, haga clic en **nuevo**y, en **Definir nuevo almacén SQL**, haga lo siguiente:
    
   - En **FQDN de SQL Server**, especifique el FQDN del servidor SQL en el que desea crear la nueva base de datos de SQL Server.
    
   - Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, luego, especifique la instancia que desee utilizar.
    
     > [!NOTE]
     > Para obtener información detallada sobre cómo configurar las bases de datos de copia de seguridad de SQL Server para la recuperación ante desastres, vea [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Definir el almacén de cumplimiento de normas de SQL Server si habilitó cumplimiento.
    
    > [!IMPORTANT]
    > Para obtener información detallada sobre cómo configurar los espejos de SQL Server para una alta disponibilidad para la base de datos del servidor de Chat persistente y la base de datos de cumplimiento del servidor de Chat persistente, vea [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Defina el almacén de archivos. Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos (por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en un salón de chat). En el caso de una topología de servidor de Chat persistente de varios servidores, debe ser una ruta de acceso de convención de nomenclatura Universal (UNC); y para una topología de servidor de Chat persistente de un único servidor, puede ser una ruta de acceso de archivo local.
    
    Para utilizar un almacén de archivos existente, haga lo siguiente:
    
    - En **FQDN del servidor de archivos**, especifique el FQDN del equipo en el que desee crear el almacén de archivos.
    
    - En **Recurso compartido de archivos**, especifique el almacén de archivos que desee utilizar.
    
      > [!IMPORTANT]
      > Puede definir el almacén de archivos en el generador de topología antes de crear el almacén de archivos, pero debe crear el almacén de archivos en la ubicación definida que definir antes de publicar la topología. Si el almacén de archivos aún no existe, no se podrá publicar la topología. 
  
11. Seleccione el grupo de servidor Front-End que se usará como próximo salto para este grupo de servidores de servidor de Chat persistente. Este es el grupo de servidor Front-End que podrá enrutar las solicitudes de servidor de Chat persistente a este grupo de servidores.
    
12. Para guardar la configuración, haga clic en **Finalizar**. El grupo de servidores de Chat persistente aparece en el generador acompañadas de la configuración de grupo de servidores específico.
    
    Para publicar su topología actualizada a la que ha agregado el servidor de Chat persistente, consulte publicar la topología actualizada.
    
    > [!NOTE]
    > Con el generador de topología ya está abierto, puede continuar con el paso 3 en publicar la topología actualizada para empezar a publicar su topología actualizada. 
  
## <a name="publish-the-updated-topology"></a>Publicar la topología actualizada
<a name="BKMK_PublishTopology"> </a>

Después de actualizar la topología en Topology Builder, debe publicar la topología en el almacén de Administración Central antes de configurar y usar Skype para Business Server. Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios en la topología y en otras opciones de configuración.
  
Antes de publicar la topología, instale las bases de datos para el servidor de Chat persistente. Use el generador de topología para instalar las bases de datos mediante la selección de **acción** e **Instalar base de datos**.
  
1. En un equipo que ejecuta Skype para Business Server o en el que el Skype para instaladas las herramientas administrativas de Business Server, inicie sesión con una cuenta que sea miembro del grupo **Administradores** del dominio y del grupo **RTCUniversalServerAdmins** , y que tiene permisos de control total (leer, escribir y modificar) en el almacén de archivos que se usará para el almacén de archivos de servidor de Chat persistente (de modo que el generador de topología puede configurar las listas de control de acceso discrecional (DACL)), o una cuenta de usuario equivalentes derechos.
    
2. Iniciar el generador de topología. Seleccione **Abrir la topología desde un archivo local**, si la ha guardado de forma local.
    
3. En el árbol de consola, secundario **Skype para Business Server 2015**y, a continuación, haga clic en **Publicar topología**.
    
4. En la página **Publicar la topología**, haga clic en **Siguiente**.
    
5. En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    

