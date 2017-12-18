---
title: "Administrar cuentas de usuario mediante la Skype para Business Connector en línea"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# Administrar cuentas de usuario mediante la Skype para Business Connector en línea

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
## Administrar cuentas de usuario

Este tema contiene las secciones siguientes:
  
- [Obtener información acerca de todo su Skype para usuarios de negocio en línea](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [Devuelve información para un usuario específico en Skype empresarial Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [Obtener información específica para usuarios específicos en Skype empresarial Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [Devolver una lista filtrada de usuarios de Skype empresarial Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> El cmdlet **Set-CsUser** también se incluye en el conjunto de cmdlets disponibles para los administradores de Skype Empresarial Online. Sin embargo, **Set-CsUser** actualmente no pueden usarse para administrar Skype Empresarial Online, excepto para el parámetro _AudioVideoDisabled_. Si intenta ejecutar el cmdlet con cualquier otro parámetro, se producirá un error con un mensaje de error similar a este: No se puede establecer "SipAddress". Este parámetro es restringido dentro de PowerShell remoto de inquilinos.
  
### Obtener información acerca de todo su Skype para usuarios de negocio en línea
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

Para obtener información sobre todos los usuarios que han sido habilitados para Skype Empresarial Online, llame el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sin ningún parámetro adicional.
  
```
Get-CsOnlineUser
```

Para devolver información para un único usuario seleccionado aleatoriamente (por ejemplo, para utilizar esta cuenta para fines de pruebas), llame el cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.
  
```
Get-CsOnlineUser -ResultSize 1
```

Que hace que el cmdlet **Get-CsOnlineUser** devolver información para un solo usuario, independientemente de cuántos usuarios tiene en su organización. Para devolver información de cinco usuarios, establezca el valor del parámetro _ResultSize_ a 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### Devuelve información para un usuario específico en Skype empresarial Online
<a name="BKMK_ReturnInfoSpecificUser"> </a>

Hay varias formas de hacer referencia a una cuenta de usuario al que llama el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Puede usar el nombre para mostrar del usuario Servicios de dominio de Active Directory (AD DS).
  
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

### Obtener información específica para usuarios específicos en Skype empresarial Online
<a name="BKMK_ReturninfoSpecificUsers"> </a>

De forma predeterminada, el cmdlet [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) devuelve una gran cantidad de información para cada cuenta de usuario de Skype Empresarial Online. Si está interesado en sólo un subconjunto de esa información, tubería los datos devueltos al cmdlet **Select-Object**. Por ejemplo, este comando devuelve todos los datos para el usuario Ken Myer y, a continuación, utiliza muestra el cmdlet **Select-Object** para limitar la información en pantalla a nombre para mostrar de Ana AD DS y plan de marcado.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

El comando siguiente se devuelve el nombre para mostrar y marcado plan para todos los usuarios.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Para buscar las propiedades de una cuenta de usuario de Skype Empresarial Online, use el siguiente comando.
  
```
Get-CsOnlineUser | Get-Member
```

### Devolver una lista filtrada de usuarios de Skype empresarial Online
<a name="BKMK_ReturnFilteredListofUsers"> </a>

Mediante el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) y los parámetros _LdapFilter_ o _Filter_, podrá volver fácilmente información sobre un conjunto concreto de usuarios. Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de finanzas.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

