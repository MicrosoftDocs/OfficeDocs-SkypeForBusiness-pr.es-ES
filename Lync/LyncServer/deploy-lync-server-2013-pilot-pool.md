---
title: Implementar el grupo piloto de Lync Server 2013
description: Implementar el grupo piloto de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550796"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a>Implementar el grupo piloto de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-22_

Uno de los primeros pasos necesarios para la migración a Lync Server 2013 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con su implementación de Lync Server 2010. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y grupos a Lync Server 2013.

Cuando se implementa un grupo piloto, se utiliza el Asistente para definir nuevo grupo de servidores front-end. Debe implementar las mismas características y cargas de trabajo en el grupo piloto de Lync Server 2013 que tiene en su grupo de servidores de Lync Server 2010. Si ha implementado el servidor de archivado, el servidor de supervisión o System Center Operations Manager para archivar o supervisar el entorno de Lync Server 2010, y desea continuar el archivado o la supervisión durante la migración, también debe implementar estas características en el entorno piloto. La versión que ha implementado para archivar o supervisar el entorno de Lync Server 2010 no capturará datos en su entorno de Lync Server 2013.

<div>


> [!NOTE]  
> El siguiente procedimiento trata las funciones y configuración que se deben tener en cuenta como parte del proceso de implementación del grupo piloto. Esta sección solo subraya puntos clave que se deberían tener en cuenta como parte de la implementación de grupo piloto. Para conocer los pasos detallados, consulte la guía de implementación de la implementación de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Para implementar un grupo piloto de Lync Server 2013**

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Expanda el árbol hasta llegar a los **grupos de servidores front-end**de **Lync Server 2013** Enterprise Edition.

3.  Haga clic con el botón secundario en **grupos de servidores front-end Enterprise Edition**y seleccione **nuevo grupo de servidores front-end**.
    
    ![Submenú selección de grupo de servidores del generador de topologías](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenú selección de grupo de servidores del generador de topologías")

4.  Especifique el FQDN de grupo de servidores. Al definir el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Lync Server 2013 no requiere que las características del grupo piloto coinciden con lo que se implementó en el grupo heredado.
    
    <div>
    

    > [!WARNING]  
    > El nombre de dominio completo (FQDN) del grupo o del servidor que defina para el grupo de servidores piloto debe ser único. No puede coincidir con el nombre del grupo de Lync Server 2010 actualmente implementado o cualquier otro servidor que esté implementado actualmente.

    
    </div>
    
    ![Página del Asistente para definir nuevo grupo de servidores front-end](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Página del Asistente para definir nuevo grupo de servidores front-end")

5.  En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si está implementado solo características de mensajería instantánea y presencia, deberá activar la casilla Conferencia para permitir la mensajería instantánea para varios participantes, pero no deberá activar las casillas Conferencia de acceso telefónico local (RTC), Enterprise Voice ni Sistema de control de admisión de llamadas, ya que representan características de conferencias de voz, vídeo y colaboración. Para obtener más información sobre cómo seleccionar características, consulte [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación sobre implementación.
    
    ![Página de selección de características del grupo de servidores front-end](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de selección de características del grupo de servidores front-end")

6.  En la página **Seleccionar roles de servidor combinados** , le recomendamos que combinar el servidor de mediación en Lync Server 2013. Al combinar una topología heredada con Lync Server 2013, es necesario que primero combinar el servidor de mediación de Lync Server 2010. Después de combinar las topologías y configurar el servidor de mediación de Lync Server 2013, puede decidir si desea mantener el servidor de mediación combinado o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Lync Server 2013 más adelante en el proceso de implementación.
    
    ![Página de selección de roles de servidor combinados del grupo de servidores front-end](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página de selección de roles de servidor combinados del grupo de servidores front-end")

7.  En la página **Asociar roles de servidor a este grupo de servidores front-end**, durante la implementación de un grupo piloto, no seleccione la opción **Habilitar el uso de un servidor perimetral por parte del componente multimedia de este grupo front-end**. Esta característica se habilitará y se pondrá en línea en una fase posterior de la migración. No seleccione esta opción por el momento.
    
    ![Página asociar roles de servidor con grupo de servidores front-end](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página asociar roles de servidor con grupo de servidores front-end")

8.  En la página **Seleccionar un servidor de aplicaciones web para Office**, haga clic en **Nuevo** y especifique el FQDN del servidor de aplicaciones.
    
    ![Definir nuevas propiedades de FQDN de Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir nuevas propiedades de FQDN de Office Web Apps Server")

9.  En la página **definir el almacén de SQL Server de archivado** , al definir el almacén de SQL Server para el archivado y la supervisión de Lync Server, seleccione la instancia de SQL Server creada anteriormente para lync Server 2013.
    
    ![Definir la página de archivado del almacén de SQL Server](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Definir la página de archivado del almacén de SQL Server")

10. Para publicar la topología, haga clic con el botón secundario en el nodo **Lync Server** y, a continuación, haga clic en **publicar topología**.
    
    ![Generador de topologías que muestra una topología configurada](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Generador de topologías que muestra una topología configurada")

11. Una vez completado el proceso de publicación, haga clic en **Finalizar**.

Para instalar una copia local del almacén de configuración e iniciar los servicios necesarios, consulte [setting up front end Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación sobre implementación.


</div>

<span> </span>

</div>

</div>

</div>

