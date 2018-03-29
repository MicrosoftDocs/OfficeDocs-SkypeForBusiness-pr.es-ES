---
title: Habilitar usuarios para E9-1-1 en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisiones necesarias para la política de ubicación para una implementación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server, incluidos los usuarios que para habilitar y cómo admitir usuarios móviles.
ms.openlocfilehash: 966344f2cfc7a964c9dda0898b4ba99c42e03193
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server-2015"></a>Habilitar usuarios para E9-1-1 en Skype Empresarial Server 2015
 
Decisiones necesarias para la política de ubicación para una implementación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server, incluidos los usuarios que para habilitar y cómo admitir usuarios móviles.
  
Durante el registro de cliente, Skype para Business Server utiliza una directiva de ubicación para configurar las propiedades de E9-1-1 para usuarios de Telefonía IP empresarial. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la política de ubicación contiene información como la emergencia cadena de marcado y proporcionar uno o no es necesario que un usuario para introducir manualmente una ubicación si el servicio de información de ubicación no automáticamente. Para una definición completa de una política de ubicación, vea [planificar políticas de ubicación de Skype para Business Server 2015](location-policies.md).
  
Skype para Business Server puede asignar una directiva de ubicación para clientes basados en la subred o para usuarios basados en global, por sitio o directiva por usuario. Para ayudarte a decidir cómo habilitarás los usuarios, necesitas responder primero las siguientes preguntas.
  
 **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**
  
> Puede asignar una ubicación para todos los usuarios de su empresa mediante una directiva de ubicación global. Sin embargo, asignando una política de ubicación a un Skype para el sitio de red de servidor empresarial y, a continuación, agregar subredes al sitio, puede limitar la compatibilidad de E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento E9-1-1 por cada sitio. 
    
 **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**
  
> Si deseas personalizar la asistencia de E9-1-1, puedes asignar directivas de ubicación directamente a usuarios o a objetos de contactos telefónicos de un área común específicos.
    
 **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿tienen los clientes que seguir habilitados en E9-1-1?**
  
> Si los usuarios se asignan global, sitio, o directiva de ubicación por usuario, pueden ser necesarios para especificar manualmente una ubicación en el cliente si el cliente no se encuentra dentro de una subred definida o no se ha encontrado ninguna ubicación por el servicio de información de ubicación. Para obtener más información, consulte [definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server 2015](manually-acquiring-a-location.md).
    

