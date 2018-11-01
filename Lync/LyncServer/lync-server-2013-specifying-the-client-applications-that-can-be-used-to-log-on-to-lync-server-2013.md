---
title: "Especificar aplicaciones cliente para iniciar sesión en Lync Server 2013"
TOCTitle: "Spéc. des app. clients pouvant être util. pour la connexion à Lync Server 2013"
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48276752
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Especificación de las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013

 

_**Última modificación del tema:** 2012-12-11_

Lync Server 2013 le permite especificar la versión de clientes que se admiten en su entorno. Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para aprovechar al máximo las características que incorpora Lync Server 2013 y mejorar la experiencia de uso global, puede usar el filtro de la versión del cliente para restringir las versiones de cliente que se van a usar en el entorno de Lync Server 2013. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.

Además de crear una directiva global, puede crear directivas de versión de cliente para un servicio o sitio en particular, o directivas cuyo ámbito este definido por el usuario y que se pueden asignar a usuarios individuales. La directiva de versión de cliente con ámbito definido por el cliente se puede asignar a usuarios individuales desde el grupo **Usuarios** en Panel de control de Lync Server.


> [!NOTE]
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.



> [!IMPORTANT]  
> Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5 o posterior, seguido de un filtro que bloquee a los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y se permitirá conectarse a los clientes que ejecuten la versión 1.5.



## Para editar la directiva predeterminada de versión de cliente

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes**.
    

    > [!NOTE]
    > La pestaña <STRONG>Directiva de versión de cliente</STRONG> está seleccionada de forma predeterminada.



4.  En la página **Directiva de versión de cliente**, haga doble clic en la directiva **Global** de la lista.

5.  En **Editar directiva de versión de cliente**, lleve a cabo uno de los procedimientos siguientes:
    
      - Haga clic en **Nueva** para crear una regla nueva de versión de cliente.
    
      - Haga clic en uno de los tipos de cliente definidos en la lista y, a continuación, haga clic en **Mostrar detalles...**.
    

    > [!NOTE]
    > Puede usar comodines para indicar el tipo de cliente.



6.  En **Aplicación**, seleccione un tipo de cliente.

7.  En **Número de versión**, siga este procedimiento:
    
      - En **Versión principal**, escriba el número que se corresponde con la versión principal del cliente.
    
      - En **Versión secundaria**, escriba el número que se corresponde con la versión secundaria del cliente.
    
      - En **Versión**, escriba el número que se corresponde con la versión principal y secundaria del cliente.
    
      - En **Actualización**, escriba el número que se corresponde con la versión actualizada del cliente.
    

    > [!NOTE]
    > Puede usar caracteres comodín para indicar el número de versión del cliente.



8.  Para especificar la operación coincidente para la versión del cliente que haya especificado en los pasos anteriores, en **Operación de comparación**, haga clic en una de las siguientes opciones:
    
      - **Igual que**
    
      - **No es**
    
      - **Anterior a**
    
      - **Anterior a o igual que**
    
      - **Posterior a**
    
      - **Posterior a o igual que**

9.  Para especificar la acción a realizar cuando se cumplen los criterios de los pasos anteriores, haga clic en una de las siguientes opciones en **Acción**:
    
      - Para permitir que el usuario inicie sesión, haga clic en **Permitir**.
    
      - Para permitir que el cliente inicie sesión y reciba actualizaciones de Windows Server Update Service o de Microsoft Update, haga clic en **Permitir y actualizar**. Esta acción está disponible únicamente cuando se selecciona Microsoft Lync 2010.
        

        > [!NOTE]
        > Si se selecciona esta opción, aparecerá una notificación la siguiente vez que los usuarios inicien sesión en Lync 2013. La notificación comunica que hay una actualización disponible, aun cuando el servicio de actualizaciones de Windows Server o Microsoft Update todavía no la hayan publicado. Para evitar confusiones, se recomienda elegir esta acción solo cuando las actualizaciones estén disponibles.

    
      - Para permitir que un cliente inicie sesión y muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Permitir con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.
    
      - Para impedir que el cliente inicie sesión, haga clic en **Bloquear**.
    
      - Para impedir que el cliente inicie sesión y permitirle que reciba actualizaciones de Windows Server Update Service o de Microsoft Update, haga clic en **Bloquear y actualizar**. Esta acción está disponible únicamente cuando se selecciona la aplicación Lync 2010.
    
      - Para impedir que un cliente inicie sesión y se muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Bloquear con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.

10. (Opcional) Si hizo clic en **Permitir con dirección URL** o **Bloquear con dirección URL** en el paso anterior, escriba la dirección URL de descarga a incluir en el mensaje en **Dirección URL**.

11. Haga clic en **Aceptar** y, a continuación, en **Confirmar**.

## Vea también

#### Otros recursos

[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

