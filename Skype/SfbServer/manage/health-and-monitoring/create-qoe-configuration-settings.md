---
title: Crear opciones de configuración de calidad de la experiencia en Skype Empresarial Server
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumen: obtenga información sobre la configuración de calidad de la experiencia (QoE) en Skype Empresarial Server.'
ms.openlocfilehash: 8cce0731112166ae232b6273b556d37d693564e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095354"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Crear opciones de configuración de calidad de la experiencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la configuración de calidad de la experiencia (QoE) en Skype Empresarial Server.
  
Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.
  
Al instalar Skype Empresarial Server, se crea una única colección global de opciones de configuración de QoE. Los administradores pueden también crear una configuración personalizada en el ámbito de sitio. Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global. Por ejemplo, si crea una configuración de ámbito de sitio para el sitio redmond, dicha configuración (en lugar de la configuración global) se usará para administrar QoE en Redmond.
  
Las opciones de configuración de QoE se pueden crear mediante el Panel de control de Skype Empresarial Server o el cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Si usa el Panel de control de Skype Empresarial Server para crear una nueva configuración, estarán disponibles las siguientes opciones:
  
|**Configuración de la interfaz de usuario**|**Parámetro de PowerShell**|**Descripción**|
|:-----|:-----|:-----|
|Nombre  <br/> |Identidad  <br/> |Identificador único de la configuración que se va a crear. Las opciones de configuración de QoE solo se pueden crear en el ámbito del sitio.  <br/> |
|Habilitar la supervisión de datos de QoE  <br/> |EnableQoE  <br/> |Especifica si los registros QoE se recopilarán y guardarán en la base de datos de supervisión.  <br/> |
|Habilitar la depuración de datos de QoE  <br/> |EnablePurging  <br/> |Especifica si los registros se purgarán después de que haya transcurrido la duración definida en los datos **de Keep QoE** para una propiedad de duración máxima (días). <br/> |
|Conservar los datos de QoE durante la duración máxima (días)  <br/> |KeepQoEDataForDays  <br/> |Número de días que se almacenarán los datos de QoE antes de purgarse de la base de datos. Este valor se omite si la depuración está deshabilitada.  <br/> |
   
> [!NOTE]
> El cmdlet New-CsQoEConfiguration incluye opciones adicionales que no están disponibles en el Panel de control de Skype Empresarial Server. Para obtener más información, vea el tema de ayuda [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para crear opciones de configuración de QoE mediante el Panel de control de Skype Empresarial Server

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol CsVoiceAdministrator, CsServerAdministrator, o CsAdministrator. Para obtener información detallada, consulte **Delegación de permisos de instalación**.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.
    
4. En la **página Datos de calidad de** la experiencia, haga clic en **Nuevo**.
    
5. En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva y haga clic en **Aceptar**.
    
6. En **Nueva configuración de calidad de la experiencia,** haga lo siguiente:
    
   - Seleccione **Habilitar la supervisión de los datos de QoE** para activar la supervisión.
    
   - Seleccione **Habilitar la depuración de datos de QoE** para activar la depuración.
    
   - En **Mantener QoE durante la duración máxima (días),** seleccione el número máximo de días que deben conservarse los registros de QoE.
    
7. Haga clic en **Confirmar**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de opciones de configuración de QoE mediante Windows PowerShell cmdlets

Puede crear opciones de configuración de QoE mediante Windows PowerShell y el cmdlet New-CsQoEConfiguration. Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para crear una nueva colección de opciones de configuración de QoE

 Este comando crea una nueva colección de opciones de configuración de QoE aplicadas al sitio Redmond:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para crear una nueva colección de opciones de configuración de QoE donde está deshabilitada la supervisión de QoE

 Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de opciones de configuración de Calidad de la experiencia que, de forma predeterminada, permitan deshabilitar la grabación de QoE, use un comando como este:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar varios valores de propiedad al crear una nueva colección de opciones de configuración de QoE

 Puede incluir varios valores de propiedad al incluir varios parámetros. Por ejemplo, este comando configura la nueva configuración para mantener los datos de QoE durante 30 días y para purgar datos antiguos a las 3:00 a.m.:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
