---
title: Planificar directivas de ubicación para Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lea este tema para aprender a planear las políticas de ubicación para una implementación de los servicios de emergencia mejorada (E9-1-1) en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 246a4bcddece986d9488c5e2bccbbece5f1a2cc9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-location-policies-for-skype-for-business-server-2015"></a>Planificar directivas de ubicación para Skype Empresarial Server 2015
 
Lea este tema para aprender a planear las políticas de ubicación para una implementación de los servicios de emergencia mejorada (E9-1-1) en Skype para Telefonía IP empresarial de Business Server. 
  
> [!NOTE]
> Skype para Business Server ahora admite la configuración de varios números de emergencia para un cliente. Si desea configurar varios números de emergencia, debe seguir la información en el [Plan para varios números de emergencia en Skype para Business Server 2015](multiple-emergency-numbers.md) y [configurar varios números de emergencia en Skype para negocios 2015](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Puede crear directivas de ubicación utilizando el Skype para el Panel de Control del negocio o mediante el cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Para obtener más información, vea [crear directivas de ubicación en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Cada directiva de ubicación contiene la información siguiente:
  
 **Habilitar 9-1-1 mejorado**
  
Si este valor se habilita, se habilita también al cliente para los servicios de emergencia mejorados (E9-1-1). Cuando un cliente se registra, intenta adquirir una ubicación desde el servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.
  
 **Ubicación**
  
Esta opción sólo se utiliza cuando se habilita **Habilitar Enhanced 9-1-1** .
  
Puede configurar **Ubicación** para definir el comportamiento del cliente de la siguiente manera:   
  
- Si se define el valor en **No**, no se pedirá al usuario una ubicación.
    
- Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud.
    
- Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede seguir utilizando el cliente.
    
> [!NOTE]
> El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto.  
  
 **Declinación de responsabilidades del servicio de emergencia mejorado**
  
En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación. En Skype para Business Server, puede utilizar Directiva de ubicación para establecer renuncias diferentes para distintas configuraciones regionales o conjuntos de usuarios diferentes.
  
 **Cadena de marcado de emergencia (número de marcado de E9-1-1)**
  
Esta cadena de marcado (menos el interlineado "+", pero incluyendo ninguna normalización realizada por Dial Plan el usuario) significa que la llamada es una llamada de emergencia. La **cadena de marcado de emergencia** implica que el cliente incluya la información de la devolución de llamadas y de la ubicación con la llamada.
  
> [!NOTE]
> Si su organización no utiliza un prefijo de acceso a línea externa, no necesitará crear regla de normalización correspondiente Plan de marcado que agrega un signo "+" en la cadena 911 antes de enviar la llamada al enrutamiento de salida en un servidor que ejecuta Skype para Business Server; la voluntad de "+" se antepone automáticamente por el Skype para cliente de negocios como consecuencia de la política de ubicación. Sin embargo, si su sitio utiliza un prefijo de acceso externo, necesita agregar una regla de normalización a la directiva aplicable Dial Plan que elimina el prefijo de acceso externo y se agrega la "+". Por ejemplo, si su ubicación utiliza un prefijo de acceso externo de 9 y un usuario marca 9 911 para realizar una llamada de emergencia, el cliente utilizará su directiva Plan de acceso telefónico para normalizar esto a +911 antes de la se evalúa el número marcado por las rutas de perfil de la ubicación del llamador. 
  
 **Máscaras de cadena de marcado de emergencia (número de marcado de E9-1-1)**
  
Una separados por punto y coma lista de cadenas de marcado que se traduce en la **Cadena de marcado de emergencia**de especificada. Por ejemplo, es aconsejable agregar 112, que es el número de servicio de emergencia para la mayor parte de Europa. Un visitante Skype para usuarios de empresa en Europa puede desconocer 911 es el número de emergencia de Estados Unidos, pero pueden marcar 112 y obtener el mismo resultado. Como con la cadena de marcado de emergencia, no incluya un signo "+" antes de cada número, y si usa códigos de acceso a línea externa, asegúrese de que hay reglas de normalización en la directiva del usuario Dial Plan quitar los dígitos del código de acceso.
  
 **Uso de RTC**
  
El nombre del uso de RTC que contiene las rutas de acceso de enrutamiento que determinan a qué tronco SIP, a qué puerta de enlace RTC o a qué puerta de enlace ELIN se dirigen las llamadas de emergencia.
  
> [!NOTE]
> Solo se puede asignar un uso a una directiva de ubicación. Este uso de PSTN reemplaza los usos PSTN asignada a una directiva de voz del usuario, pero sólo se aplica a las llamadas efectuadas a la cadena de marcado de emergencia o a una de las máscaras de cadena de marcado de emergencia. 
  
 **URI de notificación**
  
Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.
  
 **URI de conferencia**
  
Especifica el número de llamada directa a la extensión (DID) (normalmente un número del servicio de seguridad) que necesita incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.   
  
 **Modo de conferencia**
  
Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo de conferencia a través de una comunicación unidireccional o bidireccional.  
  
 **Intervalo de actualización de la ubicación**
  
Especifica la cantidad de tiempo (en horas) entre las solicitudes del cliente para una actualización de la ubicación del servicio de información de la ubicación. El valor puede ser cualquier número entre 1 y 12. El valor predeterminado es 4.
  

