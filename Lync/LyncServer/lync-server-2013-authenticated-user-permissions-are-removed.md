---
title: 'Lync Server 2013: Se quitan los permisos de usuario autenticado'
TOCTitle: Se quitan los permisos de usuario autenticado
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48275432
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Se quitan los permisos de usuario autenticado en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

En un entorno de Active Directory bloqueado, las entradas de control de acceso (ACE) de los usuarios autenticados se quitan de los contenedores de Active Directory predeterminados, incluidos el de usuarios, el de configuración y el de sistema, y de las unidades organizativas (OU) donde se almacenan los objetos de usuario y de equipo. Al eliminar las ACE de los usuarios autenticados se evita el acceso de lectura a la información de Active Directory. Al eliminar las ACE, sin embargo, se crean problemas para Lync Server 2013, porque depende de los permisos de lectura a estos contenedores para permitir que los usuarios ejecuten la preparación del dominio.

En esta situación, la pertenencia al grupo Admins. del dominio, necesaria para ejecutar la preparación del dominio, la activación de los servidores y la creación de grupos de servidores, ya no concede acceso de lectura a la información de Active Directory almacenada en los contenedores predeterminados. Debe conceder manualmente permisos de acceso de lectura en diversos contenedores del dominio raíz del bosque para comprobar si se ha realizado correctamente el requisito previo de preparación del bosque.

Para permitir que los usuarios ejecuten la preparación del dominio, la activación de los servidores o la creación de grupos de servidores en cualquier dominio que no pertenezca a la raíz del bosque, dispone de las siguientes opciones:

  - Use una cuenta que sea miembro del grupo Administradores de organización para ejecutar la preparación del dominio.

  - Usar una cuenta que sea miembro del grupo Admins. del dominio y conceder permisos de acceso de lectura a esta cuenta en cada uno de los contenedores siguientes del dominio raíz del bosque:
    
      - Dominio
    
      - Configuración o sistema

Si no desea usar una cuenta que sea miembro del grupo Administradores de organización para ejecutar la preparación del dominio o realizar otras tareas de configuración, conceda explícitamente a la cuenta que desea utilizar acceso de lectura en los contenedores pertinentes de la raíz del bosque.

## Para conceder a los usuarios permisos de acceso de lectura en los contenedores del dominio raíz del bosque

1.  Inicie sesión en el equipo que pertenece al dominio raíz del bosque con una cuenta que sea miembro del grupo Admins. del dominio raíz del bosque.

2.  Ejecute adsiedit.msc para el dominio raíz del bosque.
    
    Si se han quitado las ACE de los usuarios autenticados de los contenedores de dominio, configuración o sistema, debe conceder permisos de solo lectura al contenedor, tal y como se describe en los siguientes pasos.

3.  Haga clic con el botón secundario en el contenedor y, a continuación, haga clic en **Propiedades**.

4.  Haga clic en la pestaña **Seguridad**.

5.  Haga clic en **Avanzadas**.

6.  En la pestaña **Permisos**, haga clic en **Agregar**.

7.  Escriba el nombre del usuario o del grupo que recibe permisos usando el siguiente formato: `domain\account name` y, a continuación, haga clic en **Aceptar**.

8.  En la pestaña **Objetos** , en **Se aplica a**, haga clic en **Solo este objeto**.

9.  En **Permisos**, seleccione las siguientes ACE de permiso haciendo clic en la columna **Permitir**: **Mostrar contenido**, **Leer todas las propiedades** y **Permisos de lectura**.

10. Haga clic dos veces en **Aceptar**.

11. Repita estos pasos para cualquiera de los contenedores relevantes enumerados en el paso 2.

