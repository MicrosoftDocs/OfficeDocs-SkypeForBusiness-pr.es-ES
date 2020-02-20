---
title: 'Lync Server 2013: se quitan los permisos de usuario autenticados'
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
ms.openlocfilehash: 45080baa0839731808aefcc31c1551bfab5293db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Los permisos de usuarios autenticados se quitan en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En un entorno de Active Directory bloqueado, las entradas de control de acceso (ACE) de los usuarios autenticados se quitan de los contenedores de Active Directory predeterminados, incluidos el de usuarios, el de configuración y el de sistema, y de las unidades organizativas (OU) donde se almacenan los objetos de usuario y de equipo. Al eliminar las ACE de los usuarios autenticados se evita el acceso de lectura a la información de Active Directory. Sin embargo, la eliminación de las ACE crea problemas en Lync Server 2013 porque depende de los permisos de lectura de estos contenedores para permitir que los usuarios ejecuten la preparación del dominio.

En esta situación, la pertenencia al grupo Admins. del dominio, necesaria para ejecutar la preparación del dominio, la activación de los servidores y la creación de grupos de servidores, ya no concede acceso de lectura a la información de Active Directory almacenada en los contenedores predeterminados. Debe conceder manualmente permisos de acceso de lectura en diversos contenedores del dominio raíz del bosque para comprobar si se ha realizado correctamente el requisito previo de preparación del bosque.

Para permitir que los usuarios ejecuten la preparación del dominio, la activación de los servidores o la creación de grupos de servidores en cualquier dominio que no pertenezca a la raíz del bosque, dispone de las siguientes opciones:

  - Use una cuenta que sea miembro del grupo administradores de organización para ejecutar la preparación del dominio.

  - Usar una cuenta que sea miembro del grupo Admins. del dominio y conceder permisos de acceso de lectura a esta cuenta en cada uno de los contenedores siguientes del dominio raíz del bosque:
    
      - Dominio
    
      - Configuración o sistema

Si no desea usar una cuenta que sea miembro del grupo Administradores de organización para ejecutar la preparación del dominio o realizar otras tareas de configuración, conceda explícitamente a la cuenta que desea utilizar acceso de lectura en los contenedores pertinentes de la raíz del bosque.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>Para conceder a los usuarios permisos de acceso de lectura en los contenedores del dominio raíz del bosque

1.  Inicie sesión en el equipo que pertenece al dominio raíz del bosque con una cuenta que sea miembro del grupo Admins. del dominio raíz del bosque.

2.  Ejecute adsiedit.msc para el dominio raíz del bosque.
    
    Si se han quitado las ACE de los usuarios autenticados de los contenedores de dominio, configuración o sistema, debe conceder permisos de solo lectura al contenedor, tal y como se describe en los siguientes pasos.

3.  Haga clic con el botón secundario en el contenedor y, a continuación, haga clic en **Propiedades**.

4.  Haga clic en la pestaña **Seguridad**.

5.  Haga clic en **Avanzadas**.

6.  En la pestaña **Permisos**, haga clic en **Agregar**.

7.  Escriba el nombre del usuario o grupo que recibe permisos con el siguiente formato: `domain\account name`y, a continuación, haga clic en **Aceptar**.

8.  En la pestaña **Objetos**, en **Se aplica a**, haga clic en **Solo este objeto**.

9.  En **Permisos**, seleccione las siguientes ACE de permiso haciendo clic en la columna **Permitir**: **Mostrar contenido**, **Leer todas las propiedades** y **Permisos de lectura**.

10. Haga clic dos veces en **Aceptar**.

11. Repita estos pasos para cualquiera de los contenedores relevantes enumerados en el paso 2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

