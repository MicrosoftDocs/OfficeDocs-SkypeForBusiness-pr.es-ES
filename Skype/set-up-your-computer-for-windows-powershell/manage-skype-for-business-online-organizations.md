---
title: "Administrar Skype para las organizaciones empresariales en línea con el Skype para Business Connector en línea"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
description: "Use Windows PowerShell and the Get-CsTenant and Get-CsTenantLicensingConfiguration cmdlets to get information about your Skype for Business Online tenant."
---

# Administrar Skype para las organizaciones empresariales en línea con el Skype para Business Connector en línea

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Puede encontrar información sobre su inquilino Skype Empresarial Online usando los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration**.
  
## Administrar Skype empresarial Online inquilinos

Para obtener información sobre el inquilino Skype Empresarial Online, llame el cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.
  
```
Get-CsTenant
```

Para devolver el inquilino de al nombre e Id., utilice este comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro  _TenantID_ se requiere cuando se ejecuta cmdlets como[Conjunto CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y[Establecer CsTenantFederationConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849602).
  
Para obtener información acerca de la información de licencia del inquilino especificado está disponible en el centro de administración de Skype Empresarial Online, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

