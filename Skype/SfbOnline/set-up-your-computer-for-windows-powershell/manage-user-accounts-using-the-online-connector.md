---
title: Administrar cuentas de usuario con Online Connector
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
description: Use el cmdlet Get-CsOnlineUser en Windows PowerShell para obtener información sobre los usuarios de Skype Empresarial Online de su organización.
ms.openlocfilehash: 370150de08493507d7b401d7907c90f343802d88
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692655"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Administrar cuentas de usuario con Online Connector

## <a name="manage-user-accounts"></a>Administrar cuentas de usuario

Este tema incluye las secciones siguientes:

- [Obtener información sobre todos los usuarios de Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Información de devolución de un usuario específico en Skype Empresarial Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Devolver información específica para usuarios específicos en Skype Empresarial Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Devolver una lista filtrada de usuarios en Skype Empresarial Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> El **cmdlet Set-CsUser** también se incluye en el conjunto de cmdlets disponibles para los administradores de Skype Empresarial Online. Sin embargo, actualmente no se puede usar **Set-CsUser** para administrar Skype Empresarial Online, excepto para configurar el parámetro _AudioVideoDisabled._ Si intenta ejecutar el cmdlet con cualquier otro parámetro, se producirá un error con un mensaje de error similar a este: No se puede establecer "SipAddress". Este parámetro está restringido en PowerShell de espacio empresarial remoto.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Obtener información sobre todos los usuarios de Lync Online
<a name="BKAllUsers"> </a>

Para devolver información sobre todos los usuarios habilitados para Skype Empresarial Online, llame al cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sin parámetros adicionales.

```PowerShell
Get-CsOnlineUser
```

Para devolver información de un solo usuario seleccionado de forma aleatoria (por ejemplo, para usar esta cuenta con fines de prueba), llame al cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

Esto hace que el cmdlet **Get-CsOnlineUser** devuelva información solo para un usuario, independientemente del número de usuarios que tenga en su organización. Para devolver información para cinco usuarios, establezca el valor del parámetro _ResultSize_ en 5.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Información de devolución de un usuario específico en Skype Empresarial Online
<a name="BKSpecificUser"> </a>

Hay varias formas de hacer referencia a una cuenta de usuario específica al llamar al cmdlet [Get-CsOnlineUser.](https://go.microsoft.com/fwlink/p/?linkid=849603) Puede usar el nombre para mostrar de servicios de dominio de Active Directory (AD DS) del usuario.

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

De forma predeterminada, el cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) devuelve una gran cantidad de información para cada cuenta de usuario de Skype Empresarial Online. Si está interesado en solo un subconjunto de esa información, canalizar los datos devueltos al cmdlet **Select-Object.** Por ejemplo, este comando devuelve todos los datos del usuario Ken Myer y, después, usa el cmdlet **Select-Object** para limitar la información que se muestra en pantalla al nombre para mostrar y el plan de marcado de AD DS de Ken.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

El siguiente comando devuelve el nombre para mostrar y el plan de marcado de todos los usuarios.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para buscar las propiedades de una cuenta de usuario de Skype Empresarial Online, use el comando siguiente.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Devolver una lista filtrada de usuarios en Skype Empresarial Online
<a name="BKListofUsers"> </a>

Mediante el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) y los parámetros _LdapFilter_ o _Filter,_ puede devolver fácilmente información sobre un conjunto de usuarios de destino. Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de finanzas.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


