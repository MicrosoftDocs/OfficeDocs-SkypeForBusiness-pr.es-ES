---
title: 'Lync Server 2013: definir topologías de Director opcionales en la topología'
description: 'Lync Server 2013: defina topologías de Director opcionales en la topología.'
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
ms.openlocfilehash: 5bc82108d4277969489739fc81db07ec6f96bb96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542660"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definir topologías de Director opcionales en la topología para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Los directores de Lync Server 2013 pueden ser servidores de instancia única o se pueden instalar como un grupo de carga equilibrada de varios directores para obtener una mayor disponibilidad y capacidad. Se admiten el equilibrio de carga de hardware y el equilibrio de carga del sistema de nombres de dominio (DNS). En este tema se explica cómo configurar el equilibrio de carga de DNS para grupos de directores.

Para publicar, habilitar o deshabilitar una topología correctamente al agregar o quitar un rol de servidor, debe haber iniciado sesión con un usuario que sea miembro de los grupos **RTCUniversalServerAdmins** y **Administradores de dominio**. También es posible delegar los permisos apropiados para agregar roles de servidor. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition. Para realizar otros cambios en la configuración, solo se necesita ser miembro del grupo **RTCUniversalServerAdmins**.

En este tema se describen los pasos para definir y publicar la topología para las dos topologías de Director:

  - Para definir el director (una sola instancia)

  - Para definir el Director (grupo de varios directores)

<div>

## <a name="to-define-the-director-single-instance"></a>Para definir el Director (instancia única)

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En la página de bienvenida, haga clic en **Descargar topología de la implementación existente**.

3.  En el cuadro de diálogo **Guardar topología como**, escriba el nombre y la ubicación de la copia local de la topología existente y haga clic en **Guardar**.

4.  Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director**.

5.  En el cuadro de diálogo **Definir el FQDN del grupo director**, haga lo siguiente:
    
      - En **FQDN de grupo de servidores**, escriba el FQDN del grupo de servidores de director.
    
      - Haga clic en **Grupo de servidores de un solo equipo** y, a continuación, haga clic en **Siguiente**.

6.  En el cuadro de diálogo **Definir el recurso compartido de archivos**, siga uno de estos procedimientos:
    
    1.  Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente**, seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente**.
    
    2.  Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos**, escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente**.
    
    <div>
    

    > [!IMPORTANT]  
    > El recurso compartido de archivos que especifique o que cree en este paso debe existir o debe haberse creado antes de publicar la topología.<BR>En realidad, el recurso compartido de archivos asignado a un director no se usa, de modo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.

    
    </div>

7.  En el cuadro de diálogo **Especificar la URL de servicios web**, en **URL de base externa**, especifique el FQDN de los directores y haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > El nombre debe poder resolverse desde los servidores DNS de Internet, y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS a esa URL y las redirige al directorio virtual de servicios web externos de ese director.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end. Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end. Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

8.  Publique la topología.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Para definir el Director (grupo de directores de múltiples)

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En la página de bienvenida, haga clic en **Descargar topología de la implementación existente**.

3.  En el cuadro de diálogo **Guardar topología como**, escriba el nombre y la ubicación de la copia local de la topología existente y haga clic en **Guardar**.

4.  Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director**.

5.  En el cuadro de diálogo **Definir el FQDN del grupo director**, haga lo siguiente:
    
      - En **FQDN de grupo de servidores**, escriba el FQDN del grupo de servidores de director.
    
      - Haga clic en **Grupo de servidores de varios equipos** y, a continuación, haga clic en **Siguiente**.

6.  En el cuadro de diálogo **Definir los equipos de este grupo **, haga lo siguiente:
    
      - Especifique el FQDN de equipo del primer miembro del grupo de servidores y haga clic en **Agregar**.
    
      - Repita el paso anterior para cada equipo que quiera agregar. Cuando haya acabado, haga clic en **Siguiente**.

7.  En el cuadro de diálogo **Definir el recurso compartido de archivos**, siga uno de estos procedimientos:
    
      - Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente**, seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente**.
    
      - Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos**, escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos**, escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente**.
    
    <div>
    

    > [!IMPORTANT]  
    > El recurso compartido de archivos que especifique o que cree en este paso debe existir o debe haberse creado antes de publicar la topología.<BR>En realidad, el recurso compartido de archivos asignado a un director no se usa, de modo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.

    
    </div>

8.  En el cuadro de diálogo **Especificar la URL de servicios web**, en **URL de base externa**, especifique el FQDN de los directores y haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > El nombre debe poder resolverse en servidores DNS de Internet y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS enviadas a la dirección URL y lo envía mediante proxy al directorio virtual de servicios web externos del grupo de servidores de director.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end. Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end. Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.

    
    </div>

9.  Publique la topología.

</div>

</div>

<span> </span>

</div>

</div>

</div>

