---
title: Configurar los detalles de las llamadas y la configuración de calidad de la experiencia en Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Resumen: Obtenga información sobre cómo configurar CDR y QoE en Skype para Business Server 2015.'
ms.openlocfilehash: 0d5a6ba25a524578a13f16c92149977b0180fbdb
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569460"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server-2015"></a>Configurar los detalles de las llamadas y la configuración de calidad de la experiencia en Skype para Business Server 2015
 
**Resumen:** Obtenga información sobre cómo configurar CDR y QoE en Skype para Business Server 2015.
  
Configuración de CDR y QoE monitoring uso de informes de SQL Server Reporting Services para Skype para Business Server 2015.
  
## <a name="configure-cdr-and-qoe"></a>Configurar CDR y QoE

Después de que se ha asociado un almacén de supervisión a un grupo de servidores Front-End, configurar el almacén de supervisión y, a continuación, instalado y configurado SQL Server Reporting Services y los informes de supervisión puede administrar registro de detalles de llamadas (CDR) y la calidad de la experiencia (QoE) supervisión mediante el uso de Skype para Shell de administración de servidor empresarial. Skype para los cmdlets del Shell de administración de servidor empresarial le permiten habilitar y deshabilitar CDR y/o QoE monitoring para un sitio concreto o para su Skype completo para la implementación de Business Server; que se puede realizar con un proceso tan sencillo como este comando:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Al instalar Skype para Business Server 2015, también se instalará una colección predefinida de opciones de configuración global de CDR y QoE. En la siguiente tabla se muestran los valores predeterminados para algunos de los valores usados más frecuentemente por el registro detallado de llamadas:
  
|**Propiedad**|**Descripción**|**Valor predeterminado**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica si está habilitado o no el CDR. Si se establece en True, se recopilarán y se escribirán todos los registros del CDR en la base de datos de supervisión.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica si los registros del CDR se eliminarán o no periódicamente de la base de datos. Si se establece en True, los registros se eliminarán tras el período de tiempo especificado por las propiedades KeepCallDetailForDays (para registros del CDR) y KeepErrorReportForDays (para errores del CDR). Si se define como False, los registros detallados de llamadas se conservarán indefinidamente.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |Indica la cantidad de días que se conservarán los registros del CDR en la base de datos; los registros con mayor antigüedad que la cantidad de días especificada se eliminarán automáticamente. Pero, esto solo ocurrirá si la depuración está habilitada.  <br/> KeepCallDetailForDays puede definirse como cualquier valor entero entre 1 y 2562 días (aproximadamente 7 años).  <br/> |60 días  <br/> |
|KeepErrorReportForDays  <br/> |Indica la cantidad de días que se conservarán los informes de errores del CDR; cualquier informe con una antigüedad superior a la cantidad de días especificada se eliminará automáticamente. Informes de errores de CDR son informes de diagnóstico cargados por las aplicaciones de cliente como Skype para Business Server 2015.  <br/> Puede establecer esta propiedad en cualquier valor entero entre 1 y 2562 días.  <br/> |60 días  <br/> |
   
De manera similar, los valores predeterminados para la configuración de QoE se muestran en esta tabla:
  
|**Propiedad**|**Descripción**|**Valor predeterminado**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica si la supervisión de QoE está o no habilitada. Si se establece en True, todos los registros de QoE se recopilarán y se escribirán en la base de datos de supervisión.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica si los registros de QoE se eliminarán periódicamente de la base de datos. Si se establece en True, se eliminarán los registros tras el período de tiempo especificado por la propiedad KeepQoEDataForDays. Si se establece en False, los registros de QoE se mantendrán de manera indefinida.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Indica la cantidad de días que los registros de QoE se conservarán en la base de datos; los registros de mayor antigüedad que la cantidad de días especificada se eliminarán automáticamente. Pero, esto solo ocurrirá si la depuración está habilitada.  <br/> KeepCallDetailForDays se puede establecer en cualquier valor entero entre 1 y 2562 días.  <br/> |60 días  <br/> |
   
Si tiene que modificar estos valores globales puede hacerlo con los cmdlets Set-CsCdrConfiguration y Set-CsQoEConfiguration. Por ejemplo, este comando (ejecutar desde dentro de la Skype para Shell de administración de servidor empresarial) deshabilita a CDR supervisión en el ámbito global; que se realiza mediante la configuración de la propiedad EnableCDR en False ($False):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Tenga en cuenta que la deshabilitación de la supervisión no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala o afecta de otra manera la base de datos de supervisión de back-end. Cuando se usa Skype para Shell de administración de servidor empresarial para deshabilitar CDR o QoE monitoring todo lo que realmente hacer es impedir temporalmente que Skype para Business Server desde la recopilación y el archivado de datos de supervisión. Si desea reanudar, en este caso, la colección y el archivado de datos de CDR, lo único que tiene que hacer es establecer la propiedad EnableCDR de nuevo en True ($True):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

De manera similar, este comando deshabilita la depuración de los registros de QoE en el ámbito global:
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Además de la configuración global, los valores de configuración de CDR y QoE se pueden asignar al ámbito de sitio. Esto proporciona flexibilidad de administración adicional en lo referente a la supervisión; por ejemplo, un administrador puede habilitar la supervisión de CDR para el sitio de Redmond pero deshabilitar la supervisión de CDR para el sitio de Dublín. Para crear nuevos valores de configuración de CDR en el ámbito de sitio, use un comando similar al siguiente:
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Tenga en cuenta que los valores configurados en el ámbito del sitio tienen prioridad frente a los valores configurados en el ámbito global. Por ejemplo, supongamos que la supervisión de CDR está habilitada en el ámbito global pero deshabilitada en el ámbito de sitio (para el sitio de Redmond). Eso significa que la información del registro detallado de llamadas no se archivará para usuarios en el sitio de Redmond. Pero, los usuarios de otros sitios (es decir, los usuarios administrados por los valores globales en lugar de la configuración de sitio de Redmond) tendrán su información del registro detallado de llamadas archivada.
  
Los nuevos valores de configuración de QoE se pueden crear en el ámbito de sitio con un comando como el siguiente:
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Para obtener más información, escriba los siguientes comandos desde dentro de la Skype para Shell de administración de servidor empresarial:
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```