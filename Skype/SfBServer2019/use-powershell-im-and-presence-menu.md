---
title: Usar PowerShell para tareas en el menú Mi y Presencia
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
description: 'Summary: Skype Empresarial Server Control panel to Cmdlet mapping for IM and Presence menu.'
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888789"
---
# <a name="im-and-presence"></a>Mensajería instantánea y presencia

En este artículo se describe cómo se pueden lograr resultados similares a los del elemento de menú **Mi** y Presencia en el Panel de control heredado mediante cmdlets.

En este artículo se describen los siguientes submenúes:

- [Mensajería instantánea y presencia](#im-and-presence)
  - [Filtro de archivo](#file-filter)
  - [Filtro para direcciones URL](#url-filter)

## <a name="file-filter"></a>Filtro de archivo

**El submenú FILTRO** DE ARCHIVOS permite a los administradores administrar configuraciones de filtro de transferencia de archivos en la organización. Estas configuraciones se usan para bloquear la capacidad de un usuario de transferir determinados tipos de archivos (por ejemplo, archivos con una extensión de archivo .vbs o .ps1) mediante un cliente Skype Empresarial Server.

Veamos las distintas tareas que un usuario puede hacer en **EL FILTRO DE ARCHIVOS** y los cmdlets de Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todos los filtros de archivos

   ![Filtro de archivos de lista](./media/file-filter-1.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Ejemplo***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **Escenario 2:** Crear un nuevo filtro de archivos

   ![Crear filtro de archivos](./media/file-filter-2.png)

***Cmdlet***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***Ejemplo***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Escenario 3:** Obtener detalles de un filtro de archivos elegido

   ![Obtener filtro de archivos](./media/file-filter-3.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Ejemplo***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar filtros de archivos elegidos

   ![Eliminar filtro de archivos](./media/file-filter-4.png)

***Cmdlet***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***Ejemplo***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar un filtro de archivos

   ![Actualizar filtro de archivos](./media/file-filter-5.png)

***Cmdlet***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***Ejemplo***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>Filtro para direcciones URL

El elemento de submenú FILTRO DE DIRECCIONES URL en **MI** y Presencia permite a los administradores configurar el filtro de direcciones **URL** para que los hipervínculos con determinados prefijos se bloqueen o no estén activos. (En otras palabras, los participantes no pueden simplemente hacer clic en el vínculo e ir al sitio al que hace referencia el URI; deben copiar y pegar el vínculo manualmente en un explorador).

Consideremos las distintas tareas que un usuario puede hacer en EL FILTRO de direcciones **URL** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todos los filtros de dirección URL web

   ![Filtro de dirección URL de lista](./media/url-filter-1.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Ejemplo***

```powershell
 Get-CsImFilterConfiguration
```

---

> **Escenario 2:** Crear un nuevo filtro de dirección URL

   ![Nuevo filtro de dirección URL](./media/url-filter-2.png)

***Cmdlet***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***Ejemplo***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Escenario 3:** Obtener detalles de un filtro de dirección URL elegido

   ![Obtener filtro de dirección URL](./media/url-filter-3.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Ejemplo***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar filtros de dirección URL elegidos

   ![Eliminar filtro de dirección URL](./media/url-filter-4.png)

***Cmdlet***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***Ejemplo***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar un filtro de dirección URL

   ![Filtro de dirección URL de actualización](./media/url-filter-5.png)

***Cmdlet***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***Ejemplo***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
