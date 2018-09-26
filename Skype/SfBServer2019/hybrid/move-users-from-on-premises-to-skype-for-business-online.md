---
title: Mover usuarios de local a Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo migrar la configuración de usuario y mover los usuarios a Skype para profesionales en línea.'
ms.openlocfilehash: 9fd51c55be35e55be6ca837ccb72413043283ac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030752"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuarios de local a Skype Empresarial Online

**Resumen:** Obtenga información sobre cómo migrar la configuración de usuario y mover los usuarios a Skype para profesionales en línea.

Antes de mover realmente un usuario a Office 365, primero debe confirmar que las cuentas de usuario se sincronizan en la nube y asígneles una licencia. Para hacerlo, use el Centro de administración de Office 365.

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>Para confirmar que se ha sincronizado una cuenta de usuario local con Office 365

1. Con una cuenta de administrador de inquilinos, abra el centro de administración de Office 365 para el inquilino.  Las cuentas de administración de inquilinos deben concederse tanto la Skype para la función de administración de negocio y la función de administración de usuario (o la función de administrador Global) realizar esta función en Office 365.

2. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, haga clic en **Usuarios activos**.

3. Haga clic en **Buscar un usuario** y escriba el nombre del usuario.

4. Confirme que ve el usuario y que su estado es **Synched con Active Directory**.

    Si el usuario todavía no está sincronizado, la siguiente sincronización automática debería producirse en tres horas. También puede forzar la sincronización para que se produzca antes. Para obtener más información, vea [Forzar la sincronización de directorios](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).

Para asignar la licencia de Office 365, vea [asignar licencias a los usuarios de Office 365 para la empresa](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="migrate-user-settings-to-skype-for-business-online"></a>Migrar la configuración de usuario a Skype para profesionales en línea

Antes de migrar los usuarios a Skype para profesionales en línea, debe hacer una copia seguridad de los datos de usuario asociados con las cuentas que se va a mover. No todos los datos de usuario se mueve con la cuenta de usuario. Para obtener información, vea [requisitos de restauración y copia de seguridad: datos](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).

La configuración de usuario se mueve con la cuenta de usuario. Algunos valores de configuración locales no se mueven con la cuenta de usuario.

## <a name="move-pilot-users-to-skype-for-business-online"></a>Mover los usuarios pilotos a Skype para profesionales en línea

Antes de mover los usuarios a Skype para profesionales en línea, desea mover algunos usuarios pilotos para confirmar que el entorno está configurado correctamente. Después puede verificar que las características y los servicios de Lync funcionan del modo esperado antes de intentar mover más usuarios.

Para mover un usuario local a su Skype para inquilino en línea de negocio, ejecute los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial, con las credenciales de administrador para el inquilino de Microsoft Office 365. Reemplace "username@contoso.com" con la información para el usuario que desea mover.

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a>Mover usuarios a Skype Empresarial Online

Puede mover varios usuarios mediante el cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) -el parámetro Filter para seleccionar los usuarios con una propiedad concreta asignada a las cuentas de usuario, como RegistrarPool. A continuación, puede canalizar los usuarios devueltos al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , tal como se muestra en el ejemplo siguiente:

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

También puede usar el parámetro - OU para recuperar todos los usuarios de la unidad organizativa especificada, tal como se muestra en el ejemplo siguiente:

```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds
```

## <a name="verify-online-user-settings-and-features"></a>Comprobar las características y configuración de usuario en línea

Puede comprobar que el usuario se ha movido correctamente de las siguientes maneras:

- Vea el estado del usuario en el Panel de Control de Skype Empresarial Online. El indicador visual de los usuarios locales y los usuarios en línea es diferente.

- Ejecute el siguiente cmdlet:

  ```
  Get-CsUser -Identity
  ```


