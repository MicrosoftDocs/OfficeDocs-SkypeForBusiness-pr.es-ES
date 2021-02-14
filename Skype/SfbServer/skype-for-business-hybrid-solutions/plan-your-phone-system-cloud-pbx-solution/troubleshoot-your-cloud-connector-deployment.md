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
description: Solucione los problemas de la implementación de Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359336"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solución de problemas con la implementación de Cloud Connector

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Solucione los problemas de la implementación de Cloud Connector Edition.
  
En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas a y desde la red telefónica conmutada (RTC), puede investigar siguiendo las soluciones descritas en este tema.
  
Cloud Connector proporciona mecanismos integrados para resolver automáticamente algunos problemas. Un proceso de detección automática busca posibles problemas con los dispositivos de Cloud Connector y, si es posible, toma medidas correctivas para resolver esos problemas sin necesidad de la intervención del administrador. El proceso de detección funciona de la siguiente manera:
  
- **Secuencia de detección:** El servicio de administración de Cloud Connector ejecuta un proceso cada 60 segundos para detectar si un dispositivo está abajo. En Cloud Connector versión 2.0 y versiones posteriores, el proceso de detección usa el conmutador corpnet de Skype Empresarial para realizar conexiones de PowerShell a las máquinas de Cloud Connector; para versiones anteriores a 2.0, el proceso de detección usa el conmutador de administración de Cloud Connector.
    
    > [!NOTE]
    > Para que la recuperación automática se pueda realizar correctamente, debe haber conectividad de red entre el host y las máquinas virtuales a través del conmutador de red host. Asegúrese de comprobar la conectividad de red para asegurarse de que la detección y recuperación automáticas puedan ser correctas. 
  
- **Supervisión:** Los siguientes servicios se supervisan en Cloud Connector versión 2.0 y versiones posteriores:
    
  - Las máquinas virtuales no están conectadas a los conmutadores virtuales corporativos o de Internet de Cloud Connector
    
  - Las máquinas virtuales están en un estado guardado o detenido
    
  - Servicios del servidor de administración central: REPLICA, MASTER
    
  - Servicios del servidor de mediación: REPLICA, RTCSRV y MEDSVC
    
  - Servicios del servidor perimetral: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Las reglas de firewall de entrada están deshabilitadas para RTCSRV de CS en el servidor perimetral, RTCMEDSRV de CS en el servidor de mediación
    
    En Cloud Connector versión 1.4.2, solo se supervisan los siguientes servicios:
    
  - Servicios del servidor de mediación: RTCSRV y MEDSVC
    
  - Servicio de servidor perimetral: RTCSRV
    
- **Proceso de recuperación:** Si alguno de los servicios supervisados no está disponible, se marca un dispositivo y los servicios se detienen y se marcan manualmente hasta que se pueden resolver todos los problemas. Esto impedirá que las llamadas se enrutar a un dispositivo que pueda causar errores de llamada.
    
    El servicio de administración de Cloud Connector reintentará la recuperación automática de la siguiente manera
    
  - El intervalo de reintento inicial es cada diez segundos con un intervalo máximo de una hora.
    
  - Para los tres primeros intentos de recuperación, el tiempo de intervalo es de 10 segundos. A partir del cuarto reintento, el tiempo de intervalo aumenta dos veces el tiempo del intervalo anterior. Por ejemplo, el cuarto reintento se producirá en 20 segundos, el quinto en 40 segundos, y así sucesivamente. 
    
  - Cuando se alcanza el intervalo máximo de una hora, los reintentos continuarán una vez por hora.
    
  - Cuando la recuperación se realiza correctamente, el intervalo y los recuentos de reintentos se establecen en sus valores iniciales.
    
  - Si se reinicia el servicio de administración, el intervalo y los recuentos de reintentos se restablecen a sus valores iniciales.
    
## <a name="troubleshooting"></a>Solución de problemas

A continuación se ofrecen soluciones a los problemas que se encuentran habitualmente:
  
- **Problema: la implementación produce un error o deja de responder al ejecutar los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o es incorrecta para la NIC de administración/interna/externa.**
    
    **Solución:** Este problema no se puede resolver automáticamente. Las NIC no se pueden agregar a las máquinas virtuales mientras se ejecutan. Cierre y quite estas máquinas virtuales en el administrador de hyper-v y, a continuación, ejecute los cmdlets siguientes:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: después de instalar el servidor de Active Directory y el bosque, el servidor CMS o el servidor de mediación no se unieron al dominio correctamente.**
    
    **Solución:** Para resolver este problema, siga estos pasos:
    
  - Inicie sesión en el servidor de Active Directory y compruebe que el dominio se creó correctamente.
    
  - Inicie sesión en el servidor cms/de mediación y compruebe que en la NIC de la red corpnet se haya asignado una dirección IP válida y que el DNS y la IP estática válidos estén configurados como la dirección IP del servidor de AD.
    
  - Inicie sesión en el servidor CMS/Mediation y abra un símbolo del sistema. Asegúrese de que puede hacer ping al FQDN y la dirección IP del servidor de Active Directory. Si no puede, puede haber un conflicto de direcciones IP. Intente asignar una nueva DIRECCIÓN IP para Active Directory y actualice DNS en el servidor CMS/Mediation según corresponda.
    
- **Problema: Recibe el siguiente mensaje de error: "Remove-VMSwitch : Failed while removing virtual Ethernet switch. El conmutador virtual "Conmutador de administración de Cloud Connector" no se puede eliminar porque se usa ejecutando máquinas virtuales o se asigna a grupos de servidores secundarios".**
    
    **Solución:** El "Conmutador de administración de Cloud Connector" no se eliminó después de la implementación. Si se produce este error, vaya al administrador de Hyper-v y compruebe que aún no haya una máquina virtual conectada a él. Si todavía hay máquinas virtuales conectadas, desconéctelas y elimine el conmutador de administración. Si el conmutador de administración aún no se puede eliminar, reinicie el servidor host e inténtelo de nuevo.
    
- **Problema: Recibe el siguiente mensaje de error: "No se pudo iniciar el servicio RTCMRAUTH. Compruebe que el servicio no está deshabilitado".**
    
    > [!NOTE]
    > Este problema solo se aplica a las versiones de Cloud Connector anteriores a la 1.4.2. 
  
    El error de inicio también podría deberse a que anteriormente se conmutación por error de este servidor front-end (mediante la conmutación por error del equipo). Si ese es el caso, invoque la conmutación por recuperación (con la conmutación por recuperación del equipo).
    
    **Solución:** Este problema se produce en un servidor perimetral cuando el servidor perimetral no confía en el certificado de ca raíz o en el certificado de ca intermedia. Incluso si se puede importar el certificado externo, pero la cadena de certificados está rota. En esta condición, el servicio RTCMRAUTH o RTCSRV no se puede iniciar.
    
    Importe manualmente el certificado de ca raíz y todos los certificados de CA intermedias del certificado externo en el servidor perimetral y, a continuación, reinicie el servidor perimetral. Cuando vea los servicios RTCMRAUTH y RTCSRV iniciados en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows y se han fallado las llamadas a las que presta servicio el servidor.**
    
    **Solución:** Si implementó un entorno de alta disponibilidad, Microsoft proporciona un cmdlet para ayudar a mover una máquina host (instancia de implementación) dentro o fuera de la topología actual al comprobar e instalar la actualización de Windows manualmente. Para ello, siga estos pasos:
    
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
    
    **Solución:** Para resolver este problema, consulte [Configuración del servidor de mediación híbrido en línea.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)
    
- **Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar el servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarte de que tu función o característica recién instalada se actualice automáticamente, activa Windows Update".**
    
    **Solución:** Inicie una sesión de PowerShell remoto de inquilino con credenciales de administrador de inquilinos de Skype Empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ de su sitio:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Si  _EnableAutoUpdate_ está establecido en **True,** puede omitir este mensaje de advertencia de forma segura porque el servicio CCEManagement controlará la descarga e instalación de actualizaciones de Windows para las máquinas virtuales y el servidor host. Si  _EnableAutoUpdate está_ establecido en **False**, ejecute el siguiente cmdlet para establecerlo en **True**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como alternativa, puede buscar e instalar actualizaciones manualmente. Vea la sección siguiente.
    
- **Problema: recibe un mensaje de error: No se puede registrar el dispositivo porque la entrada o configuración actuales o porque está en conflicto con los \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> dispositivos existentes. Quite el dispositivo en conflicto o actualice la información de entrada y configuración y vuelva a registrarse. ' when run Register-CcAppliance to register current appliance to online.**
    
    **Solución:** Valores para el registro de un dispositivo y deben \<ApplianceName\> \<Mediation Server FQDN\> ser \<Mediation Server IP Address\> únicos y usarse únicamente para el registro de un dispositivo. De forma predeterminada, \<ApplianceName\> proviene del nombre de host. \<Mediation Server FQDN\> y \<Mediation Server IP Address\> se define en el archivo ini de configuración.
    
    Por ejemplo, si usa (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para registrarse en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, MEDIATION Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), tendrá el conflicto.
    
    En primer lugar, compruebe el archivo CloudConnector.ini en la sección del directorio ApplianceRoot. You will get \<SiteName\> , and values in the \<Mediation Server FQDN\> \<Mediation Server IP Address\> file. \<ApplianceName\> es el nombre del servidor host.
    
    En segundo lugar, inicie El PowerShell remoto del inquilino con sus credenciales de administrador de inquilinos de Skype Empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar los dispositivos registrados.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Después de identificar los conflictos, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: el cmdlet Get-CcRunningVersion devuelve un valor vacío si hay un dispositivo implementado ejecutándose en el host.**
    
  **Solución:** Esto puede suceder cuando actualiza de 1.3.4 o 1.3.8 a 1.4.1. Después de instalar la versión 1.4.1 con el archivo .msi, debe ejecutar antes de `Register-CcAppliance` ejecutar cualquier otro cmdlet. `Register-CcAppliance` migrará el archivo module.ini de %UserProfile%\CloudConnector a %ProgramData%\CloudConnector. Si no lo ha hecho, se creará un nuevo module.ini en la carpeta %ProgramData%\CloudConnector y se reemplazará la información de la versión de ejecución/copia de seguridad para la versión 1.3.4 o 1.3.8.
    
  Compare module.ini archivos en la carpeta %UserProfile%\CloudConnector y %ProgramData%\CloudConnector. Si hay diferencias, elimine el archivo module.ini en %ProgramData%\CloudConnector y vuelva a  `Register-CcAppliance` ejecutarlo. También puede modificar el archivo manualmente a la versión correcta en ejecución y de copia de seguridad.
    
- **Problema: después de ejecutar el cmdlet Switch-CcVersion para cambiar a una versión anterior que es diferente de la versión actual del script, no hay compatibilidad de alta disponibilidad para esta versión anterior.**
    
    **Solución:** Por ejemplo, ha actualizado de 1.4.1 a 1.4.2. La versión actual del script, que puede determinarse mediante la ejecución, y la versión en ejecución, que se puede determinar mediante la ejecución son `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2. En este momento, si ejecuta para volver a cambiar la versión en ejecución a 1.4.1, no habrá compatibilidad de alta disponibilidad para esta `Switch-CcVersion` versión anterior.
    
    Para obtener compatibilidad completa con alta disponibilidad, vuelva a la versión 1.4.2, para que la versión en ejecución y la versión de script sean las mismas. Si tiene problemas con la implementación 1.4.2, desinstale y vuelva a instalarla lo antes posible.
    
- **Problema: los certificados de entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**
    
    **Solución:** Los certificados de entidad de certificación de Skype Empresarial son válidos durante cinco años. Los certificados internos emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral son válidos durante dos años.
    
    > [!NOTE]
    > En Cloud Connector versión 2.0 y versiones posteriores, el cmdlet Renew-CcServerCertificate ha cambiado a Update-CcServerCertificate y el cmdlet Renew-CcCACertificate ha cambiado a Update-CcCACertificate. 
  
    Si los certificados internos emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral están a punto de expirar o están en peligro, ejecute el cmdlet Renew-CcServerCertificate o Update-CcServerCertificate para renovar los certificados.
    
    Si los certificados de la entidad de certificación están a punto de expirar, ejecute el cmdlet Renew-CcCACertificate o Update-CcCACertificate para renovar los certificados.
    
    **Si los certificados de la entidad de certificación están** en peligro y solo hay un dispositivo en el sitio, siga estos pasos:
    
1. Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner el dispositivo en modo de mantenimiento.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:
    
    Para las versiones de Cloud Connector anteriores a 2.0:
    
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
    
3. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado en las puertas de enlace RTC. Es posible que también deba volver a emitir el certificado en la puerta de enlace.

   ```powershell
   Export-CcRootCertificate
   ```

4. Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.

   ```powershell
   Exit-CcUpdate
   ```


    **Si los certificados de la entidad de certificación** están en peligro y hay varios dispositivos en el sitio, realice los siguientes pasos secuenciales en cada dispositivo del sitio.
    
    Microsoft recomienda realizar estos pasos durante los períodos de uso no pico.
    
1. En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar los archivos de copia de seguridad de ca en el \<SiteRoot\> directorio.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner cada dispositivo en modo de mantenimiento.

     ```powershell
     Enter-CcUpdate
     ```
    
3. En el primer dispositivo, ejecute los cmdlets siguientes para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:
    
     Para las versiones de Cloud Connector anteriores a 2.0:
    
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

4. En el primer dispositivo, ejecute el siguiente cmdlet para hacer una copia de seguridad de los archivos de ca en la \<SiteRoot\> carpeta.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. En todos los demás dispositivos del mismo sitio, ejecute los siguientes comandos para consumir los archivos de copia de seguridad de ca, de modo que todos los dispositivos usen el mismo certificado raíz y, a continuación, soliciten nuevos certificados. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo del sitio y, a continuación, instale el certificado exportado en las puertas de enlace RTC. Es posible que también deba volver a emitir el certificado en la puerta de enlace.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: Recibe el siguiente mensaje de error en el registro del servicio de administración de Cloud Connector, "C:\Archivos de programa\Skype Empresarial Cloud Connector Edition\ManagementService\CceManagementService.log": Error de CceService: 0 : Excepción inesperada al notificar el estado en línea: System.Management.Automation.CmdletInvocationException: Error de inicio de sesión para el \<Global Tenant Admin\> usuario. Cree un nuevo objeto de credenciales y asegúrese de que ha usado el nombre de usuario y la contraseña correctos. ---\>**
    
    **Solución:** Las credenciales de administrador global de inquilinos de Microsoft 365 u Office 365 se han cambiado desde que se registró el dispositivo de Cloud Connector. Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, ejecute lo siguiente desde PowerShell de administrador en el dispositivo host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: Después de cambiar la contraseña de la cuenta del servidor host que usó para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString : Clave no válida para su uso en el estado especificado". En %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o mientras se ejecuta el cmdlet Get-CcCredential.**
    
    **Solución:** Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml". Cuando cambie la contraseña del servidor host, deberá actualizar las credenciales almacenadas localmente.
    
    **Si ejecuta Cloud Connector versión 1.4.2,** vuelva a generar todas las contraseñas de Cloud Connector siguiendo estos pasos:
    
  1. Reinicie el servidor host.
    
  2. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".
    
  3. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción. Escriba las mismas contraseñas que escribió antes para la implementación de Cloud Connector.
    
     **Si ejecuta Cloud Connector versión 2.0** o posterior, vuelva a generar todas las contraseñas de Cloud Connector siguiendo estos pasos:
    
  4. Reinicie el servidor host.
    
  5. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" .
    
  6. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción. 
    
     Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 1.4.2, use la contraseña de VMAdmin para la contraseña de CceService cuando se le pida. Escriba la misma contraseña que escribió antes para la implementación de Cloud Connector para todas las demás cuentas.
    
     Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 1.4.2 y las contraseñas domainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:
    
  7. Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:
    
  8. Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
  9. Cuando se le solicite la credencial de la nueva cuenta, escriba la contraseña de la contraseña de DomainAdmin que usó antes.
    
     Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 2.0 o posterior, de forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService. Si cambió las contraseñas de DomainAdmin y VMAdmin, debe realizar los siguientes pasos:
    
  10. Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:
    
       1. Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
       2. Cuando se le solicite la credencial de la nueva cuenta, escriba la contraseña de la contraseña de DomainAdmin que usó antes.
    
  11. Ejecute Set-CcCredential -AccountType VmAdmin de la siguiente manera:
    
       1. Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.
    
       2. Cuando se le solicite la nueva credencial de cuenta, escriba la contraseña de la contraseña de VmAdmin que usó antes. 
    
- **Problema: con Cloud Connector versión 2.1 y versiones posteriores, al ejecutar Register-CcAppliance u otros cmdlets en el dispositivo, recibe un mensaje de error como: "For Each-Object : The property 'Common' cannot be found on this object. Compruebe que la propiedad existe. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Solución:** Cloud Connector 2.1 y versiones posteriores requiere .NET Framework 4.6.1 o posterior. Actualice .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar los cmdlets.

- **Problema: Con Cloud Connector Edition 2.1, al ejecutar Install-CcAppliance, recibe un mensaje de error como: "Error al instalar una nueva instancia con el error: No se puede establecer "State" porque solo se pueden usar cadenas como valores para establecer propiedades XmlNode"**

   **Solución:** En Cloudconnector.ini, en la sección [Común], agregue la configuración "Estado" como se muestra a continuación: CountryCode=US State=WA City=Redmond

   No es obligatorio que la línea "Estado" tenga valor, pero no se puede quitar la línea "Estado" del archivo Cloudconnector.ini estado.

- **Problema: recibe el siguiente mensaje de error "Dismount-WindowsImage : Dismount-WindowsImage error. Código de error = 0xc1550115" al instalar o actualizar Cloud Connector Edition.**
    
    **Solución:** Inicia una consola de PowerShell como administrador y ejecuta "DISM -Cleanup-Wim'". Esto limpiará todas las imágenes con problemas. Ejecute Install-CcAppliance o espere a que los bits se actualicen automáticamente.
    
- **Problema: se produce un error en la implementación del primer dispositivo de Cloud Connector en un entorno ha**
    
    **Solución:** Los pasos que siga dependen del motivo por el que se ha fallado la implementación:
    
  - Si se produce un error en el primer dispositivo de Cloud Connector y no se puede determinar el motivo del error, debe instalarlo de nuevo hasta que la implementación se haya realizado correctamente y, a continuación, instalar los demás dispositivos.
    
  - Si se produce un error en el primer dispositivo de Cloud Connector con un problema menor, como un problema de certificado externo, es posible que pueda solucionar el problema sin volver a instalar el dispositivo. A continuación, puede usar PowerShell remoto de inquilino para marcar la implementación como correcta de la siguiente manera. (También puede seguir los pasos siguientes si la primera implementación se ha realizado correctamente, pero, por algún motivo, Cloud Connector no puede informar de que la implementación se ha realizado correctamente).
    
  - Para obtener la identidad (GUID) del primer dispositivo de Cloud Connector, ejecute Get-CsHybridPSTNAppliance cmdlet.
    
  - Para marcar el dispositivo como implementado correctamente, ejecute el Set-CsCceApplianceDeploymentStatus como se muestra a continuación:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: debe comprobar e instalar las actualizaciones de Windows manualmente en el servidor host o en las máquinas virtuales.**
    
   **Solución:** Le recomendamos que aproveche las actualizaciones automatizadas del sistema operativo proporcionadas por Skype Empresarial Cloud Connector Edition. Después de registrar un dispositivo para la administración en línea y habilitar la actualización automática del sistema operativo, el servidor host y las máquinas virtuales comprobarán e instalarán actualizaciones de Windows automáticamente de acuerdo con la configuración de la ventana de tiempo de actualización del sistema operativo.
    
   Si necesitas comprobar e instalar actualizaciones de Windows manualmente, sigue los pasos de esta sección que se aplican a tu tipo de implementación. Debe planear la actualización del servidor host y de las máquinas virtuales que se ejecutan en él al mismo tiempo para minimizar la cantidad de tiempo de in corriente necesario para las actualizaciones.
    
   Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones a los servidores de Cloud Connector. Asegúrate de configurar Windows Update para **que no se instale** automáticamente.
    
   Para obtener información sobre cómo actualizar manualmente la implementación de Cloud Connector, consulte la sección siguiente.
    
- **Problema: cuando Cloud Connector se actualiza a una nueva compilación, los cmdlets de Cloud Connector no se actualizan.** Esto a veces sucede si se deja abierta una ventana de PowerShell cuando se produce una actualización automática.
    
  **Solución:** Para cargar los cmdlets actualizados, puede realizar uno de los siguientes pasos:
    
   - Cierre PowerShell en el dispositivo de Cloud Connector y vuelva a abrir PowerShell.
    
     - O bien, puede ejecutar Import-Module CloudConnector -Force. 
 
-   **Problema: "El término 'Stop-CsWindowsService' no se reconoce como el nombre de un cmdlet, una función, un archivo de script o un programa operable". Al intentar ejecutar Enter-CcUpdate cmdlet.**

    **Solución:** Elimine el $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea este archivo como una memoria caché de cmdlets a partir de los módulos que encuentra para que no tenga que volver a analizar todos los módulos cada vez, ya que esto haría que las cosas se ralentizase mucho. Lo más probable es que haya algunos daños en el archivo que proporcionaron resultados engañosos a PowerShell cuando estaba leyendo de esa memoria caché.

-   **Problema: "Import-Module CloudConnector" genera el error "Import-Module: El módulo especificado "CloudConnector" no se cargó porque no se encontró ningún archivo de módulo válido en ningún directorio de módulos"**

    **Resolución:**
    - Valide que realmente el módulo CloudConnector existe en c:\Archivos de programa\WindowsPowerShell\Modules
    
    - Después de validar que el módulo CloudConnector existe en esta ubicación, se puede cambiar la variable de entorno PSModulePath que almacena la ruta de acceso a las ubicaciones de los módulos:
    
     a. Cambio temporal: inicie PowerShell como administrador y ejecute el siguiente comando: $env:PSModulePath = $env:PSModulePath + "; C:\Archivos de programa\WindowsPowerShell\Modules\"
        
     b. Para el cambio persistente, inicie PowerShell como administrador y ejecute los siguientes comandos, uno a uno: $CurrentValue = [Entorno]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Archivos de programa\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Instalar las actualizaciones de Windows manualmente

Si no quieres usar actualizaciones automáticas en tu entorno, sigue estos pasos para comprobar y aplicar manualmente las actualizaciones de Windows. La comprobación e instalación de actualizaciones de Windows puede requerir un reinicio del servidor. Cuando se reinicia un servidor host, los usuarios no podrán usar Cloud Connector para realizar o recibir llamadas. Puedes comprobar e instalar actualizaciones manualmente para controlar cuándo se llevan a cabo las actualizaciones y, a continuación, reiniciar las máquinas según sea necesario durante las horas que elijas para evitar la interrupción de los servicios.
  
Para comprobar manualmente si hay actualizaciones, conéctese a cada servidor host y abra el **Panel de control.** Seleccione **Sistema y seguridad de Windows \> Update** y, a continuación, administre las actualizaciones y los reinicios del servidor según corresponda a su entorno.
  
- Si solo hay un dispositivo en el sitio, conéctese a cada máquina virtual y abra el **Panel de control.** Selecciona **Sistema y seguridad de Windows \> Update** y, a continuación, configura las actualizaciones y los reinicios del servidor según corresponda.
    
- Si hay más de un dispositivo en el sitio, los usuarios no pueden tener acceso a la instancia que se actualiza y reinicia durante las actualizaciones. Los usuarios se conectarán a otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype Empresarial comiencen en las máquinas virtuales una vez completadas las actualizaciones. Para evitar cualquier posible interrupción del servicio, puede quitar la instancia de HA mientras aplica las actualizaciones y, a continuación, restaurarla cuando se complete. Para ello:
    
1. En cada servidor host, abra una consola de PowerShell como administrador.
    
2. Quite la instancia de HA con el siguiente cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Siga los pasos para que una sola instancia aplique manualmente las actualizaciones y reinicie la máquina virtual.
    
4. Vuelva a establecer la instancia en HA con el siguiente cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

Para las implementaciones de varios sitios, siga los pasos para un solo sitio para cada sitio de la implementación, aplicando actualizaciones a un sitio cada vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Sugerencias al instalar software antivirus en el equipo host de Cloud Connector

Si necesita instalar software antivirus en el equipo host de Cloud Connector, debe agregar las siguientes exclusiones:
  
- Directorio de dispositivos local en cada equipo.
    
- Directorio de sitios remoto en cada equipo.
    
- El Directorio de sitios local del equipo hospeda la carpeta raíz del sitio compartido.
    
- %ProgramFiles%\Skype Empresarial Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- El proceso Microsoft.Rtc.CCE.ManagementService.exe.
