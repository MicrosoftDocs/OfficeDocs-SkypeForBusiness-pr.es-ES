---
title: Administrar el acceso de invitado a Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: rramesan
search.appverid: MET150
description: Los administradores de TI pueden agregar invitados en el nivel de inquilino, configurar y administrar permisos y directivas de usuarios invitados, determinar qué usuarios pueden invitar y extraer informes sobre la actividad de los usuarios invitados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 091215e37af012c2e2203b451e3df4dd9cf6480f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016728"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Administrar el acceso de invitado a Microsoft Teams
======================================

**Invitado** es un tipo de licencia de usuario o en Microsoft Teams que se incluye con todas las suscripciones a Office 365 Business Premium, Office 365 Enterprise y Office 365 educación. No se necesita ninguna otra licencia de Office 365. El acceso de invitado de Teams es una configuración a nivel de inquilino y se encuentra desactivada de forma predeterminada. Para obtener información detallada acerca de cómo habilitar el acceso de invitado, vea [Activar o desactivar el acceso de invitado a los equipos de Microsoft](set-up-guests.md).

Después de que el tipo de licencia de usuario o **invitado** está activado, puede establecer la configuración para invitados a través de los controles que describen en [las características de administración de equipos de Microsoft en su organización de Office 365](enable-features-office-365.md) y [administrar equipos durante la transición a la nueva Microsoft Los equipos y Skype para el centro de administración de negocio](manage-teams-skypeforbusiness-admin-center.md).     
    
Los administradores de TI pueden agregar invitados en el nivel de inquilino, configurar y administrar permisos y directivas de usuarios invitados, determinar qué usuarios pueden invitar y extraer informes sobre la actividad de los usuarios invitados. Estos controles están disponibles a través del Centro de administración de Office 365. Las actividades y el contenido de los usuarios invitados están protegidos con el mismo cumplimiento de normativas y auditorías que el resto de Office 365.

Los propietarios de equipo pueden invitar a nuevos invitados y agregue los usuarios invitados de Active directory existente a sus equipos. Además, los propietarios de equipo pueden establecer las capacidades relacionadas con el canal para invitados a través de **los equipos de administrar** > **permisos de invitado**, incluido el permiso de invitados crear, actualizar y eliminar los canales, como se muestra en la siguiente captura de pantalla:

![Configuración de permisos de invitado en los equipos.](media/view-guests-guest-permissions.png)
  

Además, puede usar el portal de Azure Active Directory para administrar invitados y su acceso a los recursos de Office 365 y Microsoft Teams. El acceso de invitado de Microsoft Teams puede aprovechar las funcionalidades de colaboración negocio a negocio (B2B) de Azure Active Directory como la infraestructura subyacente donde almacenar la información relacionada con los principios de seguridad (como las propiedades de identidad, las suscripciones y la configuración de autenticación multifactor). Para obtener más información sobre la colaboración B2B de Azure Active Directory, consulte [¿Qué es la colaboración B2B de Azure AD?](https://go.microsoft.com/fwlink/p/?linkid=853011) y [Preguntas más frecuentes acerca de la colaboración B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020).
> [!NOTE]
> Microsoft Teams siempre respeta la configuración externa de Azure Active Directory para permitir o impedir la adición de usuario de invitado para el inquilino. Para obtener más información, vea [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md).
  
