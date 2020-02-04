---
title: Implementar el grupo de pruebas piloto de Lync Server 2013
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
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724050"
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

Uno de los primeros pasos necesarios para la migración a Lync Server 2013 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Office Communications Server 2007 R2. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y los grupos a Lync Server 2013.

Al implementar un grupo piloto, se usa el Asistente para definir el nuevo grupo frontal. Debe implementar las mismas características y cargas de trabajo en el grupo de pruebas piloto de Lync Server 2013 que tiene en su grupo de Office Communications Server 2007 R2. Si ha implementado el servidor de archivado, Monitoring Server o System Center Operations Manager para archivar o supervisar el entorno de Office Communications Server 2007 R2, y desea seguir archivando o supervisando toda la migración, necesita también puede implementar estas características en su entorno piloto. La versión que implementó para archivar o supervisar el entorno de Office Communications Server 2007 R2 no capturará datos en el entorno de Lync Server 2013.

<div>


> [!NOTE]  
> El procedimiento siguiente describe las características y la configuración que debe tener en cuenta como parte del proceso general de implementación del grupo piloto. Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto. Para conocer los pasos detallados, consulte la guía de implementación de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Para implementar un grupo de pruebas piloto de Lync Server 2013**

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Abra el generador de topologías y elija crear una nueva topología.

3.  Escriba el dominio SIP principal.
    
    ![Crear una nueva topología, definir la página de dominio principal](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Crear una nueva topología, definir la página de dominio principal")

4.  Siga completando el asistente hasta que llegue al Asistente para **definir el nuevo grupo front end** . Haga clic en Siguiente.

5.  Escriba el FQDN del grupo. Cuando define el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Lync Server 2013 no requiere que las características de su grupo piloto coincidan con lo que se ha implementado en su grupo heredado.
    
    <div>
    

    > [!WARNING]  
    > El nombre de dominio completo (FQDN) de grupo o servidor que defina para la agrupación piloto debe ser único. No puede coincidir con el nombre del grupo de Office Communications Server 2007 R2 implementado actualmente o de cualquier otro servidor implementado actualmente.

    
    </div>
    
    ![Definir la página FQDN del grupo de servidores front-end](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir la página FQDN del grupo de servidores front-end")

6.  Defina el equipo que se agregará al grupo.
    
    ![Cuadro de diálogo definir nuevo grupo front-end](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo front-end")

7.  En la página **seleccionar características** , seleccione las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si va a implementar solo la mensajería instantánea (mi) y las características de presencia, active la casilla conferencias para permitir la mensajería instantánea entre usuarios, pero no seleccione las casillas Conferencia de acceso telefónico local (RTC), telefonía IP empresarial o control de admisión de llamadas. porque representan características de conferencia de voz, vídeo y colaboración. Para obtener más información sobre cómo seleccionar las características, vea [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación de implementación.
    
    ![Página seleccionar características de la agrupación de front-end](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página seleccionar características de la agrupación de front-end")

8.  En la página **Seleccionar roles de servidor** de la aplicación, le recomendamos que Collocate el servidor de mediación en Lync Server 2013. Al combinar una topología heredada con Lync Server 2013, es necesario que primero Collocate el servidor de mediación de Office Communications Server 2007 R2. Después de combinar las topologías y configurar el servidor de mediación de Lync Server 2013, puede decidir si desea mantener el servidor de mediación o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Lync Server 2013 más adelante en la implementación. cuatricromía.
    
    ![Página del grupo de servidores front-end seleccionar roles de servidor en la página](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página del grupo de servidores front-end seleccionar roles de servidor en la página")

9.  En la página **asociar roles de servidor con este grupo de servidores front-end** , durante la implementación de un grupo piloto, no elija la opción **habilitar un grupo perimetral para que lo use el componente multimedia de este grupo de servidores front-end** . Esta es una característica que habilitará y se conectará en línea en una fase posterior de la migración. Mantener esta configuración desactivada por ahora.
    
    ![Página asociar roles de servidor con grupo de servidores front-end](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página asociar roles de servidor con grupo de servidores front-end")

10. En la página **seleccionar un servidor de Office Web Apps** , haga clic en **nuevo**y especifique el FQDN del servidor de aplicaciones.
    
    ![Definir nuevas propiedades de FQDN de Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir nuevas propiedades de FQDN de Office Web Apps Server")

11. En la página **definir el archivado del almacén SQL Server** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013.
    
    ![Definir el archivado de la página del almacén SQL Server](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Definir el archivado de la página del almacén SQL Server")

12. En la página **definir la supervisión del almacén SQL Server** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013. Haga clic en **Finalizar**.

13. Desde el nodo superior del generador de topología, haga clic con el botón derecho en **Lync Server** y haga clic en **Editar propiedades.** Haga clic en **direcciones URL simples**.

14. Actualice la **dirección URL de acceso administrativo**.
    
    ![Editar propiedades, página direcciones URL simples](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propiedades, página direcciones URL simples")
    
    Para obtener más información sobre las direcciones URL simples, vea el tema sobre cómo [modificar o configurar direcciones URL simples en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación de implementación.

15. En **Editar propiedades**, haga clic en **servidor de administración central**.

16. En la lista desplegable, seleccione el grupo de 2013 de Lync Server.
    
    ![Editar propiedades, página servidor de administración central](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Editar propiedades, página servidor de administración central")

17. Haga clic en Aceptar para cerrar **la página Editar propiedades** .

18. En el menú **acción** , seleccione **publicar topología**.

19. Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.

20. Volver al Asistente para la implementación de Lync Server 2013, haga clic en **instalar o actualizar el sistema de Lync Server**.
    
    ![Asistente para la implementación de Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Asistente para la implementación de Lync Server 2013")

Para instalar una copia local del almacén de configuración e iniciar los servicios necesarios, consulte [configuración de servidores front-end y grupos front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación de implementación.


</div>

<span> </span>

</div>

</div>

</div>

