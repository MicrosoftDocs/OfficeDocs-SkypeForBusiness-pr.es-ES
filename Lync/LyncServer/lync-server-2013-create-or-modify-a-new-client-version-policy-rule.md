---
title: 'Lync Server 2013: crear o modificar una nueva regla de directiva de versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fec7930b8ebd7aa6bb7f50c71a1f163cdb83f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Crear o modificar una nueva regla de directiva de versión de cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-21_

Las reglas de directiva de versión de cliente definen las acciones que se deben llevar a cabo cuando los usuarios intentan iniciar sesión con clientes y versiones de cliente específicos. Puede crear o modificar reglas individuales para una directiva de versión de cliente desde el panel de control de Lync Server 2013.

<div>


> [!IMPORTANT]  
> Las reglas se enumeran en orden de prioridad. Por ejemplo, si tiene una regla que permite la conexión a los clientes que ejecutan la versión 1,5, seguido de una regla que bloquea los clientes que ejecutan una versión anterior a la 2,0, la primera regla tiene prioridad y los clientes que ejecutan la versión 1,5 tienen permiso para conectarse.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Para crear o modificar reglas de directiva de versión de cliente con el panel de control de Lync Server

1.  [Cree o modifique una nueva Directiva de versión de cliente en Lync server 2013 con el](lync-server-2013-create-or-modify-a-new-client-version-policy.md) panel de control de Lync Server.

2.  En la página **Editar Directiva de versión de cliente** , realice una de las siguientes acciones:
    
      - Haga clic en **Nueva** para crear una regla nueva de versión de cliente.
    
      - Haga clic en uno de los tipos de cliente definidos en la lista y, a continuación, haga clic en **Mostrar detalles...**.
    
    <div>
    

    > [!NOTE]  
    > Puede usar comodines para indicar el tipo de cliente.

    
    </div>

3.  En **Aplicación**, seleccione un tipo de cliente.

4.  En **Número de versión**, siga este procedimiento:
    
      - En **Versión principal**, escriba el número que se corresponde con la versión principal del cliente.
    
      - En **Versión secundaria**, escriba el número que se corresponde con la versión secundaria del cliente.
    
      - En **Versión**, escriba el número que se corresponde con la versión principal y secundaria del cliente.
    
      - En **Actualización**, escriba el número que se corresponde con la versión actualizada del cliente.
    
    <div>
    

    > [!NOTE]  
    > Puede usar caracteres comodín para indicar el número de versión del cliente.

    
    </div>

5.  Para especificar la operación coincidente para la versión del cliente que haya especificado en los pasos anteriores, en **Operación de comparación**, haga clic en una de las siguientes opciones:
    
      - **Igual que**
    
      - **No es**
    
      - **Anterior a**
    
      - **Anterior a o igual que**
    
      - **Posterior a**
    
      - **Posterior a o igual que**

6.  Para especificar la acción a realizar cuando se cumplen los criterios de los pasos anteriores, haga clic en una de las siguientes opciones en **Acción**:
    
      - Para permitir que el usuario inicie sesión, haga clic en **Permitir**.
    
      - Para permitir que el cliente inicie sesión y reciba actualizaciones de Windows Server Update Service o Microsoft Update, haga clic en **permitir y actualizar**. Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.
        
        <div>
        

        > [!NOTE]  
        > Al seleccionar esta acción, aparecerá una notificación la próxima vez que los usuarios inicien sesión en Lync 2013. La notificación comunica que hay una actualización disponible, aunque las actualizaciones aún no se hayan publicado en Windows Server Update Service o en Microsoft Update. Para evitar confusiones, se recomienda elegir esta acción solo cuando las actualizaciones estén disponibles.

        
        </div>
    
      - Para permitir que un cliente inicie sesión y muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Permitir con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.
    
      - Para impedir que el cliente inicie sesión, haga clic en **Bloquear**.
    
      - Para evitar que el cliente inicie sesión y permitir que el cliente reciba actualizaciones de Windows Server Update Service o Microsoft Update, haga clic en **bloquear y actualizar**. Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.
    
      - Para impedir que un cliente inicie sesión y se muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Bloquear con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.

7.  (Opcional) Si hizo clic en **Permitir con dirección URL** o **Bloquear con dirección URL** en el paso anterior, escriba la dirección URL de descarga a incluir en el mensaje en **Dirección URL**.

8.  Haga clic en **Aceptar** y, a continuación, en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

