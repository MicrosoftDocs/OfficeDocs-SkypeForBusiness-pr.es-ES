---
title: Modificar la configuración de una implementación de Cloud Connector existente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga los pasos descritos en este tema para modificar la configuración de un Skype existente de conector de nube de Business Edition 1.4.1 o implementación posterior.
ms.openlocfilehash: 86efbf21efae3dc95508528850a984912e4930a1
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificar la configuración de una implementación de Cloud Connector existente
 
Siga los pasos descritos en este tema para modificar la configuración de un Skype existente de conector de nube de Business Edition 1.4.1 o implementación posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar la configuración de un único sitio
<a name="BKMK_SIngleSite"> </a>

Si solo hay una aplicación en el sitio, cuando desee cambiar la configuración después de haber implementado la aplicación, puede modificar el archivo CloudConnector.ini e iniciar la implementación de nuevo.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el servidor host:  
    
  ```
  Uninstall-CcAppliance
  ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
  ```
  Unregister-CcAppliance
  ```

3. Actualice el archivo CloudConnector.ini en el directorio de la aplicación.
    
4. Ejecute el cmdlet siguiente para actualizar la configuración: (este paso sólo es aplicable para la versión 2; para las versiones anteriores, vaya al paso siguiente).
    
  ```
   Import-CcConfiguration 
  ```

5. Ejecute el siguiente cmdlet para volver a registrar el dispositivo:
    
  ```
  Register-CcAppliance
  ```

6. Ejecute el siguiente cmdlet para instalar Skype Empresarial Cloud Connector Edition:
    
  ```
  Install-CcAppliance
  ```

Si hay más de un dispositivo en el sitio, tendrá que seguir estos pasos, modificar el archivo CloudConnector.ini y volver a implementar los dispositivos uno a uno.
  
1. Ejecute el siguiente cmdlet para desinstalar todas las máquinas virtuales existentes en el dispositivo actual: 
    
  ```
  Uninstall-CcAppliance
  ```

2. Ejecute el siguiente cmdlet para anular el registro del dispositivo:
    
  ```
  Unregister-CcAppliance
  ```

3. Actualice el archivo CloudConnector.ini en el directorio de la aplicación.
    
4. Ejecute el cmdlet siguiente para actualizar la configuración: (este paso sólo es aplicable para la versión 2; para las versiones anteriores, vaya al paso siguiente).
    
  ```
   Import-CcConfiguration 
  ```

5. Ejecute el siguiente cmdlet para volver a registrar el dispositivo:
    
  ```
  Register-CcAppliance
  ```

6. Ejecute el siguiente cmdlet en todos los demás dispositivos del sitio para recoger la última configuración:
    
  ```
  Publish-CcAppliance
  ```

7. Ejecute el cmdlet siguiente para volver a implementar el conector de nube en el dispositivo actual:
    
  ```
  Install-CcAppliance
  ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificar la configuración de varios sitios
<a name="BKMK_MultipleSites"> </a>

Para modificar la configuración para varios sitios en una implementación, siga los pasos de un solo sitio, actualizar un sitio a la vez.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modificar la configuración de su inquilino de Office 365 para habilitar las actualizaciones automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar las actualizaciones automáticas de sistema operativo y las actualizaciones automáticas de Bits, debe usar el Skype para la cuenta de administrador de inquilinos empresarial para la administración en línea y usar PowerShell remoto de inquilinos como se indica a continuación.
  
Si deshabilita las actualizaciones automáticas de sistema operativo o las actualizaciones automáticas de Bits, el host y la máquina virtual es posible que se pierda importantes actualizaciones de Windows y en la nube conector no se actualiza automáticamente a la nueva versión. Las actualizaciones automáticas son altamente recomendables.
  
1. La propiedad EnableAutoUpdate del sitio debe establecerse en true (el valor predeterminado). Ejecute el siguiente cmdlet para asegurarse de que EnableAutoUpdate esté establecida en true:
    
  ```
  Get-CsHybridPSTNSite -Identity <SiteName>
  ```

2. Cree un intervalo de actualización automática para el inquilino.
    
    El intervalo de tiempo puede ser diario, semanal o mensual. En todos los casos se necesita una hora de inicio y una duración.
    
  - Para los intervalos diarios, solo se necesita la hora de inicio y la duración.  
    
  - Para los intervalos semanales, se necesitan los días de la semana, que pueden ser un solo día o varios días.
    
  - Los intervalos mensuales pueden ser de dos tipos. El primer tipo consiste en especificar un día del mes, que puede ser un solo día. El segunda tipo consiste en especificar las semanas del mes, junto con los días de la semana. Ambos elementos pueden ser únicos o múltiples.
    
  - Cada inquilino puede tener 20 intervalos definidos. El intervalo predeterminado se creará para un nuevo inquilino como intervalo predeterminado para actualizaciones del sistema operativo y de Bits. Ejecute los siguientes cmdlets para establecer un intervalo diario, semanal o mensual:
    
  ```
  New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
  ```

  - Asignar tiempo de actualización de windows para el sitio. 
    
    Los intervalos de actualización de Bits y del sistema operativo se configuran por separado. A ambos se les puede asignar un solo intervalo o varios. Además, cada intervalo se puede asignar a distintos sitios y distintos fines (actualización de Bits o del sistema operativo). Ejecute el cmdlet siguiente para establecer la ventana de tiempo para el sitio: 
    
  ```
  Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
  ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Actualizar las credenciales de administrador de inquilinos dedicado 
<a name="BKMK_MultipleSites"> </a>

Se realizan cambios administrativos en el inquilino de Office 365 para el conector de nube desde una cuenta con los permisos necesarios. En las versiones de conector en la nube antes de 2.0, esa cuenta es una cuenta de administrador de inquilinos global dedicado. En las versiones 2.0 y versiones posteriores de conector en la nube, esa cuenta puede ser una cuenta de Office 365 con Skype para derechos de administrador empresarial.
  
Si cambian sus credenciales de cuenta de administrador en Office 365, debe actualizar las credenciales en caché local en la nube Connector ejecutando el siguiente comando de PowerShell de administrador en cada dispositivo de conector en la nube que haya implementado:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Actualizar la contraseña del servidor host 
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> En esta sección es aplicable a la versión 2.0 de conector en la nube y versiones posteriores. 
  
Todas las credenciales del conector en la nube se almacenan en el siguiente archivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ". Cuando se cambia la contraseña en el servidor de host, debe actualizar las credenciales almacenadas localmente.
  
Para actualizar las credenciales almacenadas localmente en el dispositivo de conector en la nube, use los cmdlets [Get-CcCredential](get-cccredential.md) y [Set-CcCredential](set-cccredential.md) y siga estos pasos:
  
1. Ejecute los siguientes comandos para recuperar las contraseñas que necesitará más adelante:   
    
  - Get-CcCredential - AccountType del administrador del dominio - DisplayPassword
    
  - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
  - Get-CcCredential - AccountType CceService - DisplayPassword
    
2. Cambie la contraseña de su cuenta en el servidor host.
    
3. Reinicie el servidor host.
    
4. Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".
    
5. Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción. Asegúrese de que escribir la misma contraseña que escribió antes de la implementación del conector en la nube.
    
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
> En esta sección es aplicable a la versión 2.0.1 de conector en la nube y versiones posteriores. 
  
El servicio de conector en la nube ejecuta el servicio de administración del conector en la nube. La cuenta de CceService se creados durante la implementación en la nube conector Edition y se almacena en los siguientes archivos: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "y"% SystemDrive%\Programdata\Cloudconnector\credentials... CceService.xml".
  
Para asegurarse de que todos los dispositivos pueden obtener acceso el recurso compartido de directorio de sitios, la contraseña de la cuenta de CceService debe ser el mismo en todos los dispositivos que se implementan en el sitio. Tenga en cuenta lo siguiente:
  
- De forma predeterminada, la cuenta de CceService se configura como "La contraseña nunca caduca". Al actualizar la contraseña, Microsoft recomienda mantener esta configuración.
    
- Debe actualizar la contraseña durante períodos de uso máximo que no sean internos y externos a las ventanas de tiempo de actualización automática para bits o actualizaciones de Windows. Al actualizar la contraseña, el dispositivo debe vaciar y reiniciar, que tarda algún tiempo. Reiniciar el dispositivo se interrumpen las operaciones de actualización automática. 
    
- Cuando se cambia la contraseña de la cuenta CceService, debe especificar todas las credenciales y actualizarlos en el archivo almacenado localmente. 
    
Para cada dispositivo que pertenece al mismo sitio de RTC, debe especificar lo siguiente: 
  
1. Ejecute los comandos siguientes para recuperar los nombres de cuenta y contraseñas que va a usar más adelante:
    
  ```
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

2. Ejecute el cmdlet de entrar CcUpdate para purgar el dispositivo y mover en modo de mantenimiento manual.
    
3. Actualizar la contraseña de la cuenta de CceService en el servidor host.
    
4. Reinicie el servidor host.
    
5. Ejecute el cmdlet Restore-CcCredentials para volver a escribir las contraseñas que sigue a la descripción. 
    
    Asegúrese de que escribir la misma contraseña que escribió antes de la implementación de nube conector excepto para la cuenta de CceService. Para la cuenta de CceService, escriba la nueva contraseña. Asegúrese de que la nueva contraseña para la cuenta de CceService es el mismo para todos los dispositivos en el sitio de RTC.
    
6. De forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si las contraseñas de DomainAdmin, VMAdmin y CceService que se devolvieron en el paso 1 son diferentes, debe realizar los siguientes pasos:
    
1. Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:
    
  - Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
  - Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de DomainAdmin en el paso 1.
    
2. Ejecute Set-CcCredential -AccountType VmAdmin como sigue:
    
  - Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
  - Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña que devolvió la contraseña de VmAdmin en el paso 1.  
    
7. Ejecute el cmdlet de Exit CcUpdate para mover el dispositivo del modo de mantenimiento manual.
    
8. Después de completar estos pasos en todos los dispositivos en el mismo sitio de RTC, elimine los archivos siguientes en el directorio raíz del sitio:
    
  - CcLockFile
    
  - Site_\<fqdn del grupo de servidores Sip externo perimetrales\>
    
  - Tenant_\<fqdn del grupo de servidores Sip externo perimetrales\>
    
  - TenantConfigLock_\<fqdn del grupo de servidores Sip externo perimetrales\>
    
## <a name="add-a-new-sip-domain"></a>Agregar un nuevo dominio SIP 
<a name="BKMK_UpdatePassword"> </a>

Para agregar un nuevo dominio SIP (o varios dominios SIP) a la implementación existente de conector en la nube, haga lo siguiente:
  
1. Asegúrese de que haya completado los pasos para actualizar su dominio en Office 365 y tienen la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar el dominio en Office 365, vea el vídeo [configurar su dominio en Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).
    
2. Actualizar el archivo de configuración del conector en la nube con el nuevo dominio SIP o dominios.
    
3. Solicitar un nuevo certificado externo de borde con nombres de SAN adicionales para SIP.dominio para cada dominio SIP definido en la configuración del conector en la nube. 
    
4. Establezca la ruta de acceso del nuevo certificado perimetral externo como sigue:
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    Siga las instrucciones para [modificar la configuración de un único sitio](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [modificar la configuración de varios sitios](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificar el dominio SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si necesita cambiar el dominio SIP principal en la implementación del conector de la nube, haga lo siguiente:
  
1. Asegúrese de que haya completado los pasos para actualizar su dominio en Office 365 y tienen la capacidad de agregar registros DNS. Para obtener más información acerca de cómo configurar el dominio en Office 365, vea el vídeo [configurar su dominio en Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).
    
2. Actualice el archivo de configuración del conector en la nube con el nuevo dominio SIP.
    
3. Solicitar un nuevo certificado externo de borde con nombres de SAN adicionales para SIP.dominio para cada dominio SIP definido en la configuración del conector en la nube. 
    
4. Establezca la ruta de acceso del nuevo certificado perimetral externo como sigue:
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    Quitar el registro del inquilino para cada dispositivo en un sitio ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:
    
  ```
  Unregister-CcAppliance
  ```

6. 
    
    Quitar el registro de sitio para cada sitio ejecutando el siguiente cmdlet en Skype para PowerShell en línea de negocio:
    
  ```
  Remove-CsHybridPSTNSite
  ```

7. 
    
    Desinstalación de cada dispositivo ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:
    
  ```
  Uninstall-CcAppliance
  ```

8. 
    
     Registrar cada dispositivo ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:
    
  ```
  Register-ccAppliance
  ```

9. 
    
     Instalar cada dispositivo, uno por uno, ejecutando el siguiente cmdlet en Administrador de PowerShell en la nube conector:
    
  ```
  Install-CcAppliance
  ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Reemplazar el certificado externo del borde con un nuevo certificado
<a name="BKMK_UpdatePassword"> </a>

Cuando se necesita reemplazar el certificado externo del borde en los dispositivos de conector en la nube, debe obtener un nuevo certificado de servidor perimetral, preparar el archivo PFX que contiene la clave privada y la cadena de certificados completa y, a continuación, realice lo siguiente en cada dispositivo:
  
1. Coloque el dispositivo en modo de mantenimiento mediante el cmdlet ENTRAR CcUpdate.
    
2. Ejecute el siguiente comando: 
    
  ```
  Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
  ```

3. 
    
    Si la contraseña del certificado nuevo es el mismo que el anterior, la importación se completará correctamente. Si la contraseña es diferente, recibirá un error que la contraseña es incorrecta, y tendrá que restablecer la contraseña ejecutando el cmdlet Register-CcAppliance con el parámetro - Local, y de repetición, a continuación, el paso 2. 
    
4. Tomar el dispositivo del modo de mantenimiento mediante el cmdlet Exit - CcUpdate.
    

