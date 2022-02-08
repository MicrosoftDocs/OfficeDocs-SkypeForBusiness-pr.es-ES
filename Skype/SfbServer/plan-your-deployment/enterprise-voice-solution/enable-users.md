---
title: Habilitar usuarios para E9-1-1 en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial, incluidos los usuarios que se habilitarán y cómo admitir usuarios móviles.
ms.openlocfilehash: 877e813df4d1ace9084586702836db96dbb149a5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392432"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar usuarios para E9-1-1 en Skype Empresarial Server
 
Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial, incluidos los usuarios que se habilitarán y cómo admitir usuarios móviles.
  
Durante el registro de cliente, Skype Empresarial Server una directiva de ubicación para configurar las propiedades de E9-1-1 para Telefonía IP empresarial usuarios habilitados. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la directiva de ubicación contiene información como la cadena de marcado de emergencia y si un usuario debe escribir manualmente una ubicación si el servicio de información de ubicación no proporciona automáticamente una. Para obtener una definición completa de una directiva de ubicación, vea [Plan location policies for Skype Empresarial Server](location-policies.md).
  
Skype Empresarial Server puede asignar una directiva de ubicación a los clientes en función de la subred o a los usuarios en función de una directiva global, por sitio o por usuario. Para ayudarle a decidir cómo habilitará los usuarios, debe responder en primer lugar las siguientes preguntas.
  
 **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**
  
> Puede asignar una ubicación a todos los usuarios de la empresa mediante una directiva de ubicación global. Sin embargo, al asignar una directiva de ubicación a un sitio de red de Skype Empresarial Server y, a continuación, agregar subredes al sitio, puede limitar la compatibilidad con E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento de E9-1-1 por sitio. 
    
 **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**
  
> Puede asignar directivas de ubicación directamente a usuarios específicos u objetos de contactos telefónicos de un área común si desea personalizar la compatibilidad con E9-1-1.
    
 **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿deben los clientes seguir habilitados en E9-1-1?**
  
> Si a los usuarios se les asigna una directiva de ubicación global, de sitio o por usuario, puede ser necesario que escriban manualmente una ubicación en el cliente si el cliente no se encuentra dentro de una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación. Para obtener más información, vea [Define the user experience for manually acquiring a location in Skype Empresarial Server](manually-acquiring-a-location.md).
    

