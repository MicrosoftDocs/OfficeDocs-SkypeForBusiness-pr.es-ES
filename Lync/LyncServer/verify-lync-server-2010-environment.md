---
title: Comprobar el entorno de Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a98bdaa5b97193ad20a78939560190a413a87161
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515977"
---
# <a name="verify-lync-server-2010-environment"></a>Comprobar el entorno de Lync Server 2010

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Antes de implementar Lync Server 2013 en un estado de coexistencia con Lync Server 2010, debe comprobar que los servicios de Lync Server 2010 se han configurado e iniciado. Es importante identificar los servicios y características clave que existen en el entorno heredado antes de implementar un grupo piloto de Lync Server 2013. Antes de implementar Microsoft Lync Server 2013 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar qué socio federado admite la configuración de XMPP heredado. La comprobación de la implementación heredada de Lync Server 2010 implica lo siguiente:

  - Comprobación de que se han iniciado los servicios de Lync Server 2010

  - Revisión de la topología y los usuarios en Lync Server 2010.

  - Comprobar la configuración de la federación y del servidor perimetral.

  - Comprobar los servicios de XMPP y los socios federados.

**Comprobar que se han iniciado los servicios de Lync Server 2010**

1.  Desde el servidor front-end de Lync Server 2010, vaya al \\ subprograma Servicios de herramientas administrativas.

2.  Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:
    
    ![Lista de servicios que se ejecutan en el servidor front-end](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de servicios que se ejecutan en el servidor front-end")

**Revisar la topología de Lync Server 2010 en el panel de control de Lync Server**

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abra el Panel de control de Lync Server.

3.  Seleccione **Topología**. Compruebe que se muestran los diversos servidores de la implementación de Lync Server 2010.
    
    ![Página de topología del panel de control 2010 de Lync Server](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página de topología del panel de control 2010 de Lync Server")

**Para revisar los usuarios de Lync Server 2010 en el panel de control de Lync Server**

1.  Abra el Panel de control de Lync Server.

2.  Seleccione **Usuarios** y haga clic en **Buscar**.

3.  Compruebe que la columna **grupo de registrador** apunta al grupo de servidores de Lync Server 2010 para cada usuario enumerado.
    
    ![Panel de control de Lync Server 2010 enumerar usuarios](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panel de control de Lync Server 2010 enumerar usuarios")

**Para comprobar la configuración de la Federación y el servidor perimetral de Lync Server 2010**

1.  Inicie el Generador de topologías.

2.  Seleccione **Descargar una topología desde una implementación existente**.

3.  Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml predeterminado.

4.  Expanda el nodo 2010 de Lync Server para mostrar los distintos roles de servidor en la implementación.

5.  Seleccione el nodo del sitio y compruebe si se ha establecido un valor de **Asignación de ruta de federación del sitio**.
    
    ![Generador de topologías, ruta de Federación del sitio](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generador de topologías, ruta de Federación del sitio")

6.  A continuación, seleccione el grupo de servidores front-end de Standard Edition o Enterprise Edition. Determine si se ha configurado un grupo de servidores perimetrales para los medios bajo **Asociaciones**.
    
    ![Generador de topologías que muestra servidores y grupos de servidores](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generador de topologías que muestra servidores y grupos de servidores")

7.  Por último, seleccione el grupo de servidores perimetrales e identifique si un grupo de próximo salto se ha configurado bajo **Selección de próximo salto**.
    
    ![Generador de topologías, selección de próximo salto](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generador de topologías, selección de próximo salto")

**Compruebe la configuración del socio federado XMPP heredado**

1.  Desde el servidor de XMPP heredado, vaya al \\ subprograma Servicios de herramientas administrativas.

2.  Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.
    
    ![Servicio de puerta de enlace XMPP de Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP de Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

