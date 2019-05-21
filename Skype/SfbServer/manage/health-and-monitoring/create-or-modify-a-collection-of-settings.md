---
title: Crear o modificar una colección de opciones de configuración de CDR en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Resumen: Obtenga información sobre la grabación de detalles de llamadas (CDR) en Skype empresarial Server.'
ms.openlocfilehash: c0a54835fe74a32a92996874cb6fd895fd49fafc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305838"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Crear o modificar una colección de opciones de configuración de CDR en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre la grabación de detalles de llamadas (CDR) en Skype empresarial Server.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.
  
Al instalar Skype empresarial Server, se crea una única colección global de opciones de configuración de CDR. Los administradores también tienen la posibilidad de crear opciones personalizadas en el ámbito del sitio. Cuando estas opciones de ámbito de sitio se usan, tienen prioridad frente a la configuración global. Así, por ejemplo, si crea opciones de ámbito de sitio para el sitio de Redmond, serán las opciones que se usen (y no la configuración global) para administrar el CDR en Redmond.
  
Puede crear parámetros de configuración de CDR con el panel de control de Skype empresarial Server o con el cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Puede usar el panel de control de Skype empresarial Server o el cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para modificar la configuración existente. Si está usando el panel de control de Skype empresarial Server para crear o modificar parámetros, las siguientes opciones estarán disponibles:
  
|**Valor de interfaz de usuario**|**Parámetro de PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|Nombre  <br/> |Identidad  <br/> |Identificador único de los valores de configuración del CDR que se crean. Estos parámetros solo se pueden crear en el ámbito del sitio.  <br/> |
|Habilitar supervisión del CDR  <br/> |EnableCDR  <br/> |Indica si está habilitado el CDR.  <br/> |
|Habilitar la depuración de registros detallados de llamadas (CDR)  <br/> |EnablePurging  <br/> |Indica si los registros del CDR se eliminarán periódicamente de la base de datos del CDR.  <br/> |
|Conservar registros de detalles de llamadas durante un máximo de (días)  <br/> |KeepCallDetailForDays  <br/> |Indica la cantidad de días que los registros del CDR se conservarán en su base de datos correspondiente. Los registros con una antigüedad superior a la cantidad de días especificada se eliminarán automáticamente. Tenga en cuenta que es preciso habilitar la purga para que pueda completarse.  <br/> |
|Conservar los datos de los informes de errores durante el período de duración máximo (días)  <br/> |KeepErrorReportForDays  <br/> |Indica la cantidad de días que se conservarán los informes de errores del CDR. Cualquier informe con una antigüedad superior a la cantidad de días especificado se eliminará automáticamente. Los informes de errores del CDR son informes de diagnóstico que se cargan desde las aplicaciones cliente.  <br/> |
   
> [!NOTE]
> Los cmdlets New-CsCdrConfiguration y set-CsCdrConfiguration incluyen opciones adicionales que no están disponibles en el panel de control de Skype empresarial Server. Para obtener más información, consulta los temas de ayuda [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) y [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para crear la configuración de CDR con el panel de control de Skype empresarial Server

1. En el panel de control de Skype empresarial Server, haga clic en **supervisión y archivado**.
    
2. En la pestaña **grabar detalles** de la llamada, haga clic en **nuevo**.
    
3. En el cuadro de diálogo **Seleccionar un sitio**, seleccione el sitio donde desea crear los nuevos valores de configuración. Si el cuadro de diálogo está vacío, significa que ya se han asignado valores de configuración del CDR a todos los sitios (cada sitio solo puede tener una colección de valores). En tal caso, elimine o vuelva a crear la configuración, o simplemente modifique la configuración actual.
    
4. En el cuadro de diálogo **Nueva configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar la configuración de CDR existente con el panel de control de Skype empresarial Server

1. En el panel de control de Skype empresarial Server, haga clic en **supervisión y archivado**.
    
2. Haga doble clic en la colección de valores que desea modificar o seleccione la colección y haga clic en **Editar** y en **Mostrar detalles**. Tenga en cuenta que solo puede modificar una colección a la vez. Para realizar los mismos cambios en varias colecciones, use el shell de administración de Skype empresarial Server en su lugar.
    
3. En el cuadro de diálogo **Editar configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de opciones de configuración de CDR con cmdlets de Windows PowerShell

Puede crear la configuración de CDR también puede crearse con Windows PowerShell y el cmdlet **New-CsCdrConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Para crear una nueva colección de valores de configuración del CDR:

 Este comando crea una nueva colección de valores de configuración del CDR para el sitio de Redmond:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para crear una colección de valores de configuración del CDR que deshabiliten el registro detallado de llamadas:

 Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de parámetros de configuración de detalle de llamadas que, de forma predeterminada, permita el registro detallado de llamadas, use solo un comando como este:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Para especificar varios valores de propiedad al crear una nueva colección de valores de configuración del CDR:

 Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando configura los nuevos valores para conservar los registros detallados de llamadas durante 30 días y los informes de error durante 90 días:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

