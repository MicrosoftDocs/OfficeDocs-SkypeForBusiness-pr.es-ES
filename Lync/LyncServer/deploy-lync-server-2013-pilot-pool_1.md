---
title: Implementar el grupo piloto de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8c2f5ed78bb228c4e650da983a1c82456c47b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Implementar el grupo piloto de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-22_

Uno de los primeros pasos necesarios para la migración a Lync Server 2013 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Office Communications Server 2007 R2. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y grupos a Lync Server 2013.

Cuando se implementa un grupo piloto, se utiliza el Asistente para definir nuevo grupo de servidores front-end. Debe implementar las mismas características y cargas de trabajo en el grupo piloto de Lync Server 2013 que tiene en su grupo de servidores de Office Communications Server 2007 R2. Si ha implementado el servidor de archivado, el servidor de supervisión o System Center Operations Manager para archivar o supervisar el entorno de Office Communications Server 2007 R2, y desea continuar el archivado o la supervisión durante la migración, debe Implemente también estas características en el entorno piloto. La versión que ha implementado para archivar o supervisar el entorno de Office Communications Server 2007 R2 no capturará datos en su entorno de Lync Server 2013.

<div>


> [!NOTE]  
> El siguiente procedimiento trata las funciones y configuración que se deben tener en cuenta como parte del proceso de implementación del grupo piloto. Esta sección solo subraya puntos clave que se deberían tener en cuenta como parte de la implementación de grupo piloto. Para conocer los pasos detallados, consulte la guía de implementación de la implementación de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Para implementar un grupo piloto de Lync Server 2013**

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Abra el Generador de topologías y elija para crear una nueva topología.

3.  Especifique el dominio SIP principal.
    
    ![Crear una nueva topología, definir la página del dominio principal](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Crear una nueva topología, definir la página del dominio principal")

4.  Continúe completando el asistente hasta llegar al asistente **Definir el nuevo grupo de servidores front-end**. Haga clic en Siguiente.

5.  Especifique el FQDN de grupo de servidores. Al definir el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Lync Server 2013 no requiere que las características del grupo piloto coinciden con lo que se implementó en el grupo heredado.
    
    <div>
    

    > [!WARNING]  
    > El nombre de dominio completo (FQDN) del grupo o del servidor que defina para el grupo de servidores piloto debe ser único. No puede coincidir con el nombre del grupo de Office Communications Server 2007 R2 actualmente implementado o con cualquier otro servidor implementado actualmente.

    
    </div>
    
    ![Definir la página de FQDN del grupo de servidores front-end](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir la página de FQDN del grupo de servidores front-end")

6.  Defina el equipo que se agregará al grupo de servidores.
    
    ![Cuadro de diálogo definir nuevo grupo de servidores front-end](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de servidores front-end")

7.  En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si está implementado solo características de mensajería instantánea y presencia, deberá activar la casilla Conferencia para permitir la mensajería instantánea para varios participantes, pero no deberá activar las casillas Conferencia de acceso telefónico local (RTC), Enterprise Voice ni Sistema de control de admisión de llamadas, ya que representan características de conferencias de voz, vídeo y colaboración. Para obtener más información sobre cómo seleccionar características, consulte [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación sobre implementación.
    
    ![Página de selección de características del grupo de servidores front-end](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de selección de características del grupo de servidores front-end")

8.  En la página **Seleccionar roles de servidor combinados** , le recomendamos que combinar el servidor de mediación en Lync Server 2013. Al combinar una topología heredada con Lync Server 2013, es necesario que primero combinar el servidor de mediación de Office Communications Server 2007 R2. Después de combinar las topologías y configurar el servidor de mediación de Lync Server 2013, puede decidir si desea mantener el servidor de mediación combinado o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Lync Server 2013 más adelante en la implementación. proceso.
    
    ![Página de selección de roles de servidor combinados del grupo de servidores front-end](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página de selección de roles de servidor combinados del grupo de servidores front-end")

9.  En la página **Asociar roles de servidor a este grupo de servidores front-end**, durante la implementación de un grupo piloto, no seleccione la opción **Habilitar el uso de un servidor perimetral por parte del componente multimedia de este grupo front-end**. Esta característica se habilitará y se pondrá en línea en una fase posterior de la migración. No seleccione esta opción por el momento.
    
    ![Página asociar roles de servidor con grupo de servidores front-end](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página asociar roles de servidor con grupo de servidores front-end")

10. En la página **Seleccionar un servidor de aplicaciones web para Office**, haga clic en **Nuevo** y especifique el FQDN del servidor de aplicaciones.
    
    ![Definir nuevas propiedades de FQDN de Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir nuevas propiedades de FQDN de Office Web Apps Server")

11. En la página **definir el almacén de SQL Server de archivado** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013.
    
    ![Definir la página de archivado del almacén de SQL Server](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Definir la página de archivado del almacén de SQL Server")

12. En la página **definir el almacén de SQL Server de supervisión** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013. Haga clic en **Finalizar**.

13. Desde el nodo principal del Generador de topologías, haga clic con el botón secundario en **Lync Server** y haga clic en **Editar propiedades.** Haga clic en **Direcciones URL simples**.

14. Actualice la **Dirección URL de acceso administrativo**.
    
    ![Editar propiedades, página de direcciones URL sencillas](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propiedades, página de direcciones URL sencillas")
    
    Para obtener más información acerca de las direcciones URL sencillas, consulte el tema [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación sobre implementación.

15. En **Editar propiedades**, haga clic en **Servidor de administración central**.

16. En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.
    
    ![Editar propiedades, página servidor de administración central](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Editar propiedades, página servidor de administración central")

17. Haga clic en Aceptar para cerrar la página **Editar propiedades**.

18. En el menú **Acción**, seleccione **Publicar topología**.

19. Una vez completado el proceso de publicación, haga clic en  **Finalizar **.

20. Volver al Asistente para la implementación de Lync Server 2013, haga clic en **instalar o actualizar el sistema Lync Server**.
    
    ![Asistente para la implementación de Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Asistente para la implementación de Lync Server 2013")

Para instalar una copia local del almacén de configuración e iniciar los servicios necesarios, consulte [setting up front end Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación sobre implementación.


</div>

<span> </span>

</div>

</div>

</div>

