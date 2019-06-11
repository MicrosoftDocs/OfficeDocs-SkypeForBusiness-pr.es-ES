---
title: Comprobar el entorno de Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Comprobar el entorno de Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Antes de implementar Lync Server 2013 en un estado de coexistencia con Lync Server 2010, debe comprobar que los servicios de Lync Server 2010 se han configurado e iniciado. Es importante identificar los servicios clave y las características que existen en el entorno heredado antes de implementar un grupo de pruebas piloto de Lync Server 2013. Antes de implementar Microsoft Lync Server 2013 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar qué socio federado son compatibles con la configuración del XMPP heredado. Comprobar la implementación heredada de Lync Server 2010 conlleva lo siguiente:

  - Comprobar que los servicios de Lync Server 2010 se han iniciado

  - Revisar la topología y los usuarios en Lync Server 2010.

  - Comprobar la configuración del servidor perimetral y la Federación.

  - Verificación de los servicios XMPP y los socios federados.

**Comprobar que los servicios de Lync Server 2010 se han iniciado**

1.  En el servidor front-end de Lync Server 2010, vaya al subprograma Servicios de herramientas\\administrativas.

2.  Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:
    
    ![Lista de servicios que se ejecutan en el servidor front-end] (images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de servicios que se ejecutan en el servidor front-end")

**Revisar la topología de Lync Server 2010 en el panel de control de Lync Server**

1.  Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.

2.  Abra el panel de control de Lync Server.

3.  Seleccione **topología**. Compruebe que se muestran los diversos servidores de su implementación de Lync Server 2010.
    
    ![Página de topología del panel de Control 2010 de Lync Server] (images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página de topología del panel de Control 2010 de Lync Server")

**Para revisar los usuarios de Lync Server 2010 en el panel de control de Lync Server**

1.  Abra el panel de control de Lync Server.

2.  Seleccione **usuarios** y, a continuación, haga clic en **Buscar**.

3.  Compruebe que la columna **registrar grupo** apunta al grupo de servidores de Lync 2010 para cada usuario de la lista.
    
    ![Panel de control de 2010 de Lync Server] (images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panel de control de 2010 de Lync Server")

**Para comprobar la configuración de Edge y de Federación de Lync Server 2010**

1.  Iniciar el generador de topología.

2.  Seleccione **Descargar topología de la implementación existente**.

3.  Elija un nombre de archivo y guarde la topología con el tipo de archivo default. tbxml.

4.  Expanda el nodo de 2010 de Lync Server para mostrar los distintos roles de servidor en la implementación.

5.  Seleccione el nodo de sitio y compruebe si se ha establecido un valor de **asignación de enrutamiento de Federación de sitios** .
    
    ![Generador de topologías, ruta de Federación de sitios] (images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generador de topologías, ruta de Federación de sitios")

6.  A continuación, seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Determine si un grupo de medios se ha configurado para los medios por debajo de las **asociaciones**.
    
    ![Generador de topología que muestra servidores y pools] (images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generador de topología que muestra servidores y pools")

7.  Por último, seleccione el grupo de bordes y identifique si un grupo de saltos siguiente está configurado por debajo de la **selección de próximos saltos**.
    
    ![Generador de topologías, selección del próximo salto] (images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generador de topologías, selección del próximo salto")

**Comprobar la configuración heredada del socio XMPP federado**

1.  Desde el servidor XMPP heredado, vaya al subprograma\\servicios de herramientas administrativas.

2.  Compruebe que se ha iniciado el servicio de puerta de enlace XMPP de Office Communications Server.
    
    ![Servicio de puerta de enlace XMPP de Office Communications Server] (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP de Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

