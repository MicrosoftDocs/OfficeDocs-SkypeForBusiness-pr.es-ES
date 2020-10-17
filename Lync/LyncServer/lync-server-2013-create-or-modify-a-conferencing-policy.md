---
title: 'Lync Server 2013: crear o modificar una directiva de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc01c8bed503f06806c873431ef201e03c31811
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516897"
---
# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a>Crear o modificar una directiva de conferencia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-07_

Siga estos pasos para crear una directiva de conferencia de nivel de usuario o de nivel de sitio. Para obtener más información sobre cómo asignar una directiva de nivel de usuario a un usuario, consulte [asignar una directiva de conferencia por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md). Para obtener una lista de todas las opciones de configuración de directivas de conferencia disponibles, consulte [referencia de configuración de directivas de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-create-a-new-user-or-site-policy"></a>Para crear una directiva de sitio o de usuario nueva

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de Conferencia**.

4.  Haga clic en **Nuevo** y luego siga uno de estos procedimientos:
    
      - Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Directiva de conferencia nueva**, en **Nombre**, escriba un nombre descriptivo para la directiva.
    
      - Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y después en **Aceptar**.
        
        <div>
        

        > [!NOTE]  
        > El nombre del sitio pasa a ser el nombre de la directiva de conferencia y no se puede cambiar.

        
        </div>

5.  En **Descripción**, escriba una descripción para la directiva.

6.  En **Directiva de organizadores**, en **Tamaño máximo de la reunión**, escriba el número máximo de usuarios que desea que participen en una reunión. De manera predeterminada, el tamaño máximo de la reunión se establece en 250.

7.  Para impedir que los usuarios inviten a usuarios anónimos a las reuniones, desactive la casilla **Permitir a los participantes invitar a usuarios anónimos**. Los usuarios anónimos son usuarios que no tienen credenciales en los servicios de dominio de Active Directory de la organización y que, por lo tanto, no están autenticados. Normalmente, los participantes pueden invitar a usuarios anónimos a las reuniones.

8.  En **Grabación**, lleve a cabo uno de los siguientes procedimientos:
    
      - Para impedir que los participantes graben reuniones, haga clic en **Ninguna**. Esta es la configuración predeterminada.
    
      - Para permitir que los participantes graben reuniones, haga clic en **Habilitar grabación**.

9.  Para permitir que los participantes externos graben reuniones, active la casilla **Permitir a los participantes federados y anónimos grabar**. Generalmente, los participantes externos no pueden grabar las reuniones.

10. En **Audio/vídeo**, lleve a cabo uno de los siguientes procedimientos:
    
      - Para impedir el uso de audio y vídeo, haga clic en **Ninguno**.
    
      - Para permitir el uso de audio pero no de vídeo, haga clic en **Habilitar audio IP**.
    
      - Para permitir el uso de audio y de vídeo, haga clic en **Habilitar audio y vídeo IP**. Esta es la configuración predeterminada.

11. Si opta por permitir el uso de audio en **Audio/vídeo**, realice uno de los procedimientos siguientes:
    
      - Para impedir que los usuarios participen en la reunión mediante acceso telefónico, desactive la casilla **Habilitar conferencia de acceso telefónico local RTC**. Normalmente, los usuarios pueden acceder telefónicamente a las reuniones a través de la red telefónica conmutada (RTC).
    
      - Si permite que los usuarios accedan telefónicamente a las reuniones y desea permitir que usuarios no autenticados (anónimos) se unan a una reunión con llamadas salientes, active la casilla **Permitir acceso telefónico a los participantes anónimos**. Con las llamadas salientes, el servidor de conferencia llama al usuario y este contesta el teléfono para participar en la reunión. Normalmente, los usuarios anónimos no pueden participar en una reunión con llamadas salientes.

12. Si opta por permitir el uso de vídeo en **Audio/vídeo**, active **Permitir varias secuencias de vídeo**.

13. En **Colaboración de datos**, lleve a cabo uno de los siguientes procedimientos:
    
      - Para impedir la colaboración de datos, haga clic en **Ninguna**.
    
      - Para permitir la colaboración de datos, haga clic en **Habilitar colaboración de datos**. Esta es la configuración predeterminada.

14. Si opta por permitir la colaboración de datos en **Colaboración de datos**, realice uno de los procedimientos siguientes:
    
      - Para impedir descargas externas, desactive la casilla **Permitir a los participantes federados y anónimos descargar contenido**. Normalmente, los usuarios externos pueden descargar contenido.
    
      - Para impedir la transferencia de archivos, desactive la casilla **Permitir a los participantes transferir archivos**. Normalmente, los usuarios pueden transferir archivos.
    
      - Para impedir el uso de anotaciones, desactive la casilla **Habilitar anotaciones**. Para usar anotaciones en las presentaciones de PowerPoint compartidas, desactive la casilla **Habilitar anotaciones de PowerPoint**. Normalmente, las anotaciones se permiten.
    
      - Para impedir el uso de sondeos, desactive la casilla **Habilitar sondeos**. Normalmente, se permiten los sondeos.

15. En **Uso compartido de aplicaciones**, lleve a cabo uno de los siguientes procedimientos:
    
      - Para impedir el uso compartido de aplicaciones, haga clic en **Deshabilitar el uso compartido de aplicaciones**.
    
      - Para permitir el uso compartido de aplicaciones, haga clic en **Habilitar el uso compartido de aplicaciones**. Esta es la configuración predeterminada.

16. Si opta por permitir el uso compartido de aplicaciones en **Compartit aplicaciones**, realice uno de los procedimientos siguientes:
    
      - Para impedir que los participantes en una reunión controlen el uso compartido de aplicaciones, desactive la casilla **Permitir a los participantes asumir el control**. Normalmente, los participantes pueden controlar el uso compartido de las aplicaciones.
    
      - Si opta por permitir que los participantes de las reuniones controlen el uso compartido de aplicaciones, seleccione la casilla **Permitir a los participantes federados y anónimos asumir el control** para permitir que los usuarios externos controlen el uso compartido de aplicaciones. Normalmente, los usuarios externos no pueden controlar el uso compartido de las aplicaciones.

17. En **Directiva de participantes**, siga uno de estos procedimientos:
    
      - Para impedir el uso compartido de las aplicaciones y del escritorio, haga clic en **Deshabilitar el uso compartido de aplicaciones y escritorio**.
    
      - Para permitir el uso compartido de las aplicaciones pero no el uso compartido del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones**.
    
      - Para permitir el uso compartido de las aplicaciones y del escritorio, haga clic en **Habilitar el uso compartido de aplicaciones y escritorio**. Esta es la configuración predeterminada.

18. Para impedir la transferencia de archivos punto a punto, desactive la casilla **Habilitar la transferencia de archivos punto a punto**. Normalmente, se permite la transferencia de archivos punto a punto.

19. Para permitir la grabación punto a punto, active la casilla **Habilitar grabación punto a punto**. Normalmente, no se permite la grabación punto a punto.

20. Para permitir que los participantes se unan con varias secuencias de vídeo, active la casilla **Permitir que los participantes se unan con varias secuencias de vídeo**. Normalmente, se permiten varias secuencias de vídeo.

21. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a>Para modificar una directiva de usuario o de sitio existente

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.

4.  En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.

5.  En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

