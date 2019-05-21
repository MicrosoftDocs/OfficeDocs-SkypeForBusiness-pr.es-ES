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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de la implementación de la edición en la nube.
ms.openlocfilehash: 1049ec2f8f3b85c71c7b9203916b79764e9be161
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286726"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solución de problemas con la implementación de Cloud Connector
 
Solucionar problemas de la implementación de la edición en la nube.
  
En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas en los dos sentidos de la red telefónica conmutada (RTC), puede investigar el problema siguiendo las soluciones que se describen en este tema.
  
El conector de nube proporciona mecanismos integrados para resolver algunos problemas automáticamente. Un proceso de detección automática busca posibles problemas con los dispositivos de conexión en la nube y, si es posible, toma medidas correctivas para resolver esos problemas sin necesidad de que intervenga el administrador. El proceso de detección funciona de la siguiente manera:
  
- **Secuencia de detección:** El servicio de administración de conector de nube ejecuta un proceso cada 60 segundos para detectar si un dispositivo está desactivado. En la versión 2,0 y posteriores del conector de la nube, el proceso de detección usa el conmutador de CorpNet de Skype empresarial para establecer conexiones de PowerShell con las máquinas de los conectores de nube; en las versiones anteriores a 2,0, el proceso de detección usa el conmutador de administración del conector de nube.
    
    > [!NOTE]
    > Para que la recuperación automática se realice correctamente, debe haber conectividad de red entre el host y las máquinas virtuales a través del conmutador de red de hospedaje. Asegúrese de comprobar la conectividad de red para asegurarse de que la detección y recuperación automáticas pueda realizarse correctamente. 
  
- **Supervisión:** Los siguientes servicios se supervisan en la versión 2,0 y posteriores del conector de la nube:
    
  - Las máquinas virtuales no están conectadas a los conmutadores virtuales de Internet o de la organización del conector de nube
    
  - Las máquinas virtuales se encuentran en estado guardado o detenido
    
  - Servicios del servidor de administración central: réplica, maestra
    
  - Servicios del servidor de mediación: REPLICA, RTCSRV y MEDSVC
    
  - Servicios del servidor perimetral: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Las reglas de Firewall entrante están deshabilitadas para CS RTCSRV en el servidor perimetral, CS RTCMEDSRV en el servidor de mediación
    
    En el conector de nube versión 1.4.2, solo se supervisan los siguientes servicios:
    
  - Servicios del servidor de mediación: RTCSRV y MEDSVC
    
  - Servicio de servidor perimetral: RTCSRV
    
- **Proceso de recuperación:** Si algún servicio supervisado está desactivado, un dispositivo se marca y los servicios se detienen y marcan como manual hasta que se puedan resolver todos los problemas. Esto evitará que las llamadas se enruten a un dispositivo que pueda causar errores en las llamadas.
    
    El servicio de administración de conector de nube volverá a intentar la recuperación automática de la siguiente manera
    
  - El intervalo de reintento inicial es cada diez segundos, con un tiempo de intervalo máximo de una hora.
    
  - Para los tres primeros intentos de recuperación, el tiempo de intervalo es de 10 segundos. A partir del cuarto reintento, el intervalo de tiempo aumenta en dos veces el intervalo de tiempo anterior. Por ejemplo, el cuarto reintento se realizará en 20 segundos, el quinto de 40 segundos, y así sucesivamente. 
    
  - Cuando se alcanza el tiempo de intervalo máximo de una hora, los reintentos continuarán una vez cada hora.
    
  - Cuando la recuperación se realiza correctamente, el intervalo y los reintentos se establecen en sus valores iniciales.
    
  - Si el servicio de administración se reinicia, el intervalo y los recuentos de reintentos se restablecen a sus valores iniciales.
    
## <a name="troubleshooting"></a>Solución de problemas

A continuación se muestran algunas soluciones a los problemas más frecuentes:
  
- **Problema: la implementación presenta un error o deja de responder cuando se ejecutan los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o esta es incorrecta para la NIC externa, interna o de administración.**
    
    **Solución:** Este problema no se puede resolver automáticamente. No se pueden agregar NICs a las VMs mientras se ejecutan. Cierre y quite estas máquinas virtuales en Hyper-v Manager y, a continuación, ejecute los siguientes cmdlets:
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **Problema: después de instalar el servidor de Active Directory y el bosque, el servidor CMS o el servidor de mediación no se unen al dominio correctamente.**
    
    **Resolución:** para resolver este problema, lleve a cabo los siguientes pasos:
    
  - Inicie sesión en el servidor de Active Directory y compruebe que se haya creado el dominio correctamente.
    
  - Inicie sesión en el servidor CMS o de mediación, y compruebe en el NIC de red corporativa que se haya asignado una dirección IP válida y que estén configurados un DNS y una IP estática válidos como la dirección IP del servidor de AD.
    
  - Inicie sesión en el servidor CMS o de mediación y abra un símbolo del sistema. Asegúrese de poder hacer ping a la dirección IP y el FQDN del servidor de Active Directory. Si no puede, es posible que haya un conflicto con la dirección IP. Intente asignar una nueva IP para Active Directory y actualice en consecuencia el DNS en el servidor CMS o de mediación.
    
- **Problema: recibe el siguiente mensaje de error: "Remove-VMSwitch: error al quitar el conmutador Ethernet virtual. El conmutador virtual ' conmutador de administración del conector en la nube ' no se puede eliminar porque está siendo usado por máquinas virtuales en ejecución o asignado a grupos secundarios. "**
    
    **Solución:** El "conmutador de administración del conector de nube" no se eliminó después de la implementación. Si ha encontrado este error, vaya al administrador de Hyper-v y compruebe que aún no hay una máquina virtual aún conectada a ella. Si hay máquinas virtuales aún conectadas, desconéctate y elimina el conmutador de administración. Si el conmutador de administración aún no se puede eliminar, reinicie el servidor host e inténtelo de nuevo.
    
- **Problema: recibe el siguiente mensaje de error "no se pudo iniciar el servicio de RTCMRAUTH. Asegúrese de que el servicio no está deshabilitado.**
    
    > [!NOTE]
    > Este problema solo se aplica a versiones del conector de nube anteriores a la versión 1.4.2. 
  
    La imposibilidad de iniciar también puede deberse a que el servidor front-end se haya conmutado previamente por error (mediante una conmutación por error del equipo), en cuyo caso debería invocar una conmutación por recuperación (mediante una conmutación por recuperación del equipo).
    
    **Resolución:** este problema se produce en un servidor perimetral cuando dicho servidor no confía en el certificado de CA raíz o de CA intermedia, incluso cuando pueda importarse el certificado externo, pero la cadena de certificados se vea interrumpida. En esta situación, no puede iniciarse el servicio RTCMRAUTH o RTCSRV.
    
    Importe en el servidor perimetral el certificado de CA raíz y todos los certificados de CA intermedia de su certificado externo de forma manual y reinicie el servidor. Después de ver que se hayan iniciado los servicios RTCMRAUTH y RTCSRV en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:
    
  ```
  Switch-CcVersion
  ```

- 
    
    **Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows, y las llamadas a las que presta servicio el servidor están fallando.**
    
    **Resolución:** si ha implementado un entorno de alta disponibilidad, Microsoft proporciona un cmdlet que le ayudará a mover una máquina host (instancia de implementación) dentro o fuera de la topología actual cuando compruebe e instale actualizaciones de Windows de forma manual. Use los siguientes pasos para llevar a cabo esto:
    
1. En el servidor host, inicie una consola de PowerShell como administrador y después ejecute lo siguiente:
    
   ```
   Enter-CcUpdate
   ```

2. Compruebe si existen actualizaciones e instale las que estén disponibles.
    
3. En la consola de PowerShell, ejecute el siguiente cmdlet:
    
   ```
   Exit-CcUpdate
   ```

- 
    
    **Problema: cuando se realiza una llamada desde el cliente de Skype Empresarial con un número de RTC, la llamada no puede escalarse a conferencia invitando a otro número de RTC.**
    
    **Solución:** Para resolver este problema, vea [configurar la configuración del servidor de mediación híbrida en línea](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar un servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarse de que la característica o el rol recién instalados se actualicen automáticamente, active Windows Update en el Panel de control".**
    
    **Solución:** Inicie una sesión de PowerShell remoto de inquilino con credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ de su sitio:
    
  ```
  Get-CsHybridPSTNSite
  ```

    Si _EnableAutoUpdate_ se establece en **true**, puede pasar por alto este mensaje de advertencia sin riesgos porque el servicio CCEManagement se encargará de descargar e instalar las actualizaciones de Windows tanto para las máquinas virtuales como para el servidor host. Si _EnableAutoUpdate_ se establece en **false**, ejecute el cmdlet siguiente para establecerla en **true**.
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Puede también comprobar si existen actualizaciones e instalarlas manualmente. Consulte la siguiente sección.
    
- **Problema: recibe un mensaje de error: no se puede registrar el dispositivo porque el nombre \<\> de\> usuario \<y\> la \<configuración actuales del siteName \<o ApplianceName o de la dirección IP del servidor de mediación \> conflictos con dispositivos existentes. Quitar el dispositivo de conflicto o actualizar la información de entrada/configuración y vuelva a registrarse. ' cuando se ejecute Register-CcAppliance para registrar el equipo actual en Internet.**
    
    **Solución:** Los valores para \<la\>dirección \<\> IP del servidor\> de \<mediación de FQDN y mediación de ApplianceName debe ser único y solo se pueden usar para el registro de un dispositivo. De forma predeterminada \<,\> ApplianceName viene del nombre de host. \<FQDN\> del servidor de \<mediación dirección\> IP del servidor de mediación definida en el archivo ini de configuración.
    
    Por ejemplo, se usa (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para el registro en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), experimentará el conflicto.
    
    En primer lugar, verifica el archivo CloudConnector. ini en la sección ApplianceRoot Directory. \<Obtendrá los valores de\>dirección \<\> IP del servidor\> de \<nombres, FQDN y servidor de mediación en el archivo. \<ApplianceName\> es el nombre del servidor host.
    
    En segundo lugar, inicie PowerShell remoto de inquilino con sus credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar los dispositivos registrados.
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    Después de identificar cualquier conflicto, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problema: el cmdlet Get-CcRunningVersion devuelve un valor vacío si hay un dispositivo implementado ejecutándose en el host.**
    
  **Solución:** Esto puede ocurrir al actualizar de 1.3.4 o 1.3.8 a 1.4.1. Después de instalar la versión 1.4.1 con el. msi, debe ejecutar `Register-CcAppliance` antes de ejecutar cualquier otro cmdlet. `Register-CcAppliance`migrará el archivo Module. ini de%UserProfile%\CloudConnector a%ProgramData%\CloudConnector. Si lo ha perdido, se creará un nuevo Module. ini en la carpeta%ProgramData%\CloudConnector y reemplazará la información de la versión de ejecución o de copia de seguridad para 1.3.4 o 1.3.8.
    
  Compare los archivos module.ini files en la carpeta %perfilusuario%\CloudConnector y %ProgramData%\CloudConnector. Si hay diferencias, elimine el archivo Module. ini en%ProgramData%\CloudConnector y vuelva `Register-CcAppliance`a ejecutar. También puede modificar el archivo de forma manual para la versión correcta de ejecución y copia de seguridad.
    
- **Problema: después de ejecutar el cmdlet switch-CcVersion para cambiar a una versión anterior que es diferente de la versión actual del script, no hay compatibilidad de alta disponibilidad para esta versión anterior.**
    
    **Solución:** Por ejemplo, ha actualizado de 1.4.1 a 1.4.2. La versión actual de la secuencia de comandos, que se `Get-CcVersion`puede determinar al ejecutarse, y la versión en ejecución, `Get-CcRunningVersion` que se puede determinar mediante la ejecución, son 1.4.2. En este momento, si se ejecuta `Switch-CcVersion` para cambiar la versión de ejecución a 1.4.1, no habrá compatibilidad de alta disponibilidad para esta versión antigua.
    
    Para obtener compatibilidad total con alta disponibilidad, vuelva a 1.4.2 para que la versión en ejecución y la versión del script sean las mismas. Si está experimentando problemas con su implementación de 1.4.2, desinstálela y vuelva a instalarla tan pronto como sea posible.
    
- **Problema: los certificados de una entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**
    
    **Resolución:** los certificados de la entidad de certificación de Skype Empresarial son válidos durante cinco años. Los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral son válidos durante dos años.
    
    > [!NOTE]
    > En el conector de nube versión 2,0 y posteriores, el cmdlet Renew-CcServerCertificate ha cambiado a Update-CcServerCertificate y el cmdlet Renew-CcCACertificate ha cambiado a Update-CcCACertificate. 
  
    Si los certificados internos emitidos para el almacén central de administración, el servidor de mediación y el servidor perimetral están cerca de la expiración o están comprometidos, ejecute el cmdlet Renew-CcServerCertificate o Update-CcServerCertificate para renovar los certificados.
    
    Si los certificados de la entidad de certificación están cercanos, ejecute el cmdlet Renew-CcCACertificate o Update-CcCACertificate para renovar los certificados.
    
    **Si los certificados de la entidad emisora de certificados se ven comprometidos y solo hay un dispositivo en el sitio,** realice los siguientes pasos:
    
1. Ejecute el cmdlet Enter-CcUpdate para depurar los servicios y poner el dispositivo en modo de mantenimiento.
   
   ```
   Enter-CcUpdate
   ```
   
2. Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de la entidad de certificación y todos los certificados internos del servidor:
    
    Para las versiones de conector de nube antes 2,0:
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    O para el conector de nube versión 2,0 y posteriores:
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado en las puertas de enlace RTC. Es posible que también se le solicite volver a emitir el certificado en la puerta de enlace.

   ```
   Export-CcRootCertificate
   ```

4. Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.

   ```
   Exit-CcUpdate
   ```


    **Si los certificados de la entidad emisora de certificados se ven comprometidos y hay varios dispositivos en el sitio,** realice los siguientes pasos secuenciales en cada dispositivo del sitio.
    
    Microsoft recomienda que realice estos pasos durante los períodos de uso no máximo.
    
1. En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar los archivos de copia de seguridad de \<la\> entidad emisora en el directorio SiteRoot.

     ```
     Remove-CcCertificationAuthorityFile
     ```
    
2. Ejecute el cmdlet Enter-CcUpdate para drenar servicios y poner cada dispositivo en modo de mantenimiento.

     ```
     Enter-CcUpdate
     ```
    
3. En el primer dispositivo, ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor interno:
    
     Para las versiones de conector de nube antes 2,0:
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     O para el conector de nube versión 2,0 y posteriores:
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. En el primer dispositivo, ejecute el cmdlet siguiente para realizar la copia de seguridad de los \<archivos\> de CA en la carpeta SiteRoot.
    
     ```
     Backup-CcCertificationAuthority
     ```
   
5. En todos los demás dispositivos del mismo sitio, ejecute los siguientes comandos para consumir los archivos de copia de seguridad de la entidad emisora, de modo que todos los dispositivos usen el mismo certificado raíz y, a continuación, solicite certificados nuevos. 
   
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo del sitio y, a continuación, instale el certificado exportado en las puertas de enlace RTC. Es posible que también se le solicite volver a emitir el certificado en la puerta de enlace.
  
     ```
     Export-CcRootCertificate
     ```
     
7. Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento. 

     ```
     Exit-CcUpdate
     ```
    
    
- **Problema: recibe el siguiente mensaje de error en el registro del servicio de administración del conector de nube, "C:\Archivos de Files\Skype para Business Cloud Connector Edition\ManagementService\CceManagementService.log": error de CceService: excepción inesperada cuando informar del estado a conectado: System. Management. Automation. CmdletInvocationException: error de inicio de \<sesión para el\>administrador de inquilinos global de usuario. Cree un nuevo objeto de credencial, asegurándose de que ha usado el nombre de usuario y la contraseña correctos. ---\>**
    
    **Solución:** Las credenciales de administrador de inquilinos globales de Office 365 se han cambiado desde que se registró el equipo del conector en la nube. Para actualizar las credenciales almacenadas de forma local en el dispositivo de conector de nube, ejecute lo siguiente de administrador de PowerShell en el dispositivo de hospedaje:
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: después de cambiar la contraseña de la cuenta de servidor host que usó para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString: clave no válida para usarla en el estado especificado". en%ProgramFiles%\Skype para Business Cloud Connector Edition\ManagementService\CceManagementService.log o al ejecutar el cmdlet Get-CcCredential.**
    
    **Solución:** Todas las credenciales del conector de nube se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Cuando se modifica la contraseña en el servidor host, tendrá que actualizar las credenciales que hay almacenadas localmente.
    
    **Si ejecuta la versión 1.4.2 de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector mediante estos pasos:
    
  1. Reinicie el servidor host.
    
  2. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  3. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas que siguen a la descripción. Introduzca las mismas contraseñas que usó antes para la implementación de Cloud Connector.
    
     **Si está ejecutando Cloud Connector versión 2,0 o posterior,** regenere todas las contraseñas de conector de nube siguiendo estos pasos:
    
  4. Reinicie el servidor host.
    
  5. Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  6. Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas que siguen a la descripción. 
    
     Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector, use la contraseña de VMAdmin para la contraseña de CceService cuando se le solicite. Introduzca la misma contraseña que usó antes para la implementación de Cloud Connector de todas las otras cuentas.
    
     Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector y las contraseñas de DomainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:
    
  7. Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:
    
  8. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
  9. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.
    
     Si el archivo de contraseñas almacenadas en caché se generó con la versión 2,0 o posterior del conector en la nube, de forma predeterminada, VmAdmin y ID. Si ha cambiado las contraseñas de DomainAdmin y VMAdmin, debe realizar los siguientes pasos:
    
  10. Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:
    
       1. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
       2. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.
    
  11. Ejecute Set-CcCredential -AccountType VmAdmin como sigue:
    
       1. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
       2. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin que usó antes.  
    
- **Problema: con el conector de nube versión 2,1 y posteriores, cuando se ejecuta Register-CcAppliance u otros cmdlets en el dispositivo, recibe un mensaje de error como: "para cada objeto: no se puede encontrar la propiedad ' Common ' en este objeto. Compruebe que la propiedad existe. En C:\Archivos de Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Car: 14 "**
    
    **Solución:** El conector para la nube 2,1 y versiones posteriores requieren .NET Framework 4.6.1 o posterior. Actualiza .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelve a ejecutar el cmdlet (s).

- **Problema: con Cloud Connector Edition 2,1, cuando se ejecuta install-CcAppliance, recibe un mensaje de error como: "error al instalar una nueva instancia con error: no se puede establecer" State "porque solo se pueden usar cadenas como valores para establecer las propiedades de XmlNode"**

   **Solución:** En Cloudconnector. ini, en la sección [Common], agregue la configuración "State" como se muestra a continuación: CountryCode = Estados Unidos = WA City = Redmond

   No es obligatorio que la línea "State" tenga valor; sin embargo, la línea "State" no se puede quitar del archivo Cloudconnector. ini.

- **Problema: recibe el siguiente mensaje de error "dimount-WindowsImage: dimount-WindowsImage. Código de error = 0xc1550115 "al instalar o actualizar Cloud Connector Edition.**
    
    **Solución:** Inicie una consola de PowerShell como administrador, ejecute "DISM-Cleanup-Wim" ". De esta forma, se limpiarán todas las imágenes con problemas. Ejecute install-CcAppliance de nuevo o espere a que los bits se actualicen automáticamente.
    
- **Problema: no se puede implementar el primer dispositivo del conector de nube en un entorno de alta disponibilidad**
    
    **Solución:** Los pasos que realice dependerán del motivo por el que se produjo el error de implementación:
    
  - Si se produce un error en el primer dispositivo del conector de nube y no puede determinar la causa del error, debe instalar el dispositivo de nuevo hasta que la implementación sea correcta y, a continuación, instalar los otros dispositivos.
    
  - Si el primer equipo con el conector de nube falla con un problema leve, como un problema de certificado externo, es posible que pueda solucionar el problema sin volver a instalar el dispositivo. Después, puede usar PowerShell remoto de inquilino para marcar la implementación como correcta de la siguiente manera. (También puede usar los siguientes pasos si la primera implementación se realizó correctamente, pero, por algún motivo, el conector de nube no puede informar de la implementación como un éxito).
    
  - Para obtener la identidad (GUID) del primer dispositivo de conector de nube, ejecute el cmdlet Get-CsHybridPSTNAppliance.
    
  - Para marcar el dispositivo como implementado correctamente, ejecute Set-CsCceApplianceDeploymentStatus de la siguiente manera:
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problema: debe comprobar si existen actualizaciones de Windows e instalarlas manualmente en el servidor host o las máquinas virtuales.**
    
   **Resolución:** recomendamos que aproveche las actualizaciones automatizadas del sistema operativo proporcionada por Skype Empresarial Cloud Connector Edition. Después de que se registre un dispositivo para administración en línea y se habilite la actualización automática del sistema operativo, el servidor host y las máquinas virtuales automáticamente comprobarán si existen actualizaciones de Windows y las instalarán de acuerdo con la configuración de la ventana de la hora de actualización del sistema operativo.
    
   Si tiene que comprobar si existen actualizaciones de Windows e instalarlas manualmente, siga los pasos provistos en esta sección que se apliquen a su tipo de implementación. Debe planificar y actualizar tanto el servidor host como las máquinas virtuales que estén ejecutándose en él al mismo tiempo a fin de minimizar el tiempo de inactividad necesario para las actualizaciones.
    
   Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones para los servidores de Cloud Connector. Solo tiene que configurar la actualización de Windows para que **no** se instale automáticamente.
    
   Para obtener información sobre cómo actualizar manualmente su implementación de Cloud Connector, consulte la siguiente sección.
    
- **Problema: cuando el conector de nube se actualiza a una nueva compilación, los cmdlets de conector de nube no se actualizan.** Esto sucede a veces si se deja abierta una ventana de PowerShell cuando se produce la actualización automática.
    
  **Solución:** Para cargar los cmdlets actualizados, puede realizar cualquiera de los pasos siguientes:
    
   - Cierre PowerShell en el dispositivo de conector de nube y, a continuación, vuelva a abrir PowerShell.
    
     - También puede ejecutar Import-Module CloudConnector-Force. 
 
-   **Problema: "el término ' Stop-CsWindowsService ' no se reconoce como el nombre de un cmdlet, una función, un archivo de script o un programa ejecutable". error al intentar ejecutar el cmdlet Enter-CcUpdate.**

    **Solución:** Elimine el archivo $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crea este archivo como una caché de cmdlets de los módulos que encuentra, de modo que no es necesario volver a analizar todos los módulos cada vez, ya que esto ralentizaría la velocidad. Lo más probable es que haya daños en los archivos que proporcionaron resultados engañosos a PowerShell cuando se leían de esa caché.

-   **Problema: "Import-Module CloudConnector" genera el error "Import-Module: el módulo especificado" CloudConnector "no se cargó porque no se encontró ningún archivo de módulo válido en ningún directorio de módulo"**

    **Solution**
    - Valide que el módulo CloudConnector exista bajo C:\Archivos de Files\WindowsPowerShell\Modules
    
    - Después de validar que el módulo CloudConnector existe en esta ubicación, la variable de entorno PSModulePath que almacena la ruta de acceso a las ubicaciones de los módulos se puede cambiar:
    
     a. Cambio temporal: inicie PowerShell como administrador y ejecute el siguiente comando: $env:P SModulePath = $env:P SModulePath + ". C:\Archivos de Files\WindowsPowerShell\Modules\"
        
     b. Para que el cambio sea persistente, inicie PowerShell como administrador y ejecute los siguientes comandos, uno por uno: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Archivos de Files\WindowsPowerShell\Modules "," equipo ")

    
## <a name="install-windows-updates-manually"></a>Instalar actualizaciones de Windows manualmente

Si no quiere usar actualizaciones automáticas en su entorno, siga estos pasos para comprobar si existen actualizaciones de Windows y aplicarlas manualmente. Puede ser necesario reiniciar el servidor para la comprobación e instalación de actualizaciones de Windows. Cuando se reinicia un servidor host, los usuarios no podrán usar el conector de nube para realizar o recibir llamadas. Puede comprobar si existen actualizaciones e instalarlas de forma manual a fin de controlar en qué momento deben producirse, y después reiniciar las máquinas según la necesidad durante los tiempos que usted elija para evitar interrupciones de los servicios.
  
Para comprobar manualmente si existen actualizaciones, conecte cada servidor host y abra el **Panel de control**. Seleccione **Windows Update System \>and Security**y, a continuación, administre las actualizaciones y los reinicios del servidor según corresponda para su entorno.
  
- Si existe solo un dispositivo en el sitio, conecte cada máquina virtual y abra el **Panel de control**. Seleccione **Windows Update System \>and Security**y, a continuación, configure las actualizaciones y los reinicios del servidor según corresponda.
    
- Si hay más de un dispositivo en el sitio, los usuarios no pueden acceder a la instancia que se actualiza y reinicia durante las actualizaciones. Estos se conectarán con otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype Empresarial se inicien en las máquinas virtuales después de completadas las actualizaciones. Para evitar cualquier posible interrupción en el servicio, puede quitar la instancia de HA mientras aplica las actualizaciones y restaurarla cuando se completen. Para ello, realice lo siguiente:
    
1. En cada servidor host, abra una consola de PowerShell como administrador.
    
2. Quite la instancia de HA con el siguiente cmdlet:
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    Siga los pasos para una sola instancia para aplicar manualmente las actualizaciones y reinicie la máquina virtual.
    
4. Vuelva a configurar la instancia en HA con el siguiente cmdlet:
    
   ```
   Exit-CcUpdate
   ```

Para implementaciones de varios sitios, siga los pasos destinados a un único sitio para cada sitio de la implementación aplicando las actualizaciones de a uno por vez.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Sugerencias al instalar el software antivirus en el equipo host del conector de nube

Si necesita instalar software antivirus en el equipo host del conector de nube, debe agregar las siguientes exclusiones:
  
- Directorio local del equipo en cada equipo.
    
- Directorio de sitios remotos en cada equipo.
    
- El directorio de sitios locales del equipo hospeda la carpeta raíz del sitio compartido.
    
- %ProgramFiles%\Skype para Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- El proceso Microsoft. RTC. CCE. ManagementService. exe.
