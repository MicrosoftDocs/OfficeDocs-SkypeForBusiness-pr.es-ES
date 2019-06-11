---
title: 'Lync Server 2013: Probar la implementación del grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a1dc68b8dbe6285cdf4b7e9c21c873caaf730d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Probar la implementación del grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-25_

En el procedimiento siguiente se describe cómo probar la implementación del grupo de servidores front-end.

<div>

## <a name="to-test-the-pool-deployment"></a>Para probar la implementación de la agrupación

1.  Use equipos y usuarios de Active Directory para agregar el objeto de usuario de Active Directory de la función Administrador de la implementación de Lync Server 2013 (en la que está instalado el panel de control de Lync Server 2013) en el grupo **CSAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error al abrir el panel de control de Lync Server, que indica "no autorizado: acceso denegado debido a un error de autorización de control de acceso basado en roles (RBAC)."

    
    </div>

2.  Si actualmente el objeto de usuario ha iniciado sesión, cierre sesión y, luego, vuelva a iniciarla para registrar la nueva asignación de grupo.
    
    <div>
    

    > [!NOTE]  
    > La cuenta de usuario no puede ser el administrador local de ningún servidor que ejecute Lync Server 2013.

    
    </div>

3.  Use la cuenta administrativa para iniciar sesión en el equipo en el que está instalado el panel de control de Lync Server.

4.  Inicie el panel de control de Lync Server y, si se le solicita, proporcione las credenciales. El panel de control de Lync Server muestra información de implementación.

5.  En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que una marca de verificación verde para el estado de replicación está junto a cada rol de servidor de Lync Server que se ha implementado y se ha puesto en conexión.

6.  En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, haga clic en **Habilitar usuarios**.

7.  En la página **nuevo usuario de Lync Server** , haga clic en **Agregar**.

8.  Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory**, seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez que haya decidido las opciones de búsqueda, **Busque**vínculos de vínculos.

9.  En el panel Resultados de la búsqueda, seleccione todos los objetos de esta sesión de búsqueda y, a continuación, haga clic en **Aceptar**.

10. En la página **nuevo usuario de Lync Server** , el objeto o los objetos que haya seleccionado aparecerán en la pantalla **usuarios** . En la lista **asignar usuarios a un grupo** , seleccione el servidor en el que se deben alojar los objetos.
    
    A continuación se muestran varias opciones para configurar los objetos.
    
      - **Generar el URI de SIP del usuario**
    
      - **Telefonía**
    
      - **URI de línea**
    
      - **Directiva de conferencia**
    
      - **Directiva de versión de cliente**
    
      - **Directiva de PIN**
    
      - **Directiva de acceso externo**
    
      - **Directiva de archivado**
    
      - **Directiva de ubicación**
    
      - **Directiva de cliente**
    
    A fin de probar la funcionalidad básica, seleccione la opción que prefiera para la configuración de **URI de SIP del usuario** (las demás opciones de la configuración usarán la configuración predeterminada) y, a continuación, haga clic en **Habilitar**.

11. Se muestra una página de resumen que muestra una marca de verificación **** en la columna habilitada para indicar que los objetos ya están listos para su uso. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.

12. Iniciar sesión de un usuario en un equipo que se une al dominio y otro usuario en otro equipo del dominio.

13. Instale Lync 2013 en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios pueden iniciar sesión en Lync Server 2013 y pueden enviar mensajes instantáneos entre sí.

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

