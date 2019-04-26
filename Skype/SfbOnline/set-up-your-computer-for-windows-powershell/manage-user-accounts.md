---
title: Administrar cuentas de usuario
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use el cmdlet Get-CsOnlineUser en Windows PowerShell para obtener información acerca de Skype la organización para usuarios profesionales en línea.
ms.openlocfilehash: 8f6ca618925b070e1d42a215cb9afb076a1e8197
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226411"
---
# <a name="manage-user-accounts"></a>Administrar cuentas de usuario

## <a name="manage-user-accounts"></a>Administrar cuentas de usuario

Este tema incluye las secciones siguientes:

- [Obtener información sobre todos los usuarios de Lync Online](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [Devolver información para un usuario específico de Skype para profesionales en línea](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [Devolver información específica para usuarios específicos en Skype para profesionales en línea](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [Devolver una lista filtrada de usuarios de Skype para profesionales en línea](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> El cmdlet **Set-CsUser** también se incluye en el conjunto de cmdlets disponibles para Skype para los administradores de negocios en línea. Sin embargo, **Set-CsUser** actualmente no puede usarse para administrar Skype para en línea de negocio, excepto si se establece el parámetro _AudioVideoDisabled_ . Si intenta ejecutar el cmdlet con otros parámetros, producirá un error con un mensaje de error similar al siguiente: no se puede establecer "SipAddress". Este parámetro está restringido dentro de PowerShell remoto de inquilinos.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Obtener información sobre todos los usuarios de Lync Online
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Para devolver información acerca de todos los usuarios que han sido habilitados para Skype para profesionales en línea, llame al cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sin ningún parámetro adicional.

```
Get-CsOnlineUser
```

Para devolver información de un usuario único, seleccionada al azar (por ejemplo, para usar esta cuenta para realizar pruebas), llamar al cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.

```
Get-CsOnlineUser -ResultSize 1
```

Que hace que el cmdlet **Get-CsOnlineUser** devolver información de un solo usuario, independientemente de cuántos usuarios tiene en la organización. Para devolver información de cinco usuarios, establezca el valor del parámetro _ResultSize_ en 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Devolver información para un usuario específico de Skype para profesionales en línea
<a name="BKMKReturnInfoSpecificUser"> </a>

Hay varias maneras de hacer referencia a una cuenta de usuario específica cuando se llama al cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Puede usar el nombre para mostrar del usuario los servicios de dominio de Active Directory (AD DS).

```
Get-CsOnlineUser -Identity "Ken Myer"
```

Puede usar la dirección SIP del usuario.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Puede usar el nombre principal de usuario (UPN) del usuario.

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Devolver información específica para usuarios específicos en Skype para profesionales en línea
<a name="BKMKReturninfoSpecificUsers"> </a>

De forma predeterminada, el cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) devuelve una gran cantidad de información para cada Skype para la cuenta de usuario en línea de negocio. Si está interesado en sólo un subconjunto de esa información, canalizar los datos devueltos al cmdlet **Select-Object** . Por ejemplo, este comando devuelve todos los datos para el usuario Ken Myer y, a continuación, utiliza el cmdlet **Select-Object** para limitar la información que se muestra en la pantalla para el nombre para mostrar de Ken AD DS y el plan de marcado.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

El siguiente comando devuelve el nombre para mostrar y marcado planeación para todos los usuarios.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para buscar las propiedades de un Skype para la cuenta de usuario de negocio en línea, use el siguiente comando.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Devolver una lista filtrada de usuarios de Skype para profesionales en línea
<a name="BKMKReturnFilteredListofUsers"> </a>

Mediante el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) y los parámetros _LdapFilter_ o _filtro_ , fácilmente puede devolver información acerca de un conjunto concreto de usuarios. Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de finanzas.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


