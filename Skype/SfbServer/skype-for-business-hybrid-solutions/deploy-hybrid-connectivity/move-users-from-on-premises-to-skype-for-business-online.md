---
title: Mover usuarios de local a Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Resumen: Conozca cómo migrar la configuración de usuario y mover usuarios a Skype para los negocios en línea.'
ms.openlocfilehash: 352798c217cb7495134cb32996db783f7e498ded
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuarios de local a Skype Empresarial Online
 
**Resumen:** Aprenda cómo migrar la configuración de usuario y mover usuarios a Skype para los negocios en línea.
  
Antes de mover el usuario a Office 365, debería confirmar primero que las cuentas de usuario están sincronizados con la nube y asígneles una licencia. Para hacerlo, use el Centro de administración de Office 365.
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>Para confirmar que se ha sincronizado una cuenta de usuario local con Office 365

1. Con una cuenta de administrador de inquilinos, abra el [Centro de administración de Office 365](https://portal.office.com/) para el arrendatario.  Cuentas del Administrador de inquilinos deben concederse ambos el Skype para la función de administrador de empresa y la función de administración de usuario (o la función de administrador Global) realizar esta función en Office 365
    
2. En el panel de navegación izquierdo, haga clic en **Usuarios** y, después, en **Usuarios activos**.
    
3. Haga clic en **Buscar un usuario** y escriba el nombre del usuario.
    
4. Confirme que puede ver el usuario y que su estado es **Sincronizado con Active Directory**.
    
    Si el usuario todavía no está sincronizado, la siguiente sincronización automática debería producirse en tres horas. También puede forzar la sincronización para que se produzca antes. Para obtener más información, vea [Forzar la sincronización de directorios](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).
    
Para asignar la licencia de Office 365, consulte [asignación de licencias para Office 365 para el negocio](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a>Migrar la configuración de usuario Skype para los negocios en línea

Antes de empezar a migrar los usuarios a Skype para los negocios en línea, debe copia de seguridad los datos de usuario asociados a las cuentas que desea mover. No todos los datos de usuario se mueve con la cuenta de usuario. Para obtener información, consulte [requerimientos de Backup y restauración: datos](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).
  
La configuración de usuario se mueve con la cuenta de usuario. Algunos valores de configuración locales no se mueven con la cuenta de usuario.
  
## <a name="move-pilot-users-to-skype-for-business-online"></a>Trasladar a usuarios piloto a Skype para los negocios en línea

Antes de empezar a mover los usuarios a Skype para los negocios en línea, es aconsejable mover algunos usuarios piloto para confirmar que su entorno está configurado correctamente. Después puede verificar que las características y los servicios de Lync funcionan del modo esperado antes de intentar mover más usuarios.
  
Para mover un usuario local a su Skype para inquilinos de negocios en línea, ejecute los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios, utilizando las credenciales de administrador para los clientes de Microsoft Office 365. Sustituya “username@contoso.com” por la información del usuario que quiera mover.
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a>Mover usuarios a Skype Empresarial Online

Puede mover varios usuarios mediante el cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) -el parámetro Filter para seleccionar los usuarios con una propiedad específica asignada a las cuentas de usuario, como RegistrarPool. A continuación, puede canalizar los usuarios devueltos al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , como se muestra en el ejemplo siguiente.
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

También puede utilizar el parámetro - OU para recuperar todos los usuarios de la unidad organizativa especificada, tal como se muestra en el ejemplo siguiente.
  
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


