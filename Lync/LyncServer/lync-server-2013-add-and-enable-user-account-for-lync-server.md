---
title: Adición y habilitación de una cuenta de usuario de Lync Server
TOCTitle: Adición y habilitación de una cuenta de usuario de Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48274648
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Adición y habilitación de una cuenta de usuario de Lync Server

 

_**Última modificación del tema:** 2012-11-02_

Después de habilitar una cuenta de usuario en Equipos y usuarios de Active Directory, puede usar Panel de control de Lync Server para crear y habilitar nuevas cuentas de usuario de Lync Server 2013 agregando un usuario de Active Directory a Lync Server.

## Para agregar y habilitar un nuevo usuario de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Haga clic en **Habilitar usuarios**.

5.  En el cuadro de diálogo **Nuevo usuario de Lync Server**, haga clic en **Agregar**.

6.  En el cuadro **Buscar usuarios**, escriba el nombre completo o parcial, el nombre para mostrar, el apellido, el nombre de la cuenta del Administrador de cuentas de seguridad, la dirección de correo electrónico, el nombre principal del usuario (UPN) o el número de teléfono del usuario de Active Directory que está buscando y después haga clic en **Buscar**.

7.  En la tabla, seleccione la cuenta que desea agregar a Lync Server y después haga clic en **Aceptar**.

8.  Asigne el usuario a un grupo de servidores, especifique datos adicionales si lo considera necesario y asigne las directivas al usuario que desee; luego haga clic en **Habilitar**.

## Vea también

#### Tareas

[Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Quitar una cuenta de usuario de Lync Server](lync-server-2013-remove-a-user-account-from-lync-server.md)  

#### Otros recursos

[Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

