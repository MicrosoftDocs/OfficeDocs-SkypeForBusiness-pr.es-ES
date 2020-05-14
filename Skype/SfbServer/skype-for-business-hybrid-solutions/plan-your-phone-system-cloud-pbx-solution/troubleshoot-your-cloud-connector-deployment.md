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
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220230"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solución de problemas con la implementación de Cloud Connector
 
Solucionar problemas de la implementación de Cloud Connector Edition.
  
En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas a y desde la red telefónica conmutada (RTC), puede investigarlo siguiendo las soluciones que se describen en este tema.
  
Cloud Connector proporciona mecanismos integrados para resolver algunos problemas automáticamente. Un proceso de detección automática busca posibles problemas con los dispositivos de Cloud Connector y, si es posible, emprende acciones correctivas para resolver esos problemas sin necesidad de que intervenga el administrador. El proceso de detección funciona de la siguiente manera:
  
- **Secuencia de detección:** El servicio de administración de Cloud Connector ejecuta un proceso cada 60 segundos para detectar si un dispositivo está inactivo. En la versión 2,0 de Cloud Connector y versiones posteriores, el proceso de detección usa el conmutador de red corporativa de Skype empresarial para realizar conexiones de PowerShell a los equipos de Cloud Connector; para las versiones anteriores a 2,0, el proceso de detección usa el conmutador de administración de Cloud Connector.
    
    > [!NOTE]
    > Para que la recuperación automática se realice correctamente, debe haber conectividad de red entre el host y las máquinas virtuales a través del conmutador de red de host. Asegúrese de comprobar la conectividad de red para asegurarse de que la detección y la recuperación automáticas se puedan realizar correctamente. 
  
- **Supervisión:** Los siguientes servicios se supervisan en la versión 2,0 de Cloud Connector y versiones posteriores:
    
  - Las máquinas virtuales no están conectadas a los conmutadores virtuales corporativos o de Internet de Cloud Connector
    
  - Las máquinas virtuales se encuentran en estado guardado o detenido
    
  - Servicios del servidor de administración central: réplica, patrón
    
  - Servicios del servidor de mediación: REPLICA, RTCSRV y MEDSVC
    
  - Servicios del servidor perimetral: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Las reglas de Firewall de entrada están deshabilitadas para CS RTCSRV en el servidor perimetral, CS RTCMEDSRV en el servidor de mediación
    
    En la versión 1.4.2 de Cloud Connector, solo se supervisan los siguientes servicios:
    
  - Servicios del servidor de mediación: RTCSRV y MEDSVC
    
  - Servicio de servidor perimetral: RTCSRV
    
- **Proceso de recuperación:** Si alguno de los servicios supervisados está inactivo, se marca un dispositivo y los servicios se detienen y se marcan como manuales hasta que se puedan resolver todos los problemas. Esto impedirá que las llamadas se enruten a un dispositivo que puede causar errores de llamada.
    
    El servicio de administración de Cloud Connector volverá a intentar la recuperación automática de la siguiente manera
    
  - El intervalo de reintento inicial es cada diez segundos con un intervalo de tiempo máximo de una hora.
    
  - Para los tres primeros intentos de recuperación, el tiempo de intervalo es de 10 segundos. A partir del cuarto reintento, el tiempo del intervalo aumenta en dos veces el tiempo del intervalo anterior. Por ejemplo, el cuarto reintento se producirá en 20 segundos, el quinto en 40 segundos, y así sucesivamente. 
    
  - Cuando se alcanza el tiempo máximo de intervalo de una hora, los reintentos continuarán una vez por hora.
    
  - Cuando la recuperación se realiza correctamente, el intervalo y los contadores de reintentos se establecen en sus valores iniciales.
    
  - Si se reinicia el servicio de administración, el intervalo y los números de reintentos se restablecen a sus valores iniciales.
    
## <a name="troubleshooting"></a>Solución de problemas

A continuación se muestran soluciones a los problemas más comunes:
  
- **Problema: se produce un error en la implementación o deja de responder cuando se ejecutan los scripts de implementación. Después de iniciar sesión en cada máquina virtual, la dirección IP falta o es incorrecta para la NIC de administración/interno/externo.**
    
    **Solución:** Este problema no se puede resolver automáticamente. Las NICs no se pueden agregar a las máquinas virtuales mientras se ejecutan. Cierre y quite estas máquinas virtuales en el administrador de Hyper-v y, a continuación, ejecute los siguientes cmdlets:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problema: después de instalar el servidor y el bosque de Active Directory, el servidor CMS o el servidor de mediación no se unen al dominio correctamente.**
    
    **Solución:** Para resolver este problema, siga estos pasos:
    
  - Inicie sesión en el servidor de Active Directory y compruebe que el dominio se haya creado correctamente.
    
  - Inicie sesión en el servidor CMS o de mediación y compruebe que en la NIC de la red corporativa se ha asignado una dirección IP válida y que la dirección IP estática válida y el DNS están configurados como la dirección IP del servidor de AD.
    
  - Inicie sesión en el servidor CMS o de mediación y abra un símbolo del sistema. Asegúrese de que puede hacer ping en el FQDN y la dirección IP del servidor de Active Directory. Si no puede, es posible que haya un conflicto de direcciones IP. Intente asignar una nueva IP para Active Directory y actualice DNS en el servidor CMS o de mediación en consecuencia.
    
- **Problema: recibe el mensaje de error siguiente: "Remove-VMSwitch: error al quitar el conmutador Ethernet virtual. El conmutador virtual "conmutador de administración del conector de nube" no se puede eliminar porque lo están usando máquinas virtuales en ejecución o se han asignado a grupos secundarios ".**
    
    **Solución:** El "conmutador de administración del conector de nube" no se eliminó tras la implementación. Si ha encontrado este error, vaya a administrador de Hyper-v y compruebe que aún no hay una máquina virtual todavía conectada a ella. Si hay máquinas virtuales todavía conectadas, elimínelas y elimine el conmutador de administración. Si sigue sin poder eliminar el conmutador de administración, reinicie el servidor host y vuelva a intentarlo.
    
- **Problema: recibe el mensaje de error siguiente: "no se pudo iniciar el servicio RTCMRAUTH. Asegúrese de que el servicio no está deshabilitado. "**
    
    > [!NOTE]
    > Este problema solo se aplica a las versiones de Cloud Connector anteriores a 1.4.2. 
  
    El error de inicio también podría deberse a que el servidor front-end se conmute previamente por error (con la conmutación por error del equipo). Si es así, invocar conmutación por recuperación (con conmutación por recuperación del equipo).
    
    **Solución:** Este problema se produce en un servidor perimetral cuando el servidor perimetral no confía en el certificado de CA raíz o en el certificado de CA intermedio. Incluso si el certificado externo se puede importar pero la cadena de certificados está dañada. En esta condición, el servicio RTCMRAUTH o RTCSRV no puede iniciarse.
    
    Importe manualmente el certificado de CA raíz y todos los certificados de CA intermedios del certificado externo en el servidor perimetral y, a continuación, reinicie el servidor perimetral. Después de ver los servicios RTCMRAUTH y RTCSRV iniciados en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows y las llamadas a las que presta servicio el servidor están fallando.**
    
    **Solución:** Si ha implementado un entorno de alta disponibilidad, Microsoft proporciona un cmdlet para ayudar a mover un equipo host (instancia de implementación) hacia dentro o fuera de la topología actual al comprobar e instalar manualmente Windows Update. Siga estos pasos para hacerlo:
    
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
    
    **Problema: cuando se realiza una llamada desde un cliente de Skype empresarial con un número de RTC, la llamada no se puede escalar a una conferencia invitando a otro número de RTC.**
    
    **Solución:** Para resolver este problema, vea [Configure online Hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar el servidor de Active Directory: "la actualización automática de Windows no está habilitada. Para asegurarse de que el rol o la característica recién instalados se actualizan automáticamente, Active Windows Update.**
    
    **Solución:** Inicie una sesión remota de PowerShell de inquilino con credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ del sitio:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Si _EnableAutoUpdate_ se establece en **true**, puede pasar por alto este mensaje de advertencia sin ningún problema porque el servicio CCEManagement va a controlar la descarga e instalación de las actualizaciones de Windows tanto para las máquinas virtuales como para el servidor host. Si _EnableAutoUpdate_ se establece en **false**, ejecute el siguiente cmdlet para establecerlo en **true**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Como alternativa, puede buscar e instalar actualizaciones manualmente. Vea la sección siguiente.
    
- **Problema: recibe un mensaje de error que indica que no se puede registrar el dispositivo porque el nombre del sitio de entrada/configuración actual o la dirección IP del servidor de \< \> \< \> \< \> \< mediación ApplianceName \> conflictos con los dispositivos existentes. Quitar el dispositivo de conflicto o actualizar la información de entrada o configuración y volver a registrarse. ' cuando se ejecute Register-CcAppliance para registrar el dispositivo actual en línea.**
    
    **Solución:** Los valores para el \< ApplianceName \> , el FQDN del servidor de \< mediación \> y la \< dirección IP del servidor de mediación \> deben ser únicos y solo se usan para el registro de un dispositivo. De forma predeterminada, \< ApplianceName \> proviene del nombre de host. \<Servidor de mediación FQDN \> y \< dirección IP \> del servidor de mediación definida en el archivo ini de configuración.
    
    Por ejemplo, usar (ApplianceName = MyserverNew, Mediation Server FQDN = ms. contoso. com, Mediation Server IP address = 10.10.10.10) para registrarse en SiteName =, pero si hay un dispositivo registrado (ApplianceName = mi servidor, Mediation Server FQDN = ms. contoso. com, Mediation Server address = 10.10.10.10), tendrá el conflicto.
    
    En primer lugar, compruebe el archivo CloudConnector. ini en la sección ApplianceRoot del directorio. Obtendrá \< \> \< \> \< los valores de la dirección IP del servidor de mediación y el FQDN del servidor de mediación \> en el archivo. \<ApplianceName \> es el nombre del servidor host.
    
    Segundo, inicie el PowerShell remoto del inquilino con sus credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar los dispositivos registrados.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Después de identificar los conflictos, puede actualizar el archivo CloudConnector. ini con información que coincida con el dispositivo registrado, o bien anular el registro del dispositivo existente para resolver los conflictos.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: el cmdlet Get-CcRunningVersion devuelve un valor vacío si hay un dispositivo implementado en ejecución en el host.**
    
  **Solución:** Esto puede ocurrir cuando se actualiza de 1.3.4 o de 1.3.8 a 1.4.1. Después de instalar la versión 1.4.1 con el. msi, debe ejecutar `Register-CcAppliance` antes de ejecutar cualquier otro cmdlet. `Register-CcAppliance`migrará el archivo Module. ini de%UserProfile%\CloudConnector a%ProgramData%\CloudConnector. Si lo perdió, se creará un nuevo Module. ini en la carpeta%ProgramData%\CloudConnector y se reemplazará la información de la versión de ejecución/copia de seguridad para 1.3.4 o 1.3.8.
    
  Compare los archivos Module. ini de la carpeta%UserProfile%\CloudConnector y%ProgramData%\CloudConnector. Si hay diferencias, elimine el archivo Module. ini en%ProgramData%\CloudConnector y vuelva a ejecutar `Register-CcAppliance` . También puede modificar el archivo manualmente a la versión correcta de ejecución y copia de seguridad.
    
- **Problema: después de ejecutar el cmdlet switch-CcVersion para cambiar a una versión anterior que sea diferente de la versión de script actual, no hay compatibilidad de alta disponibilidad para esta versión anterior.**
    
    **Solución:** Por ejemplo, ha actualizado de 1.4.1 a 1.4.2. La versión de script actual, que se puede determinar mediante `Get-CcVersion` la ejecución, y la versión en ejecución, que se puede determinar mediante la ejecución, `Get-CcRunningVersion` son las dos 1.4.2. En este momento, si ejecuta `Switch-CcVersion` para cambiar la versión en marcha a la versión 1.4.1, no habrá compatibilidad con alta disponibilidad para esta versión anterior.
    
    Para obtener compatibilidad total con alta disponibilidad, vuelva a 1.4.2, de modo que la versión en ejecución y la versión de script sean las mismas. Si tiene problemas con la implementación de 1.4.2, desinstálelo y vuelva a instalarlo tan pronto como sea posible.
    
- **Problema: los certificados de la entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**
    
    **Solución:** Los certificados de la entidad de certificación de Skype empresarial son válidos durante cinco años. Los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral son válidos durante dos años.
    
    > [!NOTE]
    > En la versión 2,0 de Cloud Connector y versiones posteriores, el cmdlet Renew-CcServerCertificate ha cambiado a Update-CcServerCertificate y el cmdlet Renew-CcCACertificate ha cambiado a Update-CcCACertificate. 
  
    Si los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro, ejecute el cmdlet Renew-CcServerCertificate o Update-CcServerCertificate para renovar los certificados.
    
    Si los certificados de la entidad de certificación están a punto de expirar, ejecute el cmdlet Renew-CcCACertificate o Update-CcCACertificate para renovar los certificados.
    
    **Si los certificados de la entidad de certificación están en peligro y solo hay un dispositivo en el sitio, lleve a** cabo los siguientes pasos:
    
1. Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner el dispositivo en modo de mantenimiento.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:
    
    Para las versiones de Cloud Connector antes del 2,0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    O para Cloud Connector Release 2,0 y versiones posteriores:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado en sus puertas de enlace RTC. Es posible que también deba volver a emitir el certificado en la puerta de enlace.

   ```powershell
   Export-CcRootCertificate
   ```

4. Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.

   ```powershell
   Exit-CcUpdate
   ```


    **Si los certificados de la entidad de certificación están en peligro y hay varios dispositivos en el sitio,** lleve a cabo los siguientes pasos secuenciales en cada dispositivo del sitio.
    
    Microsoft recomienda que realice estos pasos durante los períodos de uso no máximos.
    
1. En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar los archivos de copia de seguridad de la entidad de certificación en el \< \> directorio SiteRoot

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner cada dispositivo en modo de mantenimiento.

     ```powershell
     Enter-CcUpdate
     ```
    
3. En el primer dispositivo, ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:
    
     Para las versiones de Cloud Connector antes del 2,0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     O para Cloud Connector Release 2,0 y versiones posteriores:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. En el primer dispositivo, ejecute el siguiente cmdlet para realizar una copia de seguridad de los archivos de CA en la \< \> carpeta SiteRoot
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. En el resto de los dispositivos del mismo sitio, ejecute los comandos siguientes para consumir los archivos de copia de seguridad de la entidad de certificación, de modo que todos los dispositivos usen el mismo certificado raíz y, a continuación, solicite nuevos certificados. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo del sitio y, a continuación, instale el certificado exportado en sus puertas de enlace RTC. Es posible que también deba volver a emitir el certificado en la puerta de enlace.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problema: recibe el siguiente mensaje de error en el registro del servicio de administración de Cloud Connector, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService error: 0: excepción inesperada al notificar el estado a online: System. Management. Automation. CmdletInvocationException: error de inicio de sesión para el \< Administrador de inquilinos global de usuario \> . Cree un nuevo objeto Credential, asegurándose de que ha usado el nombre de usuario y la contraseña correctos. ---\>**
    
    **Solución:** Se han cambiado las credenciales globales de administrador de inquilinos de Microsoft 365 u Office 365 desde que se registró el dispositivo de Cloud Connector. Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, ejecute lo siguiente desde el administrador de PowerShell en el dispositivo de host:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: después de cambiar la contraseña de la cuenta del servidor host usada para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString: clave no válida para usarla en el estado especificado" en%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o mientras ejecutamos el cmdlet Get-CcCredential.**
    
    **Solución:** Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ". Cuando cambie la contraseña en el servidor host, tendrá que actualizar las credenciales almacenadas localmente.
    
    **Si ejecuta la versión 1.4.2 de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector; para ello, siga estos pasos:
    
  1. Reinicie el servidor host.
    
  2. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".
    
  3. Inicie una consola de PowerShell como administrador y, después, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas después de la descripción. Escriba las mismas contraseñas que especificó antes para la implementación de Cloud Connector.
    
     **Si ejecuta la versión 2,0 o posterior de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector; para ello, siga estos pasos:
    
  4. Reinicie el servidor host.
    
  5. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".
    
  6. Inicie una consola de PowerShell como administrador y, después, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas después de la descripción. 
    
     Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector, use la contraseña VMAdmin para la contraseña CceService cuando se le solicite. Escriba la misma contraseña que escribió antes para la implementación de Cloud Connector en todas las demás cuentas.
    
     Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector y las contraseñas del usuario e VMAdmin son diferentes, debe realizar los siguientes pasos:
    
  7. Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:
    
  8. Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.
    
  9. Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña para la contraseña de la cuenta de usuario que usó antes.
    
     Si el archivo de contraseñas almacenadas en caché se generó con la versión 2,0 de Cloud Connector o una versión posterior, de forma predeterminada, VmAdmin y el ID detor usan la misma contraseña que CceService. Si ha cambiado las contraseñas del usuario y el VMAdmin, debe realizar los siguientes pasos:
    
  10. Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:
    
       1. Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService
    
       2. Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña para la contraseña de la cuenta de usuario que usó antes.
    
  11. Ejecute Set-CcCredential-AccountType VmAdmin de la siguiente manera:
    
       1. Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService
    
       2. Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña para la contraseña de VmAdmin que usó antes. 
    
- **Problema: con Cloud Connector versión 2,1 y posteriores, cuando se ejecuta Register-CcAppliance u otros cmdlets en el dispositivo, recibe un mensaje de error como: "para cada objeto: no se encuentra la propiedad ' Common ' en este objeto. Compruebe que la propiedad existe. En C:\Archivos de Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**
    
    **Solución:** Cloud Connector 2,1 y versiones posteriores requieren .NET Framework 4.6.1 o posterior. Actualice .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar los cmdlets.

- **Problema: con Cloud Connector Edition 2,1, cuando se ejecuta install-CcAppliance, recibe un mensaje de error como el siguiente: "error al instalar una nueva instancia con error: no se puede establecer" State "porque solo se pueden usar cadenas como valores para establecer las propiedades de XmlNode"**

   **Solución:** En Cloudconnector. ini, en la sección [Common], agregue el config "State" como se muestra a continuación: CountryCode = US State = WA City = Redmond

   No es obligatorio que la línea "State" tenga valor, pero la línea "State" no se puede quitar del archivo Cloudconnector. ini.

- **Problema: recibe el siguiente mensaje de error "Dismount-WindowsImage: Dismount-WindowsImage failed. Código de error = 0xc1550115 "al instalar o actualizar Cloud Connector Edition.**
    
    **Solución:** Inicie una consola de PowerShell como administrador, ejecute "DISM-Cleanup-Wim" ". Esto hará que se limpien todas las imágenes con problemas. Vuelva a ejecutar install-CcAppliance o espere a que los bits se actualicen automáticamente.
    
- **Problema: se produce un error en la implementación del primer dispositivo de Cloud Connector en un entorno de alta disponibilidad**
    
    **Solución:** Los pasos que debe seguir dependen de la razón por la que se produjo el error en la implementación:
    
  - Si se produce un error en el primer dispositivo de Cloud Connector y no puede determinar el motivo del error, debe instalar el dispositivo de nuevo hasta que la implementación se haya realizado correctamente y, a continuación, instalar el resto de dispositivos.
    
  - Si se produce un error leve en el primer dispositivo de Cloud Connector, como un problema de certificado externo, es posible que pueda solucionar el problema sin volver a instalar el dispositivo. A continuación, puede usar PowerShell remoto de inquilino para marcar la implementación como correcta de la siguiente manera. (También puede seguir estos pasos si la primera implementación se realizó correctamente, pero, por algún motivo, Cloud Connector no puede informar de la implementación como correcta).
    
  - Para obtener la identidad (GUID) del primer dispositivo de Cloud Connector, ejecute el cmdlet Get-CsHybridPSTNAppliance.
    
  - Para marcar el dispositivo como implementado correctamente, ejecute Set-CsCceApplianceDeploymentStatus de la siguiente manera:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: debe comprobar e instalar las actualizaciones de Windows de forma manual en el servidor host o las máquinas virtuales.**
    
   **Solución:** Le recomendamos que aproveche las ventajas de las actualizaciones del sistema operativo automatizado que proporciona Skype empresarial Cloud Connector Edition. Una vez que se ha registrado un dispositivo para la administración en línea y la actualización automática del sistema operativo está habilitada, el servidor host y las máquinas virtuales comprobarán e instalarán automáticamente las actualizaciones de Windows según la configuración de la ventana de tiempo de actualización del sistema operativo.
    
   Si necesita buscar e instalar actualizaciones de Windows manualmente, siga los pasos de esta sección que se aplican a su tipo de implementación. Debe planear la actualización del servidor host y de las máquinas virtuales que se ejecutan al mismo tiempo para minimizar la cantidad de tiempo de inactividad necesario para las actualizaciones.
    
   Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones a los servidores de Cloud Connector. Solo Asegúrese de configurar la actualización de Windows para que **no** se instale automáticamente.
    
   Para obtener información sobre cómo actualizar manualmente la implementación de Cloud Connector, consulte la siguiente sección.
    
- **Problema: cuando Cloud Connector se actualiza a una nueva compilación, los cmdlets de Cloud Connector no se actualizan.** Esto ocurre a veces si se deja abierta una ventana de PowerShell cuando se produce la actualización automática.
    
  **Solución:** Para cargar los cmdlets actualizados, puede realizar cualquiera de los siguientes pasos:
    
   - Cierre PowerShell en el dispositivo de Cloud Connector y, a continuación, vuelva a abrir PowerShell.
    
     - O bien, puede ejecutar Import-Module CloudConnector-Force. 
 
-   **Problema: "el término ' Stop-CsWindowsService ' no se reconoce como nombre de un cmdlet, función, archivo de script o programa ejecutable". error al intentar ejecutar el cmdlet Enter-CcUpdate.**

    **Solución:** Elimine el archivo $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea este archivo como una memoria caché de cmdlets a partir de los módulos que encuentra para que no tenga que volver a analizar todos los módulos cada vez, ya que esto haría que las cosas se ralentizarían realmente. Lo más probable es que haya daños en los archivos que hayan proporcionado resultados engañosos a PowerShell cuando se leían de nuevo desde esa memoria caché.

-   **Problema: "Import-Module CloudConnector" genera el error "Import-Module: el módulo especificado" CloudConnector "no se cargó porque no se encontró ningún archivo de módulo válido en ningún directorio de módulo"**

    **Resolución:**
    - Compruebe que el módulo CloudConnector existe en c:\Program Files\WindowsPowerShell\Modules
    
    - Después de comprobar que el módulo CloudConnector existe en esta ubicación, se puede cambiar la variable de entorno PSModulePath que almacena la ruta de acceso a las ubicaciones de los módulos:
    
     a. Cambio temporal: inicie PowerShell como administrador y ejecute el comando siguiente: $env:P SModulePath = $env:P SModulePath + "; C:\Archivos de Files\WindowsPowerShell\Modules\"
        
     b. Para el cambio persistente, inicie PowerShell como administrador y ejecute los siguientes comandos, uno por uno: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Archivos de Files\WindowsPowerShell\Modules "," equipo ")

    
## <a name="install-windows-updates-manually"></a>Instalar actualizaciones de Windows de forma manual

Si no desea usar actualizaciones automáticas en su entorno, siga estos pasos para buscar y aplicar manualmente las actualizaciones de Windows. La comprobación e instalación de actualizaciones de Windows puede requerir el reinicio del servidor. Cuando se reinicia un servidor host, los usuarios no podrán usar Cloud Connector para realizar o recibir llamadas. Puede buscar e instalar actualizaciones manualmente para controlar cuándo se realizan las actualizaciones y, a continuación, reiniciar los equipos según sea necesario durante las horas que elija para evitar interrupciones en los servicios.
  
Para comprobar manualmente si hay actualizaciones, conéctese a cada servidor host y abra el **Panel de control**. Seleccione ** \> Windows Update System and Security**y, a continuación, administre las actualizaciones y los reinicios de servidor según corresponda para su entorno.
  
- Si solo hay un dispositivo en el sitio, conéctese a cada máquina virtual y abra el **Panel de control**. Seleccione ** \> Windows Update System and Security**y, a continuación, configure las actualizaciones y los reinicios de servidor según corresponda.
    
- Si hay más de un dispositivo en el sitio, los usuarios no pueden acceder a la instancia que se actualiza y reinicia durante las actualizaciones. Los usuarios se conectarán a otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype empresarial se inicien en las máquinas virtuales después de que se hayan completado las actualizaciones. Para evitar cualquier posible interrupción del servicio, puede quitar la instancia de HA al aplicar las actualizaciones y, a continuación, restaurarla cuando haya finalizado. Para ello:
    
1. En cada servidor host, abra una consola de PowerShell como administrador.
    
2. Quite la instancia de HA con el siguiente cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Siga los pasos para una única instancia para aplicar manualmente las actualizaciones y reiniciar la máquina virtual.
    
4. Vuelva a establecer la instancia en HA con el siguiente cmdlet:
    
   ```powershell
   Exit-CcUpdate
   ```

Para implementaciones de varios sitios, siga los pasos para un sitio único para cada sitio de la implementación y aplique las actualizaciones a un sitio cada vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Sugerencias al instalar software antivirus en el equipo host de Cloud Connector

Si necesita instalar software antivirus en el equipo host de Cloud Connector, debe agregar las siguientes exclusiones:
  
- Directorio local de la aplicación en cada máquina.
    
- Directorio de sitios remotos en cada máquina.
    
- Directorio de sitios local en el equipo hospeda la carpeta raíz del sitio compartido.
    
- %ProgramFiles%\Skype para Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- El proceso Microsoft. RTC. CCE. ManagementService. exe.
