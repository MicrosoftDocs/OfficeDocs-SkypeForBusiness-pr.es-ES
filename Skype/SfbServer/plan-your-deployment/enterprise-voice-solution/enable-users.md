---
title: Habilitar usuarios para E9-1-1 en Skype empresarial Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisiones necesarias para la Directiva de ubicación de una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice, incluyendo qué usuarios habilitar y cómo admitir usuarios móviles.
ms.openlocfilehash: 1e714e5296e8176c9052b50a5d4ce4f2c0d6184b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276904"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar usuarios para E9-1-1 en Skype empresarial Server
 
Decisiones necesarias para la Directiva de ubicación de una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice, incluyendo qué usuarios habilitar y cómo admitir usuarios móviles.
  
Durante el registro del cliente, Skype empresarial Server usa una directiva de ubicación para configurar las propiedades E9-1-1 para los usuarios habilitados para voz. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la Directiva de ubicación contiene información como, por ejemplo, la cadena de marcado de emergencia y si un usuario debe o no especificar manualmente una ubicación si el servicio de información de ubicación no proporciona una automáticamente. Para obtener una definición completa de una directiva de ubicación, consulte [planear directivas de ubicación para Skype empresarial Server](location-policies.md).
  
Skype empresarial Server puede asignar una directiva de ubicación a clientes en función de la subred o a usuarios en función de una directiva global, por sitio o por usuario. Para ayudarte a decidir cómo habilitarás los usuarios, necesitas responder primero las siguientes preguntas.
  
 **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**
  
> Puede asignar una ubicación a todos los usuarios de su empresa mediante una directiva de ubicación global. Sin embargo, si asigna una directiva de ubicación a un sitio de red de Skype empresarial Server y luego agrega subredes al sitio, puede limitar la compatibilidad con E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento E9-1-1 en cada sitio. 
    
 **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**
  
> Si deseas personalizar la asistencia de E9-1-1, puedes asignar directivas de ubicación directamente a usuarios o a objetos de contactos telefónicos de un área común específicos.
    
 **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿tienen los clientes que seguir habilitados en E9-1-1?**
  
> Si se asigna a los usuarios una directiva de ubicación global, de sitio o por usuario, se les puede requerir introducir manualmente una ubicación en el cliente si el cliente no se encuentra en una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación. Para obtener más información, consulte [definir la experiencia de usuario para la adquisición manual de una ubicación en Skype empresarial Server](manually-acquiring-a-location.md).
    

