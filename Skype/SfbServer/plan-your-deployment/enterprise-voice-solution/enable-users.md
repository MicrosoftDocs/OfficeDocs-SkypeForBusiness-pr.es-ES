---
title: Habilitar a usuarios para E9-1-1 en Skype para Business Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice, incluido qué usuarios para habilitar y cómo admitir usuarios móviles.
ms.openlocfilehash: 24a50384ec0f455c1998aa97274890e6346e5a01
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23889912"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar a usuarios para E9-1-1 en Skype para Business Server
 
Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice, incluido qué usuarios para habilitar y cómo admitir usuarios móviles.
  
Durante el registro de cliente, Skype para Business Server usa una directiva de ubicación para configurar las propiedades de E9-1-1 para los usuarios habilitados para Enterprise Voice. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la directiva de ubicación contiene información como la emergencia cadena de marcado y, si un usuario es necesario escribir manualmente una ubicación si el servicio de información de ubicación no automáticamente proporcionar uno. Para ver una definición completa de una directiva de ubicación, vea [Planear las directivas de ubicación para Skype para Business Server](location-policies.md).
  
Skype para Business Server puede asignar una directiva de ubicación a los clientes en función de la subred, o a los usuarios en función de un global por sitio o directiva por usuario. Para ayudarte a decidir cómo habilitarás los usuarios, necesitas responder primero las siguientes preguntas.
  
 **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**
  
> Puede asignar una ubicación para todos los usuarios de su empresa mediante el uso de una directiva de ubicación global. Sin embargo, mediante la asignación de una directiva de ubicación a un Skype para el sitio de red de Business Server y, a continuación, agregar subredes al sitio, puede limitar la compatibilidad de E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento de E9-1-1 por sitio. 
    
 **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**
  
> Si deseas personalizar la asistencia de E9-1-1, puedes asignar directivas de ubicación directamente a usuarios o a objetos de contactos telefónicos de un área común específicos.
    
 **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿tienen los clientes que seguir habilitados en E9-1-1?**
  
> Si los usuarios tienen asignada una global, de sitio, o directiva de ubicación por usuario, pueden ser necesarios para especificar manualmente una ubicación en el cliente si el cliente no se encuentra dentro de una subred definida o se ha encontrado ninguna ubicación mediante el servicio de información de ubicación. Para obtener más información, consulte [definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server](manually-acquiring-a-location.md).
    

