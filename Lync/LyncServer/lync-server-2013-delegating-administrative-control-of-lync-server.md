---
title: 'Lync Server 2013: Delegación del control administrativo de Microsoft Lync Server 2013'
TOCTitle: Delegación del control administrativo de Microsoft Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48274446
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Delegación del control administrativo de Microsoft Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

En Lync Server 2013, las tareas administrativas se delegan a los usuarios con la nueva característica control de acceso basado en roles (RBAC). Cuando se instala Lync Server, se crea un número de roles RBAC. Estos roles corresponden a los grupos de seguridad universales de Servicios de dominio de Active Directory. Por ejemplo, el rol RBAC CsHelpDesk corresponde al grupo CsHelpDesk que se encuentra en el contenedor Usuarios del Contenedor de dominios de Active Directory. Además, cada rol RBAC está asociado a un grupo de cmdlets de Lync ServerWindows PowerShell. Estos cmdlets representan las tareas que pueden llevar a cabo los usuarios que tienen asignado un rol RBAC determinado. Por ejemplo, el rol CsHelpDesk se ha asignado a los cmdlets Lock-CsClientPin y UnlockCsClientPin. Eso significa que los usuarios que tienen asignado el rol CsHelpDesk pueden bloquear y desbloquear números PIN de usuario. Sin embargo, el rol CsHelpDesk no está asignado al cmdlet New-CsVoicePolicy. Eso significa que los usuarios que tengan asignado el rol CsHelpDesk no podrán crear nuevas directivas de voz

## Visualización de información sobre roles RBAC

Puede recuperar información básica sobre sus roles RBAC si ejecuta el siguiente comando en el Shell de administración de Lync Server:

    Get-CsAdminRole

Recuerde que el valor Identity de un rol RBAC (por ejemplo, CsVoiceAdministrator) tiene una asignación directa a un grupo de seguridad del contenedor Usuario de los Servicios de dominio de Active Directory.

Para ver una lista de los cmdlets que se han asignado a un rol, use un comando similar al siguiente:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

## Asignar un rol RBAC a un usuario

Para asignar un rol RBAC a un usuario, es necesario agregar a dicho usuario al grupo de seguridad apropiado de Active Directory. Por ejemplo, para asignar el rol CsLocationAdministrator a un usuario, es necesario agregar a dicho usuario al grupo CsLocationAdministrator. Eso puede hacerse siguiendo el procedimiento siguiente:

**Asignar un usuario a un grupo de seguridad**

1.  Usar una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, iniciar sesión en un equipo en el que se haya instalado el complemento Usuarios y equipos de Active Directory.

2.  Haga clic en **Inicio**, en **Todos los programas**, en **Herramientas administrativas** y después en **Usuarios y equipos de Active Directory**.

3.  En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor **Usuarios**.

4.  Haga clic con el botón secundario en el grupo de seguridad **CsLocationAdministrator** y, a continuación, seleccione **Propiedades**.

5.  En el cuadro de diálogo **Propiedades**, en la pestaña **Miembros**, haga clic en **Agregar**.

6.  En el cuadro de diálogo **Seleccionar usuarios, equipos, contactos o grupos**, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo (por ejemplo, **Ken Myer** ) en el cuadro **Escribir los nombres de objeto para seleccionar** y después haga clic en **Aceptar**.

7.  En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.

Para verificar que el rol RBAC se ha asignado, use el cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAdminRoleAssignment) y envíe al cmdlet el SamAccountName (nombre de inicio de sesión de Active Directory) del usuario. Por ejemplo, ejecute este comando desde el Shell de administración de Lync Server:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

