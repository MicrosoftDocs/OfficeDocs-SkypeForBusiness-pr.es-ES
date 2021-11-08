---
title: Usar PowerShell para tareas en el menú Cliente
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Summary: Skype Empresarial Server Control panel to Cmdlet mapping for Client menu.'
ms.openlocfilehash: 1dc0c3a9638af8fdec90fccb633909b9ccf40405
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824658"
---
# <a name="client"></a>Client

En este artículo se describe cómo  se pueden obtener resultados similares a los del elemento de menú Cliente en el Panel de control heredado mediante cmdlets.

En este artículo se describen los siguientes submenúes:

- [Cliente](#client)
  - [Directiva de versión de cliente](#client-version-policy)
  - [Configuración de versiones de cliente](#client-version-configuration)
  - [Actualización de dispositivos](#device-update)
  - [Dispositivo de la prueba](#test-device)
  - [Configuración de registro de dispositivo](#device-log-configuration)
  - [Configuración de dispositivos](#device-configuration)
  - [Directiva de movilidad](#mobility-policy)
  - [Configuración de notificaciones de inserción](#push-notification-configuration)

## <a name="client-version-policy"></a>Directiva de versiones de clientes:

El **elemento de** submenú DIRECTIVA DE VERSIÓN DE CLIENTE en el **menú** Cliente devuelve información sobre los clientes admitidos en Skype Empresarial Server cliente. Una directiva de versión de cliente permite especificar aquellos clientes que pueden iniciar sesión en Skype Empresarial Server sistema.

Consideremos las distintas tareas que un usuario puede hacer en **LA** DIRECTIVA DE VERSIÓN DE CLIENTE y los cmdlets de Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las directivas de versión de cliente

   ![Directiva de versión de cliente de lista](./media/clientversionpolicy-1.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Ejemplo***

```powershell
 Get-CsClientVersionPolicy
```

---

> **Escenario 2:** Crear una nueva directiva de versión de cliente

   ![Nueva directiva de versión de cliente](./media/clientversionpolicy-2.png)

***Cmdlet***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***Ejemplo***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Escenario 3:** Obtener detalles de una directiva de versión de cliente elegida

   ![Obtener directiva de versión de cliente](./media/clientversionpolicy-3.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Ejemplo***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar directivas de versión de cliente elegidas

   ![Eliminar directiva de versión de cliente](./media/clientversionpolicy-4.png)

***Cmdlet***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***Ejemplo***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una directiva de versión de cliente

   ![Actualizar directiva de versión de cliente](./media/clientversionpolicy-5.png)

- **Anotación 1: resultado**

    Esta anotación en la imagen indica un resultado, es decir, los datos que se recuperan y se muestran.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Ejemplo***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **Anotación 2: Opción (para el usuario)**

    Esta anotación en la imagen indica una opción para que el usuario implemente, es decir, para obtener los detalles de las reglas de directiva de versión de cliente.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Ejemplo***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **Anotación 3: Opción (para el usuario)**

    Esta anotación en la imagen indica una opción para que el usuario implemente, es decir, crear una nueva regla de directiva de versión de cliente.

    ***Cmdlet***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***Ejemplo***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **Anotación 4: Opción (para el usuario)**

    Esta anotación en la imagen indica una opción para que el usuario implemente, es decir, confirmar o guardar la regla de directiva de versión de cliente recién creada.

    ***Cmdlet***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***Ejemplo***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>Configuración de versiones de cliente

 El elemento de submenú **CONFIGURACIÓN DE** VERSIÓN DE CLIENTE devuelve información sobre los clientes admitidos en Skype Empresarial Server cliente.

Veamos las distintas tareas que un usuario puede hacer en **CONFIGURACIÓN** DE VERSIÓN DE CLIENTE y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las configuraciones de versión de cliente

   ![Configuración de la versión de cliente de lista](./media/ClientVersionConfiguration-1.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Ejemplo***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de versión de cliente

   ![Crear configuración de versión de cliente](./media/ClientVersionConfiguration-2.png)

***Cmdlet***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***Ejemplo***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **Escenario 3:** Obtener detalles de una configuración de versión de cliente elegida

   ![Obtener configuración de versión de cliente](./media/ClientVersionConfiguration-3.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Ejemplo***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar configuraciones de versión de cliente elegidas

   ![Eliminar configuración de versión de cliente](./media/ClientVersionConfiguration-4.png)

***Cmdlet***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***Ejemplo***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una configuración de versión de cliente

   ![Actualizar configuración de versión de cliente](./media/ClientVersionConfiguration-5.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Ejemplo***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **Escenario 6:** Habilitar o deshabilitar configuraciones de versión de cliente

![Habilitar configuración de versión de cliente](./media/ClientVersionConfiguration-6.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Ejemplo***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>Actualización de dispositivos

**Las reglas DEVICE UPDATE** se usan para asociar actualizaciones de firmware con dispositivos que ejecutan Skype Empresarial Teléfono Edition.

Veamos las distintas tareas que un usuario puede hacer en **DEVICE UPDATE** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las actualizaciones del dispositivo

   ![Enumerar actualización de dispositivos](./media/device-update-1.png)

***Cmdlet***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***Ejemplo***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **Escenario 2:** Eliminar actualizaciones de dispositivos

   ![Eliminar actualización de dispositivos](./media/device-update-2.png)

***Cmdlet***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***Ejemplo***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Escenario 3:** Cancelar actualizaciones de dispositivos

   ![Cancelar actualización de dispositivos](./media/device-update-3.png)

***Cmdlet***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***Ejemplo***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **Escenario 4:** Aprobar actualizaciones de dispositivos

   ![Aprobar actualización de dispositivos](./media/device-update-4.png)

***Cmdlet***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***Ejemplo***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Escenario 5:** Restaurar actualizaciones de dispositivos

   ![Restaurar actualización de dispositivos](./media/device-update-5.png)

***Cmdlet***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***Ejemplo***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>Dispositivo de la prueba

El **elemento de** submenú DISPOSITIVO DE PRUEBA proporciona una forma de que los administradores prueben las actualizaciones de firmware antes de que dichas actualizaciones se distribuyen a todos los dispositivos de una organización.

Consideremos las distintas tareas que un usuario puede hacer en **TEST DEVICE** y los cmdlets Skype Empresarial a las que se asignan esas tareas.

---
> **Escenario 1:** Enumerar todos los dispositivos de prueba

   ![Dispositivo de prueba de lista](./media/testdevice-1.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Ejemplo***

```powershell
 Get-CsTestDevice
```

---

> **Escenario 2:** Crear un nuevo dispositivo de prueba

   ![Crear dispositivo de prueba](./media/testdevice-2.png)

***Cmdlet***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***Ejemplo***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **Escenario 3:** Obtener detalles de un dispositivo de prueba elegido

   ![Obtener dispositivo de prueba](./media/testdevice-3.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Ejemplo***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **Escenario 4:** Eliminar dispositivos de prueba elegidos

   ![Eliminar dispositivo de prueba](./media/testdevice-4.png)

***Cmdlet***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***Ejemplo***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar un dispositivo de prueba

   ![Actualizar dispositivo de prueba](./media/testdevice-5.png)

***Cmdlet***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***Ejemplo***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>Configuración de registro de dispositivo

**El** elemento de submenú CONFIGURACIÓN DEL REGISTRO DE DISPOSITIVOs ayuda a administrar el servicio web de actualización de dispositivos, un componente de Skype Empresarial Server que permite a los administradores distribuir actualizaciones de firmware a teléfonos y otros dispositivos que ejecutan Skype Empresarial.

Veamos las distintas tareas que un usuario puede hacer en **DEVICE LOG CONFIGURATION** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---
> **Escenario 1:** Enumerar todas las configuraciones de registro de dispositivos

   ![Enumerar configuración del registro de dispositivos](./media/device-log-configuration-1.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Ejemplo***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de registro de dispositivos

   ![Crear configuración del registro de dispositivos](./media/device-log-configuration-2.png)

***Cmdlet***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***Ejemplo***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **Escenario 3:** Obtener detalles de una configuración de registro de dispositivo elegida

   ![Obtener configuración del registro de dispositivos](./media/device-log-configuration-3.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Ejemplo***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **Escenario 4:** Eliminar las configuraciones de registro de dispositivos elegidas

   ![Eliminar configuración del registro de dispositivos](./media/device-log-configuration-4.png)

***Cmdlet***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***Ejemplo***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualizar una configuración de registro de dispositivos

   ![Actualizar configuración del registro de dispositivos](./media/device-log-configuration-5.png)

***Cmdlet***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***Ejemplo***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>Configuración de dispositivo

**El elemento de** submenú DEVICE CONFIGURATION ayuda a administrar información sobre las opciones de administración de teléfonos UC. Estas opciones incluyen el modo de seguridad requerido y si el teléfono debe bloquearse automáticamente después de un período especificado de inactividad.

Veamos las distintas tareas que un usuario puede hacer en **DEVICE CONFIGURATION** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las directivas de movilidad

   ![Enumerar configuración de dispositivos](./media/device-configuration-1.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Ejemplo***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de dispositivo

   ![Crear configuración de dispositivos](./media/device-configuration-2.png)

***Cmdlet***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***Ejemplo***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **Escenario 3:** Obtener detalles de una configuración de dispositivo elegida

   ![Obtener configuración de dispositivos](./media/device-configuration-3.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Ejemplo***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Escenario 4:** Eliminar las configuraciones de dispositivo elegidas

   ![Eliminar configuración de dispositivos](./media/device-configuration-4.png)

***Cmdlet***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***Ejemplo***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Escenario 5:** Actualiza una configuración de dispositivo

   ![Actualizar configuración de dispositivos](./media/device-configuration-5.png)

***Cmdlet***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***Ejemplo***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>Directiva de movilidad

**MOBILITY POLICY** determina si un usuario puede usar o no Skype Empresarial Mobile. Estas directivas también administran la capacidad de un usuario de usar Vía trabajo, una característica que permite que los usuarios hagan y reciban llamadas telefónicas en su teléfono móvil con el número de teléfono del trabajo en lugar de con su número de teléfono móvil. Las directivas de movilidad también se pueden usar para hacer que Wi-Fi conexiones sea un requisito al realizar o recibir llamadas.

Veamos las distintas tareas que un usuario puede hacer en **MOBILITY POLICY** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las directivas de movilidad

   ![Directiva de movilidad de lista](media/mobility-policy-1.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Ejemplo***

```powershell
 Get-CsMobilityPolicy
```

---

> **Escenario 2:** Crear una nueva directiva de movilidad

   ![Crear directiva de movilidad](./media/mobility-policy-2.png)

***Cmdlet***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***Ejemplo***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **Escenario 3:** Obtener detalles de una directiva de movilidad elegida

   ![Obtener directiva de movilidad](./media/mobility-policy-3.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Ejemplo***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Escenario 4:** Eliminar directivas de movilidad elegidas

   ![Eliminar directiva de movilidad](./media/mobility-policy-4.png)

***Cmdlet***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***Ejemplo***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Escenario 5:** Actualizar una directiva de movilidad

   ![Actualizar directiva de movilidad](./media/mobility-policy-5.png)

***Cmdlet***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***Ejemplo***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>Configuración de notificaciones de inserción

El servicio de notificaciones de inserción (Apple Push Notification Service y Microsoft Push Notification Service) proporciona una forma de enviar notificaciones sobre eventos como nuevos mensajes instantáneos o nuevo correo de voz a dispositivos móviles como iPhones y Windows Phones. Estas notificaciones están configuradas para enviarse incluso si la aplicación Skype Empresarial en esos dispositivos está actualmente suspendida o en ejecución en segundo plano.

Veamos las distintas tareas que un usuario puede hacer en CONFIGURACIÓN DE NOTIFICACIONES **PUSH** y los cmdlets Skype Empresarial a las que se asignan las tareas.

---

> **Escenario 1:** Enumerar todas las directivas de movilidad

   ![Configuración de notificación de inserción de lista](./media/push-notification-config-1.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Ejemplo***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **Escenario 2:** Crear una nueva configuración de notificación de inserción

   ![Crear configuración de notificación de inserción](./media/push-notification-config-2.png)

***Cmdlet***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***Ejemplo***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **Escenario 3:** obtener detalles de una configuración de notificación de inserción elegida

   ![Obtener configuración de notificación de inserción](./media/push-notification-config-3.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Ejemplo***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Escenario 4:** Eliminar las configuraciones de notificación de inserción elegidas

   ![Eliminar configuración de notificación de inserción](./media/push-notification-config-4.png)

***Cmdlet***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***Ejemplo***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Escenario 5:** Actualizar una configuración de notificación de inserción

   ![Actualizar configuración de notificación de inserción](./media/push-notification-config-5.png)

***Cmdlet***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***Ejemplo***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
