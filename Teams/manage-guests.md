---
title: Administrar el acceso de invitado en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Los administradores de TI pueden agregar invitados en el nivel de inquilino, configurar y administrar permisos y directivas de usuarios invitados, determinar qué usuarios pueden invitar y extraer informes sobre la actividad de los usuarios invitados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3ede35352436074cbf7c94fc9df78100a73a017
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241813"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Administrar el acceso de invitado en Microsoft Teams
======================================

**Invitado** es un tipo de usuario o licencia de Microsoft teams que se incluye con todas las suscripciones de Office 365 Business Premium, Office 365 Enterprise y Office 365 Education. No se necesita ninguna otra licencia de Office 365. El acceso de invitado de Teams es una configuración a nivel de inquilino y se encuentra desactivada de forma predeterminada. Para obtener más información sobre cómo habilitar el acceso de invitado, vea [activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).

Después de activar el tipo de licencia o usuario **invitado** , puede configurar las opciones para los invitados a través de los controles descritos en [administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md) y [administrar equipos durante la transición al nuevo Microsoft Teams. Centro de administración](manage-teams-skypeforbusiness-admin-center.md).     
    
Los administradores de TI pueden agregar invitados en el nivel de espacio empresarial, establecer y administrar las directivas y permisos de los usuarios invitados, y extraer informes sobre la actividad de los usuarios invitados. Estos controles están disponibles a través del centro de administración de Microsoft Teams. Las actividades y el contenido de los usuarios invitados están protegidos con el mismo cumplimiento de normativas y auditorías que el resto de Office 365.

Los propietarios de equipo pueden invitar a nuevos invitados y agregar usuarios de invitados a sus equipos. Los propietarios de equipo pueden identificar a los usuarios invitados a través de **Teams** > **Manage Teams**y establecer capacidades relacionadas con los canales para los invitados a través de la configuración > de invitado de **la organización****acceso de invitado**, que incluye permitir a los invitados crear, actualizar y Elimine los canales, como se muestra en la siguiente ilustración.

![Configuración de los permisos de invitado en Teams](media/manage-guest-access-image1.png)
  
Puede usar el portal de Azure Active Directory (Azure AD) para administrar los invitados y su acceso a los recursos de Office 365 y Teams. El acceso de invitado de Teams usa las capacidades de colaboración de Azure AD negocio a negocio (B2B) como la infraestructura subyacente para almacenar información sobre los principios de seguridad, como las propiedades de identidad, las pertenencias y la configuración de la autenticación multifactor. Para obtener más información sobre B2B de Azure AD, vea [¿Qué es la colaboración B2B de Azure ad?](https://go.microsoft.com/fwlink/p/?linkid=853011) y [preguntas frecuentes sobre la colaboración B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams siempre respeta la configuración externa de Azure AD para permitir o evitar adiciones de usuarios invitados al inquilino. Para obtener más información, consulte autorizar el [acceso de invitados en Microsoft Teams](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>Diferencias entre el acceso de invitados y el acceso externo (federación)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>Revisar periódicamente el acceso de invitados

En Teams, puede Agregar 5 invitados por cada usuario con licencia. A causa de esta limitación, o porque desea mantener el inquilino actualizado, debe revisar el acceso de invitados periódicamente para identificar a los usuarios que tienen acceso que ya no necesitan. Puede usar Azure AD para crear una revisión de Access para miembros del grupo o usuarios asignados a una aplicación. Crear revisiones recurrentes de Access puede ahorrar tiempo. Si necesita revisar de forma rutinaria los usuarios que tienen acceso a una aplicación o son miembros de un grupo, puede definir la frecuencia de dichas revisiones. 

Puede realizar una revisión de acceso de invitado, pedir a los invitados que revisen su propio miembro o pedirle al propietario de la aplicación o al responsable de la toma de decisiones que realice la revisión de Access. Use el portal de Azure para realizar revisiones de acceso de invitado. Para obtener más información, vea [administrar el acceso de invitados con revisiones de Access de Azure ad](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites"></a>Requisitos previos

Las revisiones de Access están disponibles con la edición P2 Premium de Azure AD, que se incluye en Microsoft Enterprise Mobility + Security, E5. Para obtener más información, vea [Azure Active Directory Editions](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis). Cada uno de los usuarios que interactúen con esta característica mediante la creación de una revisión, la reintroducción de una revisión o la confirmación de su acceso, deben tener una licencia.

Teams no restringe el número de invitados que puede Agregar. Sin embargo, el número total de invitados que se pueden agregar a su inquilino se basa en lo que permite la licencia de AAD. Para obtener más información, vea [licencias de colaboración B2B de Azure ad](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="guest-access-latencies"></a>Latencias de acceso de invitado

La configuración de invitado se establece en Azure AD. Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365. Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que la característica de invitado no esté habilitada o que la configuración no haya entrado aún en vigor.

## <a name="more-information"></a>Más información

Para obtener información sobre cómo usar PowerShell para administrar el acceso de invitados, consulte [usar PowerShell para controlar el acceso de invitados a un equipo](guest-access-powershell.md).


