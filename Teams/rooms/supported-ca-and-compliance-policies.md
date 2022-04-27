---
title: Directivas de cumplimiento de dispositivos de Intune y acceso condicional admitidos para Salas de Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Obtenga información sobre las directivas de cumplimiento de dispositivos de Intune y acceso condicional admitidos y recomendados para Salas de Microsoft Teams.
ms.openlocfilehash: 19e4593a6135c79eb156a1b34847ab518d6e8ea4
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059241"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Directivas de cumplimiento de dispositivos de Intune y acceso condicional admitidos para Salas de Microsoft Teams

En este artículo se proporcionan directivas de cumplimiento de dispositivos de Intune y acceso condicional compatibles para Salas de Microsoft Teams. Para conocer los procedimientos recomendados y las directivas de ejemplo, vea [Acceso condicional y Intune procedimientos recomendados de cumplimiento para Salas de Microsoft Teams](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Salas de Teams ya debe implementarse en los dispositivos a los que desea asignar directivas de acceso condicional. Si aún no ha implementado Salas de Teams, vea [Crear cuentas de recursos para salas y dispositivos de Teams compartidos](with-office-365.md) e [Implementar Salas de Microsoft Teams en Android para obtener](../devices/collab-bar-deploy.md) más información.

## <a name="supported-conditional-access-policies"></a>Directivas de acceso condicional admitidas  

La siguiente lista incluye las directivas de acceso condicional admitidas para Salas de Teams en Windows y en Android. 

> [!NOTE]
> Las directivas de Android admitidas se aplican a todos los dispositivos Android en espacios compartidos, incluidos Salas de Teams en Andourd, teléfonos de área común y paneles.

| Asignación | Windows | Android |
|------------|---------|---------|
| Identidades de usuario o carga de trabajo |Compatible | Compatible |
|Aplicaciones o acciones en la nube | Compatible <br><br> Salas de Teams debe tener acceso a las siguientes tres aplicaciones en la nube cuando solo está en Teams modo: Office 365 Exchange Online, Office 365 SharePoint Online y Microsoft Teams | Compatible <br><br> Salas de Teams debe tener acceso a las siguientes tres aplicaciones en la nube cuando solo está en Teams modo: Office 365 Exchange Online, Office 365 SharePoint Online y Microsoft Teams |
|**Condiciones**| --- | --- |
| Riesgo de usuario | Compatible | Compatible |
| Riesgo de inicio de sesión | Compatible | Compatible |
| Plataformas de dispositivos | Compatible | Compatible |
| Ubicaciones | Compatible | Compatible |
|Aplicaciones cliente |No se admite| No se admite |
|Filtrar por dispositivos | Compatible | Compatible |
|**Conceder**| --- | --- |
| Bloquear el acceso | Compatible | Compatible |
| Conceder acceso | Compatible | Compatible | 
| Requerir autenticación multifactor | No se admite | No se admite |
| Requerir que el dispositivo se marque como compatible | Compatible | Compatible |
|Requerir un dispositivo unido a Azure AD híbrido | No se admite | No se admite |
|Requerir aplicación cliente aprobada | No se admite | No se admite |
| Requerir directiva de protección de aplicaciones | No se admite |No se admite |
| Requerir cambio de contraseña | No se admite | No se admite |

> [!NOTE]
> Skype Empresarial Online se ha retirado y no es compatible. Skype Empresarial aplicación en la nube en línea no es compatible con las directivas de acceso condicional basadas en el cumplimiento del dispositivo.

> [!NOTE]
> Salas de Microsoft Teams en Windows deben cumplir los siguientes requisitos para admitir los controles de concesión de cumplimiento del dispositivo:
>
> - Salas de Microsoft Teams aplicación 4.8.19.0 o posterior
> - Windows 10 versión 20H2 y posteriores (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Directivas de cumplimiento de dispositivos compatibles 

Salas de Microsoft Teams en Windows y Salas de Teams en Android admiten diferentes directivas de cumplimiento de dispositivos.

#### <a name="teams-rooms-on-windows"></a>[Salas de Teams en Windows](#tab/mtr-w)

A continuación se muestra una tabla de recomendaciones y configuración de cumplimiento de dispositivos para su uso con Salas de Teams.  

|Directiva | Disponibilidad | Notas|
|---------|-------------|-------|
| [**Estado del dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Requerir BitLocker| Compatible | Usa solo si primero has habilitado BitLocker en Salas de Teams. |
|Requerir el arranque seguro para habilitarse en el dispositivo |Compatible |El arranque seguro es un requisito de Salas de Teams. |
|Requerir integridad de código |Compatible  | La integridad del código ya es un requisito de Salas de Teams. |
| [**Propiedades de dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Versión del sistema operativo (mínimo, máximo) |No se admite | Salas de Teams las actualizaciones automáticas a versiones más recientes de Windows y establecer valores aquí podría impedir el inicio de sesión correcto después de una actualización del sistema operativo.|
|Versión del SO para dispositivos móviles (mínimo, máximo) | No admitido. | N/D |
| Compilaciones válidas del sistema operativo | No se admite | N/D |
| [**cumplimiento de Configuration Manager**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Requerir el cumplimiento del dispositivo de Configuration Manager | Compatible |  N/D |
| [**Seguridad del sistema**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Todas las directivas de contraseñas | No se admite | Las directivas de contraseñas pueden impedir que la cuenta de Skype local inicie sesión automáticamente. |
| Requiere el cifrado de almacenamiento de datos en el dispositivo. | Compatible  | Use solo si primero ha habilitado el cifrado de almacenamiento de datos en Salas de Teams. |
| Firewall | Compatible | El firewall ya es un requisito para Salas de Teams |
| Módulo de plataforma segura (TPM) | Compatible | El Módulo de plataforma segura (TPM) ya es un requisito para Salas de Teams. |
| Antivirus | Compatible | El antivirus (Windows Defender) ya es un requisito de Salas de Teams. |
| Antispyware | Compatible | Antispyware (Windows Defender) ya es un requisito de Salas de Teams. |
| Microsoft Defender Antimalware | Compatible | El antimalware de Microsoft Defender ya es un requisito de Salas de Teams. |
| Versión mínima antimalware de Microsoft Defender | No admitido. | Salas de Teams actualiza automáticamente este componente, por lo que no es necesario establecer directivas de cumplimiento.|
| Inteligencia de seguridad antimalware de Microsoft Defender
actualizado | Compatible | Valida que el antimalware de Microsoft Defender ya es un requisito de Salas de Teams. |
| Protección en tiempo real | Compatible | Las protecciones en tiempo real ya son un requisito de Salas de Teams. |
| [**Microsoft Defender para punto de conexión**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Requiere que el dispositivo esté en o por debajo de la puntuación de riesgo de la máquina. | Compatible |  N/D |

#### <a name="teams-rooms-on-android"></a>[Salas de Teams en Android](#tab/mtr-a)

A continuación se muestra una tabla de recomendaciones y configuración de cumplimiento de dispositivos para su uso con Salas de Teams.  

| Directiva | Disponibilidad | Notas |
|---------|-------------|-------|
| [**Microsoft Defender para punto de conexión**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Requerir que el dispositivo esté en o por debajo de la puntuación de riesgo del equipo | No se admite |  N/D |
| [**Estado del dispositivo**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Dispositivo administrado con el administrador de dispositivos | Obligatorio | Teams la administración de dispositivos Android requiere que el administrador de dispositivos esté habilitado. |
| Dispositivos rooteados | Compatible |  N/D |
| Requerir que el dispositivo esté en o por debajo del nivel de amenaza del dispositivo | No se admite |  N/D |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services está configurado | No se admite | Google Play no está instalado en Teams dispositivos Android. |
| Proveedor de seguridad actualizado | No se admite | Google Play no está instalado en Teams dispositivos Android. |
| Examen de amenazas en aplicaciones | No se admite | Google Play no está instalado en Teams dispositivos Android. |
| Atestación de dispositivo SafetyNet | No se admite | Google Play no está instalado en Teams dispositivos Android.|
| [**Propiedades de dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Versión del sistema operativo (mínimo, máximo) | Compatible |  N/D |
[**Seguridad del sistema**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Requiere el cifrado de almacenamiento de datos en el dispositivo. |Compatible |  N/D |
[**Seguridad del dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloquear aplicaciones de orígenes desconocidos | No se admite | Solo Teams administradores instalan aplicaciones o herramientas OEM |
| Portal de empresa integridad en tiempo de ejecución de la aplicación | Compatible |  N/D|
| Aplicaciones restringidas | No se admite |  N/D |
| Bloquear la depuración USB en el dispositivo | Compatible |  N/D|
[**Todos los dispositivos Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Número máximo de minutos de inactividad antes de que se requiera la contraseña | No se admite |  N/D |
| Requerir una contraseña para desbloquear dispositivos móviles | No se admite | N/D |
| [**Android 10 y versiones posteriores**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 y versiones anteriores o Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Tipo de contraseña necesario |No se admite | N/D|

---
