---
title: "Administrar cuentas de usuario mediante el conector en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Para obtener información acerca Skype de su organización para usuarios de negocios en línea, use el cmdlet Get-CsOnlineUser en Windows PowerShell."
ms.openlocfilehash: 299731f811163f57f54e7e2a6c8f263f6d68de5e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Administrar cuentas de usuario mediante el conector en línea

## <a name="manage-user-accounts"></a>Administrar cuentas de usuario

Este tema incluye las secciones siguientes:
  
- [Devuelven información acerca de todos los Skype para usuarios de negocios en línea](manage-user-accounts-using-the-online-connector.md#BKAllUsers)
    
- [Devolver información de un usuario específico en Skype para los negocios en línea](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)
    
- [Devolver información específica para usuarios específicos en Skype para los negocios en línea](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)
    
- [Devolver una lista filtrada de usuarios de Skype para los negocios en línea](manage-user-accounts-using-the-online-connector.md#BKListofUsers)
    
> [!NOTE]
> El cmdlet **Set-CsUser** también se incluye en el conjunto de cmdlets de Skype disponibles para los administradores de negocios en línea. Sin embargo, **Conjunto CsUser** actualmente no puede utilizarse para administrar Skype para los negocios en línea, excepto si el parámetro _AudioVideoDisabled_ . Si intenta ejecutar el cmdlet con ningún otro parámetro, se producirá un mensaje de error similar al siguiente: no se puede establecer en "SipAddress". Este parámetro es restringido en PowerShell remoto de inquilinos.
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Obtener información sobre todos los usuarios de Lync Online
<a name="BKAllUsers"> </a>

Para obtener información acerca de todos los usuarios que han sido habilitados para Skype para los negocios en línea, llame el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sin ningún parámetro adicional.
  
```
Get-CsOnlineUser
```

Para devolver información de un usuario único, seleccionado aleatoriamente (por ejemplo, para utilizar esta cuenta para fines de prueba), llame el cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.
  
```
Get-CsOnlineUser -ResultSize 1
```

Que hace que el cmdlet **Get-CsOnlineUser** devolver información de un solo usuario, independientemente de cuántos usuarios hay en su organización. Para devolver información de cinco usuarios, establezca el valor del parámetro _ResultSize_ a 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Devolver información de un usuario específico en Skype para los negocios en línea
<a name="BKSpecificUser"> </a>

Hay varias maneras de hacer referencia a una cuenta de usuario específica cuando se llama el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Puede utilizar el nombre para mostrar del usuario los servicios de dominio de Active Directory (AD DS).
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

Puede utilizar la dirección del usuario SIP.
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Puede utilizar el nombre principal de usuario (UPN) del usuario.
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Devolver información específica para usuarios específicos en Skype para los negocios en línea
<a name="BKSpecificUsers"> </a>

De forma predeterminada, el cmdlet [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) devuelve una gran cantidad de información para cada Skype para cuenta de usuario de negocios en línea. Si estás interesado en sólo un subconjunto de la información, canalizar los datos devueltos al cmdlet **Select-Object** . Por ejemplo, este comando restablece todos los datos para el usuario Ken Myer y usa el cmdlet **Select-Object** para limitar la información que aparece en la pantalla nombre para mostrar de Ken AD DS y el plan de marcado.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

El comando siguiente se devuelve el nombre para mostrar y el dial plan para todos los usuarios.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para buscar las propiedades de un Skype para cuenta de usuario de negocios en línea, utilice el siguiente comando.
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Devolver una lista filtrada de usuarios de Skype para los negocios en línea
<a name="BKListofUsers"> </a>

Mediante el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) y los parámetros _filtroLDAP_ o _filtro_ , podrá volver fácilmente información sobre un conjunto concreto de usuarios. Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de finanzas.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
