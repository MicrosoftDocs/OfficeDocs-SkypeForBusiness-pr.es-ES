---
title: Solución de problemas con la implementación de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de la implementación de Cloud Connector Edition.
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094828"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solución de problemas con la implementación de Cloud Connector

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)
 
Solucionar problemas de la implementación de Cloud Connector Edition.
  
En este tema se describen soluciones a problemas comunes con implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas a y desde la red telefónica conmutada (RTC), puede investigar siguiendo las soluciones descritas en este tema.
  
Cloud Connector proporciona mecanismos integrados para resolver automáticamente algunos problemas. Un proceso de detección automática busca posibles problemas con los dispositivos de Cloud Connector y, si es posible, realiza acciones correctivas para resolver esos problemas sin necesidad de intervención del administrador. El proceso de detección funciona de la siguiente manera:
  
- **Secuencia de detección:** El servicio de administración de Cloud Connector ejecuta un proceso cada 60 segundos para detectar si un dispositivo está abajo. En Cloud Connector versión 2.0 y versiones posteriores, el proceso de detección usa el modificador Corpnet de Skype Empresarial para realizar conexiones de PowerShell a las máquinas de Cloud Connector; para versiones anteriores a la 2.0, el proceso de detección usa el conmutador de administración de Cloud Connector.
    
    > [!NOTE]
    > Para que la recuperación automática se haga correctamente, debe haber conectividad de red entre el host y las máquinas virtuales a través del conmutador de red host. Asegúrese de comprobar la conectividad de red para asegurarse de que la detección automática y la recuperación pueden tener éxito. 
  
- **Supervisión:** Los siguientes servicios se supervisan en Cloud Connector versión 2.0 y versiones posteriores:
    
  - Las máquinas virtuales no están conectadas a los conmutadores virtuales de Cloud Connector Corporate o Internet
    
  - Las máquinas virtuales están en un estado guardado o detenido
    
  - Servicios del servidor de administración central: REPLICA, MASTER
    
  - Servicios del servidor de mediación: REPLICA, RTCSRV y MEDSVC
    
  - Servicios del servidor perimetral: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Las reglas de firewall entrantes están deshabilitadas para CS RTCSRV en el servidor perimetral, CS RTCMEDSRV en el servidor de mediación
    
    En Cloud Connector versión 1.4.2, solo se supervisan los siguientes servicios:
    
  - Servicios del servidor de mediación: RTCSRV y MEDSVC
    
  - Servicio de servidor perimetral: RTCSRV
    
- **Proceso de recuperación:** Si alguno de los servicios supervisados está abajo, se marca un dispositivo hacia abajo y los servicios se detienen y se marcan manualmente hasta que se pueden resolver todos los problemas. Esto impedirá que las llamadas se enrute a un dispositivo que puedan provocar errores de llamada.
    
    El servicio de administración de Cloud Connector reintentará la recuperación automática de la siguiente manera
    
  - El intervalo de reintento inicial es cada diez segundos con un tiempo de intervalo máximo de una hora.
    
  - Para los tres primeros intentos de recuperación, el tiempo de intervalo es de 10 segundos. A partir del cuarto reintento, el tiempo de intervalo aumenta dos veces el tiempo de intervalo anterior. Por ejemplo, el cuarto reintento se producirá en 20 segundos, el quinto en 40 segundos, y así sucesivamente. 
    
  - Cuando se alcanza el intervalo máximo de una hora, los reintentos continuarán una vez por hora.
    
  - Cuando la recuperación se realiza correctamente, los recuentos de intervalos y reintentos se establecen en sus valores iniciales.
    
  - Si se reinicia el servicio de administración, los recuentos de intervalos y reintentos se restablecen a sus valores iniciales.
    
## <a name="troubleshooting"></a>Solución de problemas

A continuación se ofrecen soluciones a los problemas que se encuentran habitualmente:
  
- **Problema: la implementación produce un error o deja de responder al ejecutar los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o es incorrecta para la NIC de administración/interna/externa.**
    
    **Resolución:** Este problema no se puede resolver automáticamente. Las NIC no se pueden agregar a las máquinas virtuales mientras se ejecutan. Cierre y quite estas máquinas virtuales en el administrador de hyper-v y, a continuación, ejecute los cmdlets siguientes:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: después de instalar el servidor de Active Directory y el bosque, el servidor CMS o el servidor de mediación no se unieron al dominio correctamente.**
    
    **Resolución:** Para resolver este problema, siga estos pasos:
    
  - Inicie sesión en Active Directory Server y compruebe que el dominio se creó correctamente.
    
  - Inicie sesión en cms/servidor de mediación y compruebe que en la NIC de corpnet está asignada una dirección IP válida y que la DIRECCIÓN IP estática y DNS válidas se configuran como la dirección IP del servidor ad.
    
  - Inicie sesión en cms/servidor de mediación y abra un símbolo del sistema. Asegúrese de que puede hacer ping en el FQDN y la dirección IP del servidor de Active Directory. Si no puede, puede haber un conflicto de direcciones IP. Intente asignar una nueva DIRECCIÓN IP para Active Directory y actualice DNS en el servidor CMS/Mediation en consecuencia.
    
- **Problema: Recibe el siguiente mensaje de error: "Remove-VMSwitch: Failed while removing virtual Ethernet switch. El conmutador virtual "Conmutador de administración de Cloud Connector" no se puede eliminar porque se usa mediante la ejecución de máquinas virtuales o la asignación a grupos de servidores secundarios".**
    
    **Resolución:** El "Conmutador de administración de Cloud Connector" no se eliminó después de la implementación. Si se produce este error, vaya al administrador de Hyper-v y compruebe que aún no hay una máquina virtual conectada a ella. Si aún hay máquinas virtuales conectadas, desconéctelas y elimine el conmutador de administración. Si el modificador de administración aún no se puede eliminar, reinicie el servidor host e inténtelo de nuevo.
    
- **Problema: recibe el siguiente mensaje de error: "No se pudo iniciar el servicio RTCMRAUTH. Compruebe que el servicio no está deshabilitado."**
    
    > [!NOTE]
    > Este problema solo se aplica a las versiones de Cloud Connector anteriores a la 1.4.2. 
  
    El error de inicio también podría deberse a que este servidor front-end se ha conmutado por error anteriormente (con la conmutación por error del equipo). Si ese es el caso, invoque la conmutación por recuperación (con la conmutación por recuperación del equipo).
    
    **Resolución:** Este problema se produce en un servidor perimetral cuando el servidor perimetral no confía en el certificado de ca raíz o el certificado de CA intermedio. Incluso si el certificado externo se puede importar, pero la cadena de certificados está rota. En esta condición, el servicio RTCMRAUTH o RTCSRV no se puede iniciar.
    
    Importe manualmente el certificado de CA raíz y todos los certificados de CA intermedios del certificado externo en el servidor perimetral y, a continuación, reinicie el servidor perimetral. Después de ver los servicios RTCMRAUTH y RTCSRV iniciados en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows y las llamadas a las que presta servicio el servidor están fallando.**
    
    **Resolución:** Si implementó un entorno de alta disponibilidad, Microsoft proporciona un cmdlet para ayudar a mover una máquina host (instancia de implementación) dentro o fuera de la topología actual al comprobar e instalar Windows Update manualmente. Para ello, siga estos pasos:
    
1. En el servidor host, inicie una consola de PowerShell como administrador y, a continuación, ejecute:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Compruebe si hay actualizaciones e instale las que estén disponibles.
    
3. En la consola de PowerShell, ejecute el siguiente cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problema: cuando se realiza una llamada desde un cliente de Skype Empresarial mediante un número RTC, la llamada no se puede escalar a una conferencia invitando a otro número RTC.**
    
    **Resolución:** Para resolver este problema, vea [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar el servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarte de que tu función o característica recién instalada se actualice automáticamente, activa Windows Update".**
    
    **Resolución:** Inicie una sesión de PowerShell remoto de inquilino con credenciales de administrador de inquilinos de Skype Empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración _EnableAutoUpdate_ del sitio:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Si  _EnableAutoUpdate_ está establecido en **True**, puedes omitir este mensaje de advertencia de forma segura porque el servicio CCEManagement controlará la descarga e instalación de actualizaciones de Windows tanto para máquinas virtuales como para el servidor host. Si  _EnableAutoUpdate está_ establecido en **False**, ejecute el cmdlet siguiente para establecerlo en **True**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como alternativa, puede buscar e instalar actualizaciones manualmente. Vea la sección siguiente.
    
- **Problema: recibe un mensaje de error: no se puede registrar el dispositivo porque la entrada/configuración actual o o \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> conflictos con los dispositivos existentes. Quite el dispositivo en conflicto o actualice la información de entrada y configuración y vuelva a registrarse. ' cuando se Register-CcAppliance para registrar el dispositivo actual en línea.**
    
    **Resolución:** Los valores de \<ApplianceName\> , y deben ser \<Mediation Server FQDN\> \<Mediation Server IP Address\> únicos y solo se usan para el registro de un dispositivo. De forma predeterminada, \<ApplianceName\> proviene del nombre de host. \<Mediation Server FQDN\> y \<Mediation Server IP Address\> definido en el archivo ini de configuración.
    
    Por ejemplo, usando (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para registrarse en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, FQDN=ms.contoso.com, Dirección IP del servidor de mediación=10.10.10.10), tendrá el conflicto.
    
    En primer lugar, compruebe el archivo CloudConnector.ini en la sección directorio ApplianceRoot. Se \<SiteName\> obtienen y \<Mediation Server FQDN\> los valores en \<Mediation Server IP Address\> el archivo. \<ApplianceName\> es el nombre del servidor host.
    
    En segundo lugar, inicie Tenant Remote PowerShell con sus credenciales de administrador de inquilinos de Skype Empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar los dispositivos registrados.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Después de identificar cualquier conflicto, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: el cmdlet Get-CcRunningVersion devuelve un valor vacío si hay un dispositivo implementado ejecutándose en el host.**
    
  **Resolución:** Esto puede ocurrir cuando se actualiza de 1.3.4 o 1.3.8 a 1.4.1. Después de instalar la versión 1.4.1 con .msi, debe ejecutar antes de `Register-CcAppliance` ejecutar cualquier otro cmdlet. `Register-CcAppliance` migrará el archivo module.ini de %UserProfile%\CloudConnector a %ProgramData%\CloudConnector. Si no lo ha hecho, se creará un nuevo module.ini en la carpeta %ProgramData%\CloudConnector y reemplazará la información de versión de ejecución y copia de seguridad para 1.3.4 o 1.3.8.
    
  Compare module.ini archivos en la carpeta %UserProfile%\CloudConnector y %ProgramData%\CloudConnector. Si hay diferencias, elimine el archivo module.ini en %ProgramData%\CloudConnector y vuelva a ejecutar  `Register-CcAppliance` . También puede modificar el archivo manualmente a la versión correcta de ejecución y copia de seguridad.
    
- **Problema: después de ejecutar el cmdlet Switch-CcVersion para cambiar a una versión anterior que es diferente de la versión de script actual, no hay compatibilidad con alta disponibilidad para esta versión antigua.**
    
    **Resolución:** Por ejemplo, ha actualizado de 1.4.1 a 1.4.2. La versión de script actual, que puede determinarse mediante la ejecución, y la versión en ejecución, que se puede determinar mediante la ejecución, son `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2. En este momento, si ejecuta para volver a cambiar la versión en ejecución a 1.4.1, no habrá compatibilidad de alta disponibilidad `Switch-CcVersion` para esta versión antigua.
    
    Para obtener compatibilidad completa con alta disponibilidad, vuelva a la versión 1.4.2, por lo que la versión en ejecución y la versión de script son las mismas. Si tiene problemas con la implementación de 1.4.2, desinstale y vuelva a instalarla lo antes posible.
    
- **Problema: los certificados de entidad de certificación o los certificados internos emitidos en el Almacén de administración central, el servidor de mediación y el servidor perimetral están a punto de expirar o están en peligro.**
    
    **Resolución:** Los certificados de entidad de certificación de Skype Empresarial son válidos durante cinco años. Los certificados internos emitidos en el Almacén de administración central, el servidor de mediación y el servidor perimetral son válidos durante dos años.
    
    > [!NOTE]
    > En Cloud Connector versión 2.0 y versiones posteriores, el cmdlet Renew-CcServerCertificate ha cambiado a Update-CcServerCertificate y el cmdlet Renew-CcCACertificate ha cambiado a Update-CcCACertificate. 
  
    Si los certificados internos emitidos en el Almacén de administración central, el servidor de mediación y el servidor perimetral están cerca de expirar o están en peligro, ejecute el cmdlet Renew-CcServerCertificate o Update-CcServerCertificate para renovar los certificados.
    
    Si los certificados de entidad de certificación están a punto de expirar, ejecute el cmdlet Renew-CcCACertificate o Update-CcCACertificate para renovar los certificados.
    
    **Si los certificados de entidad de certificación están en** peligro y solo hay un dispositivo en el sitio, siga estos pasos:
    
1. Ejecute el cmdlet Enter-CcUpdate para vaciar los servicios y poner el dispositivo en modo de mantenimiento.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Ejecute los cmdlets siguientes para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:
    
    Para versiones de Cloud Connector anteriores a la 2.0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    O para Cloud Connector versión 2.0 y versiones posteriores:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado en las puertas de enlace RTC. Es posible que también tenga que volver a emitir el certificado en la puerta de enlace.

   ```powershell
   Export-CcRootCertificate
   ```

4. Ejecute el cmdlet Exit-CcUpdate para iniciar servicios y salir del modo de mantenimiento.

   ```powershell
   Exit-CcUpdate
   ```


    **Si los certificados de entidad de certificación** están en peligro y hay varios dispositivos en el sitio, realice los siguientes pasos secuenciales en cada dispositivo del sitio.
    
    Microsoft recomienda realizar estos pasos durante los tiempos de uso no pico.
    
1. En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar los archivos de copia de seguridad de ca en el \<SiteRoot\> directorio.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Ejecute el cmdlet Enter-CcUpdate para vaciar los servicios y poner cada dispositivo en modo de mantenimiento.

     ```powershell
     Enter-CcUpdate
     ```
    
3. En el primer dispositivo, ejecute los cmdlets siguientes para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:
    
     Para versiones de Cloud Connector anteriores a la 2.0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     O para Cloud Connector versión 2.0 y versiones posteriores:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. En el primer dispositivo, ejecute el siguiente cmdlet para realizar una copia de seguridad de los archivos de ca en la \<SiteRoot\> carpeta.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. En todos los demás dispositivos del mismo sitio, ejecute los siguientes comandos para consumir los archivos de copia de seguridad de ca, de modo que todos los dispositivos usen el mismo certificado raíz y, a continuación, soliciten certificados nuevos. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo del sitio y, a continuación, instale el certificado exportado en las puertas de enlace RTC. Es posible que también tenga que volver a emitir el certificado en la puerta de enlace.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Ejecute el cmdlet Exit-CcUpdate para iniciar servicios y salir del modo de mantenimiento. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: recibe el siguiente mensaje de error en el registro del servicio de administración de Cloud Connector, "C:\Archivos de programa\Skype Empresarial Cloud Connector Edition\ManagementService\CceManagementService.log": Error de CceService: 0 : Excepción inesperada al notificar el estado en línea: System.Management.Automation.CmdletInvocationException: Error de inicio de sesión para el usuario \<Global Tenant Admin\> . Cree un nuevo objeto de credencial para asegurarse de que ha usado el nombre de usuario y la contraseña correctos. ---\>**
    
    **Resolución:** Las credenciales de administrador global de inquilinos de Microsoft 365 u Office 365 se han cambiado desde que se registró el dispositivo de Cloud Connector. Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, ejecute lo siguiente desde PowerShell de administrador en el dispositivo host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: después de cambiar la contraseña de la cuenta de servidor host que usó para la implementación, recibe el siguiente mensaje de error: "ConvertTo-SecureString: Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o mientras ejecuta el cmdlet Get-CcCredential.**
    
    **Resolución:** Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml". Cuando cambie la contraseña en el servidor host, deberá actualizar las credenciales almacenadas localmente.
    
    **Si ejecuta Cloud Connector versión 1.4.2,** vuelva a generar todas las contraseñas de Cloud Connector siguiendo estos pasos:
    
  1. Reinicie el servidor host.
    
  2. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".
    
  3. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción. Escriba las mismas contraseñas que introdujo anteriormente para la implementación de Cloud Connector.
    
     **Si ejecuta Cloud Connector versión 2.0** o posterior, vuelva a generar todas las contraseñas de Cloud Connector siguiendo estos pasos:
    
  4. Reinicie el servidor host.
    
  5. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" .
    
  6. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción. 
    
     Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 1.4.2, use la contraseña VMAdmin para la contraseña de CceService cuando se le pida. Escriba la misma contraseña que escribió antes para la implementación de Cloud Connector para todas las demás cuentas.
    
     Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 1.4.2 y las contraseñas DomainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:
    
  7. Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:
    
  8. Cuando se le pida la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
  9. Cuando se le pida la nueva credencial de cuenta, escriba la contraseña de la contraseña domainAdmin que usó antes.
    
     Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 2.0 o posterior, de forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si ha cambiado las contraseñas DomainAdmin y VMAdmin, debe realizar los pasos siguientes:
    
  10. Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:
    
       1. Cuando se le pida la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService
    
       2. Cuando se le pida la nueva credencial de cuenta, escriba la contraseña de la contraseña domainAdmin que usó antes.
    
  11. Ejecute Set-CcCredential -AccountType VmAdmin de la siguiente manera:
    
       1. Cuando se le pida la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService
    
       2. Cuando se le pida la nueva credencial de cuenta, escriba la contraseña de la contraseña de VmAdmin que usó antes. 
    
- **Problema: con Cloud Connector versión 2.1 y versiones posteriores, al ejecutar Register-CcAppliance u otros cmdlets en el dispositivo, recibe un mensaje de error como: "For Each-Object : La propiedad 'Common' no se encuentra en este objeto. Compruebe que la propiedad existe. En C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Resolución:** Cloud Connector 2.1 y versiones posteriores .NET Framework 4.6.1 o posterior. Actualice los .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar los cmdlets.

- **Problema: con Cloud Connector Edition 2.1, al ejecutar Install-CcAppliance, recibe un mensaje de error como: "Error al instalar nueva instancia con error: no se puede establecer "Estado" porque solo se pueden usar cadenas como valores para establecer propiedades XmlNode"**

   **Resolución:** En Cloudconnector.ini, en la sección [Común], agregue la configuración "Estado" como se muestra a continuación: CountryCode=US State=WA City=Redmond

   No es obligatorio que la línea "Estado" tenga valor, pero la línea "Estado" no se puede quitar del Cloudconnector.ini archivo.

- **Problema: Recibe el siguiente mensaje de error "Dismount-WindowsImage : Dismount-WindowsImage error. Código de error = 0xc1550115" al instalar o actualizar Cloud Connector Edition.**
    
    **Resolución:** Inicie una consola de PowerShell como administrador y ejecute "DISM -Cleanup-Wim'". Esto limpiará todas las imágenes con problemas. Ejecute Install-CcAppliance o espere a que los bits se actualicen automáticamente.
    
- **Problema: Se produce un error en la implementación del primer dispositivo de Cloud Connector en un entorno de HA**
    
    **Resolución:** Los pasos que siga dependen del motivo por el que se ha fallado la implementación:
    
  - Si se produce un error en el primer dispositivo de Cloud Connector y no se puede determinar el motivo del error, debe volver a instalar el dispositivo hasta que la implementación se haya realizado correctamente y, a continuación, instalar los otros dispositivos.
    
  - Si el primer dispositivo de Cloud Connector produce un error con un problema menor, como un problema de certificado externo, es posible que pueda solucionar el problema sin volver a instalar el dispositivo. A continuación, puede usar PowerShell remoto de inquilino para marcar la implementación como correcta de la siguiente manera. (También puede usar los siguientes pasos si la primera implementación se ha realizado correctamente, pero, por algún motivo, Cloud Connector no informa de la implementación como correcta).
    
  - Para obtener la identidad (GUID) del primer dispositivo de Cloud Connector, ejecute el cmdlet Get-CsHybridPSTNAppliance.
    
  - Para marcar el dispositivo como implementado correctamente, ejecute el Set-CsCceApplianceDeploymentStatus de la siguiente manera:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: debes buscar e instalar las actualizaciones de Windows manualmente en el servidor host o las máquinas virtuales.**
    
   **Resolución:** Se recomienda aprovechar las actualizaciones automatizadas del sistema operativo proporcionadas por Skype Empresarial Cloud Connector Edition. Después de registrar un dispositivo para la administración en línea y de habilitar la actualización automática del sistema operativo, el servidor host y las máquinas virtuales comprobarán e instalarán actualizaciones de Windows automáticamente de acuerdo con la configuración de la ventana de tiempo de actualización del sistema operativo.
    
   Si necesitas buscar e instalar actualizaciones de Windows manualmente, sigue los pasos de esta sección que se aplican al tipo de implementación. Debe planear la actualización del servidor host y las máquinas virtuales que se ejecutan en él al mismo tiempo para minimizar la cantidad de tiempo de inanidad necesario para las actualizaciones.
    
   Si lo prefieres, puedes usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones a los servidores de Cloud Connector. Asegúrate de configurar Windows Update para **que no se instale** automáticamente.
    
   Para obtener información sobre cómo actualizar manualmente la implementación de Cloud Connector, consulte la siguiente sección.
    
- **Problema: cuando Cloud Connector se actualiza en una nueva compilación, los cmdlets de Cloud Connector no se actualizan.** Esto sucede a veces si una ventana de PowerShell se deja abierta cuando se produce una actualización automática.
    
  **Resolución:** Para cargar los cmdlets actualizados, puede realizar uno de los siguientes pasos:
    
   - Cierre PowerShell en el dispositivo de Cloud Connector y, a continuación, vuelva a abrir PowerShell.
    
     - O bien, puede ejecutar Import-Module CloudConnector -Force. 
 
-   **Problema: "El término 'Stop-CsWindowsService' no se reconoce como el nombre de un cmdlet, función, archivo de script o programa operable". Error al intentar ejecutar Enter-CcUpdate cmdlet.**

    **Resolución:** Elimine el archivo $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea este archivo como una memoria caché de cmdlets a partir de módulos que encuentra para que no tenga que volver a analizar todos los módulos cada vez, ya que esto haría que las cosas se ralentizase. Lo más probable es que hubo algunos daños en los archivos que proporcionaron resultados engañosos a PowerShell cuando estaba leyendo de esa memoria caché.

-   **Problema: "Import-Module CloudConnector" genera el error "Import-Module: El módulo especificado "CloudConnector" no se cargó porque no se encontró ningún archivo de módulo válido en ningún directorio de módulos"**

    **Resolución:**
    - Valide que el módulo CloudConnector existe en c:\Archivos de programa\WindowsPowerShell\Modules
    
    - Después de validar que el módulo CloudConnector existe en esta ubicación, se puede cambiar la variable de entorno PSModulePath que almacena la ruta de acceso a las ubicaciones de los módulos:
    
     a. Cambio temporal: inicie Powershell como administrador y ejecute el siguiente comando: $env:PSModulePath = $env:PSModulePath + "; C:\Archivos de programa\WindowsPowerShell\Modules\"
        
     b. Para el cambio persistente, inicie PowerShell como administrador y ejecute los siguientes comandos, uno a uno: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Instalar actualizaciones de Windows manualmente

Si no quieres usar actualizaciones automáticas en tu entorno, sigue estos pasos para buscar y aplicar manualmente las actualizaciones de Windows. La comprobación e instalación de actualizaciones de Windows puede requerir un reinicio del servidor. Cuando se reinicia un servidor host, los usuarios no podrán usar Cloud Connector para realizar o recibir llamadas. Puedes comprobar e instalar actualizaciones manualmente para controlar cuándo se llevan a cabo las actualizaciones y, a continuación, reiniciar las máquinas según sea necesario durante las horas que elijas para evitar la interrupción de los servicios.
  
Para comprobar manualmente si hay actualizaciones, conéctese a cada servidor host y abra el **Panel de control**. Selecciona **Sistema y Seguridad de Windows \> Update** y, a continuación, administra las actualizaciones y los reinicios del servidor según corresponda para tu entorno.
  
- Si solo hay un dispositivo en el sitio, conéctese a cada máquina virtual y abra el **Panel de control**. Selecciona **Sistema y Seguridad de Windows \> Update** y, a continuación, configura las actualizaciones y los reinicios del servidor según corresponda.
    
- Si hay más de un dispositivo en el sitio, los usuarios no podrán acceder a la instancia que se está actualizando y reiniciando durante las actualizaciones. Los usuarios se conectarán a otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype Empresarial comiencen en las máquinas virtuales una vez completadas las actualizaciones. Para evitar cualquier posible interrupción del servicio, puede quitar la instancia de HA mientras aplica las actualizaciones y, a continuación, restaurarla cuando se complete. Para ello:
    
1. En cada servidor host, abra una consola de PowerShell como administrador.
    
2. Quite la instancia de HA con el siguiente cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Siga los pasos de una sola instancia para aplicar manualmente las actualizaciones y reiniciar la máquina virtual.
    
4. Vuelva a establecer la instancia en HA con el siguiente cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

Para las implementaciones de varios sitios, siga los pasos de un solo sitio para cada sitio de la implementación, aplicando actualizaciones a un sitio a la vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Sugerencias al instalar software antivirus en el equipo host de Cloud Connector

Si necesita instalar software antivirus en el equipo host de Cloud Connector, debe agregar las siguientes exclusiones:
  
- Directorio de dispositivo local en cada equipo.
    
- Directorio de sitios remoto en cada equipo.
    
- El Directorio de sitios local del equipo hospeda la carpeta raíz del sitio compartido.
    
- %ProgramFiles%\Skype Empresarial Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- El proceso Microsoft.Rtc.CCE.ManagementService.exe.