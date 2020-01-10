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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga los pasos que se indican en este tema para modificar la configuración de una implementación existente de Skype empresarial Cloud Connector Edition 1.4.1 o posterior.
ms.openlocfilehash: ead952c0ba567a8e5d81c52144de597e50d24014
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002290"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modify the configuration of an existing Cloud Connector deployment
 
Siga los pasos que se indican en este tema para modificar la configuración de una implementación existente de Skype empresarial Cloud Connector Edition 1.4.1 o posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar la configuración de un único sitio
<a name="BKMK_SIngleSite"> </a>

Si solo hay una aplicación en el sitio, cuando desee cambiar la configuración después de haber implementado la aplicación, puede modificar el archivo CloudConnector.ini e iniciar la implementación de nuevo.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el servidor host:  
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Actualice el archivo CloudConnector.ini en el directorio de la aplicación.
    
4. Ejecute el siguiente cmdlet para actualizar la configuración: (este paso solo se aplica a la versión 2; para versiones anteriores, vaya al paso siguiente).
    
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

Si hay más de un dispositivo en el sitio, tendrá que seguir estos pasos, modificar el archivo CloudConnector.ini y volver a implementar los dispositivos uno a uno.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el dispositivo actual: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Actualice el archivo CloudConnector.ini en el directorio de la aplicación.
    
4. Ejecute el siguiente cmdlet para actualizar la configuración: (este paso solo se aplica a la versión 2; para versiones anteriores, vaya al paso siguiente).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Ejecute el siguiente cmdlet para volver a registrar el dispositivo:
    
   ```powershell
   Register-CcAppliance
   ```

6. Ejecute el siguiente cmdlet en todos los demás dispositivos del sitio para recoger la última configuración:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Ejecute el siguiente cmdlet para volver a implementar el conector de nube en el dispositivo actual:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificar la configuración de varios sitios
<a name="BKMK_MultipleSites"> </a>

Para modificar la configuración de varios sitios en una implementación, siga los pasos correspondientes a un solo sitio y actualice un sitio a la vez.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modificar la configuración de su inquilino de Office 365 para habilitar las actualizaciones automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar las actualizaciones automáticas del sistema operativo y las actualizaciones automáticas de bits, debe usar la cuenta de administrador de inquilinos de Skype empresarial para la administración en línea y usar PowerShell remoto de inquilino de la siguiente manera.
  
Si deshabilitó las actualizaciones automáticas del sistema operativo o las actualizaciones automáticas de bits, es posible que el host y la máquina virtual pierdan las actualizaciones importantes de Windows y que el conector de nube no se actualice automáticamente a la nueva versión. Las actualizaciones automáticas son altamente recomendables.
  
1. La propiedad EnableAutoUpdate del sitio debe establecerse en true (el valor predeterminado). Ejecute el siguiente cmdlet para asegurarse de que EnableAutoUpdate esté establecida en true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Cree un intervalo de actualización automática para el inquilino.
    
    El intervalo de tiempo puede ser diario, semanal o mensual. En todos los casos se necesita una hora de inicio y una duración.
    
   - Para los intervalos diarios, solo se necesita la hora de inicio y la duración.  
    
   - Para los intervalos semanales, se necesitan los días de la semana, que pueden ser un solo día o varios días.
    
   - Los intervalos mensuales pueden ser de dos tipos. El primer tipo consiste en especificar un día del mes, que puede ser un solo día. El segunda tipo consiste en especificar las semanas del mes, junto con los días de la semana. Ambos elementos pueden ser únicos o múltiples.
    
   - Cada inquilino puede tener 20 intervalos definidos. El intervalo predeterminado se creará para un nuevo inquilino como intervalo predeterminado para actualizaciones del sistema operativo y de Bits. Ejecute los siguientes cmdlets para establecer un intervalo diario, semanal o mensual:
    
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

   - Asigne ventanas de tiempo de actualización al sitio. 
    
     Los intervalos de actualización de Bits y del sistema operativo se configuran por separado. A ambos se les puede asignar un solo intervalo o varios. Además, cada intervalo se puede asignar a distintos sitios y distintos fines (actualización de Bits o del sistema operativo). Ejecute el siguiente cmdlet para establecer la ventana de tiempo para el sitio: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Actualizar las credenciales de administrador de inquilinos dedicado 
<a name="BKMK_MultipleSites"> </a>

Los cambios administrativos en el inquilino de Office 365 para Cloud Connector se realizan desde una cuenta con los permisos necesarios. En las versiones del conector en la nube antes 2,0, esa cuenta es una cuenta de administrador de inquilinos global dedicada. En la versión 2,0 y posteriores de conector de la nube, esa cuenta puede ser una cuenta de Office 365 con derechos de administrador de Skype empresarial.
  
Si las credenciales de su cuenta de administrador cambian en Office 365, también tendrá que actualizar las credenciales locales almacenadas en caché en el conector de nube ejecutando el siguiente comando de administrador de PowerShell en cada dispositivo conector de nube que haya implementado:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Actualizar la contraseña del servidor host 
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta sección es aplicable a la versión 2,0 y posteriores del conector de la nube. 
  
Todas las credenciales del conector de nube se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Cuando se modifica la contraseña en el servidor host, tendrá que actualizar las credenciales que hay almacenadas localmente.
  
Para actualizar las credenciales almacenadas localmente en el equipo del conector de nube, use los cmdlets [Get-CcCredential](get-cccredential.md) y [set-CcCredential](set-cccredential.md) y siga estos pasos:
  
1. Ejecute los siguientes comandos para recuperar las contraseñas que necesitará más adelante:   
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Cambie la contraseña de su cuenta en el servidor host.
    
3. Reinicie el servidor host.
    
4. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas que siguen a la descripción. Asegúrese de introducir la misma contraseña que usó antes para la implementación de Cloud Connector.
    
De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si las contraseñas de DomainAdmin, VMAdmin y CceService que se devolvieron en el paso 1 son diferentes, debe realizar los siguientes pasos:
  
1. Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:
    
1. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
2. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de DomainAdmin en el paso 1.
    
2. Ejecute Set-CcCredential -AccountType VmAdmin como sigue:
    
1. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
2. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de VmAdmin en el paso 1.  
    
## <a name="update-the-password-for-the-cceservice-account"></a>Actualizar la contraseña de la cuenta de CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta sección es aplicable a Cloud Connector versión 2.0.1 y posteriores. 
  
El servicio de conector de nube ejecuta el servicio de administración de conector de nube. La cuenta CceService se crea durante la implementación de Cloud Connector Edition y se almacena en los siguientes archivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "y"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".
  
Para asegurarse de que todos los dispositivos tengan acceso al recurso compartido de directorio de sitios, la contraseña de la cuenta de CceService debe ser la misma en todos los dispositivos instalados dentro del sitio. Tenga en cuenta lo siguiente:
  
- De forma predeterminada, la cuenta CceService está configurada como "la contraseña nunca expira". Cuando actualice la contraseña, Microsoft recomienda mantener esta configuración.
    
- Debe actualizar la contraseña durante períodos de uso no máximo y fuera de las ventanas de tiempo de actualización automática para bits o actualizaciones de Windows. Cuando actualiza la contraseña, es necesario que el dispositivo se vacíe y se reinicie, lo cual tardará algún tiempo. Reiniciar el dispositivo interrumpirá las operaciones de actualización automática. 
    
- Cuando cambie la contraseña de la cuenta CceService, tendrá que especificar todas las credenciales y actualizarlas en el archivo almacenado de forma local. 
    
Para cada dispositivo que pertenezca al mismo sitio de la RTC, tendrá que especificar lo siguiente: 
  
1. Ejecute los siguientes comandos para recuperar los nombres y las contraseñas de cuenta que usará más adelante:
    
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
    
5. Ejecute el cmdlet restore-CcCredentials para volver a escribir las contraseñas que siguen a la descripción. 
    
    Asegúrese de escribir la misma contraseña que escribió antes para la implementación de Cloud Connector, excepto para la cuenta CceService. Para la cuenta CceService, escriba la nueva contraseña. Asegúrese de que la nueva contraseña de la cuenta de CceService es la misma para todos los dispositivos del sitio de la RTC.
    
6. De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si las contraseñas de DomainAdmin, VMAdmin y CceService que se devolvieron en el paso 1 son diferentes, debe realizar los siguientes pasos:
    
7. Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:
    
   - Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
   - Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de DomainAdmin en el paso 1.
    
8. Ejecute Set-CcCredential -AccountType VmAdmin como sigue:
    
   - Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
   - Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de VmAdmin en el paso 1.  
    
9. Ejecute el cmdlet Exit-CcUpdate para sacar el dispositivo del modo de mantenimiento manual.
    
10. Después de completar estos pasos en todos los dispositivos del mismo sitio de RTC, elimine los siguientes archivos en el directorio raíz del sitio:
    
    - CcLockFile
    
    - FQDN\<del grupo de SIP externo de Site_ perimetral\>
    
    - FQDN\<del grupo de SIP externo de Tenant_ perimetral\>
    
    - FQDN\<del grupo de SIP externo de TenantConfigLock_ perimetral\>
    
## <a name="add-a-new-sip-domain"></a>Agregar un nuevo dominio SIP 
<a name="BKMK_UpdatePassword"> </a>

Para agregar un nuevo dominio SIP (o varios dominios SIP) a la implementación del conector en la nube existente, haga lo siguiente:
  
1. Asegúrese de haber completado los pasos para actualizar el dominio en Office 365 y de tener la capacidad para agregar registros DNS. Para obtener más información sobre cómo configurar su dominio en Office 365, vea [Agregar un dominio a office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Actualice el archivo de configuración del conector de nube con el nuevo dominio o dominios SIP.
    
3. Solicite un nuevo certificado externo de borde con nombres SAN adicionales para SIP. dominio para cada dominio SIP definido en la configuración del conector de la nube. 
    
4. Establezca la ruta de acceso del nuevo certificado perimetral externo como sigue:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Siga las instrucciones de [Modificar la configuración de un único sitio](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [Modificar la configuración de varios sitios](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificar el dominio SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si necesita cambiar el dominio SIP principal en la implementación de Cloud Connector, haga lo siguiente:
  
1. Asegúrese de haber completado los pasos para actualizar el dominio en Office 365 y de tener la capacidad para agregar registros DNS. Para obtener más información sobre cómo configurar su dominio en Office 365, vea [Agregar un dominio a office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Actualice el archivo de configuración del conector de nube con el nuevo dominio SIP.
    
3. Solicite un nuevo certificado externo de borde con nombres SAN adicionales para SIP. dominio para cada dominio SIP definido en la configuración del conector de la nube. 
    
4. Establezca la ruta de acceso del nuevo certificado perimetral externo como sigue:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Elimine el registro de inquilinos de cada dispositivo de un sitio ejecutando el siguiente cmdlet en el administrador PowerShell en el conector en la nube:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Quite el registro de sitios para cada sitio mediante la ejecución del siguiente cmdlet en el PowerShell de Skype Empresarial Online :
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Desinstale cada dispositivo ejecutando el siguiente cmdlet en el administrador de PowerShell en el conector de nube:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Para registrar cada equipo, ejecute el siguiente cmdlet en el administrador de PowerShell del conector de nube:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Instale cada dispositivo, uno por uno, ejecutando el siguiente cmdlet en el administrador de PowerShell en el conector de nube:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Reemplazar el certificado de borde externo por un certificado nuevo
<a name="BKMK_UpdatePassword"> </a>

Si necesita reemplazar el certificado de borde externo en los dispositivos de su conexión en la nube, tendrá que obtener un nuevo certificado perimetral, preparar el archivo PFX que contiene la clave privada y la cadena de certificados completa y, a continuación, hacer lo siguiente en cada dispositivo:
  
1. Coloque el dispositivo en el modo de mantenimiento con el cmdlet Enter-CcUpdate.
    
2. Ejecute el siguiente comando: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Si la contraseña del nuevo certificado es la misma que la antigua, la importación se realizará correctamente. Si la contraseña es diferente, recibirá un error que le informará de que la contraseña es incorrecta y tendrá que restablecer la contraseña ejecutando el cmdlet Register-CcAppliance con el parámetro-local y repite el paso 2. 
    
4. Salga del dispositivo del modo de mantenimiento con el cmdlet Exit-CcUpdate.
    

