---
title: Planear varios números de emergencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Lea este tema para obtener información sobre cómo planear varios números de emergencia en Skype empresarial Server.
ms.openlocfilehash: 43214e42e4fd998aef673ad8d0fbd57ec2d3b498
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276848"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planear varios números de emergencia en Skype empresarial Server
 
Lea este tema para obtener información sobre cómo planear varios números de emergencia en Skype empresarial Server.
  
Skype empresarial Server ahora es compatible con la configuración de varios números de emergencia para un cliente. Varios números de emergencia es una nueva característica introducida en la actualización acumulativa de 2016 de junio. Mientras que Estados Unidos tiene un único número de emergencia, 911, muchos países admiten varios números de emergencia. Por ejemplo, el Reino Unido admite 999, el número de emergencia específico para el Reino Unido y 112, el número de emergencia de la Unión Europea. 
  
Esta característica también es útil para proveedores de atención de la salud dentro de los Estados Unidos que deseen tener soporte de itinerancia para números de emergencia de código azul.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Varios números de emergencia y políticas de ubicación

Para configurar las llamadas de emergencia, puede crear directivas de ubicación que definan cómo se implementarán las llamadas de emergencia. Usted usa la política de ubicación para definir qué número constituye una llamada de emergencia, por ejemplo, 911 en los Estados Unidos; 999 y 112 en el Reino Unido. La Directiva de ubicación determina si un usuario está habilitado para realizar llamadas de emergencia y, si es así, cuál es el comportamiento de una llamada de emergencia. También puede definir si se debe notificar automáticamente la seguridad corporativa y cómo debe dirigirse la llamada.
  
Para obtener más información sobre cómo definir y modificar una directiva de ubicación, consulte [planificar directivas de ubicación para Skype empresarial Server](location-policies.md) y [crear directivas de ubicación en Skype empresarial Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Estos temas describen conceptos acerca de las directivas de ubicación; sin embargo, debe seguir las instrucciones de [configurar varios números de emergencia en Skype empresarial](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) para configurar varios números de emergencia.
  
Cuando planee varios números de emergencia, tenga en cuenta lo siguiente:
  
- Con la actualización acumulativa de junio de 2016, puedes definir hasta 5 números de emergencia para una política de ubicación determinada. Con la actualización acumulativa de noviembre de 2016, este número aumenta a 100.
    
    > [!NOTE]
    > Si aún no ha actualizado a la actualización acumulativa de noviembre de 2016, consulte [actualizaciones de Skype empresarial Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Para cada número de emergencia, puedes especificar cero o más máscaras de marcado de emergencia, que son exclusivas de una política de ubicación determinada.
    
    Una máscara de marcado es un número que desea traducir en el valor del valor de número de marca de emergencia cuando se marca. Por ejemplo, supongamos que escribe un valor de 212 en este campo y el campo número de marca de emergencia tiene un valor de 911. Cuando un usuario marca 212, el número se convierte en 911. Esto permite que se marquen números de emergencia alternativos y siga haciendo que las llamadas lleguen a servicios de emergencia (por ejemplo, si alguien de un país o región con un número de emergencia diferente intenta marcar el número de ese país o región en lugar del número de la país o región en el que se encuentran actualmente). Puede definir varias máscaras de marcado de emergencia si separa los valores con signos de punto y coma. Por ejemplo, 212; 414. El límite de cadenas para una máscara de marcado es de 100 caracteres. Cada carácter debe ser un dígito del 0 al 9.
    
- Cada política de ubicación tiene un uso de una sola red telefónica conmutada (RTC) que se usa para determinar qué ruta de voz se usa para enrutar llamadas de emergencia de clientes que usen esta Directiva. El uso puede tener una ruta única por número de emergencia.
    
- Si una directiva de ubicación tiene definidos los parámetros EmergencyNumbers y DialString, y el cliente admite varios números de emergencia, tendrá prioridad el número de emergencia. Si el cliente no admite varios números de emergencia, se usa la cadena de marcado de emergencia.
    
- Para obtener información sobre qué clientes de Skype empresarial y de Lync admiten la recepción de varios números de emergencia, máscaras de marcado y usos de la red telefónica conmutada (RTC), consulte [compatibilidad con clientes](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> No puedes configurar varios números de emergencia con el panel de control de Skype para empresas. Debe usar PowerShell para configurar varios números de emergencia. 
  
Antes de configurar varios números de emergencia, tenga en cuenta lo siguiente:
  
- Para configurar varios números de emergencia, debe usar el cmdlet New-CsEmergencyNumber y debe definir directivas de ubicación que admitan más de un número de emergencia especificando el parámetro EmergencyNumbers con el [nuevo-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y Cmdlet [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Si tiene números definidos con el cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask, los valores especificados con el parámetro EmergencyNumbers tendrán prioridad sobre el antiguo los. Es decir, se ignorarán los valores de los parámetros EmergencyDialString y EmergencyDialMask.
    
- Si tiene números definidos con el cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask, *y no configura nuevos números de emergencia* , los números existentes continuarán usarse.
    
- Para que la característica de varios números de emergencia funcione, las versiones de cliente que esté ejecutando deben poder admitir la nueva característica. Los clientes más antiguos seguirán usando los valores antiguos especificados por los cmdlets Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask. 
    
- Si los usuarios van a marcar un número que coincide con la cadena de marcación, no es necesaria ninguna máscara de marcado. Por ejemplo, si el número al que un usuario marca es 911, la cadena de marcado es 911 y no se necesita ninguna máscara. 
    
Para obtener más información sobre cómo configurar varios números de emergencia, consulte [configurar varios números de emergencia en Skype empresarial](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
En la tabla siguiente se muestran las directivas de ubicación de ejemplo (para los fines del ejemplo, no se muestran todos los atributos):
  

|**Nombre de la Directiva de ubicación**|**E911 habilitado**|**Cadena de marcado de emergencia**|**Máscara de marcado**|**Números de emergencia**|**Uso de RTC**|**Ubicación requerida**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos  <br/> |Sí  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Sí  <br/> |
|Estados Unidos-Hospital  <br/> |Sí  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sí  <br/> |
|Londres  <br/> |Sí  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |No  <br/> |
|India  <br/> |Sí  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |No  <br/> |
   
 **Estados Unidos** : no hay necesidad de varios números de emergencia. En los Estados Unidos, se usan las antiguas cadenas de marcado de emergencia y configuraciones de máscara de marcado.
  
 **Estados Unidos-Hospital** : hay un requerimiento de no enmascarar "450". Para los clientes que aún no admiten varios números de emergencia, puede usar las antiguas cadenas de marcado de emergencia y configuraciones de máscaras de marcado. Para los clientes que admiten varios números de emergencia, puede definir un número de emergencia para "911" y "450" en lugar de enmascarar 450.
  
 **Londres** : para los clientes que aún no admiten varios números de emergencia, puede usar las antiguas cadenas de marcado de emergencia y configuraciones de máscaras de marcado. Para los clientes que admiten varios números de emergencia, puede definir un número de emergencia para "999" y "112" con máscaras para cada uno.
  
 **India** : todos los clientes implementados admiten varios números de emergencia. En India, solo necesitas configurar varios números de emergencia.
  
## <a name="client-support"></a>Compatibilidad con clientes
<a name="BKMK_Clients"> </a>

En la tabla siguiente se muestra la compatibilidad de clientes para varios números de emergencia. Microsoft continuará probando y liberando soporte técnico para clientes adicionales. Inténtalo de nuevo a menudo.

|**Windows**|**Versión**|
|:-----|:-----|
|**Hacer clic y ejecutar** <br/> |CC (canal actual) publicado el 10 de mayo de 2016-versión 1604 (compilación 6868,2062)  <br/> |
||FRDC (primer lanzamiento del canal actual) publicado el 14 de junio de 2016-versión 1605 (compilación 6965,2058)  <br/> |
||DC (canal diferido) publicado el 11 de octubre de 2016-versión 1605 (compilación 6965,2092)  <br/> |
|**MSI** <br/> |Actualización del 7 de junio-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac y iOS** <br/> |**Versión** <br/> |
||Cliente para Mac de Skype empresarial versión 16,9  <br/> Cliente iOS de Skype empresarial versión 6,16  <br/> |
|**Android** <br/> |**Versión** <br/> |
||Cliente Android de Skype empresarial versión 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Versión** <br/> |
|| Aastra 6721ip y Aastra 6725ip teléfonos: actualización acumulativa de septiembre de 2016 (compilación 7577,4512):[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 y HP 4120 teléfonos: actualización acumulativa de septiembre de 2016 (compilación 7577,4512):[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 y Polycom CX3000 teléfonos, actualización acumulativa de septiembre de 2016 (compilación 7577,4512):[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

