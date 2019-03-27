---
title: Planeación de varios números de emergencias en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Lea este tema para obtener información sobre cómo planear para varios números de emergencias en Skype Business Server.
ms.openlocfilehash: e3ecbc039dac510a1ebc5eb989773c1f32c3b6ac
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880766"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planeación de varios números de emergencias en Skype para Business Server
 
Lea este tema para obtener información sobre cómo planear para varios números de emergencias en Skype Business Server.
  
Skype para Business Server ahora admite la configuración de varios números de emergencias para un cliente. Varios números de emergencia es una característica nueva que se introdujo en el de 2016 junio actualización acumulativa. Mientras que los Estados Unidos tiene un único número de emergencia, 911, muchos países admiten varios números de emergencias. El Reino Unido, por ejemplo, admite 999, el número de emergencia específico para el Reino Unido y 112, el número de emergencia para la Unión Europea. 
  
Esta característica también es útil para los proveedores de atención médica dentro de Estados Unidos que desean tener compatibilidad con movilidad para varios números de emergencia código azul.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Varios números de emergencias y las directivas de ubicación

Configurar la llamada de emergencia mediante la creación de la ubicación de las directivas que definen las llamadas de emergencia cómo se implementarán. Usar la directiva de ubicación para definir qué número constituye una llamada de emergencia, por ejemplo, 911 en los Estados Unidos; 999 y 112 en el Reino Unido. La directiva de ubicación determina si un usuario está habilitado para llamadas de emergencia y, si es así, ¿qué es el comportamiento de una llamada de emergencia. También puede definir si se debe notificar automáticamente seguridad corporativa y cómo se debe enrutar la llamada.
  
Para obtener más información sobre cómo definir y modificar una directiva de ubicación, vea [Planear las directivas de ubicación para Skype para Business Server](location-policies.md) y [crear directivas de ubicación en Skype para Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). En estos temas se describen los conceptos acerca de las directivas de ubicación; Sin embargo, debe seguir las instrucciones de [configuración de varios números de emergencias en Skype para la empresa](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) para configurar varios números de emergencias.
  
Al planear para varios números de emergencias, tenga en cuenta lo siguiente:
  
- Con la de 2016 junio actualización acumulativa, puede definir hasta 5 números de emergencias para una directiva de ubicación determinada. Con la noviembre de 2016 actualización acumulativa, este número aumenta hasta 100.
    
    > [!NOTE]
    > Si aún no ha actualizado a la noviembre de 2016 actualización acumulativa, vea [actualizaciones de Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia, que son exclusivas de una directiva de ubicación determinada.
    
    Una máscara de acceso telefónico es un número que se va a traducir en el valor del valor del número marcado de emergencia cuando se marca. Por ejemplo, suponga escribe un valor de 212 en este campo y el campo número de marcado de emergencia tiene un valor de 911. Cuando un usuario marca 212, el número se traducirá a 911. Esto permite que los números de emergencias alternativos se debe marcar y seguir teniendo la llamada llegar a los servicios de emergencia (por ejemplo, si alguien de un país o región con un número diferente de emergencia intenta marcar que país o región del número en vez del número de la país o región que se encuentran actualmente en). Puede definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212; 414. El límite de cadena para una máscara de acceso telefónico es de 100 caracteres. Cada carácter debe ser un dígito de 0 a 9.
    
- Cada directiva de ubicación tiene un uso de único telefónica conmutada (RTC) que se utiliza para determinar qué ruta de voz se usa para enrutar las llamadas de emergencia desde clientes que usen esta directiva. El uso puede tener una ruta única por número de emergencia.
    
- Si tiene una directiva de ubicación los parámetros EmergencyNumbers y DialString definidos tanto el cliente es compatible con varios números de emergencias, a continuación, la emergencia número tiene prioridad. Si el cliente no es compatible con varios números de emergencias, a continuación, se utiliza la cadena de marcado de emergencia.
    
- Para obtener información acerca de qué Skype para empresas y Lync clientes de admitir la recepción de varios números de emergencias, máscaras y usos de telefónica conmutada (RTC) de red de marcado, consulte [Client admitir](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> No se pueden configurar varios números de emergencias mediante el Skype para el Panel de Control. Debe usar PowerShell para configurar varios números de emergencias. 
  
Antes de configurar varios números de emergencias, tenga en cuenta lo siguiente:
  
- Para configurar varios números de emergencias, debe usar el cmdlet New-CsEmergencyNumber, y debe definir las directivas de ubicación que admiten más de un número de emergencia al especificar el parámetro EmergencyNumbers con el [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y Cmdlets [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Si ha definido números de existentes con el cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask, los valores especificados con la EmergencyNumbers parámetro tendrá prioridad sobre el antiguo valores. Es decir, se omitirán los valores de los parámetros EmergencyDialString y EmergencyDialMask.
    
- Si ha definido mediante el Set-CsLocationPolicy o el cmdlet New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask, *y no configure nuevos números de emergencias* , los números existentes se seguirán los números existentes se puede usar.
    
- Para que funcione la característica números de emergencia varios, las versiones del cliente que está ejecutando deben ser capaces de admitir la nueva característica. Los clientes más antiguos seguirán usando los valores anteriores especificados por los cmdlets Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask. 
    
- Si los usuarios estará marcando un número que coincida con la cadena de marcado, no se requiere ninguna máscara de acceso telefónico. Por ejemplo, si marca el número de un usuario es 911, a continuación, la cadena de marcado es 911 y ninguna máscara es obligatorio. 
    
Para obtener más información acerca de cómo configurar varios números de emergencias, consulte [Configurar números de emergencia varios de Skype para la empresa](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
La siguiente tabla muestra las directivas de ubicación de ejemplo (para el ejemplo, se muestran los atributos no todas):
  

|**Nombre de la directiva de ubicación**|**E911 habilitado**|**Cadena de marcado de emergencia**|**Máscara de acceso telefónico**|**Números de emergencia**|**Uso de RTC**|**Ubicación obligatoria**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos  <br/> |Sí  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Sí  <br/> |
|Hospital de Estados Unidos  <br/> |Sí  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sí  <br/> |
|Londres  <br/> |Sí  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112 911; 117; 118  <br/> |GBEmergency  <br/> |No  <br/> |
|India  <br/> |Sí  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |No  <br/> |
   
 **Estados Unidos** : no hay ningún requisito para varios números de emergencias. En los Estados Unidos, utilice las configuraciones de cadena de marcado de emergencia y máscara de acceso telefónico antiguo.
  
 **Hospital de Estados Unidos** : hay un requisito no para enmascarar "450". Para los clientes que todavía no se admiten varios números de emergencias, puede usar las configuraciones de cadena de marcado de emergencia y máscara de acceso telefónico antiguo. Para los clientes que admiten varios números de emergencias, puede definir un número de emergencia para "911" y "450" en lugar de transparencias 450.
  
 **Londres** : para los clientes que todavía no se admiten varios números de emergencias, puede usar las configuraciones de cadena de marcado de emergencia y máscara de acceso telefónico antiguo. Para los clientes que admiten varios números de emergencias, puede definir un número de emergencia para "999" y "112" con máscaras para cada uno.
  
 **India** : todos los clientes implementados admiten varios números de emergencias. En la India, sólo necesita configurar varios números de emergencias.
  
## <a name="client-support"></a>Compatibilidad con clientes
<a name="BKMK_Clients"> </a>

En la siguiente tabla muestra la compatibilidad de cliente para varios números de emergencias. Microsoft seguirá probar y soporte técnico para los clientes adicionales de la versión. Compruebe con frecuencia.

|**Windows**|**Versión**|
|:-----|:-----|
|**Hacer clic y ejecutar** <br/> |CC (canal actual) publicado en 10 de mayo de 2016 - versión 1604 (compilación 6868.2062)  <br/> |
||FRDC (primera versión actual canal) publicado en 14 de junio de 2016 - versión 1605 (compilación 6965.2058)  <br/> |
||DC (canal aplazado) publicado en el 11 de octubre de 2016 - versión 1605 (compilación 6965.2092)  <br/> |
|**MSI** <br/> |Actualización de 7 de junio-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac y iOS** <br/> |**Versión** <br/> |
||Skype para Mac versión de cliente 16,9 de negocio  <br/> Skype para profesionales iOS versión 6.16 del cliente  <br/> |
|**Android** <br/> |**Versión** <br/> |
||Skype para profesionales Android versión de cliente 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Versión** <br/> |
|| Aastra 6721ip y Aastra 6725ip teléfonos - septiembre de 2016 acumulativa actualizan (compilación 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 y HP 4120 teléfonos - septiembre de 2016 la actualización acumulativa (compilación 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Teléfonos Polycom CX500, Polycom CX600 y Polycom CX3000 - septiembre de 2016 la actualización acumulativa (compilación 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

