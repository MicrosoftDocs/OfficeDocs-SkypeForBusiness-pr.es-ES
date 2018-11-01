---
title: Planeación de las directivas de ubicación de Skype para Business Server
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lea este tema para aprender a planear las directivas de ubicación para una implementación de servicios de emergencia mejorado (E9-1-1) en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: ed5eb479224c82757d808c202633cd79f466a543
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839430"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planeación de las directivas de ubicación de Skype para Business Server
 
Lea este tema para aprender a planear las directivas de ubicación para una implementación de servicios de emergencia mejorado (E9-1-1) en Skype para Business Server Enterprise Voice. 
  
> [!NOTE]
> Skype para Business Server ahora admite la configuración de varios números de emergencias para un cliente. Si desea configurar varios números de emergencias, debe seguir la información de [planeación para varios números de emergencias en Skype para Business Server](multiple-emergency-numbers.md) y [configurar varios números de emergencias en Skype para la empresa](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Crear directivas de ubicación mediante el Skype para el Panel de Control o mediante el cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Para obtener más información, vea [crear directivas de ubicación en Skype para Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Cada directiva de ubicación contiene la información siguiente:
  
 **Habilitar 9-1-1 mejorado**
  
Si este valor se habilita, se habilita también al cliente para los servicios de emergencia mejorados (E9-1-1). Cuando se registra un cliente, intenta adquirir una ubicación del servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.
  
 **Ubicación**
  
Esta configuración se usa únicamente cuando **Habilitar 9-1-1 mejorado** está habilitada. 
  
Puede configurar **Ubicación** para definir el comportamiento del cliente de la siguiente manera:   
  
- Si se define el valor en **No**, no se pedirá al usuario una ubicación.
    
- Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud.
    
- Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede seguir utilizando el cliente.
    
> [!NOTE]
> El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto.  
  
 **Declinación de responsabilidades del servicio de emergencia mejorado**
  
En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación. En Skype para Business Server, puede usar la directiva de ubicación para establecer la declinación de responsabilidades diferentes para distintas configuraciones regionales o distintos conjuntos de usuarios.
  
 **Cadena de marcado de emergencia (número de marcado de E9-1-1)**
  
Esta cadena de marcado (menos el interlineado "+", pero incluido cualquier normalización hecha por el Plan de marcado para el usuario) significa que la llamada es una llamada de emergencia. La **cadena de marcado de emergencia** implica que el cliente incluya la información de la devolución de llamadas y de la ubicación con la llamada.
  
> [!NOTE]
> Si su organización no utiliza un prefijo de acceso a línea externa, no es necesario crear una Plan de marcado de normalización regla correspondiente que agrega un "+" a la cadena 911 antes de enviar la llamada para el enrutamiento saliente en un servidor que ejecuta Skype para Business Server; se eliminará mediante la "+" se antepone automáticamente por el Skype para clientes empresariales como consecuencia de la directiva de ubicación. Sin embargo, si el sitio usa un prefijo de acceso externo, debe agregar una regla de normalización a la directiva aplicable Plan de marcado que se elimina el prefijo de acceso externo y se agrega el "+". Por ejemplo, si su ubicación utiliza un prefijo de acceso externo de 9 y un usuario marca 9 911 para realizar una llamada de emergencia, el cliente usará su directiva de Plan de marcado para normalizar esto a +911 antes de que se evalúa el número marcado por las rutas en el perfil de ubicación del autor de la llamada. 
  
 **Máscaras de cadena de marcado de emergencia (número de marcado de E9-1-1)**
  
Una separados por punto y coma lista de cadenas de marcado que se traduce en la **Cadena de marcado de emergencia**de especificada. Por ejemplo, es posible que desee agregar 112, que es el número de servicio de emergencia para la mayoría de Europa. Un visitante Skype para usuarios de empresa de Europa no puede saber que 911 es el número de emergencia de Estados Unidos, pero puede marcar 112 y obtener el mismo resultado. Como con la cadena de marcado de emergencia, no incluya un "+" delante de cada número y usar los códigos de acceso de línea externa, asegúrese de que hay reglas de normalización en la directiva de Plan de marcado del usuario para quitar desactiva el dígito del código de acceso.
  
 **Uso de RTC**
  
El nombre del uso de RTC que contiene las rutas de acceso de enrutamiento que determinan a qué tronco SIP, a qué puerta de enlace RTC o a qué puerta de enlace ELIN se dirigen las llamadas de emergencia.
  
> [!NOTE]
> Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC reemplaza los usos de RTC asignados a la directiva de voz del usuario, pero sólo se aplica a las llamadas realizadas a la cadena de marcado de emergencia o en una de las máscaras de cadena de marcado de emergencia. 
  
 **URI de notificación**
  
Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.
  
 **URI de conferencia**
  
Especifica el número de llamada directa a la extensión (DID) (normalmente un número del servicio de seguridad) que necesita incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.   
  
 **Modo de conferencia**
  
Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo de conferencia a través de una comunicación unidireccional o bidireccional.  
  
 **Intervalo de actualización de la ubicación**
  
Especifica la cantidad de tiempo (en horas) entre las solicitudes de cliente para una actualización de la ubicación del servicio de información de ubicación. El valor puede ser cualquier número entre 1 y 12. El valor predeterminado es 4.
  

