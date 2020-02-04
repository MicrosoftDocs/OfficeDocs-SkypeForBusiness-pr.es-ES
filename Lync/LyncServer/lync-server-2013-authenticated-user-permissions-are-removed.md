---
title: 'Lync Server 2013: Se quitan los permisos de usuario autenticado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Se quitan los permisos de usuario autenticado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En un entorno de Active Directory bloqueado, las entradas de control de acceso (ACE) de usuarios autenticados se quitan de los contenedores predeterminados de Active Directory, incluidos los usuarios, la configuración o el sistema y las unidades organizativas en las que el usuario y el equipo se almacenan los objetos. Quitar las entradas de acceso de los usuarios autenticadas impide el acceso de lectura a la información de Active Directory. Sin embargo, al quitar las ACE se crean problemas para Lync Server 2013 porque depende de los permisos de lectura de estos contenedores para permitir que los usuarios ejecuten la preparación del dominio.

En esta situación, la pertenencia al grupo de administradores de dominio, que es necesaria para ejecutar la preparación del dominio, la activación del servidor y la creación de grupos, ya no concede acceso de lectura a la información de Active Directory almacenada en los contenedores predeterminados. Debe conceder manualmente permisos de acceso de lectura en varios contenedores del dominio raíz del bosque para comprobar que se ha completado el procedimiento de preparación del bosque con requisitos previos.

Para permitir que un usuario ejecute la preparación del dominio, la activación de servidor o la creación de grupos en cualquier dominio raíz que no sea de bosque, tiene las siguientes opciones:

  - Use una cuenta que sea miembro del grupo administradores de organización para ejecutar la preparación del dominio.

  - Use una cuenta que sea miembro del grupo administradores de dominio y otorgue a esta cuenta permisos de acceso de lectura en cada uno de los siguientes contenedores del dominio raíz del bosque:
    
      - Admin
    
      - Configuración o sistema

Si no desea usar una cuenta que sea miembro del grupo administradores de la organización para ejecutar la preparación del dominio u otras tareas de configuración, conceda explícitamente a la cuenta que desea usar acceso de lectura en los contenedores relevantes de la raíz del bosque.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>Para conceder a los usuarios permisos de acceso de lectura en los contenedores del dominio raíz del bosque

1.  Inicie sesión en el equipo unido al dominio raíz del bosque con una cuenta que sea miembro del grupo administradores de dominio para el dominio raíz del bosque.

2.  Ejecute ADSIEdit. msc para el dominio raíz del bosque.
    
    Si se quitaron las ACE de usuarios autenticados del contenedor del dominio, de la configuración o del sistema, debe conceder permisos de solo lectura para el contenedor, como se describe en los siguientes pasos.

3.  Haga clic con el botón secundario en el contenedor y después haga clic en **propiedades**.

4.  Haga clic en la pestaña **seguridad** .

5.  Haga clic en **Opciones avanzadas**.

6.  En la pestaña **permisos** , haga clic en **Agregar**.

7.  Escriba el nombre del usuario o grupo que recibe permisos con el siguiente formato: `domain\account name`y, a continuación, haga clic en **Aceptar**.

8.  En la pestaña **objetos** , en **se aplica a**, haga clic en **solo este objeto**.

9.  En **permisos**, seleccione la siguiente opción permitir entradas ACE haciendo clic en la columna **permitir** : **contenido**de la lista, **leer todas las propiedades**y **permisos de lectura**.

10. Haga clic en **Aceptar** dos veces.

11. Repita estos pasos para cualquiera de los contenedores relevantes enumerados en el paso 2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

