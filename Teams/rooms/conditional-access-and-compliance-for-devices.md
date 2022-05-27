---
title: Procedimientos recomendados de acceso condicional y cumplimiento para Salas de Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Obtenga más información sobre las directivas recomendadas de cumplimiento del dispositivo de Intune y el acceso condicional y los procedimientos recomendados para Salas de Microsoft Teams.
ms.openlocfilehash: b4e1d3cb91ff68e664d590c8e180e55211ca93b0
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675492"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Cumplimiento de Intune y acceso condicional para Salas de Microsoft Teams

En este artículo se proporcionan requisitos y procedimientos recomendados para las directivas de cumplimiento de dispositivos de Intune y acceso condicional para Salas de Microsoft Teams que se usan en espacios compartidos.

## <a name="requirements"></a>Requirements

Salas de Teams ya debe implementarse en los dispositivos a los que desea asignar directivas de acceso condicional. Si aún no ha implementado Salas de Teams, vea [Crear cuentas de recursos para salas y dispositivos de Teams compartidos](with-office-365.md) e [Implementar Salas de Microsoft Teams en Android](../devices/collab-bar-deploy.md) para obtener más información.

Se requiere un plan de servicio Azure Active Directory P1 para usar el acceso condicional. Se incluye en la licencia de Salas de Microsoft Teams.

## <a name="teams-rooms-conditional-access-best-practices"></a>Salas de Teams procedimientos recomendados de acceso condicional

Las directivas de acceso condicional pueden proteger el proceso de inicio de sesión en dispositivos que están en espacios compartidos y que usan varias personas. Para obtener información general sobre el acceso condicional en Azure Active Directory (Azure AD), vea [¿Qué es el acceso condicional en Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Al usar acceso condicional para proteger Salas de Teams, tenga en cuenta los siguientes procedimientos recomendados:

-   Para simplificar la implementación y la administración, incluya todas las cuentas de recursos de sala Microsoft 365 asociadas con Salas de Teams en un grupo de usuarios.

-   Tenga un estándar de nomenclatura para todas las cuentas de recursos Salas de Teams. Por ejemplo, los nombres de cuenta "mtr-room1@contoso.com" y "mtr-room2@contoso.com" comienzan con el prefijo "mtr-".
    Cuando los nombres de cuenta están estandarizados, puede usar grupos dinámicos en Azure AD para aplicar automáticamente directivas de acceso condicional a todas estas cuentas a la vez. Vea [Reglas para la pertenencia a grupos rellenados dinámicamente](/azure/active-directory/enterprise-users/groups-dynamic-membership) para obtener más información sobre los grupos dinámicos.

Para obtener una lista de las asignaciones de acceso condicional admitidas para Salas de Teams, vea [Directivas de acceso condicional compatibles](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Directiva de acceso condicional de ejemplo

En el ejemplo siguiente, la directiva de acceso condicional funciona de la siguiente manera:

1.  El inicio de sesión de la cuenta debe ser un miembro de un grupo de usuarios específico, en este ejemplo, el grupo "Dispositivos compartidos".

2.  El inicio de sesión de la cuenta solo debe intentar acceder a Exchange Online, Microsoft Teams o SharePoint Online. Se rechazarán los intentos de iniciar sesión en cualquier otra aplicación cliente.

3.  La cuenta de recursos debe iniciar sesión en la plataforma del dispositivo Windows.

4.  La cuenta de recursos también debe iniciar sesión desde una ubicación de confianza conocida.

Si estas condiciones se cumplen correctamente y el usuario escribe el nombre de usuario y la contraseña correctos, la cuenta del recurso iniciará sesión en Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Acceso condicional con cumplimiento de Microsoft Intune para Salas de Teams

Los requisitos de cumplimiento son reglas definidas que los dispositivos deben cumplir para que se marquen como compatibles, como la versión mínima del sistema operativo. Los dispositivos deben considerarse compatibles antes de poder usarse para iniciar sesión en una cuenta de recursos.

Para obtener una lista de las directivas de cumplimiento de Intune admitidas para Salas de Teams, consulte [Directivas de cumplimiento de dispositivos compatibles](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Para obtener más información sobre cómo configurar Intune con dispositivos Teams Android, consulta [Configurar Intune para inscribir dispositivos basados en Teams Android](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Ejemplo (solo Windows): Acceso condicional con cumplimiento de Intune dispositivo

En este ejemplo para Salas de Teams en Windows

1. Es necesario que se esté ejecutando un firewall en Salas de Teams en Windows.

2. Requiere que Microsoft Defender se ejecute en Salas de Teams.

3. Si una sala de Teams no cumple ninguno de estos requisitos, no se marcará como compatible y los dispositivos no iniciarán sesión.

Esta directiva de cumplimiento se aplica a todos los usuarios, no solo a Teams cuentas de recursos.
