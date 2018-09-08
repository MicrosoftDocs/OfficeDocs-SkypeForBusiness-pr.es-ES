---
title: Solución de problemas con la implementación de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solución de problemas de la implementación de nube conector Edition.
ms.openlocfilehash: 5d34cc78c7afa9a0d4e459e87d885c82b437bae0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882291"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Solución de problemas con la implementación de Cloud Connector
 
Solución de problemas de la implementación de nube conector Edition.
  
En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas en los dos sentidos de la red telefónica conmutada (RTC), puede investigar el problema siguiendo las soluciones que se describen en este tema.
  
En la nube conector proporciona mecanismos integrados para resolver algunos problemas de automáticamente. Un proceso de detección automática busca posibles problemas con los dispositivos de conector en la nube y, si es posible, realiza una acción correctiva para resolver estos problemas sin necesidad de intervención del administrador. El proceso de detección funciona de la siguiente manera:
  
- **Secuencia de detección:** El servicio de administración del conector en la nube ejecuta un proceso de cada 60 segundos para detectar si un dispositivo está inactivo. En el conector en la nube versión 2.0 y versiones posterior, el proceso de detección usa el Skype para modificador Corpnet empresarial para realizar conexiones de PowerShell para las máquinas de conector en la nube; para las versiones anteriores a 2.0, el proceso de detección usa el modificador de administración del conector de la nube.
    
    > [!NOTE]
    > Para que la recuperación automática se realice correctamente, debe haber conectividad de red entre el host y máquinas virtuales a través del conmutador de red de host. Asegúrese de comprobar la conectividad de red para asegurarse de que la detección automática y recuperación puede tener éxito. 
  
- **Supervisión:** Los siguientes servicios se supervisan en la nube Connector versión 2.0 y versiones posterior:
    
  - Las máquinas virtuales no están conectadas a la nube conector corporativo o modificadores virtuales de Internet
    
  - Las máquinas virtuales se encuentran en un estado detenido o guardado
    
  - Servicios de servidor de administración centrales: réplica, patrón
    
  - Servicios de servidor de mediación: réplica, RTCSRV y MEDSVC
    
  - Servicios de servidores perimetrales: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Las reglas están deshabilitadas para RTCSRV CS en servidor perimetral, CS RTCMEDSRV en el servidor de mediación de firewall de entrada
    
    En el conector en la nube versión 1.4.2, se supervisan únicamente los servicios siguientes:
    
  - Servicios de servidor de mediación: RTCSRV y MEDSVC
    
  - Servicio de servidor perimetral: RTCSRV
    
- **Proceso de recuperación:** Si todos los servicios supervisados están inactivos, un dispositivo se marca hacia abajo, y servicios se ha detenido y marcados manuales hasta que se pueden resolver todos los problemas. Esto evita que las llamadas de enrutamiento a un dispositivo que puede causar errores de llamadas.
    
    El servicio de administración del conector en la nube se volverá a intentar la recuperación automática de manera
    
  - El intervalo de reintento inicial es cada diez segundos con un tiempo de intervalo máximo de una hora.
    
  - Para los intentos de tres en primer lugar recuperación, el intervalo de tiempo es de 10 segundos. A partir del cuarto reintento, aumenta el intervalo de tiempo por dos veces el anterior intervalo de tiempo. Por ejemplo, el cuarto reintento se se producen en 20 segundos, la quinta en 40 segundos y así sucesivamente. 
    
  - Cuando se alcanza el intervalo máximo de tiempo de una hora, reintentos continuará una vez cada hora.
    
  - Cuando la recuperación es correcta, se establecen los recuentos de intervalo e inténtelo de nuevo en sus valores iniciales.
    
  - Si se reinicia el servicio de administración, se restablecen los recuentos de intervalo e inténtelo de nuevo a sus valores iniciales.
    
## <a name="troubleshooting"></a>Solución de problemas

A continuación se muestran soluciones para problemas habituales:
  
- **Problema: la implementación presenta un error o deja de responder cuando se ejecutan los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o esta es incorrecta para la NIC externa, interna o de administración.**
    
    **Resolución:** No se puede resolver este problema automáticamente. NIC no se puede agregar a las máquinas virtuales mientras se están ejecutando. Por favor, apagar y quitar estas máquinas virtuales en el Administrador de hyper-v, a continuación, ejecutar los cmdlets siguientes:
    
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
    
  - Inicie sesión en el servidor de mediación/CMS y abra un símbolo del sistema. Asegúrese de que puede hacer ping a la dirección IP y FQDN del servidor de directorio activo. Si no se puede, puede haber un conflicto de dirección IP. Intente asignar una nueva dirección IP para Active Directory y actualizar DNS en el servidor de mediación/CMS en consecuencia.
    
- **Problema: Recibe el siguiente mensaje de error "Remove-VMSwitch: error al eliminar la conmutación de Ethernet virtual. El modificador virtual 'Administración del conector en la nube cambiar' no pueden eliminarse porque está siendo utilizado mediante la ejecución de máquinas virtuales ni asignado a los grupos de servidores secundarios."**
    
    **Resolución:** No se ha eliminado el "conmutador de administración de conector en la nube" después de la implementación. Si presiona la tecla este error, vaya al administrador de Hyper-v y compruebe que haya no sigue una máquina virtual que sigue conectada a ella. Si hay máquinas virtuales que sigue conectadas, desconectar ellos y elimine el modificador de administración. Si aún no se puede eliminar el modificador de administración, reinicie el servidor de host e inténtelo de nuevo.
    
- **Problema: Recibe el mensaje de error siguiente, "servicio RTCMRAUTH no se pudo iniciar. Compruebe que el servicio no está deshabilitado."**
    
    > [!NOTE]
    > Este problema solo se aplica a las versiones del conector de nube anteriores a 1.4.2. 
  
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
    
    **Resolución:** Para resolver este problema, vea [Configure online híbrido configuración del servidor de mediación](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar un servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarse de que la característica o el rol recién instalados se actualicen automáticamente, active Windows Update en el Panel de control".**
    
    **Resolución:** Iniciar una sesión de PowerShell remoto inquilino con Skype para credenciales de administrador de inquilinos de negocio y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ del sitio:
    
  ```
  Get-CsHybridPSTNSite
  ```

    Si _EnableAutoUpdate_ está establecida en **True**, puede ignorar este mensaje de advertencia debido a que el servicio CCEManagement controlará la descarga e instalación de actualizaciones de Windows para las máquinas virtuales y el servidor host. Si _EnableAutoUpdate_ está establecida en **False**, ejecute siguiente cmdlet para establecer en **True**.
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Puede también comprobar si existen actualizaciones e instalarlas manualmente. Consulte la siguiente sección.
    
- **Problema: Recibe un mensaje de error: no se puede registrar el dispositivo debido a que la configuración actual de entrada/ \<SiteName\> o \<ApplianceName\> o \<el FQDN del servidor de mediación\> o \<dirección IP de servidor de mediación \> entra en conflicto con appliance(s) existente. Quitar dispositivo de conflicto o actualizar la información de configuración de entrada y, a continuación, vuelva a registrar. ' cuando se ejecuta Register-CcAppliance para registrar el dispositivo actual a en línea.**
    
    **Resolución:** Los valores para la \<ApplianceName\>, \<el FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> debe ser único y sólo utilizan para el registro de un dispositivo. De forma predeterminada, \<ApplianceName\> proviene del nombre de host. \<FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> definido en el archivo de configuración de ini.
    
    Por ejemplo, se usa (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para el registro en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), experimentará el conflicto.
    
    En primer lugar, compruebe el archivo CloudConnector.ini en la sección de directorio ApplianceRoot. Obtendrá \<SiteName\>, \<el FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> valores en el archivo. \<ApplianceName\> es el nombre del servidor host.
    
    En segundo lugar, inicio inquilino PowerShell remoto con su Skype para credenciales de administrador de inquilinos de negocio, a continuación, ejecute el siguiente cmdlet para comprobar la appliance(s) registrados.
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    Después de identificar cualquier conflicto, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
-    **Problema: El cmdlet Get-CcRunningVersion devuelve un valor vacío si no hay un dispositivo implementado que se ejecutan en el host.**
    
    **Resolución:** esto puede producirse cuando se actualiza de 1.3.4 o 1.3.8 a 1.4.1. Después de instalar la versión 1.4.1 con .msi, debe ejecutar `Register-CcAppliance` antes de ejecutar cualquier otro cmdlet. `Register-CcAppliance` migrará el archivo module.ini de %perfilusuario%\CloudConnector a %ProgramData%\CloudConnector. Si no se hizo esto, se creará un nuevo module.ini en la carpeta %ProgramData%\CloudConnector y se reemplazará la información de la versión de copia de seguridad/en ejecución para 1.3.4 o 1.3.8.
    
    Compare los archivos module.ini files en la carpeta %perfilusuario%\CloudConnector y %ProgramData%\CloudConnector. Si hay diferencias, elimine el archivo module.ini en %ProgramData%\CloudConnector y volver a ejecutar `Register-CcAppliance`. También puede modificar el archivo manualmente a la ejecución correcta y la versión de copia de seguridad.
    
- **Problema: Después de ejecutar el cmdlet CcVersion de modificador para cambiar a una versión anterior que es diferente de la versión actual de secuencia de comandos, no hay ninguna compatibilidad de alta disponibilidad para esta versión anterior.**
    
    **Resolución:** Por ejemplo, ha actualizado desde 1.4.1 a 1.4.2. La versión actual de secuencia de comandos, que se puede determinar mediante la ejecución de `Get-CcVersion`y la versión que se está ejecutando, que se puede determinar mediante la ejecución de `Get-CcRunningVersion` son ambos 1.4.2. En este momento, si ejecuta `Switch-CcVersion` para la versión que se está ejecutando volver a 1.4.1, a continuación, no habrá ningún soporte de alta disponibilidad para esta versión anterior.
    
    Para obtener compatibilidad total con alta disponibilidad, vuelva a 1.4.2 para que la versión en ejecución y la versión del script sean las mismas. Si está experimentando problemas con su implementación de 1.4.2, desinstálela y vuelva a instalarla tan pronto como sea posible.
    
- **Problema: los certificados de una entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**
    
    **Resolución:** los certificados de la entidad de certificación de Skype Empresarial son válidos durante cinco años. Los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral son válidos durante dos años.
    
    > [!NOTE]
    > En el conector en la nube versión 2.0 y versiones posterior, el cmdlet renovar CcServerCertificate ha cambiado a CcServerCertificate de actualización y el cmdlet renovar CcCACertificate ha cambiado a CcCACertificate de actualización. 
  
    Si los certificados internos emitidos para el almacén de Administración Central, el servidor de mediación y el servidor perimetral están cerca de expiración o ve comprometida, ejecutan el renovar CcServerCertificate o el cmdlet Update-CcServerCertificate para renovar los certificados.
    
    Si los certificados de entidad de certificación son cerca de expiración, ejecute el cmdlet renovar CcCACertificate o CcCACertificate de actualización para renovar sus certificados.
    
    **Si se ve comprometidos certificados de entidades emisoras y hay un único dispositivo en el sitio,** realice los siguientes pasos:
    
1. Ejecute el cmdlet Enter-CcUpdate para depurar los servicios y poner el dispositivo en modo de mantenimiento.
    
2. Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de la entidad de certificación y todos los certificados internos del servidor:
    
    Para las versiones en la nube conector antes de 2.0:
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    O bien, para la versión de conector en la nube 2.0 y versiones posterior:
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.
    
4. Ejecute el cmdlet Export-CcRootCertificate en el archivo local file del dispositivo y después copie e instale el certificado exportado en sus puertas de enlace de RTC.
    
    **Si se ve comprometidos certificados de entidades emisoras y hay varios dispositivos en el sitio,** realice la siguiente secuencia de pasos en cada dispositivo en el sitio.
    
    Microsoft recomienda que realice estos pasos durante las horas que no sean de máximo uso.
    
  - En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar la entidad de certificación en los archivos de copia de seguridad la \<SiteRoot\> Active directory.
    
  - Ejecute el cmdlet de entrar CcUpdate para purgar servicios y coloque cada dispositivo en el modo de mantenimiento.
    
  - Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de la entidad de certificación y todos los certificados internos del servidor:
    
    Para las versiones en la nube conector antes de 2.0:
    
    ```
    Reset-CcCACertificate
    Renew-CcServerCertificate
    Remove-CcLegacyServerCertificate 
    ```

    O bien, para la versión de conector en la nube 2.0 y versiones posterior:
    
    ```
    Reset-CcCACertificate
    Update-CcServerCertificate
    Remove-CcLegacyServerCertificate 
    ```

  - En el primer dispositivo, ejecute el siguiente cmdlet para realizar una copia de seguridad de los archivos de la entidad emisora de certificados para la \<SiteRoot\> carpeta. Más adelante, en todos los otros dispositivos en el mismo sitio, el cmdlet Reset-CcCACertificate consumirá automáticamente los archivos de copia de seguridad de la entidad emisora de certificados y dispositivos, usarán el mismo certificado raíz.
    
    ```
    Backup-CcCertificationAuthority
    ```

  - Ejecute el cmdlet de Exit CcUpdate para iniciar servicios y salir del modo de mantenimiento. 
    
  - Si se utiliza TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo en el sitio y, a continuación, instale el certificado exportado a las puertas de enlace RTC. 
    
- **Problema: Recibe el mensaje de error siguiente en el registro de servicio de administración del conector en la nube, "C:\Program Files\Skype para profesionales en la nube conector Edition\ManagementService\CceManagementService.log": CceService Error: 0: excepción inesperada cuando informar del estado a online: System.Management.Automation.CmdletInvocationException: error de inicio de sesión para el usuario \<Global Administrador de inquilinos\>. Cree un nuevo objeto de credencial, asegurándose de que se han utilizado el nombre de usuario correcto y la contraseña. ---\>**
    
    **Resolución:** Las credenciales de administración de Office 365 inquilino global se han cambiado desde que se registró el dispositivo conector en la nube. Para actualizar las credenciales almacenadas localmente en el dispositivo de conector en la nube, ejecute lo siguiente desde el Administrador de PowerShell en el dispositivo de host:
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problema: Después de cambiar la contraseña de la cuenta del servidor de host utilizados para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString: especificar la clave no es válido para su uso en estado." en %ProgramFiles%\Skype para la nube de Business Connector Edition\ManagementService\CceManagementService.log o mientras se ejecuta el cmdlet Get-CcCredential.**
    
    **Resolución:** Todas las credenciales del conector en la nube se almacenan en el siguiente archivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ". Cuando se cambia la contraseña en el servidor de host, debe actualizar las credenciales almacenadas localmente.
    
    **Si ejecuta la versión 1.4.2 de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector mediante estos pasos:
    
    1. Reinicie el servidor host.
    
    2. Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".
    
    3. Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción. Escriba las mismas contraseñas que ha especificado antes de la implementación del conector en la nube.
    
    **Si está ejecutando en la nube conector versión 2.0 o posterior,** vuelva a generar todas las contraseñas de conector en la nube, siga estos pasos:
    
    1. Reinicie el servidor host.
    
    2. Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".
    
    3. Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción. 
    
    Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector, use la contraseña de VMAdmin para la contraseña de CceService cuando se le solicite. Introduzca la misma contraseña que usó antes para la implementación de Cloud Connector de todas las otras cuentas.
    
    Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector y las contraseñas de DomainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:
    
    1. Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:
    
    2. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
    3. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.
    
    Si se ha generado el archivo de contraseña almacenada en caché con el conector de nube versión 2.0 o posterior, de forma predeterminada, VmAdmin y Administrador de dominio usan la misma contraseña como CceService. Si cambia la contraseña del administrador del dominio y VMAdmin, debe realizar los siguientes pasos:
    
    1. Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:
    
        1. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
        2. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.
    
    2. Ejecute Set-CcCredential -AccountType VmAdmin como sigue:
    
        1. Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.
    
        2. Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin que usó antes.  
    
- **Problema: Con la nube conector versión 2.1 y versiones posterior, cuando se ejecuta registrar CcAppliance u otros cmdlets en el dispositivo, recibirá un mensaje de error como: "para cada objeto: la propiedad 'Comunes' no se encuentra en este objeto. Compruebe que existe la propiedad. En C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**
    
    **Resolución:** En la nube conector 2.1 y posterior requiere .NET Framework 4.6.1 o posterior. Por favor, actualice .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar la cmdlet(s).

- **Problema: Con la nube conector Edition 2.1, al ejecutar Install-CcAppliance, recibirá un mensaje de error como: "no se pudo instalar la nueva instancia con error: no se puede establecer el"Estado"porque sólo cadenas se pueden utilizar como valores para establecer las propiedades de XmlNode"**

   **Resolución:** En Cloudconnector.ini, en la sección [Common], agregue la configuración de "Estado" como sigue: CountryCode = US estado = ciudad WA = Redmond

   No es obligatorio para la línea de "Estado" tiene valor, sin embargo, la línea de "Estado" no se puede quitar el archivo Cloudconnector.ini.

- **Problema: Recibe el siguiente mensaje de error "Dismount-WindowsImage: no se pudo Dismount-WindowsImage. Código de error = 0xc1550115 "al instalar o actualizar la edición de conector en la nube.**
    
    **Resolución:** Iniciar una consola de PowerShell como administrador, ejecute "DISM-Cleanup-Wim'". Esto va a limpiar todas las imágenes con problemas. Vuelva a ejecutar Install-CcAppliance o espere a que los bits actualizar automáticamente.
    
- **Problema: Implementación del primer dispositivo conector en la nube en un entorno de alta disponibilidad se produce un error**
    
    **Resolución:** Los pasos que seguir dependen de la razón del error en la implementación:
    
  - Si se produce un error en el primer dispositivo de conector en la nube y no puede determinar el motivo del error, debe instalar de nuevo el dispositivo hasta que la implementación se realizó correctamente y, a continuación, instale los demás dispositivos.
    
  - Si se produce un error en el primer dispositivo de conector en la nube con un problema menor, por ejemplo, un problema de certificado externo, es posible que pueda solucionar el problema sin tener que volver a instalar el dispositivo. Se puede, a continuación, el uso de inquilinos PowerShell remoto para marcar la implementación como correcta de la siguiente manera. (También puede usar los siguientes pasos si la finalización correcta de la primera implementación, pero, por algún motivo, el conector de la nube se produce un error informar de la implementación como un éxito.)
    
  - Para obtener la identidad (GUID) del primer dispositivo conector en la nube, ejecute el cmdlet Get-CsHybridPSTNAppliance.
    
  - Para marcar el dispositivo implementado como correctamente, ejecute el Set-CsCceApplianceDeploymentStatus como sigue:
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

-  **Problema: debe comprobar si existen actualizaciones de Windows e instalarlas manualmente en el servidor host o las máquinas virtuales.**
    
    **Resolución:** recomendamos que aproveche las actualizaciones automatizadas del sistema operativo proporcionada por Skype Empresarial Cloud Connector Edition. Después de que se registre un dispositivo para administración en línea y se habilite la actualización automática del sistema operativo, el servidor host y las máquinas virtuales automáticamente comprobarán si existen actualizaciones de Windows y las instalarán de acuerdo con la configuración de la ventana de la hora de actualización del sistema operativo.
    
    Si tiene que comprobar si existen actualizaciones de Windows e instalarlas manualmente, siga los pasos provistos en esta sección que se apliquen a su tipo de implementación. Debe planificar y actualizar tanto el servidor host como las máquinas virtuales que estén ejecutándose en él al mismo tiempo a fin de minimizar el tiempo de inactividad necesario para las actualizaciones.
    
    Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones para los servidores de Cloud Connector. Solo tiene que configurar la actualización de Windows para que **no** se instale automáticamente.
    
    Para obtener información sobre cómo actualizar manualmente su implementación de Cloud Connector, consulte la siguiente sección.
    
-   **Problema: Al conector de la nube se actualiza a una nueva compilación, cmdlets de conector en la nube no se actualizan.** En ocasiones, esto ocurre si una ventana de PowerShell se deja abierta cuando se produzca la actualización automática.
    
    **Resolución:** Para cargar los cmdlets actualizados, puede hacer lo siguiente:
    
     - Cierre de PowerShell en el dispositivo de conector en la nube y, a continuación, vuelva a abrir PowerShell.
    
     - O bien, puede ejecutar Import-Module CloudConnector-Force. 
    
## <a name="install-windows-updates-manually"></a>Instalar manualmente las actualizaciones de Windows

Si no quiere usar actualizaciones automáticas en su entorno, siga estos pasos para comprobar si existen actualizaciones de Windows y aplicarlas manualmente. Puede ser necesario reiniciar el servidor para la comprobación e instalación de actualizaciones de Windows. Cuando se reinicia un servidor de host, los usuarios no podrán utilizar el conector de la nube para realizar o recibir llamadas. Puede comprobar si existen actualizaciones e instalarlas de forma manual a fin de controlar en qué momento deben producirse, y después reiniciar las máquinas según la necesidad durante los tiempos que usted elija para evitar interrupciones de los servicios.
  
Para comprobar manualmente si existen actualizaciones, conecte cada servidor host y abra el **Panel de control**. Seleccione **sistema y seguridad \>Windows Update**y, a continuación, administrar las actualizaciones y se reinicia según corresponda para su entorno de servidor.
  
- Si existe solo un dispositivo en el sitio, conecte cada máquina virtual y abra el **Panel de control**. Seleccione **sistema y seguridad \>Windows Update**y, a continuación, configurar las actualizaciones y el servidor se reinicia según corresponda.
    
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
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Sugerencias al instalar el software antivirus en el equipo host de conector en la nube

Si necesita instalar un software antivirus en el equipo host de conector en la nube, debe agregar las exclusiones siguientes:
  
- Directorio de dispositivo local en cada equipo.
    
- Directorio de sitio remoto en cada equipo.
    
- Directorio de sitio local en el equipo hospeda la carpeta raíz del sitio compartido.
    
- %ProgramFiles%\Skype para Business Edition de conector en la nube
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- El proceso de Microsoft.Rtc.CCE.ManagementService.exe.
