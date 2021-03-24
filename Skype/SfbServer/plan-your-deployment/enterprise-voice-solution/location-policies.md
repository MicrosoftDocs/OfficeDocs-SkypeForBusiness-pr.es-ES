---
title: Planear directivas de ubicación para Skype Empresarial Server
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lea este tema para obtener información sobre cómo planear directivas de ubicación para una implementación mejorada de servicios de emergencia (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101456"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planear directivas de ubicación para Skype Empresarial Server
 
Lea este tema para obtener información sobre cómo planear directivas de ubicación para una implementación mejorada de servicios de emergencia (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial. 
  
> [!NOTE]
> Skype Empresarial Server ahora admite la configuración de varios números de emergencia para un cliente. Si desea configurar varios números de emergencia, debe seguir la información de [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) y Configure multiple emergency numbers in Skype for [Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Puede crear directivas de ubicación mediante el Panel de control de Skype Empresarial o mediante el cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Para obtener más información, vea [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Cada directiva de ubicación contiene la información siguiente:
  
 **Habilitar 9-1-1 mejorado**
  
Cuando se habilita este valor, el cliente está habilitado para servicios de emergencia mejorados (E9-1-1). Cuando un cliente se registra, intenta adquirir una ubicación del servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.
  
 **Location**
  
Esta configuración solo se usa cuando **habilitar 9-1-1** mejorado está habilitado.
  
Puede configurar la opción **Ubicación** para definir el comportamiento del cliente de la siguiente manera:
  
- Si se define el valor en **No**, no se pedirá al usuario una ubicación.
    
- Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud.
    
- Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y no podrá anular la solicitud hasta que haya introducido una solicitud. En ambos casos el usuario puede continuar usando el cliente.
    
> [!NOTE]
> El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto. 
  
 **Declinación de responsabilidad de servicio de emergencia mejorado**
  
En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación. En Skype Empresarial Server, puede usar la directiva de ubicación para establecer diferentes declinaciones de responsabilidades para diferentes configuraciones regionales o diferentes conjuntos de usuarios.
  
 **Cadena de marcado de emergencia (número de marcado E9-1-1)**
  
Esta cadena de marcado (menos el "+" inicial, pero incluida cualquier normalización realizada por el Plan de marcado del usuario) significa que una llamada es una llamada de emergencia. La **cadena de marcado de emergencia** comporta la adición a la llamada de información de ubicación y devolución de llamada por parte del cliente.
  
> [!NOTE]
> Si su organización no usa un prefijo de acceso de línea externa, no es necesario crear una regla de normalización del plan de marcado correspondiente que agrega un "+" a la cadena 911 antes de enviar la llamada al enrutamiento saliente en un servidor que ejecute Skype Empresarial Server; el cliente de Skype Empresarial antepone automáticamente el "+" como resultado de la directiva de ubicación. Sin embargo, si el sitio usa un prefijo de acceso externo, debe agregar una regla de normalización a la directiva de plan de marcado aplicable que elimina el prefijo de acceso externo y agrega el "+". Por ejemplo, si su ubicación usa un prefijo de acceso externo de 9 y un usuario marca 9 911 para realizar una llamada de emergencia, el cliente usará su directiva de plan de marcado para normalizar esto a +911 antes de que las rutas del perfil de ubicación del autor de la llamada evalúen el número marcado. 
  
 **Máscaras de cadena de marcado de emergencia (máscara de marcado E9-1-1)**
  
Una lista de cadenas de marcado separadas por caracteres de punto y coma que deben convertirse a la **cadena de marcado de emergencia** especificada. Por ejemplo, es posible que desee agregar 112, que es el número del servicio de emergencia para la mayor parte de Europa. Es posible que un usuario de Skype Empresarial visitante de Europa no sepa que 911 es el número de emergencia de Estados Unidos, pero puede marcar el 112 y obtener el mismo resultado. Al igual que con la cadena de marcado de emergencia, no incluya un "+" antes de cada número y, si usa códigos de acceso de línea externa, asegúrese de que hay reglas de normalización en la directiva de plan de marcado del usuario para quitar el dígito del código de acceso.
  
 **Uso de RTC**
  
El nombre del uso de RTC que contiene las rutas de acceso que determinan en qué tronco SIP o puerta de enlace RTC se realizarán las llamadas de emergencia.
  
> [!NOTE]
> Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC invalida los usos de RTC asignados a la directiva de voz del usuario, pero solo se aplica a las llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de cadena de marcado de emergencia. 
  
 **URI de notificación**
  
Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.
  
 **URI de conferencia**
  
Especifica el número de llamada directa a la extensión (DID) (normalmente un número del departamento de seguridad) que debe incluirse en el modo de conferencia cuando se realiza una llamada de emergencia. 
  
 **Modo de conferencia**
  
Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo conferencia mediante comunicación unidireccional o bidireccional. 
  
 **Intervalo de actualización de la ubicación**
  
Especifica la cantidad de tiempo (en horas) entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación. El valor se puede definir en cualquier número incluido entre 1 y 12. El valor predeterminado es 4.
