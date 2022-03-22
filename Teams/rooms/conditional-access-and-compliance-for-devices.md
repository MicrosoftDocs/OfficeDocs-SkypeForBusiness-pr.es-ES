---
title: Procedimientos recomendados de cumplimiento y acceso condicional para Salas de Microsoft Teams
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
description: Obtenga información sobre las directivas recomendadas de cumplimiento de dispositivos de Intune y acceso condicional para Salas de Microsoft Teams.
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689190"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Cumplimiento de Intune y acceso condicional para Salas de Microsoft Teams

En este artículo se proporcionan requisitos y procedimientos recomendados para las directivas de cumplimiento de dispositivos de Intune y acceso condicional para Salas de Microsoft Teams que se usan en espacios compartidos.

## <a name="requirements"></a>Requirements

Salas de Teams ya debe implementarse en los dispositivos a los que desea asignar directivas de acceso condicional. Si aún no ha implementado Salas de Teams, vea Crear cuentas de recursos para [](with-office-365.md) salas y dispositivos Teams compartidos e Implementar [Salas de Microsoft Teams en Android](../devices/collab-bar-deploy.md) para obtener más información.

Se Azure Active Directory plan de servicio P1 para usar el acceso condicional. Se incluye en la Salas de Microsoft Teams licencia.

## <a name="teams-rooms-conditional-access-best-practices"></a>Salas de Teams procedimientos recomendados de acceso condicional

Las directivas de acceso condicional pueden proteger el proceso de inicio de sesión en dispositivos que se encuentran en espacios compartidos y que usan varias personas. Para obtener información general sobre el acceso condicional en Azure Active Directory (Azure AD), vea ¿Qué es el acceso [condicional en Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Al usar acceso condicional para proteger Salas de Teams, tenga en cuenta los siguientes procedimientos recomendados:

-   Para simplificar la implementación y la administración, incluya todas las Microsoft 365 de recursos de sala asociadas a Salas de Teams en un grupo de usuarios.

-   Tenga un estándar de nomenclatura para todas las Salas de Teams recursos. Por ejemplo, los nombres de cuenta "mtr-room1@contoso.com" y "mtr-room2@contoso.com" comienzan con el prefijo "mtr-".
    Cuando los nombres de cuenta están estandarizados, puede usar grupos dinámicos en Azure AD para aplicar automáticamente directivas de acceso condicional a todas estas cuentas a la vez. Vea [Reglas para la pertenencia a grupos rellenados](/azure/active-directory/enterprise-users/groups-dynamic-membership) dinámicamente para obtener más información sobre los grupos dinámicos.

Para obtener una lista de las asignaciones de acceso condicional compatibles Salas de Teams, vea [Directivas de acceso condicional admitido](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Ejemplo de directiva de acceso condicional

En el ejemplo siguiente, la directiva de acceso condicional funciona de la siguiente manera:

1.  La cuenta que inicia sesión debe ser miembro de un grupo de usuarios específico, en este ejemplo, el grupo "Dispositivos compartidos".

2.  El inicio de sesión de la cuenta solo debe intentar acceder a Exchange Online, Microsoft Teams o SharePoint en línea. Se rechazarán los intentos de iniciar sesión en cualquier otra aplicación cliente.

3.  La cuenta de recursos debe iniciar sesión en la Windows dispositivo.

4.  La cuenta de recursos también debe iniciar sesión desde una ubicación conocida de confianza.

Si estas condiciones se cumplen correctamente y el usuario escribe el nombre de usuario y la contraseña correctos, la cuenta de recursos iniciará sesión Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Acceso condicional con Microsoft Intune cumplimiento normativo Salas de Teams

Los requisitos de cumplimiento son reglas definidas que los dispositivos deben cumplir para que se marquen como compatibles, como la versión mínima del sistema operativo. Los dispositivos deben considerarse compatibles antes de poder usarse para iniciar sesión en una cuenta de recursos.

Para obtener una lista de directivas de cumplimiento de Intune compatibles Salas de Teams, vea [Directivas de cumplimiento de dispositivos compatibles](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Para obtener más información sobre cómo configurar Intune Teams dispositivos Android, vea Configurar Intune para inscribir Teams [dispositivos basados en Android](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Ejemplo (solo Windows): Acceso condicional con el cumplimiento de dispositivos intune

En este ejemplo para Salas de Teams en Windows

1. Requerir que se ejecute un firewall en Salas de Teams en Windows.

2. Requiere que Microsoft Defender se ejecute en Salas de Teams.

3. Si un Teams no cumple ninguno de estos requisitos, no se marcará como compatible y los dispositivos no iniciarán sesión.

Esta directiva de cumplimiento se aplica a todos los usuarios, no solo a Teams de recursos.
