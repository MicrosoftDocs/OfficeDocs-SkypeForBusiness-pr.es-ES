---
title: Implementar el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumen: lea este tema para obtener información sobre cómo implementar el Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 406f4188347d32111bea4952815237b7f1015574
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105386"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Implementar el administrador de estadísticas para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo implementar el Administrador de estadísticas para Skype Empresarial Server.
  
 El Administrador de estadísticas de Skype Empresarial Server es una herramienta eficaz que le permite ver datos de rendimiento y estado de Skype Empresarial Server en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas.
  
Antes de intentar instalar el Administrador de estadísticas, asegúrese de que está familiarizado con los requisitos de software, redes y hardware. Para obtener más información, vea [Plan for Statistics Manager for Skype for Business Server](plan.md).
  
> [!NOTE]
> Si va a actualizar desde una versión anterior del Administrador de estadísticas, vea [Upgrade Statistics Manager for Skype for Business Server](upgrade.md). 
  
> [!NOTE]
> El sitio web del Administrador de estadísticas se ha probado y funciona correctamente en Internet Explorer 11+, Edge 20.10240+ y Chrome 46+ (versión perenne actual). 
  
Puede encontrar el Administrador de estadísticas descargable en [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) . 
  
En este tema se presentan las siguientes secciones:
  
- [Implementar el Administrador de estadísticas](deploy.md#BKMK_Deploy)
    
- [Solucionar problemas de implementación](deploy.md#BKMK_Troubleshoot)
    
- [Crear un certificado autofirmado](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Implementar el Administrador de estadísticas
<a name="BKMK_Deploy"> </a>

Para implementar el Administrador de estadísticas, siga estos pasos:
  
1. Prepare el equipo host de escucha instalando el sistema de almacenamiento en memoria caché de Redis y asegurándose de que ha instalado los certificados adecuados.
    
2. Instale el servicio de escucha en el equipo host. 
    
3. Instale el sitio web en el equipo host.
    
4. Instale un agente en cada equipo de Skype Empresarial Server que desee supervisar.
    
5. Importe la topología de los servidores que está supervisando.
    
> [!NOTE]
> Redis, el servicio de escucha y el sitio web deben instalarse en el mismo equipo host. Asegúrese de que el equipo host no tenga instalado Skype Empresarial Server. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparar el equipo host de escucha

Para preparar el equipo host, deberá instalar el sistema de almacenamiento en memoria caché de Redis y asegurarse de que hay un certificado válido en el equipo. Microsoft recomienda instalar la compilación estable más reciente de Redis 3.0. Statistics Manager versión 2.0 se ha probado con Redis 3.2.100. 
  
1. Descargue Redis desde el siguiente sitio: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) . 
    
    Los instaladores sin firma se pueden descargar desde [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Si es necesario, los archivos binarios firmados están disponibles a través de los administradores de paquetes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) y [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Ejecute el msi proporcionado y siga las indicaciones.
    
   - No active la casilla para agregar una regla de firewall.
    
2. El servicio de escucha requiere un certificado. Microsoft recomienda encarecidamente que tenga un certificado firmado por una entidad de certificación de confianza. 
    
    Si desea usar un certificado autofirmado (para fines de prueba en un laboratorio, por ejemplo), consulte [Create a self-signed certificate](deploy.md#BKMK_SelfCert).
    
    Tenga en cuenta que el agente usa la comprobación de huella digital del certificado (en lugar de la verificación en cadena). No realizará la validación completa del certificado porque es posible usar certificados autofirmados.
    
### <a name="install-the-listener-service"></a>Instalar el servicio de escucha

Instale el servicio de escucha en el equipo host ejecutando el StatsManPerfAgentListener.msi y especificando lo siguiente:
  
1. Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y, a continuación, haga clic en **Siguiente**. 
    
2. En la página siguiente, especifique la siguiente información:
    
   - **Contraseña del servicio:** Esta es la contraseña que usarán los agentes remotos para autenticarse en el servicio de escucha.
    
   - **Puerto de servicio:** Este es el número de puerto HTTPS que usará el agente de escucha para comunicarse con los agentes. Durante la instalación, este puerto se permitirá a través del firewall local, se creará una ACL de dirección URL y se enlazará un certificado SSL a este puerto. El valor predeterminado es 8443.
    
   - **Huella digital del certificado:** Esta es la huella digital del certificado que usará el agente de escucha para cifrar el protocolo HTTPS. El servicio de red debe tener acceso de lectura a la clave privada.
    
     Haga clic **en el botón Seleccionar...** para elegir la huella digital.
    
     Puede encontrar la huella digital del certificado mediante el Administrador de certificados o mediante el siguiente comando de PowerShell:
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **Instalar Dir:** Este es el directorio en el que se instalarán los archivos binarios. Puede cambiarlo desde el valor predeterminado mediante el **botón Examinar....**
    
   - **Dir de AppData:** Este es el directorio donde se almacenarán la carpeta Registros y otros datos. Puede cambiarlo desde el valor predeterminado. No se eliminará al desinstalar.
    
3. Haga clic en **Instalar**.
    
Para validar la instalación, siga estos pasos:
  
1. Abrir un explorador y navegar a https://localhost: \<service-port\> /healthcheck/
    
    De forma predeterminada, el puerto de servicio es 8443 (a menos que haya especificado otro puerto).
    
2. Para asegurarse de que el agente de escucha se ha instalado correctamente, busque lo siguiente:
    
   - Si se muestra la página de comprobación de mantenimiento, la instalación de escucha se ha realizado correctamente.
    
   - Si KnownServerCount es 1 o superior, se establece la conexión a Redis.
    
   - Después de esperar unos minutos y después de instalar al menos un agente, compruebe que el contador ValuesWritten aumenta.
    
### <a name="install-the-website"></a>Instalar el sitio web

Instale el sitio web en el equipo host ejecutando el StatsManWebSite.msi (incluido con Skype Empresarial Server, administrador de estadísticas de [Real-Time (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)y especificando lo siguiente:
  
1. Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y, a continuación, haga clic en **Siguiente**. 
    
2. En la página siguiente, especifique la siguiente información:
    
   - **Puerto de servicio:** Este es el número de puerto en el que escuchará el sitio web. Puede cambiarlo más adelante mediante el enlace del administrador de IIS. Durante la instalación, este puerto se permitirá a través del firewall local.
    
   - **Instalar Dir:** Este es el directorio donde se instalarán los archivos binarios. Puede cambiarlo desde el valor predeterminado mediante el **botón Examinar....**
    
   - **Dir de AppData:** Este es el directorio donde se almacenarán la carpeta Registros y otros datos. Puede cambiarlo desde el valor predeterminado. No se eliminará al desinstalar.
    
3. Haga clic en **Instalar**.
    
Para ver el sitio web, abra un explorador y vaya a: http://localhost ,webport \> /.
  
Para ver solo información de estado, abra un explorador y vaya a: http://localhost: \<webport\> /healthcheck/.
  
De forma predeterminada, el número de puerto web es 8080. Puede cambiar el enlace de puerto del sitio web mediante el administrador de IIS.
  
El instalador web agrega un grupo de seguridad local, denominado StatsManWebSiteUsers. Puede agregar cuentas a este grupo de seguridad para conceder acceso al sitio web. 
  
### <a name="install-the-agents"></a>Instalar los agentes

Instale un agente en cada Skype Empresarial Server que desee supervisar ejecutando el StatsManPerfAgent.msi y especificando lo siguiente:
  
1. Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y, a continuación, haga clic en **Siguiente**. 
    
2. En la página siguiente, especifique la siguiente información:
    
   - **Contraseña del servicio:** Esta es la contraseña que usará el agente remoto para autenticarse en el servicio de escucha.
    
   - **URI de servicio:** Este es el URI donde reside el agente de escucha. Debe usar el https://name:port formato.
    
     Puede usar un nombre NETBIOS o un FQDN. Puede usar el nombre que también  se  especifica como el asunto o los nombres alternativos de sujeto del certificado en el servicio de escucha, pero no es un requisito.
    
   - **Huella digital del servicio:** Esta es la huella digital del certificado SSL que usa listener. El agente usará esta huella digital para autenticarse en el agente de escucha. (No realizará la validación completa del certificado porque es posible usar certificados autofirmados).
    
   - **Instalar Dir:** Este es el directorio en el que se instalarán los archivos binarios. Puede cambiarlo desde el valor predeterminado mediante el **botón Examinar....**
    
   - **Dir de AppData:** Este es el directorio donde se almacenarán la carpeta Logs y el password.txt cifrado. Puede cambiarlo desde el valor predeterminado. No se eliminará al desinstalar.
    
3. Haga clic en **Instalar**.
    
Si va a instalar un agente en numerosas máquinas, probablemente querrá hacerlo en modo desatendido. Por ejemplo: 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importar la topología
<a name="BKMK_ImportTopology"> </a>

Después de instalar y ejecutar el Administrador de estadísticas, debe importar la topología de Skype Empresarial Server para que el Administrador de estadísticas conozca el sitio, el grupo y el rol de cada servidor. Para importar la topología de Skype Empresarial Server, usará el cmdlet [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) para recuperar información sobre cada grupo de servidores en uso en su organización y, a continuación, importar esta información en el Administrador de estadísticas.
  
Para importar la topología de Skype Empresarial Server, siga estos pasos:
  
1. En un host que tenga los cmdlets de PowerShell de Skype Empresarial Server:
    
    a. Ejecute el siguiente comando: 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copie el archivo "mypoolinfo.xml" en el servidor que ejecuta el agente de escucha.
    
2. En el host que ejecuta el agente de escucha:
    
   a. Ejecute PowerShell.
    
   b. Vaya al directorio en el que está instalado el agente de escucha. El valor predeterminado es: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Para confirmar qué servidores se van a agregar y actualizar, ejecute el siguiente comando:
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

El siguiente comando permite ver todas las opciones:
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Para ver la información del servidor importada actualmente, ejecute el siguiente script: 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

Si desea supervisar servidores que no están en la topología de Skype Empresarial Server (un Exchange Server, por ejemplo), puede realizar una importación de un solo servidor en el host que ejecuta el agente de escucha. Para realizar una importación de un solo servidor, siga estos pasos:
  
1. Vaya al directorio en el que está instalado el agente de escucha. El valor predeterminado es: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Ejecute el siguiente comando:
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Solucionar problemas de implementación
<a name="BKMK_Troubleshoot"> </a>

Si un agente no se inicia, compruebe lo siguiente: 
  
- ¿El agente está registrado en el Administrador de estadísticas?
    
    1. Asegúrese de que ha seguido las instrucciones para importar la topología. Consulte [Import the topology](deploy.md#BKMK_ImportTopology).
        
    2. Si el agente está en un servidor que no aparece en la topología (por ejemplo, los nodos de un clúster alwayson de SQL), deberá agregar el agente manualmente siguiendo las instrucciones de [Importar](deploy.md#BKMK_ImportTopology)la topología .
    
- ¿Puede el agente ponerse en contacto con el agente de escucha?
    
    1. Asegúrese de que se está ejecutando el servicio de escucha. 
        
        Si no se está ejecutando, asegúrese de que Se está ejecutando Redis y, a continuación, intente reiniciar el agente de escucha.
        
    2. Asegúrese de que el puerto está abierto para el servicio de escucha y de que el equipo agente puede comunicarse con el puerto.
    
- Para asegurarse de que el Administrador de estadísticas recopila datos, puede comprobar el archivo CSV de la siguiente manera. 
    
    El siguiente comando recupera los nombres de almacenamiento del contador: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    El siguiente comando recupera los valores de los contadores especificados: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Para obtener información sobre todos los eventos que puede ver en el registro de eventos de la aplicación, vea [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Crear un certificado autofirmado
<a name="BKMK_SelfCert"> </a>

Microsoft recomienda encarecidamente que use un certificado firmado por una entidad de certificación de confianza. Sin embargo, si desea usar un certificado autofirmado con fines de prueba, haga lo siguiente: 
  
1. Desde una consola de PowerShell mientras ha iniciado sesión como administrador, escriba lo siguiente:
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Escriba  `certlm.msc` . Esto abrirá el Administrador de certificados para el equipo local.
    
3. Vaya a **Personal** y, a continuación, abra **Certificados**.
    
4. Haga clic con el botón **secundario en StatsManListener: \> Todas las tareas: Administrar claves \> privadas...**
    
5. Haga clic en **Agregar**.
    
6. En el **cuadro Escriba los nombres de objeto que desea** seleccionar, escriba lo siguiente: Servicio de red
    
7. Haga clic en **Aceptar**.
    
8. En **Control total,** active **la** casilla Permitir. (Solo es necesario el acceso de lectura).
    
9. Haga clic en **Aceptar**.
    
## <a name="for-more-information"></a>Más información
<a name="BKMK_SelfCert"> </a>

Para obtener más información, vea los artículos siguientes: 
  
- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)
    
- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)
    
- [Solucionar problemas del Administrador de estadísticas para Skype Empresarial Server](troubleshoot.md) ß