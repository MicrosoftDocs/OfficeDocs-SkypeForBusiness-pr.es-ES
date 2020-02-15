---
title: Planeación de varios números de emergencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Lea este tema para obtener información sobre cómo planear varios números de emergencia en Skype empresarial Server.
ms.openlocfilehash: 10b6d02391fbf1ac7af1ae5233261c36fd2fd6ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983025"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planeación de varios números de emergencia en Skype empresarial Server
 
Lea este tema para obtener información sobre cómo planear varios números de emergencia en Skype empresarial Server.
  
Skype empresarial Server ahora admite la configuración de varios números de emergencia para un cliente. Varios números de emergencia son una nueva característica que se presenta en la actualización acumulativa de junio de 2016. Mientras que Estados Unidos tiene un solo número de emergencia, 911, muchos países admiten varios números de emergencia. El Reino Unido, por ejemplo, admite tanto 999, el número de emergencia específico del Reino Unido y 112, el número de emergencia de la Unión Europea. 
  
Esta característica también es útil para los proveedores de atención de la salud dentro de los Estados Unidos que quieren tener soporte de itinerancia para varios números de emergencia de código azul.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Varios números de emergencia y directivas de ubicación

Las llamadas de emergencia se configuran mediante la creación de directivas de ubicación que definen cómo se implementarán las llamadas de emergencia. La Directiva de ubicación se usa para definir el número que constituye una llamada de emergencia, por ejemplo, 911 en Estados Unidos; 999 y 112 en el Reino Unido. La Directiva de ubicación determina si un usuario está habilitado para las llamadas de emergencia y, si es así, el comportamiento de una llamada de emergencia. También puede definir si la seguridad corporativa se debe notificar automáticamente y cómo se debe enrutar la llamada.
  
Para obtener más información acerca de cómo definir y modificar una directiva de ubicación, consulte [plan Location Policies for Skype for Business Server](location-policies.md) y [Create Location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). En estos temas se describen los conceptos sobre las directivas de ubicación; sin embargo, debe seguir las instrucciones que se indican en [Configure Multiple Emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) para configurar varios números de emergencia.
  
Al planear varios números de emergencia, tenga en cuenta lo siguiente:
  
- Con la actualización acumulativa de junio de 2016, puede definir hasta 5 números de emergencia para una directiva de ubicación determinada. Con la actualización acumulativa de noviembre de 2016, este número aumenta a 100.
    
    > [!NOTE]
    > Si aún no ha actualizado a la actualización acumulativa de noviembre de 2016, consulte [actualizaciones para Skype empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia, que son únicas para una directiva de ubicación determinada.
    
    Una máscara de marcado es un número que desea traducir en el valor del número de marcado de emergencia cuando se marca. Por ejemplo, supongamos que especifica un valor de 212 en este campo y el campo de número de marcado de emergencia tiene un valor de 911. Cuando un usuario marca 212, el número se convierte en 911. Esto permite que los números de emergencia alternativos se marquen y sigan teniendo la llamada a los servicios de emergencia (por ejemplo, si alguien de un país o región con un número de emergencia diferente intenta marcar el número de ese país o región en lugar del número del país o región en el que se encuentran actualmente). Para definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212;414. El límite de cadena para una máscara de marcado es de 100 caracteres. Todos los caracteres deben ser dígitos del 0 al 9.
    
- Cada directiva de ubicación tiene un uso de red telefónica conmutada (RTC) único que se usa para determinar qué ruta de voz se usa para enrutar llamadas de emergencia de clientes que usan esta Directiva. El uso puede tener una ruta única por número de emergencia.
    
- Si una directiva de ubicación tiene definidos los parámetros EmergencyNumbers y DialString, y el cliente admite varios números de emergencia, el número de emergencia tiene prioridad. Si el cliente no admite varios números de emergencia, se utiliza la cadena de marcado de emergencia.
    
- Para obtener información acerca de qué clientes de Skype empresarial y Lync admiten la recepción de varios números de emergencia, máscaras de marcado y usos públicos de la red telefónica conmutada (RTC), consulte [Client Support](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> No puede configurar varios números de emergencia mediante el panel de control de Skype empresarial. Debe usar PowerShell para configurar varios números de emergencia. 
  
Antes de configurar varios números de emergencia, tenga en cuenta lo siguiente:
  
- Para configurar varios números de emergencia, debe usar el cmdlet New-CsEmergencyNumber y debe definir directivas de ubicación que admitan más de un número de emergencia especificando el parámetro EmergencyNumbers con los cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Si tiene números existentes definidos con el cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask, los valores especificados con el parámetro EmergencyNumbers tendrán prioridad sobre el antiguo valor. Es decir, se omitirán los valores de los parámetros EmergencyDialString y EmergencyDialMask.
    
- Si tiene números existentes definidos con el cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask *y no configura nuevos números de emergencia* , se seguirán usando los números existentes.
    
- Para que funcione la característica de varios números de emergencia, las versiones de cliente que esté ejecutando deben ser capaces de admitir la nueva característica. Los clientes más antiguos seguirán usando los valores antiguos especificados por los cmdlets Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask. 
    
- Si los usuarios van a marcar un número que coincide con la cadena de marcado, no se requiere ninguna máscara de marcado. Por ejemplo, si el número que marca un usuario es 911, la cadena de marcado es 911 y no se requiere ninguna máscara. 
    
Para obtener más información acerca de la configuración de varios números de emergencia, vea [Configure Multiple Emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
En la tabla siguiente se muestran directivas de ubicación de ejemplo (para fines del ejemplo, no se muestran todos los atributos):
  

|**Nombre de la Directiva de ubicación**|**E911 habilitado**|**Cadena de marcado de emergencia**|**Máscara de marcado**|**Números de emergencia**|**Uso de RTC**|**Ubicación requerida**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos  <br/> |Sí  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Sí  <br/> |
|Hospital estadounidense  <br/> |Sí  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sí  <br/> |
|México  <br/> |Sí  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |No  <br/> |
|India  <br/> |Sí  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |No  <br/> |
   
 **Estados Unidos** : no hay ningún requisito para varios números de emergencia. En los Estados Unidos, se usa la antigua cadena de marcado de emergencia y las configuraciones de máscara de marcado.
  
 **US-Hospital** — hay un requisito para no enmascarar "450". Para los clientes que todavía no admiten varios números de emergencia, puede usar la antigua cadena de marcado de emergencia y configuraciones de máscara de marcado. Para los clientes que admiten varios números de emergencia, puede definir un número de emergencia tanto para "911" como para "450" en lugar de enmascarar 450.
  
 **Londres** : para clientes que todavía no admiten varios números de emergencia, puede usar la antigua cadena de marcado de emergencia y configuraciones de máscara de marcado. En el caso de los clientes que admiten varios números de emergencia, puede definir un número de emergencia para "999" y "112" con máscaras para cada uno.
  
 **India** : todos los clientes implementados admiten varios números de emergencia. En India, solo tiene que configurar varios números de emergencia.
  
## <a name="client-support"></a>Compatibilidad con clientes
<a name="BKMK_Clients"> </a>

En la siguiente tabla se muestra la compatibilidad de clientes para varios números de emergencia. Microsoft seguirá comprobando y publicando la compatibilidad para clientes adicionales. Consúltelo con frecuencia.

|**Windows**|**Version**|
|:-----|:-----|
|**Hacer clic y ejecutar** <br/> |CC (canal actual) lanzado el 10 de mayo de 2016-versión 1604 (compilación 6868,2062)  <br/> |
||FRDC (canal actual de First Release) publicada el 14 de junio de 2016-versión 1605 (compilación 6965,2058)  <br/> |
||DC (canal diferido) lanzado el 11 de octubre de 2016-versión 1605 (compilación 6965,2092)  <br/> |
|**MS** <br/> |Actualización del 7 de junio-[https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac y iOS** <br/> |**Version** <br/> |
||Cliente de Skype empresarial para Mac versión 16,9  <br/> Cliente iOS de Skype empresarial versión 6,16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Cliente de Android de Skype empresarial versión 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip y Aastra 6725ip telephones-actualización acumulativa de septiembre de 2016 (compilación 7577,4512):[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| Teléfonos HP 4110 y HP 4120-actualización acumulativa de septiembre de 2016 (compilación 7577,4512):[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 y Polycom CX3000 teléfonos para la actualización acumulativa de septiembre de 2016 (compilación 7577,4512):[https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

