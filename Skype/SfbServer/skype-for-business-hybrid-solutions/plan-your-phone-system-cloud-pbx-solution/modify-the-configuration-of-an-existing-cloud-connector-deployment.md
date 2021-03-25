---
title: Modificar la configuración de una implementación de Cloud Connector existente
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
description: Siga los pasos descritos en este tema para modificar la configuración de una implementación existente de Skype Empresarial Cloud Connector Edition 1.4.1 o posterior.
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109176"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificar la configuración de una implementación de Cloud Connector existente

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)

Siga los pasos descritos en este tema para modificar la configuración de una implementación existente de Skype Empresarial Cloud Connector Edition 1.4.1 o posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar la configuración de un solo sitio
<a name="BKMK_SIngleSite"> </a>

Si solo hay un dispositivo en el sitio, cuando desee cambiar las opciones de configuración después de implementar el dispositivo, puede modificar el archivo CloudConnector.ini e iniciar la implementación de nuevo.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el servidor host: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Actualice el CloudConnector.ini en el Directorio de dispositivos.
    
4. Ejecute el siguiente cmdlet para actualizar la configuración: (Este paso solo es aplicable para la versión 2; para las versiones anteriores, vaya al paso siguiente).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Ejecute el siguiente cmdlet para volver a registrar el dispositivo:
    
   ```powershell
   Register-CcAppliance
   ```

6. Ejecute el siguiente cmdlet para instalar Skype Empresarial Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Si hay más de un dispositivo en el sitio, deberá seguir estos pasos, modificar el archivo CloudConnector.ini y volver a implementar los dispositivos uno por uno.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el dispositivo actual: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Actualice el CloudConnector.ini en el Directorio de dispositivos.
    
4. Ejecute el siguiente cmdlet para actualizar la configuración: (Este paso solo es aplicable para la versión 2; para las versiones anteriores, vaya al paso siguiente).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Ejecute el siguiente cmdlet para volver a registrar el dispositivo:
    
   ```powershell
   Register-CcAppliance
   ```

6. Ejecute el siguiente cmdlet en todos los demás dispositivos del sitio para recuperar la configuración más reciente:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Ejecute el siguiente cmdlet para volver a implementar Cloud Connector en el dispositivo actual:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificar la configuración de varios sitios
<a name="BKMK_MultipleSites"> </a>

Para modificar la configuración de varios sitios en una implementación, siga los pasos de un solo sitio, actualizando un sitio a la vez.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Modificar la configuración de su organización de Microsoft 365 u Office 365 para habilitar actualizaciones automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar las actualizaciones automáticas del sistema operativo y las actualizaciones automáticas de Bits, debe usar la cuenta de administrador de inquilinos de Skype Empresarial para la administración en línea y usar PowerShell remoto de inquilino de la siguiente manera.
  
Si deshabilitaste las actualizaciones automáticas del sistema operativo o las actualizaciones automáticas de Bits, es posible que el host y la máquina virtual pierdan actualizaciones importantes de Windows y Cloud Connector no se actualizará a la nueva versión automáticamente. Se recomienda habilitar las actualizaciones automáticas.
  
1. La propiedad EnableAutoUpdate del sitio debe establecerse en true (el valor predeterminado). Ejecute el siguiente cmdlet para asegurarse de que EnableAutoUpdate está establecido en true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Crear ventana de tiempo de actualización automática para el inquilino.
    
    La ventana de tiempo puede ser diaria, semanal y mensual. Todas las ventanas de tiempo necesitan una hora de inicio y una duración.
    
   - Para una ventana de hora diaria, solo se necesitan la hora de inicio y la duración. 
    
   - Para una ventana de tiempo semanal, se necesitan días de la semana, que pueden ser un solo día o varios días.
    
   - Para una ventana de tiempo mensual, puede haber dos tipos. El primer tipo es especificar el día del mes, que puede ser un solo día. El segundo tipo es especificar las semanas del mes, junto con los días de la semana, que pueden ser un solo elemento o varios elementos.
    
   - Cada espacio empresarial puede tener 20 ventanas definidas. La ventana de hora predeterminada se creará para un nuevo inquilino como la ventana de tiempo predeterminada para la actualización del sistema operativo y la actualización de bits. Ejecute los cmdlets siguientes para establecer la ventana de hora diaria, semanal o mensual:
    
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
    
     Las ventanas Bits update time y OS update time se configuran por separado. A ambos se les puede asignar una o varias ventanas de tiempo. Cada ventana de tiempo se puede asignar a diferentes sitios y fines diferentes (actualización de bits y actualización del sistema operativo). Ejecute el siguiente cmdlet para establecer la ventana de tiempo del sitio: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Actualizar las credenciales de administrador de inquilinos dedicados
<a name="BKMK_MultipleSites"> </a>

Los cambios administrativos en la organización de Microsoft 365 u Office 365 para Cloud Connector se realizan desde una cuenta con los permisos necesarios. En versiones de Cloud Connector anteriores a la 2.0, esa cuenta es una cuenta de administrador de inquilinos global dedicada. En Cloud Connector versiones 2.0 y posteriores, esa cuenta puede ser una cuenta de Microsoft 365 u Office 365 con derechos de administrador de Skype Empresarial.
  
Si las credenciales de la cuenta de administrador cambian en Microsoft 365 u Office 365, también debe actualizar las credenciales almacenadas en caché localmente en Cloud Connector ejecutando el siguiente comando de PowerShell de administrador en cada aplicación de Cloud Connector que haya implementado:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Actualizar la contraseña del servidor host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta sección es aplicable a Cloud Connector versión 2.0 y versiones posteriores. 
  
Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml". Cuando cambie la contraseña en el servidor host, deberá actualizar las credenciales almacenadas localmente.
  
Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, use los cmdlets [Get-CcCredential](get-cccredential.md) y [Set-CcCredential](set-cccredential.md) y siga estos pasos:
  
1. Ejecute los siguientes comandos para recuperar las contraseñas que necesitará más adelante: 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Cambie la contraseña de su cuenta en el servidor host.
    
3. Reinicie el servidor host.
    
4. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".
    
5. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción. Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector.
    
De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si las contraseñas DomainAdmin, VMAdmin y CceService devueltas en el paso 1 son diferentes, debe realizar los pasos siguientes:
  
1. Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:
    
1. Cuando se le pida la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
2. Cuando se le pida la nueva credencial de cuenta, escriba la contraseña de la contraseña domainadmin devuelta en el paso 1.
    
2. Ejecute Set-CcCredential -AccountType VmAdmin de la siguiente manera:
    
1. Cuando se le pida la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
2. Cuando se le pida la nueva credencial de cuenta, escriba la contraseña de la contraseña vmadmin devuelta en el paso 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Actualizar la contraseña de la cuenta CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta sección es aplicable a Cloud Connector versión 2.0.1 y versiones posteriores. 
  
El servicio Cloud Connector ejecuta el servicio de administración de Cloud Connector. La cuenta CceService se crea durante la implementación de Cloud Connector Edition y se almacena en los siguientes archivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" y "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Para asegurarse de que todos los dispositivos pueden tener acceso al recurso compartido de directorios del sitio, la contraseña de la cuenta CceService debe ser la misma en todos los dispositivos implementados dentro del sitio. Tenga en cuenta lo siguiente:
  
- De forma predeterminada, la cuenta CceService está configurada como "La contraseña nunca expira". Al actualizar la contraseña, Microsoft recomienda mantener esta configuración.
    
- Debes actualizar la contraseña durante períodos de uso no pico y fuera de las ventanas de tiempo de actualización automática para bits o actualizaciones de Windows. Al actualizar la contraseña, el dispositivo debe vaciarse y reiniciarse, lo que lleva algún tiempo. Reiniciar el dispositivo interrumpirá las operaciones de actualización automática. 
    
- Al cambiar la contraseña de la cuenta CceService, deberá especificar todas las credenciales y actualizarlas en el archivo almacenado localmente. 
    
Para cada dispositivo que pertenezca al mismo sitio RTC, deberá especificar lo siguiente: 
  
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

2. Ejecute el cmdlet Enter-CcUpdate para vaciar el dispositivo y moverlo al modo de mantenimiento manual.
    
3. Actualice la contraseña de la cuenta CceService en el servidor host.
    
4. Reinicie el servidor host.
    
5. Ejecute el cmdlet Restore-CcCredentials para volver a escribir las contraseñas después de la descripción. 
    
    Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector excepto para la cuenta CceService. Para la cuenta CceService, escriba la nueva contraseña. Asegúrese de que la nueva contraseña de la cuenta CceService es la misma para todos los dispositivos del sitio RTC.
    
6. De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si las contraseñas DomainAdmin, VMAdmin y CceService devueltas en el paso 1 son diferentes, debe realizar los pasos siguientes:
    
7. Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:
    
   - Cuando se le pida la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
   - Cuando se le pida la nueva credencial de cuenta, escriba la contraseña de la contraseña domainadmin devuelta en el paso 1.
    
8. Ejecute Set-CcCredential -AccountType VmAdmin de la siguiente manera:
    
   - Cuando se le pida la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
   - Cuando se le pida la nueva credencial de cuenta, escriba la contraseña de la contraseña vmadmin devuelta en el paso 1. 
    
9. Ejecute el cmdlet Exit-CcUpdate para sacar el dispositivo del modo de mantenimiento manual.
    
10. Después de completar estos pasos en todos los dispositivos del mismo sitio RTC, elimine los siguientes archivos en el directorio raíz del sitio:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Agregar un nuevo dominio SIP
<a name="BKMK_UpdatePassword"> </a>

Para agregar un nuevo dominio SIP (o varios dominios SIP) a la implementación existente de Cloud Connector, haga lo siguiente:
  
1. Asegúrese de que ha completado los pasos para actualizar el dominio en Microsoft 365 u Office 365 y tener la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar el dominio en Microsoft 365 u Office 365, vea Agregar un dominio [a Microsoft 365 u Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Actualice el archivo de configuración de Cloud Connector con el nuevo dominio SIP o dominios.
    
3. Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para sip.domain para cada dominio SIP definido en la configuración de Cloud Connector. 
    
4. Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Siga las instrucciones para [Modificar la configuración de un solo sitio](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o Modificar la configuración de varios [sitios](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificar el dominio SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si necesita cambiar el dominio SIP principal en la implementación de Cloud Connector, haga lo siguiente:
  
1. Asegúrese de que ha completado los pasos para actualizar el dominio en Microsoft 365 u Office 365 y tener la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar el dominio en Microsoft 365 u Office 365, vea Agregar un dominio [a Microsoft 365 u Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Actualice el archivo de configuración de Cloud Connector con el nuevo dominio SIP.
    
3. Solicite un nuevo certificado externo perimetral con nombres SAN adicionales para sip.domain para cada dominio SIP definido en la configuración de Cloud Connector. 
    
4. Establezca la ruta de acceso para el nuevo certificado externo perimetral de la siguiente manera:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Para quitar el registro de inquilino para cada dispositivo de un sitio, ejecute el siguiente cmdlet en el administrador de PowerShell en Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Para quitar el registro del sitio para cada sitio, ejecute el siguiente cmdlet en PowerShell de Skype Empresarial Online:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Desinstale cada dispositivo ejecutando el siguiente cmdlet en el administrador de PowerShell en Cloud Connector:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registre cada dispositivo ejecutando el siguiente cmdlet en el administrador de PowerShell en Cloud Connector:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Instale cada dispositivo, uno a uno, ejecutando el siguiente cmdlet en el administrador de PowerShell en Cloud Connector:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Reemplazar el certificado perimetral externo por un nuevo certificado
<a name="BKMK_UpdatePassword"> </a>

Cuando necesite reemplazar el certificado perimetral externo en los dispositivos de Cloud Connector, deberá obtener un nuevo certificado perimetral, preparar el archivo PFX que contiene la clave privada y la cadena de certificados completa y, a continuación, hacer lo siguiente en cada dispositivo:
  
1. Ponga el dispositivo en modo de mantenimiento mediante el cmdlet Enter-CcUpdate.
    
2. Ejecute el siguiente comando: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Si la contraseña del nuevo certificado es la misma que la anterior, la importación se realizará correctamente. Si la contraseña es diferente, recibirá un error de que la contraseña es incorrecta y tendrá que restablecer la contraseña ejecutando el cmdlet Register-CcAppliance con el parámetro -Local y, a continuación, repitiendo el paso 2. 
    
4. Saque el dispositivo del modo de mantenimiento mediante el cmdlet Exit -CcUpdate.
