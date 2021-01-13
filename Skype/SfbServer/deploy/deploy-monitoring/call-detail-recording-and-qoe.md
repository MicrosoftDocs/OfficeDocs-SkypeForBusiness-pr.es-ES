---
title: Configurar el registro detallado de llamadas y la calidad de la experiencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Resumen: obtenga información sobre cómo configurar CDR y QoE en Skype Empresarial Server.'
ms.openlocfilehash: dd8611723e3d83f8a4553ba2148ee5ae29791e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802290"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurar el registro detallado de llamadas y la calidad de la experiencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar CDR y QoE en Skype Empresarial Server.
  
Configure la supervisión de CDR y QoE con SQL Server reporting Services para Skype Empresarial Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurar CDR y QoE

Después de asociar un almacén de supervisión con un grupo de servidores front-end, configurar el almacén de supervisión y, a continuación, instalar y configurar SQL Server Reporting Services e informes de supervisión, puede administrar la supervisión del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) mediante el Shell de administración de Skype Empresarial Server. Los cmdlets del Shell de administración de Skype Empresarial Server le permiten habilitar y deshabilitar la supervisión de CDR o QoE para un sitio determinado o para toda la implementación de Skype Empresarial Server; que se puede hacer con un comando tan simple como este:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Al instalar Skype Empresarial Server, también instalará una colección predefinida de opciones de configuración global para CDR y QoE. Los valores predeterminados para algunos de los valores usados más frecuentemente por el Registro de detalles de llamadas se muestran en la siguiente tabla:
  
|**Propiedad**|**Descripción**|**Valor predeterminado**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica si está habilitado o no el CDR. Si se establece en True, se recopilarán y se escribirán todos los registros del CDR en la base de datos de supervisión.  <br/> |Verdadero  <br/> |
|EnablePurging  <br/> |Indica si los registros del CDR se eliminarán o no periódicamente de la base de datos. Si se establece en True, los registros se eliminarán tras el período de tiempo especificado por las propiedades KeepCallDetailForDays (para registros del CDR) y KeepErrorReportForDays (para errores del CDR). Si se define como False, los registros de detalles de llamadas se conservarán indefinidamente.  <br/> |Verdadero  <br/> |
|KeepCallDetailForDays  <br/> |Indica el número de días en que se conservarán los registros del CDR en la base de datos; los registros con mayor antigüedad que el número de días especificados se eliminarán automáticamente. Sin embargo, esto solo ocurrirá si la depuración está habilitada.  <br/> KeepCallDetailForDays puede definirse como cualquier valor entero entre 1 y 2562 días (aproximadamente 7 años).  <br/> |60 días  <br/> |
|KeepErrorReportForDays  <br/> |Indica el número de días que se conservarán los informes de errores del CDR; cualquier informe con una antigüedad superior al número de días especificado se eliminará automáticamente. Los informes de errores de CDR son informes de diagnóstico cargados por aplicaciones cliente como Skype Empresarial Server.  <br/> Puede establecer esta propiedad en cualquier valor entero entre 1 y 2562 días.  <br/> |60 días  <br/> |
   
De manera similar, los valores predeterminados para la configuración de QoE se muestran en esta tabla:
  
|**Propiedad**|**Descripción**|**Valor predeterminado**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica si la supervisión de QoE está o no habilitada. Si se establece en True, todos los registros de QoE se recopilarán y se escribirán en la base de datos de supervisión.  <br/> |Verdadero  <br/> |
|EnablePurging  <br/> |Indica si los registros de QoE se eliminarán periódicamente de la base de datos. Si se establece en True, se eliminarán los registros tras el período de tiempo especificado por la propiedad KeepQoEDataForDays. Si se establece en False, los registros de QoE se mantendrán de manera indefinida.  <br/> |Verdadero  <br/> |
|KeepQoEDataForDays  <br/> |Indica el número de días que los registros de QoE se conservarán en la base de datos; los registros de mayor antigüedad que el número de días especificados se eliminarán automáticamente. Sin embargo, esto solo ocurrirá si la depuración está habilitada.  <br/> KeepCallDetailForDays se puede establecer en cualquier valor entero entre 1 y 2562 días.  <br/> |60 días  <br/> |
   
Si tiene que modificar estos valores globales puede hacerlo mediante los cmdlets Set-CsCdrConfiguration y Set-CsQoEConfiguration. Por ejemplo, este comando (ejecutado desde el Shell de administración de Skype Empresarial Server) deshabilita la supervisión de CDR en el ámbito global; que se realiza estableciendo la propiedad EnableCDR en False ($False):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Tenga en cuenta que la deshabilitación de la supervisión no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala o afecta de otra manera la base de datos de supervisión de back-end. Cuando usa el Shell de administración de Skype Empresarial Server para deshabilitar la supervisión de CDR o QoE, lo único que realmente hace es impedir temporalmente que Skype Empresarial Server recopile y archive los datos de supervisión. Si desea reanudar, en este caso, la colección y el archivado de datos de CDR, todo lo que tiene que hacer es establecer la propiedad EnableCDR de nuevo en True ($True):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

De manera similar, este comando deshabilita la depuración de los registros de QoE en el ámbito global:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Además de la configuración global, los valores de configuración de CDR y QoE se pueden asignar al ámbito de sitio. Esto proporciona flexibilidad de administración adicional en lo referente a la supervisión; por ejemplo, un administrador puede habilitar la supervisión de CDR para el sitio de Redmond pero deshabilitar la supervisión de CDR para el sitio de Dublín. Para crear nuevos valores de configuración de CDR en el ámbito de sitio, use un comando similar al siguiente:
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Tenga en cuenta que los valores configurados en el ámbito del sitio tienen prioridad frente a los valores configurados en el ámbito global. Por ejemplo, supongamos que la supervisión de CDR está habilitada en el ámbito global pero deshabilitada en el ámbito de sitio (para el sitio de Redmond). Eso significa que la información de registro de detalles de llamada no se archivará para usuarios en el sitio de Redmond. Sin embargo, los usuarios de otros sitios (es decir, los usuarios administrados por los valores globales en lugar de la configuración de sitio de Redmond) tendrán su información de registro de detalle de llamada archivada.
  
Los nuevos valores de configuración de QoE se pueden crear en el ámbito de sitio mediante un comando como el siguiente:
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Para obtener más información, escriba los siguientes comandos desde el Shell de administración de Skype Empresarial Server:
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
