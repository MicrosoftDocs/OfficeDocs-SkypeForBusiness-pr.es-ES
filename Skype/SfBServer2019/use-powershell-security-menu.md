---
title: Usar PowerShell para tareas en el menú Seguridad
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Summary: Skype Empresarial Server Control panel to Cmdlet mapping for Security menu.'
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824997"
---
# <a name="security"></a>Seguridad

En este artículo se describe cómo  se pueden obtener resultados similares a los del elemento de menú Seguridad en el Panel de control heredado mediante cmdlets.

En este artículo se describen los siguientes submenúes:

- [Seguridad](#security)
  - [Registrador](#registrar)
  - [Servicio Web](#web-service)
  - [Directiva de PIN](#pin-policy)

## <a name="registrar"></a>Registrador

**El** submenú REGISTRAR permite a los administradores administrar servidores proxy a través de las opciones de configuración del servidor proxy. Esta configuración, que se puede aplicar tanto en el ámbito global como en el ámbito de servicio (aunque solo para el servidor perimetral y los servicios de registrador) permite controlar aspectos como los protocolos de autenticación que pueden usar los extremos de cliente y si la compresión se usará o no en las conexiones de servidor proxy entrantes y salientes.

Consideremos las distintas tareas que un usuario puede hacer en **REGISTRAR** y los cmdlets Skype Empresarial a las que se asignan esas tareas.

---

> **Escenario 1:** Enumerar todas las configuraciones de proxy

   ![Configuración de proxy de lista](./media/proxy-configurations-1.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Ejemplo***

```powershell
 Get-CsProxyConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de proxy

   ![Crear configuración de proxy](./media/proxy-configurations-2.png)

***Cmdlet***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***Ejemplo***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **Escenario 3:** Obtener detalles de una configuración de proxy elegida

   ![Obtener configuración de proxy](./media/proxy-configurations-3.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Ejemplo***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **Escenario 4:** Eliminar configuraciones de proxy elegidas

   ![Eliminar configuración de proxy](./media/proxy-configurations-4.png)

***Cmdlet***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***Ejemplo***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **Escenario 5:** Actualizar una configuración de proxy

   ![Actualizar configuración de proxy](./media/proxy-configurations-5.png)

***Cmdlet***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***Ejemplo***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>Servicio Web

El **elemento de submenú SERVICIO WEB** en Seguridad permite a los administradores administrar las opciones de configuración de servicios web en toda la organización;  esto incluye la administración de la expansión de grupos, la configuración de certificados y los métodos de autenticación permitidos. Dado que los administradores pueden configurar diferentes configuraciones en el ámbito global, de sitio y de servicio (aunque solo para el servicio de servicios web), se pueden personalizar las capacidades de servicios web para diferentes usuarios y diferentes ubicaciones.

Veamos las distintas tareas que un usuario puede hacer en EL SERVICIO **WEB** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las configuraciones de servicio web

   ![Enumerar la configuración del servicio web](./media/web-service-1.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Ejemplo***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de servicio web

   ![Nueva configuración del servicio web](./media/web-service-2.png)

***Cmdlet***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***Ejemplo***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **Escenario 3:** Obtener detalles de una configuración de servicio web elegida

   ![Obtener configuración del servicio web](./media/web-service-3.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Ejemplo***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar las configuraciones de servicio web elegidas

   ![Eliminar configuración del servicio web](./media/web-service-4.png)

***Cmdlet***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***Ejemplo***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una configuración de servicio web

   ![Actualizar configuración del servicio web](./media/Web-service-5.png)

***Cmdlet***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***Ejemplo***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>Directiva de PIN

Los administradores pueden usar **LA DIRECTIVA de PIN** para administrar las propiedades de autenticación de PIN; por ejemplo, se puede especificar la longitud mínima de un PIN y determinar si se permiten PIN que usan "patrones comunes" como dígitos consecutivos (por ejemplo, un PIN como 123456)

Veamos las distintas tareas que un usuario puede hacer en LA DIRECTIVA de **PIN** y los cmdlets Skype Empresarial a las que se asignan esas tareas.

---

> **Escenario 1:** Enumerar todas las directivas de PIN

   ![Directiva de pin de lista](./media/pin-policy-1.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Ejemplo***

```powershell
 Get-CsPinPolicy
```

---

> **Escenario 2:** Crear una nueva directiva de PIN

   ![Crear directiva de patillas](./media/pin-policy-2.png)

***Cmdlet***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***Ejemplo***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **Escenario 3:** Obtener detalles de una directiva de PIN elegida

   ![Obtener directiva de PIN](./media/pin-policy-3.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Ejemplo***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **Escenario 4:** Eliminar directivas de PIN elegidas

   ![Eliminar directiva de PIN](./media/pin-policy-4.png)

***Cmdlet***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***Ejemplo***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **Escenario 5:** Actualizar una directiva de PIN

   ![Actualizar directiva de PIN](./media/pin-policy-5.png)

***Cmdlet***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***Ejemplo***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
