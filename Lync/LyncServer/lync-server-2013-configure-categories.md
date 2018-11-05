---
title: 'Lync Server 2013: Configurar categorías'
TOCTitle: Configurar categorías
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48275142
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar categorías en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

En Panel de control de Lync Server 2013, puede utilizar el apartado **Categoría** de la página **Chat persistente** para configurar las categorías. Una categoría de salón de Chat persistente es una estructura lógica para organizar salones de chat. Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar a los usuarios y grupos de usuarios que pueden crear o unirse a los salones de chat. Puede utilizar las categorías para aplicar limitaciones éticas entre las distintas subdivisiones dentro de sus organizaciones

Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías. Cada categoría describe su contenido con metadatos como el *nombre* y la *descripción* . Además, la categoría tiene propiedades que se pueden definir para controlar el comportamiento de los salones de chat que pertenecen a esta categoría, por ejemplo si el salón de chat permite *invitaciones* , *cargas de archivos* o contiene el *historial de chat* .

## Configuración de las categorías de las salas de chat

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio**, seleccione Panel de control de Lync Server o abra una ventana del navegador y, a continuación, introduzca la URL del administrador. Para obtener información detallada acerca de los distintos métodos, puede utilizar Panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > También puede utilizar cmdlets Windows PowerShell. Para más información, vea <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuración del servidor de chat persistente con cmdlets de Windows PowerShell</a> en la documentación de implementación.
    


3.  En la barra de navegación de la izquierda, haga clic en **Chat persistente** y, a continuación, haga clic en **Categoría**.
    
    Para varias implementaciones Grupo de servidores de chat persistente, seleccione el grupo de servidores adecuado de la lista desplegable.

4.  En la página **Categoría**, haga clic en **Nuevo** o **Editar**.

5.  En **Seleccionar un servicio**, seleccione el servicio correspondiente para la Grupo de servidores de chat persistente en el que es necesario crear la categoría. El servicio es el grupo de servidores Servidor de chat persistente que el Chat persistente (cliente) utiliza para identificar a qué grupo pertenece la categoría. Una categoría puede pertenecer a solo un Grupo de servidores de chat persistente y no se puede mover a otro o compartir con otro grupo de servidores.

6.  En **Nueva categoría**, haga lo siguiente:
    
    1.  En **Nombre**, especifique un nombre para la nueva categoría de sala.
    
    2.  En **Descripción**, proporcione una descripción detallada sobre la categoría del salón (por ejemplo, una categoría de salón para Contoso).
    
    3.  Para controlar si las invitaciones se puede habilitar para salones de chat que pertenecen a esta categoría, active o desactive la casilla **Permitir invitaciones**. Si está activada, los salones en esta categoría puedan tener invitaciones activas o inactivas; si está desactivada, el salón de esta categoría no puede tener invitaciones. Si un salón tiene invitaciones activas, cuando se agrega un nuevo miembro a un salón, este recibe una notificación del nuevo salón en su cliente de Chat persistente.
    
    4.  Para controlar las cargas de archivos en salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar carga de archivos**. Si está activada, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos; si no está activada, los salones de esta categoría no pueden tener cargas de archivos.
        
        > [!IMPORTANT]  
        > Esta configuración se aplica en el servidor debido a que las aplicaciones personalizadas o los clientes Chat en grupo anteriores que usan Office Communications Server 2007 R2Servidor de chat en grupo o Lync Server 2010, chat en grupo pueden publicar archivos en un salón. El cliente Lync 2013 no tiene capacidad para cargar/descargar archivos, de modo que si tiene una implementación de Lync 2013 pura o un cliente Lync 2013, no será posible publicar archivos en un salón de chat de Servidor de chat persistente.
        
    
    5.  Para controlar el historial de chats, active o desactive la casilla **Habilitar historial de chat**. Si está activada, los salones de chat serán persistentes, en caso contrario, los mensajes de chats no persisten. Si el cumplimiento está habilitado, los chats del salón se guardarán en consecuencia, pero los usuarios no podrán tener acceso a los mensajes antiguos. Esta opción puede usarse para salones designados para la colaboración en tiempo real, ad hoc que no necesiten que el historial de chat persista.

7.  En **Editar categoría**, haga lo siguiente:
    
      - En **Pertenencia**, en la sección **Miembros permitidos**, agregue o quite usuarios y otras entidades de seguridad de Servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que pueden agregarse como miembros de los salones de chat pertenecientes a la categoría. Las entidades de seguridad permitidas por una categoría pueden buscar salones en la categoría (a menos que el salón está oculto, en cuyo caso solo los miembros del salón pueden buscarla en el directorio).
    
      - En **Pertenencia**, en el apartado **Miembros denegados**, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con miembros denegados del salón.
    
      - En **Pertenencia**, en la sección **Creadores**, agregue o quite usuarios y otras entidades de seguridad de Active Directory asociadas con los creadores de la categoría. Un creador es un usuario que tiene permisos para crear salones de chat y asignar los administradores y los miembros de los salones de chat.

8.  Haga clic en **Confirmar**.

