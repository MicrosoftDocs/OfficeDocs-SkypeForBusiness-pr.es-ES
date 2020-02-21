---
title: 'Lync Server 2013: probar la implementación del grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 552677dde2706265093879bc9b48ac803e1365fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Probar la implementación del grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-25_

El siguiente procedimiento describe cómo probar la implementación del grupo de servidores front-end.

<div>

## <a name="to-test-the-pool-deployment"></a>Para probar la implementación del grupo

1.  Use usuarios y equipos de Active Directory para agregar el objeto de usuario de Active Directory del rol de administrador para la implementación de Lync Server 2013 (en el que está instalado el panel de control de Lync Server 2013) al grupo **CSAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error al abrir el panel de control de Lync Server, lo que indica que "no autorizado: acceso denegado debido a un error de autorización de control de acceso basado en roles (RBAC)."

    
    </div>

2.  Si el objeto de usuario ha iniciado sesión, cierre sesión y, a continuación, vuelva a iniciar sesión para registrar la nueva asignación de grupo.
    
    <div>
    

    > [!NOTE]  
    > La cuenta de usuario no puede ser el administrador local de ningún servidor que ejecute Lync Server 2013.

    
    </div>

3.  Use la cuenta administrativa para iniciar sesión en el equipo en el que está instalado el panel de control de Lync Server.

4.  Inicie el panel de control de Lync Server y, si se le pide, proporcione las credenciales. El panel de control de Lync Server muestra la información de implementación.

5.  En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que una marca de verificación verde para el estado de replicación es junto a cada rol de servidor de Lync Server que se ha implementado y se ha puesto en línea.

6.  En la barra de navegación izquierda, haga clic en **Usuarios** y haga clic en **Habilitar usuarios**.

7.  En la página **Nuevo usuario de Lync Server**, haga clic en **Agregar**.

8.  Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory** seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez establecidas las opciones de búsqueda, haga clic en **Buscar**.

9.  En en el panel de resultados de la búsqueda, seleccione todos los objetos de esta sesión de búsqueda y haga clic en **Aceptar**.

10. En la página **Nuevo usuario de Lync Server** el objeto o los objetos seleccionados están en la pantalla **Usuarios**. En la lista **Asignar usuarios a un grupo**, seleccione el servidor en el que se deben hospedar los objetos.
    
    A continuación se presentan una serie de opciones para configurar los objetos.
    
      - **Generar el URI del SIP del usuario**
    
      - **Telefonía**
    
      - **URI de línea**
    
      - **Directiva de conferencia**
    
      - **Directiva de versión de clientes**
    
      - **Directiva de PIN**
    
      - **Directiva de acceso externo**
    
      - **Directiva de archivado**
    
      - **Directiva de ubicación**
    
      - **Directiva de cliente**
    
    Para probar la funcionalidad básica, seleccione la opción que prefiera para el parámetro **Generar el URI del SIP de usuario** (las otras opciones de la configuración usan los valores predeterminados) y haga clic en **Habilitar**.

11. En pantalla se muestra una página de resumen con una marca de verificación en la columna **Habilitado** para indicar que los objetos ya están listos para usarse. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.

12. Un usuario debe iniciar sesión en un equipo integrado en el dominio y otro usuario, en otro equipo del dominio.

13. Instale Lync 2013 en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios puedan iniciar sesión en Lync Server 2013 y que puedan enviar mensajes instantáneos entre sí.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

