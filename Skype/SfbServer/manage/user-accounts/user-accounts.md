---
title: Administrar cuentas de usuario de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server.
ms.openlocfilehash: 8aeebafc0e221cd51df76233f6dce1f1e53fb429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897320"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Administrar cuentas de usuario de Skype para Business Server

Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server.

Para obtener información acerca de cómo habilitar a un usuario de Active Directory, vea [crear una nueva cuenta de usuario](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Para obtener información sobre cómo eliminar un usuario de Active Directory, vea [Eliminar una cuenta de usuario](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).

Estos procedimientos se deben realizar durante un período de mantenimiento, cuando Skype para uso empresarial es más bajo. Si esto se realiza en una programación diaria o semanal vendrá determinada por las necesidades de su organización.

Este artículo contiene los siguientes procedimientos:

- [Para buscar uno o varios usuarios](user-accounts.md#Search)

- [Agregar y habilitar un nuevo Skype para usuario Business Server](user-accounts.md#Add)

- [Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype para Business Server](user-accounts.md#Disable)

- [Deshabilitar a un usuario para Enterprise Voice](user-accounts.md#Disable_EV)

- [Quitar una cuenta de usuario con el Skype para Shell de administración de servidor empresarial](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Para buscar uno o varios usuarios
<a name="Search"> </a>

Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype para Business Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.

Puede buscar los usuarios mediante el Skype para Panel de Control de servidor empresarial o los usuarios de Active Directory y complemento de equipos. El siguiente procedimiento describe cómo usar Skype para el Panel de Control de servidor empresarial para buscar los usuarios.

> [!NOTE]
> En un entorno con una topología de bosque central, los resultados de búsqueda podrían no ser exactos al buscar un usuario por dirección de correo electrónico del usuario. En su lugar, puede buscar los usuarios mediante la especificación de un prefijo de dirección SIP, por ejemplo, sip: nombre, agregar un filtro de búsqueda y seleccione una dirección SIP que contiene una dirección de correo electrónico parcial o use el cmdlet **Get-CSUser** .

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellidos, nombre de cuenta SAM, la dirección SIP o URI de la cuenta de usuario que desea buscar y, a continuación, haga clic en **Buscar**de línea.

5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:

   a. Haga clic en la flecha para expandir en la esquina superior derecha de la pantalla por encima de **los resultados de búsqueda**y, a continuación, haga clic en **Agregar filtro**.

   b. Especifique la propiedad de usuario escribe en él o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.

   c. En la lista **igual a** , haga clic en **igual a** o **no igual a**.

   d. En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados de búsqueda y, a continuación, haga clic en **Buscar**.

6. En **Los resultados de búsqueda**, aparecerán los resultados de búsqueda. Puede seleccionar cualquier o todos los usuarios en la lista y realizar tareas de configuración en los usuarios que seleccione.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Agregar y habilitar un nuevo Skype para usuario Business Server
<a name="Add"> </a>

Después de habilitar una cuenta de usuario en usuarios y equipos de usuarios de Active Directory, puede usar Skype para el Panel de Control de Business Server para crear y habilitar nuevas Skype Business Server las cuentas de usuario mediante la adición de un usuario de Active Directory a Skype para Business Server.

También puede usar un cmdlet, específicamente [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. Haga clic en **Permitir a los usuarios**.

5. En el cuadro de diálogo **Nuevo usuario de Lync Server** , haga clic en **Agregar**.

6. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre, Mostrar nombre, nombre, apellidos, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección de correo electrónico, nombre Principal del usuario (UPN) o número de teléfono de la cuenta de usuario de Active Directory que desee y, a continuación, haga clic en **Buscar**.

7. En la tabla, seleccione la cuenta que desea agregar a Skype para Business Server y, a continuación, haga clic en **Aceptar**.

8. Asigne al usuario a un grupo de servidores, especificar detalles adicionales y asigne las directivas al usuario que desee y, a continuación, haga clic en **Habilitar**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype para Business Server
<a name="Disable"> </a>

Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada anteriormente en Skype para Business Server sin perder el Skype para la configuración del servidor de negocio que ha configurado para la cuenta de usuario. Debido a que no se pierde la Skype para la configuración de cuenta de usuario de Business Server, puede volver a habilitar una cuenta de usuario habilitada anteriormente nuevo sin tener que volver a configurar la cuenta de usuario.

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellidos, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desea deshabilitar o volver a habilitar.

6. En el menú **acción** , realice una de las siguientes opciones:

   - Para deshabilitar temporalmente la cuenta de usuario de Skype para Business Server, haga clic en **deshabilitar temporalmente para Lync Server**.

   - Para habilitar la cuenta de usuario de Skype para Business Server, haga clic en **volver a habilitar para Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar Windows Powershell para deshabilitar o volver a habilitar cuentas de usuario

Las cuentas de usuario pueden deshabilitadas temporalmente y, a continuación, más adelante volver a habilitarse, mediante el cmdlet **Set-CsUser** . Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.

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

Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .

## <a name="disable-a-user-for-enterprise-voice"></a>Deshabilitar a un usuario para Enterprise Voice
<a name="Disable_EV"> </a>

Use el procedimiento siguiente para deshabilitar Enterprise Voice para una cuenta de usuario que está habilitada para Skype en Business Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para deshabilitar una cuenta de usuario para Enterprise Voice

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desea habilitar para Enterprise Voice.

6. En el menú **Editar**, haga clic en **Mostrar detalles**.

7. En la página **Editar usuario de Lync Server** , en **telefonía**, haga clic en cualquier opción excepto **Telefonía IP empresarial**.

    > [!NOTE]
    > Para restringir la capacidad de un usuario realizar llamadas de audio o vídeos mediante el uso de Lync, en **telefonía**, haga clic en **Audio y vídeo deshabilitados**.

8. Haga clic en **Confirmar**.

El usuario es ahora no se puede usar la característica de Enterprise Voice. Información relacionada: <br/>[Enterprise Voice y movilidad](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Habilitar a usuarios para Enterprise Voice en Skype para Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de administración de Skype Empresarial Server](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Quitar una cuenta de usuario con el Skype para Shell de administración de servidor empresarial
<a name="Remove"> </a>

Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada anteriormente en Skype para Business Server.

> [!NOTE]
> Eliminación de un usuario hará que perder cualquier configuración establecida para la cuenta de usuario. Si desea deshabilitar temporalmente una cuenta de usuario en su lugar, vea [Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype para Business Server](user-accounts.md#Disable).

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3. En la barra de navegación izquierda, haga clic en **Usuarios**.

4. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellidos, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.

5. En la tabla, haga clic en la cuenta de usuario que desea quitar.

6. En el menú **acción** , seleccione **quitar de Lync Server**y un cuadro de diálogo aparecerá el cuadro.

7. En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Quitar cuentas de usuario con los cmdlets de Windows Powershell

Puede quitar cuentas de usuario mediante el cmdlet Disable-CsUser. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.

### <a name="to-remove-a-user-account"></a>Para quitar una cuenta de usuario
Para quitar una cuenta de usuario, use el cmdlet Disable-CsUser. Por ejemplo:

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Para obtener más información, vea el tema de ayuda para el cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Vea también
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
