---
title: 'Lync Server 2013: Definir topologías de Director opcionales en la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86f3c78730e8c866e3838f22a1267a57bb3d237b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definir topologías de Director opcionales en la topología para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Los directores de Lync Server 2013 pueden ser servidores de instancia única o se pueden instalar como un grupo de varios directores con equilibrio de carga para ofrecer mayor disponibilidad y capacidad. Se admiten el equilibrio de carga de hardware y el equilibrio de carga del sistema de nombres de dominio (DNS). En este tema se explica cómo configurar el equilibrio de carga de DNS para los grupos de directores.

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos **administradores de dominio** y **RTCUniversalServerAdmins** . También puede delegar los derechos y permisos adecuados para agregar roles de servidor. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition. Para otros cambios de configuración, solo es necesario pertenecer al grupo **RTCUniversalServerAdmins** .

En este tema se describen los pasos necesarios para definir y publicar la topología de las dos topologías de Director:

  - Para definir el director (instancia única)

  - Para definir el director (grupo de varios directores)

<div>

## <a name="to-define-the-director-single-instance"></a>Para definir el director (instancia única)

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En la Página principal, haga clic en **Descargar topología de la implementación existente**.

3.  En el cuadro de diálogo **Guardar topología como** , escriba el nombre y la ubicación de la copia local de la topología existente y, a continuación, haga clic en **Guardar**.

4.  Expanda el sitio en el que planea agregar el director, haga clic con el botón secundario en **grupos de directores**y, a continuación, haga clic en **nuevo grupo de directores**.

5.  En el cuadro de diálogo **definir el FQDN del grupo de directores** , haga lo siguiente:
    
      - En **FQDN del grupo**, escriba el FQDN del grupo de directores.
    
      - Haga clic en **grupo de equipos únicos**y, a continuación, en **siguiente**.

6.  En el cuadro de diálogo **definir el uso compartido de archivos** , realice una de las siguientes acciones:
    
    1.  Para usar un recurso compartido de archivos existente, haga clic en usar un recurso compartido de archivos **definido previamente**, seleccione un recurso compartido de archivos de la lista y haga clic en **siguiente**.
    
    2.  Para crear un nuevo recurso compartido de archivos, haga clic en **definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN del servidor de archivos**, escriba el nombre del recurso compartido en el **recurso compartido de archivos**y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!IMPORTANT]  
    > El recurso compartido de archivos que especifique o cree en este paso debe existir o crearse antes de publicar la topología.<BR>El recurso compartido de archivos asignado a un director no se utiliza realmente, por lo que puede asignar el recurso compartido de archivos de cualquier grupo de la organización.

    
    </div>

7.  En el cuadro de diálogo **especificar dirección URL de servicios web** , en **dirección URL base externa**, especifique el FQDN de los directores y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > El nombre debe poder resolverse desde los servidores DNS de Internet y apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS a esa dirección URL y los envía al directorio virtual de servicios Web externo de ese director.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end. Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

8.  Publique la topología.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Para definir el director (grupo de varios directores)

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En la Página principal, haga clic en **Descargar topología de la implementación existente**.

3.  En el cuadro de diálogo **Guardar topología como** , escriba el nombre y la ubicación de la copia local de la topología existente y, a continuación, haga clic en **Guardar**.

4.  Expanda el sitio en el que planea agregar el director, haga clic con el botón secundario en **grupos de directores**y, a continuación, haga clic en **nuevo grupo de directores**.

5.  En el cuadro de diálogo **definir el FQDN del grupo de directores** , haga lo siguiente:
    
      - En **FQDN del grupo**, escriba el FQDN del grupo de directores.
    
      - Haga clic en **grupo de varios equipos**y, a continuación, en **siguiente**.

6.  En el cuadro de diálogo **definir los equipos de este grupo** , haga lo siguiente:
    
      - Especifique el FQDN del equipo del primer miembro del grupo y, a continuación, haga clic en **Agregar**.
    
      - Repita el paso anterior para cada equipo que desee agregar. Cuando haya terminado, haga clic en **siguiente**.

7.  En el cuadro de diálogo **definir el uso compartido de archivos** , realice una de las siguientes acciones:
    
      - Para usar un recurso compartido de archivos existente, haga clic en usar un recurso compartido de archivos **definido previamente**, seleccione un recurso compartido de archivos de la lista y haga clic en **siguiente**.
    
      - Para crear un nuevo recurso compartido de archivos, haga clic en **definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN del servidor de archivos**, escriba el nombre del recurso compartido en el **recurso compartido de archivos**y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!IMPORTANT]  
    > El recurso compartido de archivos que especifique o cree en este paso debe existir o crearse antes de publicar la topología.<BR>El recurso compartido de archivos asignado a un director no se utiliza realmente, por lo que puede asignar el recurso compartido de archivos de cualquier grupo de la organización.

    
    </div>

8.  En el cuadro de diálogo **especificar dirección URL de servicios web** , en **dirección URL base externa**, especifique el FQDN de los directores y, a continuación, haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > El nombre debe poder resolverse desde los servidores DNS de Internet y apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS enviadas a esa dirección URL y las envía al directorio virtual de servicios Web externo de ese grupo de directores.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end. Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

9.  Publique la topología.

</div>

</div>

<span> </span>

</div>

</div>

</div>

