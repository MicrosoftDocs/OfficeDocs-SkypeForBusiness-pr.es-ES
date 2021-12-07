---
title: Administrar cuentas de usuario para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype Empresarial Server.
ms.openlocfilehash: 39016a83c11553cd39448efa34d61ffbba5045e9
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314218"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Administrar cuentas de usuario para Skype Empresarial Server

En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype Empresarial Server.

Para obtener información sobre cómo habilitar un usuario de Active Directory, vea [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)). Para obtener información sobre cómo eliminar un usuario de Active Directory, vea [Eliminar una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).

Estos procedimientos deben realizarse durante una ventana de mantenimiento, cuando Skype Empresarial menor uso. Si esto se realiza en una programación diaria o semanal, se determinará según las necesidades de su organización.

Este artículo contiene los siguientes procedimientos:

- [Buscar uno o más usuarios](#search-for-one-or-more-users)

- [Agregar y habilitar un nuevo Skype Empresarial Server usuario](#add-and-enable-a-new-skype-for-business-server-user)

- [Deshabilitar o volver a habilitar una cuenta de usuario para Skype Empresarial Server](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [Deshabilitar un usuario para Telefonía IP empresarial](#disable-a-user-for-enterprise-voice)

- [Quitar una cuenta de usuario con el Shell Skype Empresarial Server administración](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>Buscar uno o más usuarios

Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype Empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.

Puede buscar usuarios mediante el panel de control Skype Empresarial Server o el complemento Usuarios y equipos de Active Directory. En el siguiente procedimiento se describe cómo usar Skype Empresarial Server Panel de control para buscar usuarios.

> [!NOTE]
> En un entorno con una topología de bosque central, es posible que los resultados de la búsqueda no sean precisos al buscar un usuario por la dirección de correo electrónico del usuario. En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, sip:name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial, o usar el cmdlet **Get-CSUser**.

### <a name="search-for-users-using-the-new-control-panel"></a>Buscar usuarios con el nuevo Panel de control 

1. Abra una ventana del explorador y escriba la dirección URL de administración para abrir el panel Skype Empresarial Server control.
 
2. Inicie sesión con una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator.

3. En el panel izquierdo, seleccione **Usuarios**.

4. En la **página Usuarios,** en **el** cuadro Buscar, escriba todo o la primera parte del nombre para mostrar que desea buscar y presione **Entrar**.

5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:

    1. Haga clic en el botón de filtro situado junto al **cuadro** Buscar.

    2. En el panel **Filtro** que aparece, seleccione la propiedad de usuario necesaria haciendo clic en la flecha de la lista desplegable.

    3. Haga clic en la flecha de la lista desplegable de operadores para seleccionar el operador necesario.

    4. En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados de búsqueda y, a continuación, haga clic en **Aceptar**.

6. Los resultados de la búsqueda aparecen en la **página** Usuarios. Puede seleccionar uno, varios o todos los usuarios de la lista y realizar tareas de configuración en los usuarios seleccionados.

> [!NOTE]
> El nuevo Panel de control no está disponible para Skype Empresarial Server 2015.

### <a name="search-for-users-using-the-legacy-control-panel"></a>Buscar usuarios con el Panel de control heredado 

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. En el panel izquierdo, seleccione **Usuarios**.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee buscar y después haga clic en **Buscar**.

5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:

    1. Haga clic en la flecha para expandir de la esquina superior derecha de la pantalla que hay sobre **Resultados de la búsqueda** y después haga clic en **Agregar filtro**.

    2. Escriba la propiedad de usuario escribiendo o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.

    3. En la **lista Igual a,** **seleccione Igual a** o No igual **a**.

    4. En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados y después haga clic en **Buscar**.

6. Los resultados de búsqueda aparecerán en el cuadro **Resultados de búsqueda**. Puede seleccionar uno, varios o todos los usuarios de la lista y realizar tareas de configuración en los usuarios seleccionados.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Agregar y habilitar un nuevo Skype Empresarial Server usuario

Después de habilitar una cuenta de usuario en Usuarios y equipos de Active Directory, puede usar el Panel de control de Skype Empresarial Server para crear y habilitar nuevas cuentas de usuario de Skype Empresarial Server agregando un usuario de Active Directory Skype Empresarial Server.

También puede usar un cmdlet, específicamente [Enable-CsUser](/powershell/module/skype/enable-csuser).

### <a name="add-a-user-using-the-new-control-panel"></a>Agregar un usuario mediante el nuevo Panel de control 

1. Abra una ventana del explorador y escriba la dirección URL de administración para abrir el panel Skype Empresarial Server control.
 
2. Inicie sesión con una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator.

3. Vaya a **Usuarios**  >  **Habilitar usuarios** y haga clic en **Agregar**.

4. En el **cuadro Buscar,** escriba todo o la primera parte del nombre para mostrar y haga clic en **Buscar**.

5. (Opcional) Para especificar criterios de usuario adicionales, haga clic **en + Agregar** filtro , seleccione la propiedad de usuario necesaria, seleccione el operador y escriba el valor. Haga clic en **Buscar**.

6. En la tabla, seleccione la cuenta que desea agregar a Skype Empresarial Server y, a continuación, haga clic en **Aceptar**.

7. Asigne al usuario a un grupo de servidores, especifique los detalles adicionales y asigne las directivas necesarias al usuario y, a continuación, haga clic en **Habilitar**.

> [!NOTE]
> El nuevo Panel de control no está disponible para Skype Empresarial Server 2015.

### <a name="add-a-user-using-the-legacy-control-panel"></a>Agregar un usuario mediante el Panel de control heredado 

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. Vaya a **Usuarios**  >  **Habilitar usuarios** Nuevo usuario de Lync  >  **Server** y haga clic en **Agregar.**

6. En el cuadro **Buscar usuarios**, escriba el nombre completo o parcial, el nombre para mostrar, el apellido, el nombre de la cuenta del Administrador de cuentas de seguridad, la dirección de correo electrónico, el nombre principal del usuario (UPN) o el número de teléfono del usuario de Active Directory que está buscando y después haga clic en **Buscar**.

7. En la tabla, seleccione la cuenta que desea agregar a Skype Empresarial Server y, a continuación, haga clic en **Aceptar**.

8. Asigne el usuario a un grupo de servidores, especifique datos adicionales si lo considera necesario y asigne las directivas al usuario que desee; luego haga clic en **Habilitar**.

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>Deshabilitar o volver a habilitar una cuenta de usuario para Skype Empresarial Server

Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada anteriormente en Skype Empresarial Server sin perder la configuración de Skype Empresarial Server configuración que configuró para la cuenta de usuario. Dado que no pierde la configuración Skype Empresarial Server cuenta de usuario, puede volver a habilitar una cuenta de usuario habilitada anteriormente sin tener que volver a configurar la cuenta de usuario.

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>Deshabilitar o volver a habilitar una cuenta de usuario con el nuevo Panel de control

1. Abra una ventana del explorador y escriba la dirección URL de administración para abrir el panel Skype Empresarial Server control.
 
2. Inicie sesión con una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator.

3. En el panel izquierdo, seleccione **Usuarios**.

4. En la **página Usuarios,** en el **cuadro Buscar,** escriba todo o la primera parte del nombre para mostrar y presione **Entrar**.

5. En la tabla, haga doble clic en la cuenta de usuario que desea deshabilitar o volver a habilitar.
    1. En el panel que aparece, para deshabilitar temporalmente la cuenta de usuario para Skype Empresarial Server, seleccione **Deshabilitar usuario**. En el panel que aparece, haga clic **en Guardar**.
    2. Para volver a habilitar la cuenta de usuario para Skype Empresarial Server, en el panel, seleccione **Volver a habilitar usuario**. En el siguiente panel que aparece, haga clic en **Guardar**.

> [!NOTE]
> El nuevo Panel de control no está disponible para Skype Empresarial Server 2015.

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>Deshabilitar o volver a habilitar una cuenta de usuario con el Panel de control heredado

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. En el panel izquierdo, seleccione **Usuarios**.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desea deshabilitar o volver a habilitar.

6. En el **menú** Acción, realice una de las siguientes acciones:
   1. Para deshabilitar temporalmente la cuenta de usuario Skype Empresarial Server, seleccione **Deshabilitar temporalmente para Lync Server**.
   2. Para habilitar la cuenta de usuario para Skype Empresarial Server, **seleccione Volver a habilitar para Lync Server**.
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>Deshabilitar o volver a habilitar cuentas de usuario mediante Windows PowerShell

Las cuentas de usuario se pueden deshabilitar temporalmente y, posteriormente, volver a habilitarse mediante el cmdlet **Set-CsUser.** Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea [Administración remota de PowerShell de Microsoft Lync](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). El proceso es el mismo en Skype Empresarial Server.

### <a name="to-disable-a-user-account-using-windows-powershell"></a>Para deshabilitar una cuenta de usuario mediante Windows PowerShell

- Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad enabled en False ($False). Por ejemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>Para volver a habilitar una cuenta de usuario mediante Windows PowerShell

- Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad enabled en True ($True). Por ejemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obtener más información, vea el tema de ayuda del cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Deshabilitar un usuario para Telefonía IP empresarial

Use el siguiente procedimiento para deshabilitar Telefonía IP empresarial una cuenta de usuario habilitada para Skype Empresarial Server.

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>Deshabilitar un usuario para Telefonía IP empresarial con el nuevo Panel de control

1. Abra una ventana del explorador y escriba la dirección URL de administración para abrir el panel Skype Empresarial Server control.
 
2. Inicie sesión con una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator.

3. En el panel izquierdo, haga clic en **Usuarios**.

4. En el **cuadro Buscar,** escriba todo o la primera parte del nombre para mostrar y haga clic en **Buscar**.

5. En la tabla, haga doble clic en la cuenta de usuario que desea deshabilitar para Telefonía IP empresarial.

6. En el panel que aparece, haga clic en el icono de lápiz situado junto a **Directivas asignadas**.

7. En el panel **Directivas asignadas,** en **Telefonía,** haga clic en cualquier opción excepto **Telefonía IP empresarial** en la lista desplegable.

8. Haga clic en **Guardar**.

    > [!NOTE]
    > Para restringir que un usuario haga llamadas de audio o vídeo, en **Telefonía,** haga clic en **Audio/Vídeo deshabilitado.**

El usuario ahora no puede usar la característica Telefonía IP empresarial usuario. 

> [!NOTE]
> El nuevo Panel de control no está disponible para Skype Empresarial Server 2015.

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>Deshabilitar una cuenta de usuario para Telefonía IP empresarial usar el Panel de control heredado

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. En el panel izquierdo, haga clic en **Usuarios**.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desea habilitar para Telefonía IP empresarial.

6. En el menú **Editar**, haga clic en **Mostrar detalles**.

7. En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en cualquier opción excepto **Telefonía IP empresarial**.

    > [!NOTE]
    > Para restringir que un usuario haga llamadas de audio o vídeo mediante Lync, en **Telefonía,** haga clic en **Audio/vídeo deshabilitado.**

8. Haga clic en **Confirmar**.

El usuario ahora no puede usar la característica Telefonía IP empresarial usuario.

Información relacionada: <br/>[Telefonía IP empresarial y movilidad](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de administración de Skype Empresarial Server](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Quitar una cuenta de usuario con el Shell Skype Empresarial Server administración

Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada anteriormente en Skype Empresarial Server.

> [!NOTE]
> Eliminar un usuario provocará que pierda los parámetros que haya configurado para la cuenta de usuario. Si desea deshabilitar temporalmente una cuenta de usuario en su [lugar,](#disable-or-re-enable-a-user-account-for-skype-for-business-server)vea Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype Empresarial Server .

### <a name="remove-a-user-using-the-new-control-panel"></a>Quitar un usuario mediante el nuevo Panel de control

1. Abra una ventana del explorador y escriba la dirección URL de administración para abrir el panel Skype Empresarial Server control.
 
2. Inicie sesión con una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator.

3. En el panel izquierdo, seleccione **Usuarios**.

4. En el **cuadro Buscar,** escriba todo o la primera parte del nombre para mostrar y haga clic en **Buscar**.

5. En la tabla, haga doble clic en la cuenta de usuario que desea quitar.

6. En el panel que aparece, haga clic **en Quitar usuario**. En el siguiente panel que aparece, haga clic en **Aceptar**.

> [!NOTE]
> El nuevo Panel de control no está disponible para Skype Empresarial Server 2015.

### <a name="remove-a-user-using-the-legacy-control-panel"></a>Quitar un usuario mediante el Panel de control heredado

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3. En el panel izquierdo, seleccione **Usuarios**.

4. En  el cuadro Buscar usuarios, escriba todo o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desea quitar y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desee quitar.

6. En el menú **Acción**, seleccione **Quitar de Lync Server** y, a continuación, aparecerá un cuadro de diálogo.

7. En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Quitar cuentas de usuario con Windows PowerShell cmdlets

Puede quitar cuentas de usuario mediante el cmdlet Disable-CsUser usuario. Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server de administración o desde una sesión remota Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea [Administración remota de PowerShell de Microsoft Lync](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). El proceso es el mismo en Skype Empresarial Server.

Para quitar una cuenta de usuario, utilice el cmdlet Disable-CsUser. Por ejemplo:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Una vez que se haya ejecutado este comando, no hay manera de volver a habilitar la cuenta y las configuraciones previas. En su lugar, necesitará utilizar el cmdlet Enable-CsUser para crear una cuenta nueva para Ken Myer.

Para obtener más información, vea el tema de ayuda del cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Consulte también

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
