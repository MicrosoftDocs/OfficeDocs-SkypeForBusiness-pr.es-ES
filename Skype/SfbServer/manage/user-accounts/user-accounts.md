---
title: Administrar cuentas de usuario de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype empresarial Server.
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009643"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Administrar cuentas de usuario de Skype empresarial Server

En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype empresarial Server.

Para obtener información sobre cómo habilitar un usuario de Active Directory, consulte [crear una nueva cuenta de usuario](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx). Para obtener información sobre cómo eliminar un usuario de Active Directory, consulte [eliminar una cuenta de usuario](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).

Estos procedimientos deben realizarse durante un período de mantenimiento, cuando el uso de Skype empresarial es el más bajo. Si se realiza una programación diaria o semanal, ésta será determinada por las necesidades de la organización.

Este artículo contiene los procedimientos siguientes:

- [Para buscar uno o más usuarios](user-accounts.md#Search)

- [Agregar y habilitar un nuevo usuario de Skype empresarial Server](user-accounts.md#Add)

- [Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype empresarial Server](user-accounts.md#Disable)

- [Deshabilitar a un usuario para la telefonía IP empresarial](user-accounts.md#Disable_EV)

- [Quitar una cuenta de usuario con el shell de administración de Skype empresarial Server](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Para buscar uno o más usuarios
<a name="Search"> </a>

Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.

Puede buscar usuarios mediante el panel de control de Skype empresarial Server o el complemento usuarios y equipos de Active Directory. El siguiente procedimiento describe cómo usar el panel de control de Skype empresarial Server para buscar usuarios.

> [!NOTE]
> En un entorno con una topología de bosque central, los resultados de la búsqueda podrían no ser precisos al buscar a un usuario por la dirección de correo electrónico del usuario. En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, sip:name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial, o usar el cmdlet **Get-CSUser**.

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee buscar y después haga clic en **Buscar**.

5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:

   a. Haga clic en la flecha para expandir de la esquina superior derecha de la pantalla que hay sobre **Resultados de la búsqueda** y después haga clic en **Agregar filtro**.

   b. Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.

   c. En la lista **Igual a**, haga clic en **Igual a** o **No igual a**.

   d. En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados y después haga clic en **Buscar**.

6. Los resultados de búsqueda aparecerán en el cuadro **Resultados de búsqueda**. Puede seleccionar uno, varios o todos los usuarios de la lista y realizar tareas de configuración en los usuarios seleccionados.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Agregar y habilitar un nuevo usuario de Skype empresarial Server
<a name="Add"> </a>

Después de habilitar una cuenta de usuario en usuarios y equipos de Active Directory, puede usar el panel de control de Skype empresarial Server para crear y habilitar nuevas cuentas de usuario de Skype empresarial Server mediante la adición de un usuario de Active Directory a Skype empresarial Server.

También puede usar un cmdlet, específicamente [enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. Haga clic en **Habilitar usuarios**.

5. En el cuadro de diálogo **Nuevo usuario de Lync Server**, haga clic en **Agregar**.

6. En el cuadro **Buscar usuarios**, escriba el nombre completo o parcial, el nombre para mostrar, el apellido, el nombre de la cuenta del Administrador de cuentas de seguridad, la dirección de correo electrónico, el nombre principal del usuario (UPN) o el número de teléfono del usuario de Active Directory que está buscando y después haga clic en **Buscar**.

7. En la tabla, seleccione la cuenta que desea agregar a Skype empresarial Server y, a continuación, haga clic en **Aceptar**.

8. Asigne el usuario a un grupo de servidores, especifique datos adicionales si lo considera necesario y asigne las directivas al usuario que desee; luego haga clic en **Habilitar**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype empresarial Server
<a name="Disable"> </a>

Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada previamente en Skype empresarial Server sin perder la configuración de Skype empresarial Server que ha configurado para la cuenta de usuario. Como no pierde la configuración de la cuenta de usuario de Skype empresarial Server, puede volver a habilitar una cuenta de usuario habilitada previamente sin tener que volver a configurar la cuenta de usuario.

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Usuarios **.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desee deshabilitar o volver a habilitar.

6. En el menú **acción** , realice una de las siguientes acciones:

   - Para deshabilitar temporalmente la cuenta de usuario de Skype empresarial Server, haga clic en **deshabilitar temporalmente para Lync Server**.

   - Para habilitar la cuenta de usuario de Skype empresarial Server, haga clic en **volver a habilitar para Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar Windows PowerShell para deshabilitar o volver a habilitar cuentas de usuario

Las cuentas de usuario se pueden deshabilitar temporalmente y, más adelante, volver a habilitarlas mediante el cmdlet **set-CsUser** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, vea el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.

### <a name="to-disable-a-user-account"></a>Para deshabilitar una cuenta de usuario

- Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en false ($False). Por ejemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Para volver a habilitar una cuenta de usuario

- Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en true ($True). Por ejemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .

## <a name="disable-a-user-for-enterprise-voice"></a>Deshabilitar a un usuario para la telefonía IP empresarial
<a name="Disable_EV"> </a>

Use el siguiente procedimiento para deshabilitar Enterprise Voice para una cuenta de usuario habilitada para Skype empresarial Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para deshabilitar una cuenta de usuario para telefonía IP empresarial

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desee habilitar para la telefonía IP empresarial.

6. En el menú **Editar **, haga clic en **Mostrar detalles **.

7. En la página **Editar usuario de Lync Server **, en **Telefonía **, haga clic en cualquier opción excepto **Telefonía IP empresarial **.

    > [!NOTE]
    > Para impedir que un usuario realice llamadas de audio o vídeo mediante Lync, en **telefonía**, haga clic en **audio y vídeo deshabilitado**.

8. Haga clic en **Confirmar**.

El usuario ahora no puede usar la característica Enterprise Voice. Información relacionada: <br/>[Telefonía IP empresarial y movilidad](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Habilitar a los usuarios para la telefonía IP empresarial en Skype empresarial Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de administración de Skype Empresarial Server](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Quitar una cuenta de usuario con el shell de administración de Skype empresarial Server
<a name="Remove"> </a>

Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada anteriormente en Skype empresarial Server.

> [!NOTE]
> Eliminar un usuario provocará que pierda los parámetros que haya configurado para la cuenta de usuario. Si desea deshabilitar temporalmente una cuenta de usuario en su lugar, vea [deshabilitar o volver a habilitar una cuenta de usuario previamente habilitada para Skype empresarial Server](user-accounts.md#Disable).

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Usuarios **.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desee quitar.

6. En el menú **Acción**, seleccione **Quitar de Lync Server** y, a continuación, aparecerá un cuadro de diálogo.

7. En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Quitar cuentas de usuario con cmdlets de Windows PowerShell

Puede eliminar cuentas de usuario con el cmdlet Disable-CsUser. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, vea el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.

### <a name="to-remove-a-user-account"></a>Para quitar una cuenta de usuario
Para quitar una cuenta de usuario, utilice el cmdlet Disable-CsUser. Por ejemplo:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Para obtener más información, consulte el tema de ayuda para el cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Vea también
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
