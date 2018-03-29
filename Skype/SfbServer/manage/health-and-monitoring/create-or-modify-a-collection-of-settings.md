---
title: Crear o modificar una colección de opciones de configuración de CDR en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Resumen: Conozca detalles de llamadas (CDR) de grabación en Skype para Business Server 2015.'
ms.openlocfilehash: 9861c3e2fba0f601e47e093a664999052d128f95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server-2015"></a>Crear o modificar una colección de opciones de configuración de CDR en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información acerca de detalles de llamadas (CDR) de grabación en Skype para Business Server 2015.
  
El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y su duración.
  
Al instalar Skype para Business Server 2015 un único, colección global CDR de opciones de configuración se crea para usted. Los administradores también tienen la posibilidad de crear opciones personalizadas en el ámbito del sitio. Cuando estas opciones de ámbito de sitio se usan, tienen prioridad frente a la configuración global. Así, por ejemplo, si crea opciones de ámbito de sitio para el sitio de Redmond, serán las opciones que se usen (y no la configuración global) para administrar el CDR en Redmond.
  
Puede crear valores de configuración de CDR mediante cualquier Skype para Panel de Control de servidor de negocios o el cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Puede utilizar Skype para Panel de Control de servidor de negocios o el cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para modificar la configuración existente. Si utiliza Skype para Business Server Control Panel para crear o modificar la configuración, las siguientes opciones estarán disponibles para usted:
  
|**Configuración de la interfaz de usuario**|**Parámetro de PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|Nombre  <br/> |Identidad  <br/> |Identificador único de los valores de configuración del CDR que se crean. Estos parámetros solo se pueden crear en el ámbito del sitio.  <br/> |
|Habilitar supervisión del CDR  <br/> |EnableCDR  <br/> |Indica si está habilitado el CDR.  <br/> |
|Habilitar la depuración de registros detallados de llamadas (CDR)  <br/> |EnablePurging  <br/> |Indica si los registros del CDR se eliminarán periódicamente de la base de datos del CDR.  <br/> |
|Conservar registros de detalles de llamadas durante un máximo de (días)  <br/> |KeepCallDetailForDays  <br/> |Indica la cantidad de días que los registros del CDR se conservarán en su base de datos correspondiente. Los registros con una antigüedad superior a la cantidad de días especificada se eliminarán automáticamente. Tenga en cuenta que es preciso habilitar la purga para que pueda completarse.  <br/> |
|Conservar los datos de los informes de errores durante el período de duración máximo (días)  <br/> |KeepErrorReportForDays  <br/> |Indica la cantidad de días que se conservarán los informes de errores del CDR. Cualquier informe con una antigüedad superior a la cantidad de días especificado se eliminará automáticamente. Los informes de errores del CDR son informes de diagnóstico que se cargan desde las aplicaciones cliente.  <br/> |
   
> [!NOTE]
> Los cmdlets New-CsCdrConfiguration y CsCdrConfiguration del conjunto incluyen opciones adicionales no están disponibles en Skype para Panel de Control de servidor empresarial. Consulte la [CsCdrConfiguration de nuevo](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) y los temas de Ayuda de [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para obtener más información.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para crear opciones de configuración de CDR mediante Skype para Panel de Control de servidor empresarial

1. En Skype para Business Server Control Panel, haga clic en **supervisión y archivado**.
    
2. En la ficha **Llamar al registro de detalles** , haga clic en **nuevo**.
    
3. En el cuadro de diálogo **Seleccionar un sitio**, seleccione el sitio donde desea crear los nuevos valores de configuración. Si el cuadro de diálogo está vacío, significa que ya se han asignado valores de configuración del CDR a todos los sitios (cada sitio solo puede tener una colección de valores). En tal caso, elimine o vuelva a crear la configuración, o simplemente modifique la configuración actual.
    
4. En el cuadro de diálogo **Nueva configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar opciones de configuración de CDR existentes mediante Skype para Panel de Control de servidor de Business

1. En Skype para Business Server Control Panel, haga clic en **supervisión y archivado**.
    
2. Haga doble clic en la colección de valores que desea modificar o seleccione la colección y haga clic en **Editar** y en **Mostrar detalles**. Tenga en cuenta que solo puede modificar una colección a la vez. Para realizar los mismos cambios a varias colecciones, utilice el Skype para el Shell de administración de servidor empresarial.
    
3. En el cuadro de diálogo **Editar configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de opciones de configuración de CDR mediante Cmdlets de Windows PowerShell

Puede crear configuración de CDR configuración también pueden crearse mediante el uso de Windows PowerShell y el cmdlet **New-CsCdrConfiguration** . Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
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

Para obtener más información, vea el tema de ayuda para el cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

