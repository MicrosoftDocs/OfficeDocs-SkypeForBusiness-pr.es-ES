---
title: Usar PowerShell para tareas en el menú Supervisión y archivado
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
description: 'Summary: Skype Empresarial Server Control panel to Cmdlet mapping for Monitoring and Archiving menu.'
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626484"
---
# <a name="monitoring-and-archiving"></a>Supervisión y archivado

En este artículo se describe cómo  se pueden lograr resultados similares a los del elemento de menú Supervisión y archivado del Panel de control heredado mediante cmdlets.

En este artículo se describen los siguientes submenúes:

- [Supervisión y archivado](#monitoring-and-archiving)
  - [Registro de detalles de llamadas](#call-detail-recording)
  - [Datos de calidad de la experiencia](#quality-of-experience-data)
  - [Directiva de archivado](#archiving-policy)
  - [Configuración de archivado](#archiving-configuration)

## <a name="call-detail-recording"></a>Registro de detalles de llamadas

**El submenú REGISTRO DE DETALLES** DE LLAMADAS permite a los administradores administrar la configuración de grabación de detalles de llamadas (CDR). Cdr le permite realizar un seguimiento del uso de cosas como sesiones de mensajería instantánea punto a punto, llamadas telefónicas de voz sobre protocolo de Internet (VoIP) y llamadas de conferencia.

Veamos las distintas tareas que un usuario puede hacer en **REGISTRO** DE DETALLES DE LLAMADAS y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las configuraciones de CDR

   ![Configuración de cdr de lista](./media/cdr-configurations-1.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Ejemplo***

```powershell
 Get-CsCdrConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de CDR

   ![Crear configuración de Cdr](./media/cdr-configurations-2.png)

***Cmdlet***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***Ejemplo***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **Escenario 3:** Obtener detalles de una configuración de CDR elegida

   ![Obtener configuración de Cdr](./media/cdr-configurations-3.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Ejemplo***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar configuraciones de CDR elegidas

   ![Eliminar configuración de Cdr](./media/cdr-configurations-4.png)

***Cmdlet***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***Ejemplo***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una configuración de CDR

   ![Actualizar configuración de Cdr](./media/cdr-configurations-5.png)

***Cmdlet***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***Ejemplo***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>Datos de calidad de la experiencia

El **submenú QUALITY OF EXPERIENCE DATA** permite a los administradores administrar la configuración de calidad de la experiencia (QoE). en toda la organización; esto incluye la administración de la expansión de grupos, la configuración de certificados y los métodos de autenticación permitidos. Dado que los administradores pueden configurar diferentes configuraciones en el ámbito global, de sitio y de servicio (aunque solo para el servicio de servicios web), se pueden personalizar las capacidades de servicios web para diferentes usuarios y diferentes ubicaciones.

Veamos las distintas tareas que un usuario puede hacer en EL SERVICIO **WEB** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las configuraciones de QoE

   ![Enumerar configuración de QoE](./media/qoe-configuration-1.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Ejemplo***

```powershell
 Get-CsQoEConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de QoE

   ![Nueva configuración de QoE](./media/qoe-configuration-2.png)

***Cmdlet***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***Ejemplo***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **Escenario 3:** Obtener detalles de una configuración de QoE elegida

   ![Obtener configuración de QoE](./media/qoe-configuration-3.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Ejemplo***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar las configuraciones de QoE elegidas

   ![Eliminar configuración de QoE](./media/qoe-configuration-4.png)

***Cmdlet***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***Ejemplo***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una configuración de QoE

   ![Actualizar configuración de QoE](./media/qoe-configuration-5.png)

***Cmdlet***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***Ejemplo***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>Directiva de archivado

Los administradores pueden usar **LA DIRECTIVA DE ARCHIVADO** para administrar directivas de archivado de sesiones de mensajería instantánea (MI). Las directivas de archivado permiten archivar todas las sesiones de mensajería instantánea y conferencia web que tienen lugar entre usuarios internos y/o entre usuarios internos y usuarios externos

Consideremos las distintas tareas que un usuario puede hacer en **LA** DIRECTIVA DE ARCHIVADO y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las directivas de archivado

   ![Directiva de archivado de listas](./media/archiving-policy-1.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Ejemplo***

```powershell
 Get-CsArchivingPolicy
```

---

> **Escenario 2:** Crear una nueva directiva de archivado

   ![Crear directiva de archivado](./media/archiving-policy-2.png)

***Cmdlet***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***Ejemplo***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **Escenario 3:** Obtener detalles de una directiva de archivado elegida

   ![Obtener directiva de archivado](./media/archiving-policy-3.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Ejemplo***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar directivas de archivado elegidas

   ![Eliminar directiva de archivado](./media/archiving-policy-4.png)

***Cmdlet***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***Ejemplo***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una directiva de archivado

   ![Actualizar directiva de archivado](./media/archiving-policy-5.png)

***Cmdlet***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***Ejemplo***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>Configuración de archivado

Los administradores pueden usar **LA CONFIGURACIÓN DE ARCHIVADO** para configurar cómo (o si) se archivan las sesiones de mensajería instantánea (MI) en la organización.

Veamos las distintas tareas que un usuario puede hacer en **CONFIGURACIÓN** DE ARCHIVADO y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las configuraciones de archivado

   ![Configuración de archivado de listas](./media/archiving-configuration-1.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Ejemplo***

```powershell
 Get-CsArchivingConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de archivado

   ![Crear configuración de archivado](./media/archiving-configuration-2.png)

***Cmdlet***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***Ejemplo***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **Escenario 3:** Obtener detalles de una configuración de archivado elegida

   ![Obtener configuración de archivado](./media/archiving-configuration-3.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Ejemplo***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar las configuraciones de archivado elegidas

   ![Eliminar configuración de archivado](./media/archiving-configuration-4.png)

***Cmdlet***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***Ejemplo***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una configuración de archivado

   ![Actualizar configuración de archivado](./media/archiving-configuration-5.png)

***Cmdlet***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***Ejemplo***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
