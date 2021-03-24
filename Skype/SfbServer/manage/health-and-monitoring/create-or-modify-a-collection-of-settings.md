---
title: Crear o modificar una colección de opciones de configuración de CDR en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Resumen: obtenga información sobre la grabación detallada de llamadas (CDR) en Skype Empresarial Server.'
ms.openlocfilehash: da4383ef31b2d3ee781c445f2c935b79ea89bed8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095374"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Crear o modificar una colección de opciones de configuración de CDR en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la grabación detallada de llamadas (CDR) en Skype Empresarial Server.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y la duración de la misma.
  
Al instalar Skype Empresarial Server, se crea automáticamente una colección global de opciones de configuración de CDR. Los administradores pueden también crear una configuración personalizada en el ámbito de sitio. Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global. Por ejemplo, si crea una configuración cuyo ámbito es el sitio para el sitio de Redmond, se usará dicha configuración (en lugar de la configuración global) para administrar el CDR de Redmond.
  
Puede crear opciones de configuración de CDR mediante el Panel de control de Skype Empresarial Server o el cmdlet [New-CsCdrConfiguration.](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Puede usar el Panel de control de Skype Empresarial Server o el cmdlet [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para modificar la configuración existente. Si usa el Panel de control de Skype Empresarial Server para crear o modificar la configuración, estarán disponibles las siguientes opciones:
  
|**Configuración de la interfaz de usuario**|**Parámetro de PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|Nombre  <br/> |Identidad  <br/> |Identificador único de los valores de configuración del CDR que se crean. Estos parámetros solo se pueden crear en el ámbito del sitio.  <br/> |
|Habilitar supervisión del CDR  <br/> |EnableCDR  <br/> |Indica si está o no habilitado el CDR.  <br/> |
|Habilitar depuración de registros de detalles de llamadas (CDR)  <br/> |EnablePurging  <br/> |Indica si los registros del CDR se eliminarán periódicamente de su base de datos correspondiente.  <br/> |
|Conservar registros de detalles de llamadas durante un máximo de (días)  <br/> |KeepCallDetailForDays  <br/> |Indica el número de días que los registros del CDR se conservarán en su base de datos correspondiente. Los registros con una antigüedad superior al número de días especificado se eliminarán automáticamente. Tenga en cuenta que debe habilitar la purga para que pueda completarse.  <br/> |
|Conservar los datos de los informes de errores durante el período de duración máximo (días)  <br/> |KeepErrorReportForDays  <br/> |Indica el número de días que se conservarán los informes de errores del CDR. Cualquier informe con una antigüedad superior al número de días especificado se eliminará automáticamente. Los informes de errores del CDR son informes de diagnóstico que se cargan desde las aplicaciones cliente.  <br/> |
   
> [!NOTE]
> Los cmdlets New-CsCdrConfiguration y Set-CsCdrConfiguration incluyen opciones adicionales que no están disponibles en el Panel de control de Skype Empresarial Server. Vea los [temas de ayuda New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) y [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para obtener más información.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para crear opciones de configuración de CDR mediante el Panel de control de Skype Empresarial Server

1. En el Panel de control de Skype Empresarial Server, haga clic **en Supervisión y archivado.**
    
2. En la **pestaña Registro detallado de llamadas,** haga clic en **Nuevo**.
    
3. En el cuadro de diálogo **Seleccionar un sitio**, seleccione el sitio donde desea crear los nuevo valores de configuración. Si el cuadro de diálogo está vacío, significa que ya se han asignado valores de configuración del CDR a todos los sitios (cada sitio solo puede tener una colección de valores). En tal caso, elimine o vuelva a crear la configuración, o simplemente modifique la configuración actual.
    
4. En el cuadro de diálogo **Nueva configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar las opciones de configuración de CDR existentes mediante el Panel de control de Skype Empresarial Server

1. En el Panel de control de Skype Empresarial Server, haga clic **en Supervisión y archivado.**
    
2. Haga doble clic en la colección de valores que desea modificar, o seleccione la colección, y haga clic en **Editar** y en **Mostrar detalles**. Tenga en cuenta que solo puede modificar una colección a la vez. Para realizar los mismos cambios en varias colecciones, use el Shell de administración de Skype Empresarial Server en su lugar.
    
3. En el cuadro de diálogo **Editar configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de opciones de configuración de CDR mediante cmdlets Windows PowerShell cdr

También puede crear opciones de configuración de CDR mediante Windows PowerShell y el cmdlet **New-CsCdrConfiguration.** Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Para crear una nueva colección de valores de configuración del CDR:

 Este comando crea una nueva colección de valores de configuración del CDR para el sitio de Redmond:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para crear una colección de valores de configuración del CDR que deshabiliten el registro detallado de llamadas:

 Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de parámetros de configuración de detalle de llamadas que, de forma predeterminada, permita el registro detallado de llamadas, use solo un comando como este:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Para especificar varios valores de propiedad al crear una nueva colección de valores de configuración del CDR:

 Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando configura los nuevos valores para conservar los registros detallados de llamadas durante 30 días y los informes de error durante 90 días:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Para obtener más información, vea el tema de ayuda del cmdlet [New-CsCdrConfiguration.](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)
