---
title: Planificar directivas de ubicación para Skype empresarial Server
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lea este tema para obtener información sobre cómo planear directivas de ubicación para una implementación de servicios de emergencia mejorada (E9-1-1) en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276757"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planificar directivas de ubicación para Skype empresarial Server
 
Lea este tema para obtener información sobre cómo planear directivas de ubicación para una implementación de servicios de emergencia mejorada (E9-1-1) en Skype empresarial Server Enterprise Voice. 
  
> [!NOTE]
> Skype empresarial Server ahora es compatible con la configuración de varios números de emergencia para un cliente. Si desea configurar varios números de emergencia, debe seguir la información de [plan para varios números de emergencia en Skype empresarial Server](multiple-emergency-numbers.md) y [configurar varios números de emergencia en Skype empresarial](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Puedes crear directivas de ubicación con el panel de control de Skype para empresas o mediante el cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Para obtener más información, consulte [crear directivas de ubicación en Skype empresarial Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Cada directiva de ubicación contiene la información siguiente:
  
 **Habilitar 9-1-1 mejorado**
  
Si este valor se habilita, se habilita también al cliente para los servicios de emergencia mejorados (E9-1-1). Cuando un cliente se registra, intenta adquirir una ubicación desde el servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.
  
 **Ubicación**
  
Esta configuración se usa únicamente cuando **Habilitar 9-1-1 mejorado** está habilitada. 
  
Puede configurar **Ubicación** para definir el comportamiento del cliente de la siguiente manera:   
  
- Si se define el valor en **No**, no se pedirá al usuario una ubicación.
    
- Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud.
    
- Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede seguir utilizando el cliente.
    
> [!NOTE]
> El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto.  
  
 **Declinación de responsabilidades del servicio de emergencia mejorado**
  
En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación. En Skype empresarial Server, puede usar la Directiva de ubicación para establecer distintas renuncias para diferentes configuraciones regionales o conjuntos de usuarios diferentes.
  
 **Cadena de marcado de emergencia (número de marcado de E9-1-1)**
  
Esta cadena de marcado (menos el "+" inicial, pero incluida la normalización que realiza el plan de marcado del usuario) significa que una llamada es una llamada de emergencia. La **cadena de marcado de emergencia** implica que el cliente incluya la información de la devolución de llamadas y de la ubicación con la llamada.
  
> [!NOTE]
> Si su organización no usa un prefijo de acceso de línea externa, no es necesario crear una regla de normalización de plan de marcado correspondiente que agregue un signo "+" a la cadena de 911 antes de enviar la llamada al enrutamiento de salida en un servidor que ejecute Skype empresarial Server. el cliente de Skype empresarial agrega automáticamente el prefijo "+" como resultado de la política de ubicación. Sin embargo, si su sitio usa un prefijo de acceso externo, tendrá que agregar una regla de normalización a la Directiva del plan de marcado correspondiente que elimina el prefijo de acceso externo y agrega el signo "+". Por ejemplo, si su ubicación usa un prefijo de acceso externo de 9 y un usuario marca 9 911 para realizar una llamada de emergencia, el cliente usará su Directiva de plan de marcado para normalizarlo a + 911 antes de que el número marcado sea evaluado por las rutas en el perfil de ubicación de la persona que llama. 
  
 **Máscaras de cadena de marcado de emergencia (número de marcado de E9-1-1)**
  
Lista separada por punto y coma de cadenas de marcado que se traduce en la **cadena de marcado de emergencia**especificada. Por ejemplo, es posible que desee agregar 112, que es el número de servicio de emergencia de la mayor parte de Europa. Es posible que un usuario de Skype empresarial que visita desde Europa no sepa que 911 es el número de emergencia de Estados Unidos, pero sí puede marcar 112 y obtener el mismo resultado. Al igual que con la cadena de marcado de emergencia, no incluya un signo "+" antes de cada número y, si usa códigos de acceso de línea externa, asegúrese de que existen reglas de normalización en la Directiva del plan de marcado del usuario para quitar el dígito de código de acceso.
  
 **Uso de RTC**
  
El nombre del uso de RTC que contiene las rutas de acceso de enrutamiento que determinan a qué tronco SIP, a qué puerta de enlace RTC o a qué puerta de enlace ELIN se dirigen las llamadas de emergencia.
  
> [!NOTE]
> Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC reemplaza los usos de RTC asignados a la Directiva de voz del usuario, pero solo se aplica a las llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de cadena de marcado de emergencia. 
  
 **URI de notificación**
  
Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.
  
 **URI de conferencia**
  
Especifica el número de llamada directa a la extensión (DID) (normalmente un número del servicio de seguridad) que necesita incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.   
  
 **Modo de conferencia**
  
Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo de conferencia a través de una comunicación unidireccional o bidireccional.  
  
 **Intervalo de actualización de la ubicación**
  
Especifica la cantidad de tiempo (en horas) entre las solicitudes de un cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor puede ser cualquier número entre 1 y 12. El valor predeterminado es 4.
  

