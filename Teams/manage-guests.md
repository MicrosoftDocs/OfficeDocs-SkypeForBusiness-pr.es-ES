---
title: Administrar el acceso de invitado a Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Los administradores de TI pueden agregar invitados en el nivel de inquilino, configurar y administrar permisos y directivas de usuarios invitados, determinar qué usuarios pueden invitar y extraer informes sobre la actividad de los usuarios invitados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02faf85d91657c487c02503b69b08078b81c88de
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
<a name="manage-guest-access-in-microsoft-teams"></a>Administrar el acceso de invitado a Microsoft Teams
======================================

**Invitado** es un tipo de licencia de usuario o en Teams de Microsoft que se incluye con todas las suscripciones Premium de negocio de Office 365, Office 365 Enterprise y formación de Office 365. No se necesita ninguna otra licencia de Office 365. El acceso de invitado de Teams es una configuración a nivel de inquilino y se encuentra desactivada de forma predeterminada. Para obtener más información acerca de cómo habilitar el acceso de invitado, consulte [Activar o desactivar acceso de invitado a equipos de Microsoft](set-up-guests.md).

Después de activar el tipo de licencia de usuario o **invitado** , puede configurar opciones para los clientes a través de los controles descritos en [las características de administrar equipos de Microsoft en su organización de Office 365](enable-features-office-365.md#settings-by-userlicense-type).     
    
Los administradores de TI pueden agregar invitados en el nivel de inquilino, configurar y administrar permisos y directivas de usuarios invitados, determinar qué usuarios pueden invitar y extraer informes sobre la actividad de los usuarios invitados. Estos controles están disponibles a través del Centro de administración de Office 365. Las actividades y el contenido de los usuarios invitados están protegidos con el mismo cumplimiento de normativas y auditorías que el resto de Office 365.

Propietarios de equipo pueden invitar a nuevos invitados y agregue los usuarios invitados de directorio existente a sus equipos. Además, los propietarios del equipo pueden establecer capacidades de canal para invitados a través de **administrar equipos** > **permisos de invitado**, incluido el permiso de los clientes crear, actualizar y eliminar canales, como se muestra en la siguiente captura de pantalla:

![Configuración de permisos de invitado en los equipos.](media/view-guests-guest-permissions.png)
  

Además, puede usar el portal de Azure Active Directory para administrar invitados y su acceso a los recursos de Office 365 y Microsoft Teams. El acceso de invitado de Microsoft Teams puede aprovechar las funcionalidades de colaboración negocio a negocio (B2B) de Azure Active Directory como la infraestructura subyacente donde almacenar la información relacionada con los principios de seguridad (como las propiedades de identidad, las suscripciones y la configuración de autenticación multifactor). Para obtener más información sobre la colaboración B2B de Azure Active Directory, consulte [¿Qué es la colaboración B2B de Azure AD?](https://go.microsoft.com/fwlink/p/?linkid=853011) y [Preguntas más frecuentes acerca de la colaboración B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020).
> [!NOTE]
> Teams de Microsoft siempre respeta la configuración de Active Directory de Azure externo para permitir o evitar la adición de un usuario invitado del inquilino. Para obtener más información, vea [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md).
  
