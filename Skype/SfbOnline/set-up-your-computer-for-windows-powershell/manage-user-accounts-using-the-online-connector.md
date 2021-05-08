---
title: Administrar cuentas de usuario con El conector en línea
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use el cmdlet Get-CsOnlineUser en Windows PowerShell para obtener información sobre los Skype Empresarial en línea de su organización.
ms.openlocfilehash: fa647a7ba80fc649146e2278fb2041343354dead
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238545"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Administrar cuentas de usuario con El conector en línea

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a>Administrar cuentas de usuario

Este tema incluye las secciones siguientes:

- [Obtener información sobre todos los usuarios de Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Devolver información para un usuario específico en Skype Empresarial Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Devolver información específica para usuarios específicos en Skype Empresarial Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Devolver una lista filtrada de usuarios en Skype Empresarial Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> El cmdlet **Set-CsUser** también se incluye en el conjunto de cmdlets disponibles para Skype Empresarial en línea. Sin embargo, **Set-CsUser** no se puede usar actualmente para administrar Skype Empresarial Online, excepto para establecer el _parámetro AudioVideoDisabled._ Si intenta ejecutar el cmdlet con cualquier otro parámetro, se producirá un error con un mensaje de error similar a este: No se puede establecer "SipAddress". Este parámetro está restringido en PowerShell de inquilino remoto.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Obtener información sobre todos los usuarios de Lync Online
<a name="BKAllUsers"> </a>

Para devolver información sobre todos los usuarios que se han habilitado para Skype Empresarial Online, llame al cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) sin ningún parámetro adicional.

```PowerShell
Get-CsOnlineUser
```

Para devolver información para un único usuario seleccionado aleatoriamente (por ejemplo, para usar esta cuenta con fines de prueba), llame al cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

Esto hace que el cmdlet **Get-CsOnlineUser** devuelva información solo para un usuario, independientemente de cuántos usuarios tenga en su organización. Para devolver información para cinco usuarios, establezca el valor del parámetro _ResultSize_ en 5.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Devolver información para un usuario específico en Skype Empresarial Online
<a name="BKSpecificUser"> </a>

Hay varias formas de hacer referencia a una cuenta de usuario específica al llamar al cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser) Puede usar el nombre para mostrar de servicios de dominio de Active Directory (AD DS) del usuario.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

Puede usar la dirección SIP del usuario.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Puede usar el nombre principal de usuario (UPN) del usuario.

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Devolver información específica para usuarios específicos en Skype Empresarial Online
<a name="BKSpecificUsers"> </a>

De forma predeterminada, el cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) devuelve una gran cantidad de información para cada Skype Empresarial cuenta de usuario en línea. Si solo está interesado en un subconjunto de esa información, canalizar los datos devueltos al cmdlet **Select-Object.** Por ejemplo, este comando devuelve todos los datos del usuario Ken Myer y, a continuación, usa el cmdlet **Select-Object** para limitar la información que se muestra en pantalla al nombre para mostrar y el plan de marcado de Ad DS de Ken.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

El siguiente comando devuelve el nombre para mostrar y el plan de marcado para todos los usuarios.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para buscar las propiedades de una Skype Empresarial de usuario en línea, use el comando siguiente.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Devolver una lista filtrada de usuarios en Skype Empresarial Online
<a name="BKListofUsers"> </a>

Con el cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) y los parámetros _LdapFilter_ o _Filter,_ puede devolver fácilmente información sobre un conjunto de usuarios dirigido. Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de Finanzas.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
