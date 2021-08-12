---
title: Planear varios números de emergencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Lea este tema para obtener información sobre cómo planear varios números de emergencia en Skype Empresarial Server.
ms.openlocfilehash: 1db97627ef783e5fa69bb7a186940c589f4aae40039563c3155c7cb29d5166aa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329554"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planear varios números de emergencia en Skype Empresarial Server
 
Lea este tema para obtener información sobre cómo planear varios números de emergencia en Skype Empresarial Server.
  
Skype Empresarial Server ahora admite la configuración de varios números de emergencia para un cliente. Varios números de emergencia es una nueva característica que se introdujo en la actualización acumulativa de junio de 2016. Aunque Estados Unidos tiene un único número de emergencia, 911, muchos países admiten varios números de emergencia. El Reino Unido, por ejemplo, admite tanto 999, el número de emergencia específico del Reino Unido, como el 112, el número de emergencia de la Unión Europea. 
  
Esta característica también es útil para los proveedores de atención médica dentro de los Estados Unidos que desean tener soporte móvil para varios números de emergencia azules de código.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Varios números de emergencia y directivas de ubicación

Para configurar las llamadas de emergencia, cree directivas de ubicación que definan cómo se implementarán las llamadas de emergencia. La directiva de ubicación se usa para definir qué número constituye una llamada de emergencia( por ejemplo, 911 en los Estados Unidos; 999 y 112 en el Reino Unido. La directiva de ubicación determina si un usuario está habilitado para llamadas de emergencia y, si es así, cuál es el comportamiento de una llamada de emergencia. También puede definir si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.
  
Para obtener más información acerca de cómo definir y modificar una directiva de ubicación, vea [Plan location policies for Skype Empresarial Server](location-policies.md) y Create location policies in [Skype Empresarial Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). En estos temas se describen conceptos sobre directivas de ubicación; sin embargo, debe seguir las instrucciones de Configurar varios números de [emergencia en Skype Empresarial](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) configurar varios números de emergencia.
  
Al planear varios números de emergencia, tenga en cuenta lo siguiente:
  
- Con la actualización acumulativa de junio de 2016, puede definir hasta 5 números de emergencia para una directiva de ubicación determinada. Con la actualización acumulativa de noviembre de 2016, este número aumenta a 100.
    
    > [!NOTE]
    > Si aún no ha actualizado a la actualización acumulativa de noviembre de 2016, vea [Updates to Skype Empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia, que son únicas para una directiva de ubicación determinada.
    
    Una máscara de marcado es un número que desea traducir al valor del valor del número de marcado de emergencia cuando se marca. Por ejemplo, supongamos que escribe un valor de 212 en este campo y que el campo número de marcado de emergencia tiene un valor de 911. Cuando un usuario marca 212, el número se traducirá al 911. Esto permite que se marquen números de emergencia alternativos y que la llamada llegue a los servicios de emergencia (por ejemplo, si alguien de un país o región con un número de emergencia diferente intenta marcar el número de ese país o región en lugar del número del país o región en el que se encuentra actualmente). Para definir varias máscaras de marcado de emergencia, separe los valores con punto y coma. Por ejemplo, 212;414. El límite de cadena de una máscara de marcado es de 100 caracteres. Todos los caracteres deben ser dígitos del 0 al 9.
    
- Cada directiva de ubicación tiene un único uso de red telefónica conmutada (RTC) que se usa para determinar qué ruta de voz se usa para enrutar llamadas de emergencia de clientes que usan esta directiva. El uso puede tener una ruta única por número de emergencia.
    
- Si una directiva de ubicación tiene definidos los parámetros EmergencyNumbers y DialString y el cliente admite varios números de emergencia, el número de emergencia tiene prioridad. Si el cliente no admite varios números de emergencia, se usa la cadena de marcado de emergencia.
    
- Para obtener información sobre qué clientes de Skype Empresarial y Lync admiten la recepción de varios números de emergencia, máscaras de marcado y usos de la red telefónica conmutada (RTC), vea [Client support](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> No puede configurar varios números de emergencia mediante el Panel Skype Empresarial control. Debe usar PowerShell para configurar varios números de emergencia. 
  
Antes de configurar varios números de emergencia, tenga en cuenta lo siguiente:
  
- Para configurar varios números de emergencia, debe usar el cmdlet New-CsEmergencyNumber y debe definir directivas de ubicación que admitan más de un número de emergencia especificando el parámetro EmergencyNumbers con los [cmdlets New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) y [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)
    
- Si tiene números existentes definidos mediante el cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask, los valores especificados con el parámetro EmergencyNumbers tendrán prioridad sobre los valores antiguos. Es decir, se omitirán los valores de los parámetros EmergencyDialString y EmergencyDialMask.
    
- Si tiene números existentes definidos mediante el cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask,  y no configura nuevos números de emergencia, se seguirán usando los números existentes.
    
- Para que la característica de varios números de emergencia funcione, las versiones de cliente que está ejecutando deben ser compatibles con la nueva característica. Los clientes más antiguos seguirán usando los valores antiguos especificados por los cmdlets Set-CsLocationPolicy o New-CsLocationPolicy con los parámetros EmergencyDialString y EmergencyDialMask. 
    
- Si los usuarios marcarán un número que coincida con la cadena de marcado, no se requiere ninguna máscara de marcado. Por ejemplo, si el número que marca un usuario es 911, la cadena de marcado es 911 y no se requiere máscara. 
    
Para obtener más información acerca de la configuración de varios números de emergencia, vea [Configure multiple emergency numbers in Skype Empresarial](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
En la tabla siguiente se muestran directivas de ubicación de ejemplo (para fines del ejemplo, no se muestran todos los atributos):
  

|**Nombre de directiva de ubicación**|**E911 habilitado**|**Cadena de marcado de emergencia**|**Máscara de marcado**|**Números de emergencia**|**Uso de RTC**|**Ubicación necesaria**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos  <br/> |Sí  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |Sí  <br/> |
|US-Hospital  <br/> |Sí  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sí  <br/> |
|Londres  <br/> |Sí  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |No  <br/> |
|India  <br/> |Sí  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |No  <br/> |
   
 **Estados Unidos:** no hay ningún requisito para varios números de emergencia. En Estados Unidos, se usan las configuraciones antiguas de cadena de marcado de emergencia y máscara de marcado.
  
 **US-Hospital:** hay un requisito de no enmascarar "450". Para los clientes que aún no admiten varios números de emergencia, puede usar las configuraciones antiguas de cadena de marcado de emergencia y máscara de marcado. Para los clientes que admiten varios números de emergencia, puede definir un número de emergencia para "911" y "450" en lugar de enmascarar 450.
  
 **Londres:** para clientes que aún no admiten varios números de emergencia, puede usar las configuraciones antiguas de cadena de marcado de emergencia y máscara de marcado. Para los clientes que admiten varios números de emergencia, puede definir un número de emergencia para "999" y "112" con máscaras para cada uno.
  
 **India:** todos los clientes implementados admiten varios números de emergencia. En India, solo necesita configurar varios números de emergencia.
  
## <a name="client-support"></a>Compatibilidad con clientes
<a name="BKMK_Clients"> </a>

En la tabla siguiente se muestra la compatibilidad del cliente con varios números de emergencia. Microsoft seguirá pruebando y liberando soporte técnico para clientes adicionales. Consúltelo con frecuencia.

|**Windows**|**Versión**|
|:-----|:-----|
|**Hacer clic y ejecutar** <br/> |CC (Canal actual) publicado el 10 de mayo de 2016 - Versión 1604 (compilación 6868.2062)  <br/> |
||FRDC (First Release Current Channel) publicado el 14 de junio de 2016 - Versión 1605 (compilación 6965.2058)  <br/> |
||DC (Canal diferido) publicado el 11 de octubre de 2016 - Versión 1605 (compilación 6965.2092)  <br/> |
|**MSI** <br/> |Actualización del 7 de junio: [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac e iOS** <br/> |**Versión** <br/> |
||Skype Empresarial Versión 16.9 del cliente Mac  <br/> Skype Empresarial cliente de iOS 6.16  <br/> |
|**Android** <br/> |**Versión** <br/> |
||Skype Empresarial Versión 6.17 del cliente Android  <br/> |
|**Lync Phone Edition** <br/> |**Versión** <br/> |
|| Teléfonos Aastra 6721ip y Aastra 6725ip - Actualización acumulativa de septiembre de 2016 (compilación 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| Teléfonos HP 4110 y HP 4120: actualización acumulativa de septiembre de 2016 (compilación 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Teléfonos Polycom CX500, Polycom CX600 y Polycom CX3000: actualización acumulativa de septiembre de 2016 (compilación 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
