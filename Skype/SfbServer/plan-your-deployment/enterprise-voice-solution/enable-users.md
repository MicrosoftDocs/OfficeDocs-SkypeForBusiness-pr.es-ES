---
title: Habilitar usuarios para E9-1-1 en Skype Empresarial Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial, incluidos los usuarios que se habilitarán y cómo admitir usuarios móviles.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825750"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar usuarios para E9-1-1 en Skype Empresarial Server
 
Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial, incluidos los usuarios que se habilitarán y cómo admitir usuarios móviles.
  
Durante el registro del cliente, Skype Empresarial Server usa una directiva de ubicación para configurar las propiedades de E9-1-1 para los Telefonía IP empresarial habilitados para clientes. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la directiva de ubicación contiene información como la cadena de marcado de emergencia y si un usuario debe especificar manualmente una ubicación si el servicio de información de ubicación no proporciona automáticamente una. Para obtener una definición completa de una directiva de ubicación, consulte [Plan location policies for Skype for Business Server](location-policies.md).
  
Skype Empresarial Server puede asignar una directiva de ubicación a los clientes en función de la subred o a los usuarios en función de una directiva global, por sitio o por usuario. Para ayudarle a decidir cómo habilitará los usuarios, debe responder en primer lugar las siguientes preguntas.
  
 **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**
  
> Puede asignar una ubicación a todos los usuarios de la empresa mediante una directiva de ubicación global. Sin embargo, al asignar una directiva de ubicación a un sitio de red de Skype Empresarial Server y, a continuación, agregar subredes al sitio, puede limitar la compatibilidad con E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento de E9-1-1 por sitio. 
    
 **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**
  
> Puede asignar directivas de ubicación directamente a usuarios específicos u objetos de contactos telefónicos de un área común si desea personalizar la compatibilidad con E9-1-1.
    
 **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿deben los clientes seguir habilitados en E9-1-1?**
  
> Si a los usuarios se les asigna una directiva de ubicación global, de sitio o por usuario, puede que se les requiera que introduzcan manualmente una ubicación en el cliente si el cliente no se encuentra dentro de una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación. Para obtener más información, consulte Definir la experiencia del usuario para adquirir manualmente una [ubicación en Skype Empresarial Server.](manually-acquiring-a-location.md)
    

