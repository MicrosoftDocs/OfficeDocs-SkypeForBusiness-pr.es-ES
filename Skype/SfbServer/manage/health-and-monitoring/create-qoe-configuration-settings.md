---
title: Crear opciones de configuración de calidad de la experiencia en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumen: Obtenga información sobre la configuración de calidad de la experiencia (QoE) en Skype para Business Server.'
ms.openlocfilehash: aef6ff9f981af92427bbc3b6d276b2fdefb45616
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926637"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Crear opciones de configuración de calidad de la experiencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre la configuración de calidad de la experiencia (QoE) en Skype para Business Server.
  
Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.
  
Al instalar Skype para Business Server, una única colección global de opciones de configuración de QoE se crea para usted. Los administradores también tienen la posibilidad de crear opciones personalizadas en el ámbito del sitio. Cuando estas opciones de ámbito de sitio se usan, tienen prioridad frente a la configuración global. Así, por ejemplo, si crea opciones de ámbito de sitio para el sitio de Redmond, serán las opciones que se usen (y no la configuración global) para administrar la calidad de la experiencia en Redmond.
  
Configuración de QoE se puede crear mediante el uso de ambos Skype para el Panel de Control de servidor empresarial o el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) . Si usa Skype para el Panel de Control de servidor empresarial para crear opciones de las siguientes opciones estarán disponibles para usted:
  
|**Valor de interfaz de usuario**|**Parámetro de PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|Nombre  <br/> |Identidad  <br/> |Identificador único de la opción que se va a crear. La opción de configuración de QoE solo se puede crear en el ámbito del sitio.  <br/> |
|Habilitar supervisión de datos de calidad de la experiencia (QoE)  <br/> |EnableQoE  <br/> |Especifica si los registros QoE se recopilarán y guardarán en la base de datos de supervisión.  <br/> |
|Habilitar purgado de datos de calidad de la experiencia (QoE)  <br/> |EnablePurging  <br/> |Especifica si los registros se van a purgar una vez transcurrida la duración definida en la propiedad **Conservar datos de QoE durante el período de duración máximo (días)**. <br/> |
|Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)  <br/> |KeepQoEDataForDays  <br/> |Cantidad de días en que los datos de QoE se almacenarán antes de que se purguen de la base de datos. Este valor se ignora si el purgado está deshabilitado.  <br/> |
   
> [!NOTE]
> El cmdlet New-CsQoEConfiguration incluye opciones adicionales no está disponibles en Skype para el Panel de Control de servidor empresarial. Para obtener más información, vea el tema de Ayuda de [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para crear opciones de configuración de QoE mediante Skype para el Panel de Control de servidor empresarial

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.
    
4. En la página **Datos de calidad de la experiencia**, haga clic en **Nuevo**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que va a aplicar la directiva y, luego, en **Aceptar**.
    
6. En **Nueva configuración de calidad de la experiencia**, haga lo siguiente:
    
   - Seleccione **Habilitar supervisión de datos de calidad de la experiencia (QoE)** para activar la supervisión.
    
   - Seleccione **Habilitar purgado de datos de calidad de la experiencia (QoE)** para activar el purgado.
    
   - En **Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)**, seleccione la cantidad máxima de días durante la que se tienen que conservar los registros de QoE.
    
7. Haga clic en **Confirmar**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de opciones de configuración de QoE mediante Cmdlets de Windows PowerShell

Puede crear opciones de configuración de QoE mediante el uso de Windows PowerShell y el cmdlet New-CsQoEConfiguration. Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para crear una colección de opciones de configuración de QoE

 Con este comando se crea una colección de opciones de configuración de QoE para usarla en el sitio de Redmond:
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para crear una colección de opciones de configuración de QoE cuando la supervisión de QoE está deshabilitada

 Dado que en el comando anterior no se ha especificado ningún parámetro (aparte del obligado Identity), la nueva colección de opciones de configuración usará los valores predeterminados en todas sus propiedades. Para crear opciones que usen otros valores de propiedad, bastará con incluir el parámetro y los valores que sean adecuados. Por ejemplo, use un comando como el siguiente para crear una colección de opciones de configuración de calidad de la experiencia que permita deshabilitar el registro de QoE de forma predeterminada:
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar varios valores de propiedad al crear una colección de opciones de configuración de QoE

 Si desea especificar varios valores de propiedad, es preciso incluir varios parámetros. Por ejemplo, con este comando se configuran nuevas opciones que permiten conservar los datos de QoE durante 30 días y purgar los datos antiguos a las 3:00 AM:
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  

