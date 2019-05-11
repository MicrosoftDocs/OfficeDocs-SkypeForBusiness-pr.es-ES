---
title: Administrar el acceso de invitado en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Los administradores de TI pueden agregar invitados en el nivel de inquilino, configurar y administrar permisos y directivas de usuarios invitados, determinar qué usuarios pueden invitar y extraer informes sobre la actividad de los usuarios invitados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44769df812e667ab5b108dcb42d8bb96453f15af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885109"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Administrar el acceso de invitado en Microsoft Teams
======================================

**Invitado** es un tipo de licencia de usuario o en Microsoft Teams que se incluye con todas las suscripciones a Office 365 Business Premium, Office 365 Enterprise y Office 365 educación. No se necesita ninguna otra licencia de Office 365. El acceso de invitado de Teams es una configuración a nivel de inquilino y se encuentra desactivada de forma predeterminada. Para obtener información detallada acerca de cómo habilitar el acceso de invitado, vea [Activar o desactivar el acceso de invitado a los equipos de Microsoft](set-up-guests.md).

Después de que el tipo de licencia de usuario o **invitado** está activado, puede establecer la configuración para invitados a través de los controles que describen en [y la [configuración de administración de equipos de Microsoft para su organización](enable-features-office-365.md) administrar equipos durante la transición a la nueva Teams Microsoft Centro de administración de](manage-teams-skypeforbusiness-admin-center.md).     
    
Los administradores de TI pueden agregar invitados en el nivel de inquilino, establecer y administrar los permisos y las directivas de usuario de invitado y extracción informa sobre la actividad de usuario de invitado. Estos controles están disponibles a través del centro de administración de Microsoft Teams. Las actividades y el contenido de los usuarios invitados están protegidos con el mismo cumplimiento de normativas y auditorías que el resto de Office 365.

Los propietarios de equipo pueden invitar a nuevos invitados y agregue los usuarios invitados de Active directory existente a sus equipos. Los propietarios de equipo pueden identificar a los usuarios de invitado a través de **los equipos** > **administrar equipos**y las capacidades relacionadas con el canal de conjunto de invitados a través de la **configuración de toda la organización** > **acceso como invitado**, incluido el permiso de invitados crear, actualizar, y eliminar canales, como se muestra en la siguiente captura de pantalla.

![Configuración de permisos de invitado en los equipos](media/manage-guest-access-image1.png)
  
Puede usar el portal de Azure Active Directory para administrar los invitados y su acceso a Office 365 y recursos de los equipos. El acceso de invitado de Microsoft Teams puede aprovechar las funcionalidades de colaboración negocio a negocio (B2B) de Azure Active Directory como la infraestructura subyacente donde almacenar la información relacionada con los principios de seguridad (como las propiedades de identidad, las suscripciones y la configuración de autenticación multifactor). Para obtener más información sobre la colaboración B2B de Azure Active Directory, consulte [¿Qué es la colaboración B2B de Azure AD?](https://go.microsoft.com/fwlink/p/?linkid=853011) y [Preguntas más frecuentes acerca de la colaboración B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams siempre respeta la configuración externa de Azure Active Directory para permitir o evitar adiciones de usuario de invitado para el inquilino. Para obtener más información, vea [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>Diferencias entre el acceso de invitados y el acceso externo (federación)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>Revise periódicamente el acceso como invitado

En los equipos, puede agregar a 5 invitados para cada usuario con licencia. Debido a esta limitación, o debido a que desea mantener el inquilino al día, debe revisar periódicamente para identificar a los usuarios que tienen acceso a los que no necesite acceso como invitado. Puede usar Azure Active Directory (AD Azure) para crear una revisión de acceso para los miembros del grupo o los usuarios asignados a una aplicación. Creación periódica access revisiones pueden ahorrar tiempo. Si necesita revisar periódicamente los usuarios que tienen acceso a una aplicación o son miembros de un grupo, puede definir la frecuencia de las revisiones. 

Puede realizar una revisión de acceso de invitado usted mismo, pregunte invitados para revisar su propia pertenencia o solicite un propietario de la aplicación o la toma de decisiones para llevar a cabo la revisión de acceso. Utilice el portal de Azure para llevar a cabo revisiones de acceso de invitado. Para obtener más información, vea [administrar el acceso de invitado con acceso de Azure AD revisa](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites"></a>Requisitos previos

Revisiones de Access están disponibles con la edición Premium P2 de Azure AD, que se incluye en Microsoft Enterprise movilidad + seguridad, E5. Para obtener más información, vea "Elegir una edición" en [las ediciones de Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis). Cada usuario que interactúa con esta característica mediante la creación de una revisión, rellenar una revisión o confirmar su acceso, debe tener una licencia. 

Los equipos no limita el número de invitados que se puede agregar. Sin embargo, el número total de los invitados que se pueden agregar a su inquilino se basa en qué su AAD de licencias permite. Para obtener más información, vea [licencias de colaboración de Azure AD B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="guest-access-latencies"></a>Latencias de acceso de invitado

La configuración de invitado se establece en Azure Active Directory. Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365. Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que la característica de invitado no esté habilitada o que la configuración no haya entrado aún en vigor.

## <a name="more-information"></a>Más información

Para obtener información acerca del uso de PowerShell para administrar el acceso de invitado, consulte [Use PowerShell para controlar el acceso de invitado a un equipo](guest-access-powershell.md).


