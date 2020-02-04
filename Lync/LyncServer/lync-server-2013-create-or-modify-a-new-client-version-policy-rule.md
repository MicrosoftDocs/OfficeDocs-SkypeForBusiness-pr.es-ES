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
ms.openlocfilehash: 442341c51ef6477f72fb9e88cdea5fe7fc527aa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Crear o modificar una nueva regla de directiva de versión de cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-21_

Las reglas de directiva de versión de cliente definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes específicos y versiones de cliente. Puede crear o modificar reglas individuales para una directiva de versión de cliente desde el panel de control de Lync Server 2013.

<div>


> [!IMPORTANT]  
> Las reglas se muestran en orden de prioridad. Por ejemplo, si tiene una regla que permite a los clientes que ejecutan la versión 1,5 se conecte, seguido de una regla que bloquea los clientes que ejecutan una versión anterior a la 2,0, la primera regla tiene prioridad y los clientes que ejecutan la versión 1,5 pueden conectarse.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Para crear o modificar reglas de directiva de versión de cliente con el panel de control de Lync Server

1.  [Cree o modifique una nueva Directiva de versión de cliente en Lync server 2013 con el](lync-server-2013-create-or-modify-a-new-client-version-policy.md) panel de control de Lync Server.

2.  En la página **Editar Directiva de versión del cliente** , realice una de las siguientes acciones:
    
      - Haga clic en **nuevo** para crear una nueva regla de versión de cliente.
    
      - Haga clic en uno de los tipos de cliente definidos en la lista y, a continuación, haga clic en **Mostrar detalles**.
    
    <div>
    

    > [!NOTE]  
    > Puede usar caracteres comodín para indicar el tipo de cliente.

    
    </div>

3.  En **agente de usuario**, seleccione un tipo de cliente.

4.  En **número de versión**, haga lo siguiente:
    
      - En **versión principal**, escriba el número que corresponde a la versión principal del cliente.
    
      - En **versión secundaria**, escriba el número que corresponde a la versión secundaria del cliente.
    
      - En **crear**, escriba el número que corresponde a la versión principal y secundaria del cliente.
    
      - En **Actualizar**, escriba el número que corresponde a la versión actualizada del cliente.
    
    <div>
    

    > [!NOTE]  
    > Puede usar caracteres comodín para indicar el número de versión del cliente.

    
    </div>

5.  Para especificar la operación correspondiente a la versión del cliente que especificó en los pasos anteriores, en **operación de comparación**, haga clic en una de las opciones siguientes:
    
      - **Igual que**
    
      - **No es**
    
      - **Anterior a**
    
      - **Anterior a o igual que**
    
      - **Posterior a**
    
      - **Posterior a o igual que**

6.  Para especificar **la acción que**se realizará cuando se cumplan los criterios de los pasos anteriores, haga clic en una de las siguientes acciones:
    
      - Para permitir que el cliente inicie sesión, haga clic en **permitir**.
    
      - Para permitir que el cliente inicie sesión y reciba actualizaciones de Windows Server Update Services o Microsoft Update, haga clic en **permitir y actualizar**. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.
        
        <div>
        

        > [!NOTE]  
        > Si selecciona esta acción, una notificación aparecerá la próxima vez que los usuarios inicien sesión en Lync 2013. La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado. Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.

        
        </div>
    
      - Para permitir que el cliente inicie sesión y muestre un mensaje sobre dónde Descargar otra versión del cliente, haga clic en **permitir con la dirección URL**. La dirección URL se especifica más adelante en este procedimiento.
    
      - Para evitar que el cliente inicie sesión, haga clic en **bloquear**.
    
      - Para evitar que el cliente inicie sesión y permitir que el cliente reciba actualizaciones de Windows Server Update Services o Microsoft Update, haga clic en **bloquear y actualizar**. Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.
    
      - Para evitar que el cliente inicie sesión y muestre un mensaje sobre dónde Descargar otra versión del cliente, haga clic en **bloquear con dirección URL**. La dirección URL se especifica más adelante en este procedimiento.

7.  Faculta Si hizo clic en **permitir con URL** o **bloque con dirección URL** en el paso anterior, escriba la dirección URL de descarga del cliente que se incluirá en el mensaje de la **dirección URL**.

8.  Haga clic en **Aceptar**y, a continuación, en **Ejecutar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

