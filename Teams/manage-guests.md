---
title: Administrar el acceso de invitado en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a crear sus primeros equipos y canales, a incorporar a los primeros usuarios, a supervisar el uso y los comentarios, y a obtener recursos para planificar la implementación en toda la organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 544dcb4ffd424512797d3791e2eda6b22439c084
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777845"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Administrar el acceso de invitado en Microsoft Teams
======================================

> [!IMPORTANT]
> Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto. 

**Guest** es un tipo de usuario en Microsoft teams que se incluye con todas las suscripciones Microsoft 365 Business Standard, Office 365 Enterprise, Microsoft 365 Business Basic y Office 365 educación. No se necesita ninguna otra licencia de Office 365. Más adelante encontrará más información sobre las [licencias de acceso de invitado](#guest-access-licensing-limits) .

El acceso de invitado de Teams es una configuración a nivel de inquilino y se encuentra desactivada de forma predeterminada. Para obtener más información sobre cómo activar el acceso de invitados, vea [activar o desactivar el acceso de invitados a los equipos](set-up-guests.md), o use la [lista de comprobación de acceso de invitados](guest-access-checklist.md) para que le guíe por la configuración.

Después de activar el acceso de invitados, puede configurar las opciones de los invitados con los controles descritos en [administrar la configuración de Teams de la organización](enable-features-office-365.md) y [administrar equipos durante la transición al nuevo centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md).     
    
Los administradores de TI pueden agregar invitados en el nivel de espacio empresarial, establecer y administrar las directivas y permisos de los usuarios invitados, y extraer informes sobre la actividad de los usuarios invitados. Estos controles están disponibles en el centro de administración de Teams. El contenido y las actividades de los usuarios invitados se encuentran en el mismo cumplimiento y protección de auditoría que el resto de la 365.

Los propietarios de equipo pueden invitar a nuevos invitados y agregar usuarios de invitados a sus equipos en el centro de administración de Teams. Identifique los invitados en la **Página Teams** > **Manage Teams** y establezca capacidades relacionadas con los canales para los invitados en la página de**acceso de invitado** de la configuración > de toda la **organización**. La configuración incluye permitir a los invitados crear, actualizar y eliminar canales, como se muestra en la siguiente ilustración.

![Configuración de los permisos de invitado en Teams](media/manage-guest-access-image1.png)
  
Puede usar el portal de Azure Active Directory (Azure AD) para administrar los invitados y su acceso a los recursos de Office 365 y Teams. El acceso de invitado de Teams usa las capacidades de colaboración de Azure AD negocio a negocio (B2B) como la infraestructura subyacente para almacenar información sobre los principios de seguridad, como las propiedades de identidad, las pertenencias y la configuración de la autenticación multifactor. Para obtener más información sobre B2B de Azure AD, vea [¿Qué es la colaboración B2B de Azure ad?](https://go.microsoft.com/fwlink/p/?linkid=853011) y [preguntas frecuentes sobre la colaboración B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams siempre respeta la configuración externa de Azure AD para permitir o evitar adiciones de usuarios invitados al inquilino. Para obtener más información, consulte [autorizar el acceso de invitados en Microsoft Teams](Teams-dependencies.md).


## <a name="guest-access-licensing-limits"></a>Límites de licencias de acceso de invitado

Teams no limita el número de invitados que se pueden agregar. Sin embargo, el número total de invitados que se pueden agregar a su espacio empresarial depende de su licencia de Azure AD. Generalmente, son 5 invitados por usuario con licencia. Para obtener más información, vea [Licencia de colaboración de Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

Debido a estas limitaciones de licencia (y a mantener su inquilino actualizado), debe revisar el acceso de invitados periódicamente para identificar a los usuarios que tienen acceso que ya no necesitan. Puede usar Azure AD para crear una revisión de Access para miembros del grupo o usuarios asignados a una aplicación. Crear revisiones recurrentes de Access puede ahorrar tiempo. Si necesita revisar de forma rutinaria los usuarios que tienen acceso a una aplicación o son miembros de un grupo, puede definir la frecuencia de dichas revisiones. 

Puede realizar una revisión de acceso de invitado, pedir a los invitados que revisen su propio miembro o pedirle al propietario de la aplicación o al responsable de la toma de decisiones que realice la revisión de Access. Use el portal de Azure para realizar revisiones de acceso de invitado. Para obtener más información, vea [administrar el acceso de invitados con revisiones de Access de Azure ad](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Requisitos previos para las revisiones de acceso de Azure AD

Las revisiones de Access están disponibles con la edición P2 Premium de Azure AD, que se incluye en Microsoft Enterprise Mobility + Security, E5. Para obtener más información, vea [Azure Active Directory Editions](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis). Cada uno de los usuarios que interactúen con esta característica mediante la creación de una revisión, la reintroducción de una revisión o la confirmación de su acceso, deben tener una licencia.



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>Tiempo de posposición para que la configuración de acceso de invitado surta efecto

Para la configuración de acceso de invitado en Azure Active Directory, tarda 2-24 horas para que los cambios surtan efecto en Microsoft 365 u Office 365. Si un usuario ve el mensaje "Póngase en contacto con el administrador" cuando intenta agregar un invitado a su equipo, es posible que la característica de invitado no se haya activado o que la configuración aún no sea efectiva. Para obtener ayuda con problemas para configurar el acceso de invitados, lea [solucionar problemas de acceso de invitados en Teams](troubleshoot-guest-access.md).

  
## <a name="external-access-federation-vs-guest-access"></a>Acceso externo (federación) frente a acceso de invitado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Más información

Para obtener información sobre cómo usar PowerShell para administrar el acceso de invitados, consulte [usar PowerShell para controlar el acceso de invitados a un equipo](guest-access-powershell.md).


