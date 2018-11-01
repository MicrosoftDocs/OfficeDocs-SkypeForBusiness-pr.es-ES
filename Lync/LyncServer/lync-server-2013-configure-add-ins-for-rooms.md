---
title: 'Lync Server 2013: Configurar complementos para salones'
TOCTitle: Configurar complementos para salones
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48275245
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar complementos para salones en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

En Panel de control de Lync Server 2013, puede usar la sección **Complemento** de la página **Chat persistente** para asociar direcciones URL a salones de Chat persistente. Estas direcciones URL aparecen en el cliente de Lync 2013 en el salón de chat en el panel de extensibilidad de conversación. Un administrador debe agregar complementos a la lista de complementos registrados, permitiendo que los salones se asocien a uno de los complementos registrados antes de que los usuarios puedan ver esta actualización en su cliente de Lync 2013.

Los complementos se usan para ampliar la experiencia en el salón. Un complemento normal podría incluir una dirección URL que señale a una aplicación Silverlight que se intercepta cuando se envía un tablero de cotizaciones a un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad. Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".

## Procedimiento para configurar complementos para salones de chat

1.  Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  En el menú **Inicio**, seleccione el Panel de control de Lync Server o abra la ventana del explorador y, después, escriba la dirección URL del administrador. Para más información sobre los diferentes métodos que puede usar para abrir el Panel de control de Lync Server, vea [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > También puede utilizar cmdlets Windows PowerShell. Para más información, vea <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuración del servidor de chat persistente con cmdlets de Windows PowerShell</a> en la documentación de implementación.
    


3.  En la barra de navegación izquierda, haga clic en **Chat persistente** y después en **Complemento**.
    
    Para varias implementaciones Grupo de servidores de chat persistente, seleccione el grupo de servidores adecuado de la lista desplegable.

4.  En la página **Complemento**, haga clic en **Nuevo**.

5.  En **Seleccionar un servicio**, seleccione el servicio correspondiente a Grupo de servidores de chat persistente donde necesita crear el complemento. Los complementos no se pueden mover de un grupo a otro o compartirse entre diferentes grupos.

6.  En **Complemento nuevo**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para el nuevo complemento.
    
      - En **URL**, especifique la dirección URL que se va a asociar al complemento. Las direcciones URL se limitan a protocolos http y https.

7.  Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md)  

#### Conceptos

[Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

