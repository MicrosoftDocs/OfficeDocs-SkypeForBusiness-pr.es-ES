---
title: Usar PowerShell para tareas en el menú Topología
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
description: 'Resumen: Skype Empresarial Server panel de control a asignación de cmdlet para el menú Topología.'
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626483"
---
# <a name="topology"></a>Topología

En este artículo se describe cómo  se pueden obtener resultados similares a los del elemento de menú Topología en el Panel de control heredado mediante cmdlets.

En este artículo se describen los siguientes submenúes:

- [Topología](#topology)
  - [Estado](#status)
  - [Aplicación de servidor](#server-application)
  - [Direcciones URL sencillas](#simple-url)
  - [Aplicación de confianza](#trusted-application)

## <a name="status"></a>Estado

**El** submenú STATUS permite a los administradores administrar los equipos de la topología.

Consideremos las distintas tareas que un usuario puede hacer en **STATUS** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todos los equipos y su estado

   ![Enumerar equipo y estado](./media/topology-status-1.png)

   ***Cmdlet***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***Ejemplo***

   ```powershell
    Get-CsPool
   ```

   ***Cmdlet***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***Ejemplo***

   ```powershell
    Get-CsComputer
   ```

   ***Cmdlet***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***Ejemplo***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>Aplicación de servidor

Las aplicaciones de servidor hacen referencia a los programas individuales que se ejecutan en Skype Empresarial Server. **El** submenú APLICACIÓN DE SERVIDOR proporciona una forma para que los administradores devuelvan información sobre cualquiera (o todas) de las aplicaciones que se ejecutan como parte de Skype Empresarial Server.

Consideremos las distintas tareas que un usuario puede hacer en **SERVER APPLICATION** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las aplicaciones de servidor

   ![Aplicación de servidor de lista](./media/server-application-1.png)

***Cmdlet***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Ejemplo***

```powershell
 Get-CsServerApplication
```

---

> **Escenario 2:** Habilitar/Deshabilitar o seleccionar crítico/ anular la selección crítica de una aplicación de servidor

   ![Editar aplicación de servidor](./media/server-application-2.png)

***Cmdlet***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Ejemplo***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>Direcciones URL sencillas

Las direcciones URL sencillas facilitan a los usuarios unirse a reuniones y conferencias, y también facilitan a los administradores iniciar sesión en el Panel de control de Skype Empresarial Server.El submenú **DIRECCIÓN URL SIMPLE** ayuda al administrador a verlos.

Consideremos las distintas tareas que un usuario puede hacer en la **dirección URL SIMPLE** y los cmdlets Skype Empresarial a las que se asignan esas tareas.

---
> **Escenario 1:** Enumerar todas las configuraciones de dirección URL sencillas

   ![Enumerar dirección URL sencilla](./media/simple-url-1.png)

***Cmdlet***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***Ejemplo***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>Aplicación de confianza

Una aplicación de confianza es una aplicación desarrollada por un tercero que tiene el estado de confianza para ejecutarse como parte de Skype Empresarial Server pero que no es una parte integrada del producto. El **submenú APLICACIÓN DE** CONFIANZA ayuda al administrador a verlos.

Consideremos las distintas tareas que un usuario puede hacer en **TRUSTED APPLICATION** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las aplicaciones de confianza

   ![Enumerar aplicación de confianza](./media/trusted-application-1.png)

***Cmdlet***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***Ejemplo***

```powershell
 Get-CsTrustedApplication
```

---
