---
title: Implementar el grupo de pruebas piloto de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Implementar el grupo de pruebas piloto de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-22_

Uno de los primeros pasos necesarios para la migración a Lync Server 2013 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Lync Server 2010. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y los grupos a Lync Server 2013.

Al implementar un grupo piloto, se usa el Asistente para definir el nuevo grupo frontal. Debe implementar las mismas características y cargas de trabajo en el grupo de pruebas piloto de Lync Server 2013 que tiene en su grupo de Lync Server 2010. Si ha implementado el servidor de archivado, Monitoring Server o System Center Operations Manager para archivar o supervisar el entorno de Lync Server 2010, y desea seguir archivando o supervisando toda la migración, también debe implementar estos características del entorno de la prueba piloto. La versión que implementó para archivar o supervisar el entorno de Lync Server 2010 no capturará datos en el entorno de Lync Server 2013.

<div>


> [!NOTE]  
> El procedimiento siguiente describe las características y la configuración que debe tener en cuenta como parte del proceso general de implementación del grupo piloto. Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto. Para conocer los pasos detallados, consulte la guía de implementación de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Para implementar un grupo de pruebas piloto de Lync Server 2013**

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Expanda el árbol hasta llegar a los **grupos de servidores front-end**de **Lync Server 2013** Enterprise Edition.

3.  Haga clic con el botón secundario en **grupos front-end Enterprise Edition**y seleccione **nuevo grupo de servidores front-end**.
    
    ![Submenú selección del grupo de servidores del generador] de topologías (images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenú selección del grupo de servidores del generador") de topologías

4.  Escriba el FQDN del grupo. Cuando define el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Lync Server 2013 no requiere que las características de su grupo piloto coincidan con lo que se ha implementado en su grupo heredado.
    
    <div>
    

    > [!WARNING]  
    > El nombre de dominio completo (FQDN) de grupo o servidor que defina para la agrupación piloto debe ser único. No puede coincidir con el nombre del grupo de servidores de Lync Server 2010 actualmente implementado o cualquier otro servidor implementado actualmente.

    
    </div>
    
    ![Página FQDN del Asistente para definir un nuevo grupo front end] (images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Página FQDN del Asistente para definir un nuevo grupo front end")

5.  En la página **seleccionar características** , seleccione las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si va a implementar solo la mensajería instantánea (mi) y las características de presencia, active la casilla conferencias para permitir la mensajería instantánea entre usuarios, pero no seleccione las casillas Conferencia de acceso telefónico local (RTC), telefonía IP empresarial o control de admisión de llamadas. porque representan características de conferencia de voz, vídeo y colaboración. Para obtener más información sobre cómo seleccionar las características, vea [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación de implementación.
    
    ![Página seleccionar características de la agrupación de front-end] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página seleccionar características de la agrupación de front-end")

6.  En la página **Seleccionar roles de servidor** de la aplicación, le recomendamos que Collocate el servidor de mediación en Lync Server 2013. Al combinar una topología heredada con Lync Server 2013, es necesario que primero Collocate el servidor de mediación de Lync Server 2010. Después de combinar las topologías y configurar el servidor de mediación de Lync Server 2013, puede decidir si desea mantener el servidor de mediación o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Lync Server 2013 más adelante en la implementación. cuatricromía.
    
    ![Página del grupo de servidores front-end seleccionar roles de servidor en la página] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página del grupo de servidores front-end seleccionar roles de servidor en la página")

7.  En la página **asociar roles de servidor con este grupo de servidores front-end** , durante la implementación de un grupo piloto, no elija la opción **habilitar un grupo perimetral para que lo use el componente multimedia de este grupo de servidores front-end** . Esta es una característica que habilitará y se conectará en línea en una fase posterior de la migración. Mantener esta configuración desactivada por ahora.
    
    ![Página asociar roles de servidor con grupo de servidores front-end] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página asociar roles de servidor con grupo de servidores front-end")

8.  En la página **seleccionar un servidor de Office Web Apps** , haga clic en **nuevo**y especifique el FQDN del servidor de aplicaciones.
    
    ![Definir nuevas propiedades de FQDN de Office Web Apps Server] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir nuevas propiedades de FQDN de Office Web Apps Server")

9.  En la página **definir el archivado del almacén SQL Server** , al definir el almacén de SQL Server para el archivado y la supervisión de Lync Server, seleccione la instancia de SQL Server creada anteriormente para Lync Server 2013.
    
    Definir el archivado de la ![página del almacén SQL Server] Definir el archivado de la (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "página del almacén SQL Server")

10. Para publicar su topología, haga clic con el botón secundario en el nodo de **Lync Server** y, a continuación, haga clic en **publicar topología**.
    
    ![Generador de topología que muestra una topología] configurada (images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Generador de topología que muestra una topología") configurada

11. Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.

Para instalar una copia local del almacén de configuración e iniciar los servicios necesarios, consulte [configuración de servidores front-end y grupos front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación de implementación.


</div>

<span> </span>

</div>

</div>

</div>

