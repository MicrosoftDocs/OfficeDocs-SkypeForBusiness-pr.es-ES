---
title: Modificación de la configuración de una implementación existente de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga los pasos de este tema para modificar la configuración de una implementación existente de Skype empresarial Cloud Connector Edition 1.4.1 o posterior.
ms.openlocfilehash: 4c2c0b8ad5340cd4ae4275f1ac009bf3d9d3ec0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018011"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificación de la configuración de una implementación existente de Cloud Connector
 
Siga los pasos de este tema para modificar la configuración de una implementación existente de Skype empresarial Cloud Connector Edition 1.4.1 o posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar la configuración de un sitio único
<a name="BKMK_SIngleSite"> </a>

Si solo hay un dispositivo en el sitio, cuando desee cambiar las opciones de configuración una vez implementado el dispositivo, puede modificar el archivo CloudConnector. ini e iniciar la implementación de nuevo.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el servidor host: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Actualice el archivo CloudConnector. ini en el directorio de dispositivos.
    
4. Ejecute el siguiente cmdlet para actualizar la configuración: (este paso solo es aplicable a la versión 2; para versiones anteriores, vaya al paso siguiente).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Ejecute el siguiente cmdlet para volver a registrar el dispositivo:
    
   ```powershell
   Register-CcAppliance
   ```

6. Ejecute el siguiente cmdlet para instalar Skype empresarial Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Si hay más de un dispositivo en el sitio, tendrá que seguir estos pasos, modificar el archivo CloudConnector. ini y volver a implementar los dispositivos uno a uno.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el dispositivo actual: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Actualice el archivo CloudConnector. ini en el directorio de dispositivos.
    
4. Ejecute el siguiente cmdlet para actualizar la configuración: (este paso solo es aplicable a la versión 2; para versiones anteriores, vaya al paso siguiente).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Ejecute el siguiente cmdlet para volver a registrar el dispositivo:
    
   ```powershell
   Register-CcAppliance
   ```

6. Ejecute el siguiente cmdlet en el resto de los dispositivos del sitio para seleccionar la última configuración:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Ejecute el siguiente cmdlet para volver a implementar Cloud Connector en el dispositivo actual:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificación de la configuración de varios sitios
<a name="BKMK_MultipleSites"> </a>

Para modificar la configuración de varios sitios en una implementación, siga los pasos de un sitio único, actualizando un sitio cada vez.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modificar la configuración de su inquilino de Office 365 para habilitar las actualizaciones automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar las actualizaciones automáticas del sistema operativo y las actualizaciones automáticas de bits, debe usar la cuenta de administrador de inquilinos de Skype empresarial para la administración en línea y usar PowerShell remoto del inquilino de la siguiente manera.
  
Si deshabilitó las actualizaciones automáticas del sistema operativo o actualizaciones automáticas de bits, el host y la máquina virtual podrían perderse actualizaciones de Windows importantes y Cloud Connector no se actualizará automáticamente a la nueva versión. Se recomienda encarecidamente habilitar las actualizaciones automáticas.
  
1. La propiedad EnableAutoUpdate del sitio debe establecerse en true (el valor predeterminado). Ejecute el siguiente cmdlet para asegurarse de que EnableAutoUpdate está establecido en true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Crear ventana de tiempo de actualización automática para el inquilino.
    
    La ventana de tiempo puede ser diaria, semanal o mensual. Siempre que Windows necesite una hora de inicio y una duración.
    
   - Para un período de tiempo diario, solo se necesita la hora de inicio y la duración. 
    
   - Para un intervalo de tiempo semanal, se necesitan días de la semana, que pueden ser un solo día o varios días.
    
   - Para un intervalo mensual, puede haber dos tipos. El primer tipo es especificar el día del mes, que puede ser un solo día. El segundo tipo es especificar las semanas del mes, junto con los días de la semana, que ambos pueden ser un único elemento o varios elementos.
    
   - Cada inquilino puede tener 20 ventanas de tiempo definidas. Se creará la ventana de tiempo predeterminada para un nuevo inquilino como ventana de tiempo predeterminada para la actualización del sistema operativo y la actualización de bits. Ejecute los cmdlets siguientes para establecer el intervalo de tiempo diario, semanal o mensual:
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Asignar ventanas de tiempo de actualización al sitio. 
    
     Las ventanas hora de actualización de bits y hora de actualización del sistema operativo se configuran por separado. Ambos se pueden asignar a una o varias ventanas de tiempo. Cada ventana de tiempo se puede asignar a distintos sitios y a diferentes propósitos (actualización de bits y actualización del sistema operativo). Ejecute el siguiente cmdlet para establecer el período de tiempo para el sitio: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Actualizar las credenciales de administrador del espacio dedicado
<a name="BKMK_MultipleSites"> </a>

Los cambios administrativos en el inquilino de Office 365 para Cloud Connector se realizan desde una cuenta con los permisos necesarios. En la versión de Cloud Connector anterior a 2,0, esa cuenta es una cuenta de administrador de inquilino global dedicada. En Cloud Connector versiones 2,0 y posteriores, esa cuenta puede ser una cuenta de Office 365 con derechos de administrador de Skype empresarial.
  
Si las credenciales de la cuenta de administrador cambian en Office 365, también deberá actualizar las credenciales almacenadas en caché local en Cloud Connector mediante la ejecución del siguiente comando de PowerShell de administrador en cada dispositivo de Cloud Connector que haya implementado:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Actualizar la contraseña del servidor host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta sección se aplica a Cloud Connector versión 2,0 y versiones posteriores. 
  
Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Cuando cambie la contraseña en el servidor host, tendrá que actualizar las credenciales almacenadas localmente.
  
Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, use los cmdlets [Get-CcCredential](get-cccredential.md) y [set-CcCredential](set-cccredential.md) y siga estos pasos:
  
1. Ejecute los siguientes comandos para recuperar las contraseñas que necesitará más adelante: 
    
   - Get-CcCredential-AccountType-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. Cambie la contraseña de su cuenta en el servidor host.
    
3. Reinicie el servidor host.
    
4. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Inicie una consola de PowerShell como administrador y, después, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas después de la descripción. Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector.
    
De forma predeterminada, VmAdmin y valor detor usan la misma contraseña que CceService. Si las contraseñas del usuario, la VMAdmin y la CceService devueltas en el paso 1 son diferentes, debe realizar los siguientes pasos:
  
1. Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:
    
1. Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.
    
2. Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña de la contraseña del ID de usuario devuelta en el paso 1.
    
2. Ejecute Set-CcCredential-AccountType VmAdmin de la siguiente manera:
    
1. Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.
    
2. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin devuelta en el paso 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Actualizar la contraseña de la cuenta CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta sección se aplica a Cloud Connector versión 2.0.1 y versiones posteriores. 
  
El servicio de Cloud Connector ejecuta el servicio de administración de Cloud Connector. La cuenta CceService se crea durante la implementación de Cloud Connector Edition y se almacena en los siguientes archivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "y"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".
  
Para asegurarse de que todos los dispositivos puedan acceder al directorio compartido de sitios, la contraseña de la cuenta CceService debe ser la misma en todos los dispositivos que se hayan implementado en el sitio. Tenga en cuenta lo siguiente:
  
- De forma predeterminada, la cuenta CceService está configurada como "la contraseña nunca expira". Al actualizar la contraseña, Microsoft recomienda conservar esta configuración.
    
- Debe actualizar la contraseña durante los períodos de uso no máximos y fuera de las ventanas de tiempo de actualización automáticas para bits o actualizaciones de Windows. Al actualizar la contraseña, el dispositivo debe purgarse y reiniciarse, lo que lleva algún tiempo. Si reinicia el dispositivo, se interrumpirán las operaciones de actualización automática. 
    
- Al cambiar la contraseña de la cuenta CceService, tendrá que especificar todas las credenciales y actualizarlas en el archivo almacenado localmente. 
    
Para cada dispositivo que pertenezca al mismo sitio de RTC, tendrá que especificar lo siguiente: 
  
1. Ejecute los siguientes comandos para recuperar los nombres de cuenta y las contraseñas que usará más adelante:
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. Ejecute el cmdlet Enter-CcUpdate para purgar el dispositivo y moverlo al modo de mantenimiento manual.
    
3. Actualice la contraseña de la cuenta CceService en el servidor host.
    
4. Reinicie el servidor host.
    
5. Ejecute el cmdlet restore-CcCredentials para volver a escribir las contraseñas a continuación de la descripción. 
    
    Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector, excepto para la cuenta CceService. Para la cuenta CceService, escriba la nueva contraseña. Asegúrese de que la nueva contraseña de la cuenta CceService es la misma para todos los dispositivos del sitio RTC.
    
6. De forma predeterminada, VmAdmin y valor detor usan la misma contraseña que CceService. Si las contraseñas del usuario, la VMAdmin y la CceService devueltas en el paso 1 son diferentes, debe realizar los siguientes pasos:
    
7. Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:
    
   - Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.
    
   - Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña de la contraseña del ID de usuario devuelta en el paso 1.
    
8. Ejecute Set-CcCredential-AccountType VmAdmin de la siguiente manera:
    
   - Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.
    
   - Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin devuelta en el paso 1. 
    
9. Ejecute el cmdlet Exit-CcUpdate para desplazar el dispositivo fuera del modo de mantenimiento manual.
    
10. Después de completar estos pasos en todos los dispositivos del mismo sitio RTC, elimine los siguientes archivos del directorio raíz del sitio:
    
    - CcLockFile
    
    - FQDN\<del grupo de SIP externo de Site_ perimetral\>
    
    - FQDN\<del grupo de SIP externo de Tenant_ perimetral\>
    
    - FQDN\<del grupo de SIP externo de TenantConfigLock_ perimetral\>
    
## <a name="add-a-new-sip-domain"></a>Adición de un nuevo dominio SIP
<a name="BKMK_UpdatePassword"> </a>

Para agregar un nuevo dominio SIP (o varios dominios SIP) a la implementación existente de Cloud Connector, haga lo siguiente:
  
1. Asegúrese de que ha completado los pasos para actualizar el dominio en Office 365 y de que tiene la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar su dominio en Office 365, consulte [Agregar un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Actualice el archivo de configuración de Cloud Connector con el nuevo dominio o dominios SIP.
    
3. Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para SIP. domain para cada dominio SIP definido en la configuración de Cloud Connector. 
    
4. Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Siga las instrucciones para [modificar la configuración de un único sitio](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [modificar la configuración de varios sitios](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificar el dominio SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si necesita cambiar el dominio SIP principal en su implementación de Cloud Connector, haga lo siguiente:
  
1. Asegúrese de que ha completado los pasos para actualizar el dominio en Office 365 y de que tiene la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar su dominio en Office 365, consulte [Agregar un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Actualice el archivo de configuración de Cloud Connector con el nuevo dominio SIP.
    
3. Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para SIP. domain para cada dominio SIP definido en la configuración de Cloud Connector. 
    
4. Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Quite el registro de inquilino de cada dispositivo en un sitio mediante la ejecución del siguiente cmdlet en el PowerShell del administrador en Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Quite el registro de sitios para cada sitio mediante la ejecución del siguiente cmdlet en PowerShell de Skype empresarial online:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Para desinstalar cada dispositivo, ejecute el siguiente cmdlet en el administrador de PowerShell de Cloud Connector:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registre cada dispositivo mediante la ejecución del siguiente cmdlet en el PowerShell del administrador en Cloud Connector:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Instale cada dispositivo, uno a uno, mediante la ejecución del siguiente cmdlet en el PowerShell del administrador en Cloud Connector:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Reemplazar el certificado perimetral externo por un certificado nuevo
<a name="BKMK_UpdatePassword"> </a>

Cuando necesite reemplazar el certificado perimetral externo en los dispositivos de Cloud Connector, tendrá que obtener un nuevo certificado perimetral, preparar el archivo PFX que contiene la clave privada y la cadena de certificados completa y, a continuación, hacer lo siguiente en cada dispositivo:
  
1. Coloque el dispositivo en modo de mantenimiento mediante el cmdlet Enter-CcUpdate.
    
2. Ejecute el siguiente comando: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Si la contraseña del nuevo certificado es la misma que la antigua, la importación se realizará correctamente. Si la contraseña es diferente, recibirá un error que le informará de que la contraseña es incorrecta y tendrá que restablecer la contraseña si ejecuta el cmdlet Register-CcAppliance con el parámetro-local y, a continuación, se repite el paso 2. 
    
4. Saque el dispositivo del modo de mantenimiento mediante el cmdlet Exit-CcUpdate.
    

