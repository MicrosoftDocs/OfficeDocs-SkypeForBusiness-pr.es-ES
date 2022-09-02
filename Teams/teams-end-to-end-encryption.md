---
title: Cifrado de un extremo a otro para Microsoft Teams
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 03/08/2022
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: Obtenga información sobre las capacidades de cifrado mejoradas en Microsoft Teams y administre el cifrado de un extremo a otro mediante el Centro de administración de Teams y Microsoft PowerShell.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: e090c465b46370367d96a782e12f38161465ce33
ms.sourcegitcommit: 479e236aa8a9a91df4894ed3cce4c287a1354d80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67572090"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls"></a>Usar el cifrado de un extremo a otro para las llamadas de Microsoft Teams uno a uno

> [!IMPORTANT]
> El modelo de servicio de Teams y su compatibilidad con el cifrado están sujetos a cambios para mejorar las experiencias de los clientes. Por ejemplo, el servicio deja de usar periódicamente conjuntos de cifrado que ya no se consideran seguros. Cualquiera de estos cambios se haría con el objetivo de mantener Teams seguro y confiable por naturaleza. Además, todo el contenido de los clientes de los centros de datos de Microsoft está cifrado. Para obtener información sobre las capas de cifrado en Microsoft 365, consulte [Cifrado en Microsoft 365](/microsoft-365/compliance/encryption).

El cifrado de un extremo a otro, o E2EE, se produce cuando el contenido se cifra antes de que el destinatario previsto lo envíe y descifre. Con el cifrado de un extremo a otro, solo los dos sistemas de punto de conexión están implicados en el cifrado y descifrado de los datos de llamada. Ninguna otra parte, incluido Microsoft, tiene acceso a la conversación descifrada.

Con E2EE para las llamadas individuales no programadas, sólo el flujo de medios en tiempo real, es decir, los datos de vídeo y de voz, para las llamadas de equipos individuales están cifrados de extremo a extremo. Ambas partes deben activar esta configuración para habilitar el cifrado de un extremo a otro. El [Cifrado en Microsoft 365](/microsoft-365/compliance/encryption) protege el chat, el uso compartido de archivos, la presencia y otro contenido en la llamada.

Las llamadas cifradas de un extremo a otro se pueden realizar entre dos partes cuando: las partes usan la versión más reciente del cliente de escritorio de Teams para Windows o Mac, están en un dispositivo móvil con la actualización más reciente para iOS y Android, o están en una Salas de Teams en un dispositivo Windows con la actualización más reciente.

Si no habilita el cifrado de un extremo a otro, Teams todavía protege una llamada o reunión mediante el cifrado basado en estándares del sector. Los datos intercambiados durante las llamadas siempre son seguros mientras están en tránsito y en reposo. Para obtener más información, vea [Cifrado multimedia para Teams](teams-security-guide.md#media-encryption).

Durante una llamada cifrada de un extremo a otro, Teams protege las siguientes características:

- Audio

- Vídeo

- Pantalla compartida

Las siguientes características avanzadas no están disponibles durante una llamada E2EE:

- Subtítulos en directo y transcripción

- Transferencia de llamada

- Combinación de llamadas

- Estacionar llamada

- Consultar y después transferir

- Llamar al complemento y transferir a otro dispositivo

- Añadiendo un participante

- Grabación

Además, si su organización usa la grabación de cumplimiento, el cifrado de un extremo a otro no está disponible. Para obtener más información sobre cómo Teams admite la grabación de cumplimiento, vea [Introducción a la grabación basada en directivas de Teams para llamadas y reuniones](teams-recording-policy.md).

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>Configurar el cifrado de un extremo a otro para Microsoft Teams

Complete estas tareas para que los usuarios puedan realizar llamadas cifradas de un extremo a otro.

- Habilite el cifrado de un extremo a otro para su organización mediante la creación de una o varias directivas que definan quién puede usar el cifrado de un extremo a otro. Antes de empezar, asegúrese de que a su cuenta profesional o educativa se le ha asignado el rol de administrador global o de Teams. Para obtener información, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md). Cuando esté listo para configurar E2EE, puede usar el Centro de administración de Teams o Microsoft PowerShell.

- Active las llamadas cifradas de un extremo a otro en la configuración de Teams en su dispositivo. Cada usuario necesita completar esta tarea, pero solo tiene que hacerlo en un dispositivo. Teams sincroniza esta configuración entre los puntos de conexión admitidos para cada usuario. Para obtener instrucciones, vea [Usar el cifrado de un extremo a otro para llamadas de Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>Usar el Centro de administración de Teams para configurar el cifrado de un extremo a otro

La directiva global, predeterminada para toda la organización especifica que el cifrado de un extremo a otro está deshabilitado. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Para habilitar el cifrado de un extremo a otro, cree una nueva directiva de cifrado o modifique la directiva predeterminada global. Para habilitar el cifrado de un extremo a otro mediante el Centro de administración de Teams, complete estos pasos.

1. Con una cuenta profesional o educativa a la que se haya asignado el rol de administrador global o de Teams, inicie sesión en el centro de administración de [Teams](https://admin.teams.microsoft.com/).

2. Vaya a **Directivas de cifrado mejoradas**.

3. Elija la directiva predeterminada o elija **Agregar** para agregar una nueva directiva y, a continuación, asigne un nombre a la nueva directiva.

4. Para habilitar el cifrado de extremo a extremo para los usuarios, para **Cifrado de llamadas de extremo a extremo**, elija **Anulación por parte del usuario deshabilitada** y, a continuación, elija **Guardar**.

   Para deshabilitar el cifrado de extremo a extremo, elija **Deshabilitado**.

Una vez que haya terminado de configurar la directiva, asígnela a usuarios, grupos o a todo el inquilino de la misma manera que administra otras directivas de Teams. Para obtener información sobre el uso de directivas en Teams, vea [Administrar Teams con directivas](manage-teams-with-policies.md).

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>Uso de Microsoft PowerShell para configurar el cifrado de un extremo a otro

Puede administrar directivas de cifrado de un extremo a otro mediante Microsoft PowerShell y el Centro de administración de Teams. En el módulo de PowerShell de Teams se incluyen varios cmdlets de cifrado de un extremo a otro y se documentan en la [Referencia de cmdlets de Microsoft Teams](/powershell/teams/?view=teams-ps&preserve-view=true). En este artículo se enumeran los cmdlets que puede usar y se proporcionan configuraciones de ejemplo sencillas. Estas configuraciones usan la directiva global predeterminada. Es posible que su organización requiera una configuración de directiva más compleja. En la referencia de cmdlet se proporciona información completa sobre estos cmdlets.

Cmdlets de PowerShell de cifrado de un extremo a otro:

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) devuelve información sobre las directivas de cifrado mejoradas de Teams en su organización.

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) asigna y anula la asignación de directivas de cifrado mejoradas existentes a un usuario. Usar `$NULL` para anular la asignación de todas las directivas de un usuario.

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) crea una nueva directiva de cifrado mejorada de Teams.

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) elimina una directiva de cifrado mejorada de la organización. No se puede eliminar la directiva global predeterminada.

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) actualiza los valores en una directiva de cifrado mejorada de Teams existente.

Su cuenta de trabajo o escuela necesita el Teams o el rol de administrador global para configurar el cifrado de un extremo a otro.

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Para habilitar el cifrado de un extremo a otro para todo el inquilino mediante la directiva global

Para habilitar el cifrado de un extremo a otro para todo el inquilino estableciendo la directiva global predeterminada, ejecute el cmdlet [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) como se indica a continuación.

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

Donde:

- `Global` significa que está estableciendo esta configuración en la directiva predeterminada global de toda la organización.

- `DisabledUserOverride` significa que E2EE está deshabilitado en Teams de forma predeterminada, pero los usuarios pueden invalidar el valor predeterminado y activar E2EE en su configuración de Teams.

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Para deshabilitar el cifrado de un extremo a otro para todo el inquilino mediante la directiva global

Si ha realizado cambios en la directiva global, puede volver a cambiar la configuración ejecutando el cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) como se indica a continuación.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

Donde:

- `Global` significa que está estableciendo esta configuración en la directiva predeterminada global de toda la organización.

- `Disabled` significa que está deshabilitando E2EE para todos los usuarios y los usuarios no pueden activarlo en su configuración de Teams.

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>Para habilitar el cifrado de un extremo a otro para un único usuario

Para habilitar el cifrado de un extremo a otro para un usuario, ejecute el cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) como se indica a continuación.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

Donde:

- *`username`* es el nombre del usuario.

- *`policyname`* es el nombre que desea usar para la directiva. Los nombres de directiva no pueden contener espacios, por ejemplo, ContosoE2EEUserPolicy.

Los usuarios aún necesitan activar las llamadas cifradas de un extremo a otro en su configuración de Teams para poder realizar una llamada cifrada de un extremo a otro. Para ver las instrucciones, consulte [Usar cifrado de extremo a extremo para las llamadas de Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)

Por ejemplo:

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>Para anular la asignación de una directiva de cifrado de un extremo a otro de un solo usuario

Los usuarios pueden tener una única directiva de cifrado asignada a la vez. Cuando se anula la asignación de una directiva de un usuario, se asigna al usuario la directiva global, predeterminada para toda la organización. No se puede anular la asignación de la directiva predeterminada. Para anular la asignación de una directiva de cifrado de un extremo a otro de un usuario, ejecute el cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) como se indica a continuación.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>Activar el cifrado de un extremo a otro en el dispositivo

Para obtener instrucciones, vea [Usar el cifrado de un extremo a otro para llamadas de Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

## <a name="related-topics"></a>Temas relacionados

[Las 12 tareas principales de los equipos de seguridad para dar soporte al trabajo desde casa](/microsoft-365/security/top-security-tasks-for-remote-work)

[Administrar la configuración de reuniones en Microsoft Teams](./meeting-settings-in-teams.md)
