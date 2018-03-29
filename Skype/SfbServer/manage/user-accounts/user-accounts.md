---
title: Administrar cuentas de usuario de Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server 2015.
ms.openlocfilehash: bd09687a6a2d2f3d1e8dcfe13b7f8aa64648e56b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-user-accounts-for-skype-for-business-server-2015"></a>Administrar cuentas de usuario de Skype para Business Server 2015
 
Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server 2015.
  
Para obtener información sobre cómo habilitar a un usuario de Active Directory, vea [crear una nueva cuenta de usuario](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Para obtener información sobre cómo eliminar un usuario de Active Directory, vea [Eliminar una cuenta de usuario](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).
  
Estos procedimientos deben realizarse durante un período de mantenimiento, cuando Skype para uso comercial es el más bajo. Si esto se realiza en una programación diaria o semanal determinará las necesidades de su organización. 
  
Este artículo contiene los siguientes procedimientos:
  
- [Para buscar uno o más usuarios](user-accounts.md#Search)
    
- [Agregar y habilitar un nuevo Skype para usuario Business Server 2015](user-accounts.md#Add)
    
- [Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype para Business Server](user-accounts.md#Disable)
    
- [Deshabilitar a un usuario de Telefonía IP empresarial](user-accounts.md#Disable_EV)
    
- [Quitar una cuenta de usuario con el Skype para el Shell de administración de servidor empresarial](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a>Para buscar uno o más usuarios
<a name="Search"> </a>

Puede utilizar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype para Business Server 2015. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.
  
Puede buscar usuarios utilizando el Skype para el Panel de Control de Business Server o Active Directory Users y complemento equipos. El procedimiento siguiente describe cómo usar Skype para Business Server Control Panel para buscar usuarios.
  
> [!NOTE]
> En un entorno con una topología de bosque central, resultados de búsqueda podrían no ser exactos al buscar un usuario por su dirección de correo electrónico del usuario. En su lugar, puede buscar los usuarios especificando un prefijo de dirección SIP, por ejemplo, sip: nombre, agregar un filtro de búsqueda y seleccione una dirección SIP que contiene una dirección de correo electrónico parcial o usar el cmdlet **Get-Csusuario** .
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellido, nombre de cuenta SAM, dirección SIP o línea de URI de la cuenta de usuario que desea buscar y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en el botón de flecha de expansión en la esquina superior derecha de la pantalla situada por encima de los **resultados de la búsqueda**y, a continuación, haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario escribiéndola o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.
    
   c. En la lista **igual a** , haga clic en **igual a** o **no igual a**.
    
   d. En el cuadro de texto, escriba los criterios de búsqueda que desee utilizar para filtrar los resultados de la búsqueda y, a continuación, haga clic en **Buscar**.
    
6. Resultados de la búsqueda aparecen en los **Resultados de la búsqueda**. Puede seleccionar alguno o todos los usuarios en la lista y realizar tareas de configuración de los usuarios que seleccione.
    
## <a name="add-and-enable-a-new-skype-for-business-server-2015-user"></a>Agregar y habilitar un nuevo Skype para usuario Business Server 2015
<a name="Add"> </a>

Después de habilitar una cuenta de usuario en Active Directory Users and Computers, puede utilizar Skype para Business Server Control Panel para crear y habilitar el nuevo Skype para cuentas de usuario de Business Server 2015 agregando un usuario de Active Directory a Skype para Business Server 2015.
  
También puede utilizar un cmdlet, específicamente [Habilitar Csusuario](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Haga clic en **Permitir a los usuarios**.
    
5. En el cuadro de diálogo **Nuevo usuario de Lync Server** , haga clic en **Agregar**.
    
6. En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre, Mostrar nombre, nombre, apellido, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección de correo electrónico, nombre Principal de usuario (UPN) o número de teléfono de la cuenta de usuario de Active Directory que desee y, a continuación, haga clic en **Buscar**.
    
7. En la tabla, seleccione la cuenta que desea agregar a Skype para Business Server 2015 y, a continuación, haga clic en **Aceptar**.
    
8. Asignar al usuario a un grupo, especifique detalles adicionales y asignar las directivas para el usuario que desee y, a continuación, haga clic en **Habilitar**.
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype para Business Server
<a name="Disable"> </a>

Puede utilizar el procedimiento siguiente para deshabilitar una cuenta de usuario previamente habilitado en Skype para Business Server sin perder la Skype para la configuración del servidor de la empresa que ha configurado para la cuenta de usuario. Porque no se pierden el Skype para la configuración de cuentas de usuario de Business Server, se puede volver a habilitar una cuenta de usuario previamente habilitado otra vez sin tener que volver a configurar la cuenta de usuario. 
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellido, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea volver a habilitar o deshabilitar.
    
6. En el menú **acción** , siga uno de estos procedimientos:
    
   - Para deshabilitar temporalmente la cuenta de usuario de Skype para Business Server, haga clic en **deshabilitar temporalmente para Lync Server**.
    
   - Para habilitar la cuenta de usuario de Skype para Business Server, haga clic en **volver a habilitar para Lync Server**.
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar Windows Powershell para deshabilitar o volver a habilitar las cuentas de usuario

Las cuentas de usuario pueden temporalmente deshabilitadas y posteriormente volver a habilitarla después, mediante el cmdlet **Set-Csusuario** . Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-disable-a-user-account"></a>Para deshabilitar una cuenta de usuario

- Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en False ($False). Por ejemplo:
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Para volver a habilitar una cuenta de usuario

- Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en True ($True). Por ejemplo:
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Set-Csusuario](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .
  
## <a name="disable-a-user-for-enterprise-voice"></a>Deshabilitar a un usuario de Telefonía IP empresarial
<a name="Disable_EV"> </a>

Utilice el procedimiento siguiente para deshabilitar la Telefonía IP empresarial en una cuenta de usuario está habilitada para Skype en Business Server 2015.
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para deshabilitar una cuenta de usuario para Telefonía IP empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea habilitar para Telefonía IP empresarial.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En la página **Modificar usuario de Lync Server** , **telefonía**, haga clic en cualquier opción excepto **Telefonía IP empresarial**.
    
    > [!NOTE]
    > Para impedir que un usuario realizar llamadas de audio o vídeo utilizando Lync en **telefonía**, haga clic en **deshabilitado de Audio y vídeo**. 
  
8. Haga clic en **Confirmar**.
    
El usuario es ahora no puede utilizar la característica de Telefonía IP empresarial. Información relacionada: <br/>[Movilidad y Telefonía IP empresarial](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Permitir que los usuarios de Telefonía IP empresarial en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Quitar una cuenta de usuario con el Skype para el Shell de administración de servidor empresarial
<a name="Remove"> </a>

Puede utilizar el siguiente procedimiento para quitar una cuenta de usuario previamente agregado de Skype para Business Server 2015. 
  
> [!NOTE]
> Quitar un usuario hará que pierda cualquier configuración de la cuenta de usuario. Si desea deshabilitar temporalmente una cuenta de usuario en su lugar, vea [Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype para Business Server](user-accounts.md#Disable). 
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellido, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea quitar.
    
6. En el menú **acción** , seleccione **quitar de Lync Server**y un cuadro de diálogo aparecerá el cuadro de.
    
7. En el cuadro de diálogo, seleccione **Aceptar** para eliminar el usuario.
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Quitar cuentas de usuario con los cmdlets de Windows Powershell

Puede quitar cuentas de usuario mediante el cmdlet Disable-Csusuario. Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-remove-a-user-account"></a>Para quitar una cuenta de usuario
Para quitar una cuenta de usuario, utilice el cmdlet Disable-Csusuario. Por ejemplo:
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
Para obtener más información, vea el tema de ayuda para el cmdlet [Disable-Csusuario](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .
  
## <a name="see-also"></a>Vea también
<a name="Remove"> </a>

#### 

[Habilitar CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[Deshabilitar CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

