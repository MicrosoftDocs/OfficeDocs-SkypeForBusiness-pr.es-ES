---
title: Directivas de cumplimiento de dispositivos de Intune y acceso condicional compatibles Salas de Microsoft Teams
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
description: Obtenga información sobre las directivas de cumplimiento de dispositivos de Intune y acceso condicional admitidas y recomendadas para Salas de Microsoft Teams.
ms.openlocfilehash: f3b115430779324a260232ce45ba125859abdde8
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689184"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Directivas de cumplimiento de dispositivos de Intune y acceso condicional compatibles Salas de Microsoft Teams

En este artículo se proporcionan directivas de cumplimiento de dispositivos de Intune y acceso condicional compatibles para Salas de Microsoft Teams. Para obtener procedimientos recomendados y directivas de ejemplo, vea Procedimientos recomendados de cumplimiento de Intune y acceso condicional [para Salas de Microsoft Teams](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Salas de Teams ya debe implementarse en los dispositivos a los que desea asignar directivas de acceso condicional. Si aún no ha implementado Salas de Teams, vea Crear cuentas de recursos para [](with-office-365.md) salas y dispositivos Teams compartidos e Implementar [Salas de Microsoft Teams en Android](../devices/collab-bar-deploy.md) para obtener más información.

## <a name="supported-conditional-access-policies"></a>Directivas de acceso condicional compatibles  

En la lista siguiente se incluyen las directivas de acceso condicional compatibles para Salas de Teams en Windows y en Android:

| Asignación | Windows | Android |
|------------|---------|---------|
| Identidades de usuario o carga de trabajo |Compatible | Compatible |
|Acciones o aplicaciones en la nube | Compatible <br><br> Salas de Teams tener acceso a las tres aplicaciones en la nube siguientes cuando se encuentra en Teams modo único: Office 365 Exchange Online, Office 365 SharePoint Online y Microsoft Teams | Compatible <br><br> Salas de Teams tener acceso a las tres aplicaciones en la nube siguientes cuando se encuentra en Teams modo único: Office 365 Exchange Online, Office 365 SharePoint Online y Microsoft Teams |
|**Condiciones**| --- | --- |
| Riesgo de usuario | Compatible | Compatible |
| Riesgo de inicio de sesión | Compatible | Compatible |
| Plataformas de dispositivos | Compatible | Compatible |
| Ubicaciones | Compatible | Compatible |
|Aplicaciones cliente |No se admite| No se admite |
|Filtro para dispositivos | Compatible | Compatible |
|**Conceder**| --- | --- |
| Bloquear el acceso | Compatible | Compatible |
| Conceder acceso | Compatible | Compatible | 
| Requerir autenticación multifactor | No se admite | No se admite |
| Requerir que el dispositivo se marque como compatible | Compatible | Compatible |
|Requerir dispositivo Azure AD híbrido unido | No se admite | No se admite |
|Requerir aplicación de cliente aprobada | No se admite | No se admite |
| Requerir directiva de protección de aplicaciones | No se admite |No se admite |
| Requerir cambio de contraseña | No se admite | No se admite |

> [!NOTE]
> Skype Empresarial Online se retira y no se admite. Skype Empresarial aplicación en la nube en línea no es compatible con directivas de acceso condicional basadas en el cumplimiento de dispositivos.

> [!NOTE]
> Salas de Microsoft Teams en Windows deben cumplir los siguientes requisitos para admitir los controles de concesión de cumplimiento del dispositivo:
>
> - Salas de Microsoft Teams aplicación 4.8.19.0 o posterior
> - Windows 10 versión 20H2 y posteriores (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Directivas de cumplimiento de dispositivos compatibles 

Salas de Microsoft Teams en Windows y Salas de Teams android admiten diferentes directivas de cumplimiento de dispositivos.

#### <a name="teams-rooms-on-windows"></a>[Salas de Teams en Windows](#tab/mtr-w)

A continuación se muestra una tabla de configuración de cumplimiento de dispositivos y recomendaciones para su uso con Salas de Teams.  

|Directiva | Disponibilidad | Notas|
|---------|-------------|-------|
| [**Estado del dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Requerir BitLocker| Compatible | Solo se usa si primero ha habilitado BitLocker en Salas de Teams. |
|Requerir que el inicio seguro esté habilitado en el dispositivo |Compatible |El inicio seguro es un requisito para Salas de Teams. |
|Requerir integridad del código |Compatible  | La integridad del código ya es un requisito para Salas de Teams. |
| [**Propiedades del dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Versión del sistema operativo (mínima, máxima) |No se admite | Salas de Teams se actualiza automáticamente a las versiones más recientes de Windows y los valores de configuración aquí podrían impedir el inicio de sesión correcto después de una actualización del sistema operativo.|
|Versión del sistema operativo para dispositivos móviles (mínimo, máximo) | No admitido. | N/D |
| Compilaciones válidas del sistema operativo | No se admite | N/D |
| [**Cumplimiento de Configuration Manager**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Requerir el cumplimiento de dispositivos de Configuration Manager | Compatible |  N/D |
| [**Seguridad del sistema**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Todas las directivas de contraseña | No se admite | Las directivas de contraseña pueden impedir que Skype cuenta local inicie sesión automáticamente. |
| Requerir cifrado de almacenamiento de datos en el dispositivo. | Compatible  | Solo se usa si primero ha habilitado el cifrado del almacenamiento de datos en Salas de Teams. |
| Firewall | Compatible | El firewall ya es un requisito para Salas de Teams |
| Módulo de plataforma de confianza (TPM) | Compatible | El Módulo de plataforma de confianza (TPM) ya es un requisito para Salas de Teams. |
| Antivirus | Compatible | Antivirus (Windows Defender) ya es un requisito para Salas de Teams. |
| Antispyware | Compatible | Antispyware (Windows Defender) ya es un requisito para Salas de Teams. |
| Microsoft Defender Antimalware | Compatible | Microsoft Defender Antimalware ya es un requisito para Salas de Teams. |
| Versión mínima antimalware de Microsoft Defender | No admitido. | Salas de Teams actualiza automáticamente este componente para que no sea necesario establecer directivas de cumplimiento.|
| Inteligencia de seguridad de Microsoft Defender Antimalware
actualizado | Compatible | Valide que Microsoft Defender Antimalware ya es un requisito para Salas de Teams. |
| Protección en tiempo real | Compatible | Las protecciones en tiempo real ya son un requisito para Salas de Teams. |
| [**Microsoft Defender para endpoint**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Requerir que el dispositivo esté en o debajo de la puntuación de riesgo de la máquina. | Compatible |  N/D |

#### <a name="teams-rooms-on-android"></a>[Salas de Teams en Android](#tab/mtr-a)

A continuación se muestra una tabla de configuración de cumplimiento de dispositivos y recomendaciones para su uso con Salas de Teams.  

| Directiva | Disponibilidad | Notas |
|---------|-------------|-------|
| [**Microsoft Defender para endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Requerir que el dispositivo esté en o debajo de la puntuación de riesgo de la máquina | No se admite |  N/D |
| [**Estado del dispositivo**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Dispositivo administrado con el administrador de dispositivos | No admitido. | Teams dispositivos Android se administran con dispositivos
administrador. |
| Dispositivos rooteados | Compatible |  N/D |
| Requerir que el dispositivo esté en o bajo el nivel de amenaza del dispositivo | No se admite |  N/D |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services está configurado | No se admite | Google Play no está instalado en Teams dispositivos Android. |
| Proveedor de seguridad actualizado | No se admite | Google Play no está instalado en Teams dispositivos Android. |
| Análisis de amenazas en aplicaciones | No se admite | Google Play no está instalado en Teams dispositivos Android. |
| Atestación del dispositivo SafetyNet | No se admite | Google Play no está instalado en Teams dispositivos Android.|
| [**Propiedades del dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Versión del sistema operativo (mínima, máxima) | Compatible |  N/D |
[**Seguridad del sistema**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Requerir cifrado de almacenamiento de datos en el dispositivo. |Compatible |  N/D |
[**Seguridad del dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloquear aplicaciones de orígenes desconocidos | No se admite | Solo Teams los administradores instalan aplicaciones o herramientas OEM |
| Portal de empresa de tiempo de ejecución de la aplicación | Compatible |  N/D|
| Aplicaciones restringidas | No se admite |  N/D |
| Bloquear la depuración USB en el dispositivo | Compatible |  N/D|
[**Todos los dispositivos Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Minutos máximos de inactividad antes de que se requiera la contraseña | No se admite |  N/D |
| Requerir una contraseña para desbloquear dispositivos móviles | No se admite | N/D |
| [**Android 10 y versiones posteriores**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 y versiones anteriores o Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Tipo de contraseña obligatorio |No se admite | N/D|

---
