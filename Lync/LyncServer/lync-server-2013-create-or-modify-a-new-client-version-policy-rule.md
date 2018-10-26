---
title: Crear o modificar una nueva regla de directiva de versión de cliente
TOCTitle: Crear o modificar una nueva regla de directiva de versión de cliente
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ898478(v=OCS.15)
ms:contentKeyID: 52061697
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una nueva regla de directiva de versión de cliente

 

_**Última modificación del tema:** 2013-01-21_

Las reglas de directiva de versión de cliente definen las acciones que se deben llevar a cabo cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos. Puede crear o cambiar reglas individuales para una directiva de versión de cliente desde el Panel de control de Lync Server 2013.

> [!IMPORTANT]  
> Las reglas se enumeran en orden de prioridad. Por ejemplo, si tiene una regla que permite conectarse a los clientes que estén ejecutando la versión 1.5 o versiones posteriores, seguida de una regla que bloquee a los clientes que estén ejecutando una versión anterior a la 2.0, la primera regla tiene prioridad y se permitirá conectarse a los clientes que ejecuten la versión 1.5.



## Para crear o cambiar reglas de directiva de versión de cliente con el Panel de control de Lync Server

1.  [Crear o modificar una nueva directiva de versión de cliente](lync-server-2013-create-or-modify-a-new-client-version-policy.md) con el Panel de control de Lync Server.

2.  En la página **Editar directiva de versión de cliente**, haga una de las acciones siguientes:
    
      - Haga clic en **Nueva** para crear una regla nueva de versión de cliente.
    
      - Haga clic en uno de los tipos de cliente definidos en la lista y después haga clic en **Mostrar detalles**.
    

    > [!NOTE]
    > Puede usar caracteres comodín para indicar el tipo de cliente.



3.  En **Agente de usuario**, seleccione un tipo de cliente.

4.  En **Número de versión**, haga lo siguiente:
    
      - En **Versión principal**, escriba el número que corresponda a la versión principal del cliente.
    
      - En **Versión secundaria**, escriba el número que corresponda a la versión secundaria del cliente.
    
      - En **Compilación**, escriba el número que corresponda a la versión principal y secundaria del cliente.
    
      - En **Actualización**, escriba el número que corresponda a la versión actualizada del cliente.
    

    > [!NOTE]
    > Puede usar caracteres comodín para indicar el número de versión del cliente.



5.  Para especificar la operación coincidente para la versión del cliente que haya especificado en los pasos anteriores, en **Operación de comparación**, haga clic en una de las siguientes opciones:
    
      - **Igual que**
    
      - **No es**
    
      - **Más reciente que**
    
      - **Más reciente o igual que**
    
      - **Más antiguo que**
    
      - **Más antiguo o igual que**

6.  Para especificar la acción que se llevará a cabo cuando se cumplan los criterios de los pasos anteriores, haga clic en una de las siguientes opciones de **Acción**:
    
      - Para permitir que el cliente inicie sesión, haga clic en **Permitir**.
    
      - Para permitir que el cliente inicie sesión y reciba actualizaciones de Windows Server Update Service o de Microsoft Update, haga clic en **Permitir y actualizar**. Esta acción está disponible únicamente cuando se selecciona **OC**.
        

        > [!NOTE]
        > Si se selecciona esta opción, aparecerá una notificación la siguiente vez que los usuarios inicien sesión en Lync 2013. La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado. Para evitar confusiones, se recomienda elegir esta acción solo cuando las actualizaciones estén disponibles.

    
      - Para permitir que un cliente inicie sesión y se muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Permitir con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.
    
      - Para impedir que el cliente inicie sesión, haga clic en **Bloquear**.
    
      - Para impedir que el cliente inicie sesión y permitirle que reciba actualizaciones de Windows Server Update Service o de Microsoft Update, haga clic en **Bloquear y actualizar**. Esta acción está disponible únicamente cuando se selecciona la aplicación **OC**.
    
      - Para impedir que un cliente inicie sesión y se muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Bloquear con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.

7.  (Opcional) Si hizo clic en **Permitir con dirección URL** o **Bloquear con dirección URL** en el paso anterior, escriba en **URL** la dirección URL para la descarga del cliente que se incluirá en el mensaje.

8.  Haga clic en **Aceptar** y, a continuación, en **Confirmar**.

