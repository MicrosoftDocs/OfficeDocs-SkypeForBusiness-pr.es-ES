---
title: Implementar el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumen: lea este tema para obtener información sobre cómo implementar el administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 901720f87cf1c0bf78f558ed0d031bd41377799a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898261"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Implementar el administrador de estadísticas para Skype Empresarial Server
 
**Resumen**: lea este tema para obtener información sobre cómo implementar el administrador de estadísticas para Skype Empresarial Server.
  
 El administrador de estadísticas de Skype Empresarial Server es una eficaz herramienta que le permite ver los datos de mantenimiento y rendimiento de Skype Empresarial Server en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del administrador de estadísticas.
  
Antes de instalar el administrador de estadísticas, consulte los requisitos de software, red y hardware. Para obtener más información, vea [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md).
  
> [!NOTE]
> Si está llevando a cabo una actualización a partir de una versión anterior del administrador de estadísticas, consulte [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md). 
  
> [!NOTE]
> El sitio web del administrador de estadísticas se ha probado y funciona correctamente en Internet Explorer 11+, Microsoft Edge 20.10240+ y Chrome 46+ (versión actual con actualización automática). 
  
Puede encontrar el archivo descargable del administrador estadísticas en [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload). 
  
Este tema incluye las secciones siguientes:
  
- [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy)
    
- [Solucionar problemas de la implementación](deploy.md#BKMK_Troubleshoot)
    
- [Crear un certificado autofirmado](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Implementar el administrador de estadísticas
<a name="BKMK_Deploy"> </a>

Para implementar el administrador de estadísticas, siga estos pasos:
  
1. Prepare el equipo host de escucha instalando el sistema de almacenamiento en caché en memoria Redis y asegurándose de que están instalados los certificados adecuados.
    
2. Instale el servicio de escucha en el equipo host. 
    
3. Instale el servicio de sitio web en el equipo host.
    
4. Instale un agente en cada equipo de Skype Empresarial Server que quiera supervisar.
    
5. Importe la topología para los servidores que va a supervisar.
    
> [!NOTE]
> Redis, el servicio de escucha y el servicio de sitio web deben estar instalados en el mismo equipo host. Asegúrese de que Skype Empresarial Server no está instalado en el equipo host. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparar el equipo host de escucha

Para preparar el equipo host, debe instalar el sistema de almacenamiento en caché en memoria Redis y asegurarse de que el equipo cuenta con un certificado válido. Microsoft recomienda instalar la compilación estable más reciente de Redis 3.0. La versión 2.0 del administrador de estadísticas se ha probado con Redis 3.2.100. 
  
1. Descargue Redis desde el sitio: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    Puede descargar instaladores sin firmar desde [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases).
    
    Si lo necesita, hay binarios firmados disponibles a través de gestores de paquetes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) y [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Ejecute el msi proporcionado y siga las instrucciones.
    
   - No marque la casilla para agregar una regla de firewall.
    
2. El servicio de escucha requiere un certificado. Microsoft recomienda encarecidamente usar un certificado firmado por una autoridad de certificación de confianza. 
    
    Si desea usar un certificado autofirmado para realizar pruebas en un entorno de laboratorio, por ejemplo, consulte [Crear un certificado autofirmado](deploy.md#BKMK_SelfCert).
    
    Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena). No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.
    
### <a name="install-the-listener-service"></a>Instalar el servicio de escucha

Para instalar el servicio de escucha en el equipo host, ejecute StatsManPerfAgentListener.msi y especifique lo siguiente:
  
1. Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**.  
    
2. En la página siguiente, indique la información que se indica a continuación:
    
   - **Contraseña del servicio:** esta es la contraseña que utilizarán los agentes remotos para autenticarse en el servicio de escucha.
    
   - **Puerto de servicio**: este es el número de puerto HTTPS que el servicio de escucha usará para comunicarse con los agentes. Durante la instalación, este puerto podrá pasar por el firewall local, se creará una ACL de URL y se vinculará un certificado SSL con este puerto. El valor predeterminado es 8443.
    
   - **Huella digital de certificado**: esta es la huella digital de certificado que el servicio de escucha usará para cifrar el protocolo HTTPS. El servicio de red debe tener acceso de lectura a la clave privada.
    
     Haga clic en el botón **Seleccionar...** para elegir la huella digital.
    
     Puede buscar la huella digital del certificado usando el administrador de certificados o con el siguiente comando de PowerShell:
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Directorio de instalación**: este es el directorio en el que se instalarán los binarios. Puede cambiar el valor predeterminado a través del botón **Examinar...**.
    
   - **Directorio de datos de aplicación**: este es el directorio en el que se almacenarán la carpeta de registros y otros datos. Puede cambiar el valor predeterminado. No se eliminará ni se desinstalará.
    
3. Haga clic en **Instalar**.
    
Para validar la instalación, realice los siguientes pasos:
  
1. Abra un explorador y vaya a https://localhost:\<service-port\>/healthcheck/.
    
    De forma predeterminada, el puerto del servicio es 8443 (a no ser que especifique otro).
    
2. Para asegurarse de que el servicio de escucha se ha instalado correctamente, busque lo siguiente:
    
   - Si se muestra la página de comprobación de estado, la instalación del servicio de escucha se ha realizado correctamente.
    
   - Si el valor de KnownServersCount es 1 o superior, se ha establecido la conexión con Redis.
    
   - Tras esperar unos minutos y después de instalar al menos un agente, compruebe si crece el valor de ValuesWritten.
    
### <a name="install-the-website"></a>Instalar el servicio de sitio web

Para instalar el servicio de sitio web en el equipo host, ejecute StatsManWebSite.msi (incluido en la [versión de 64 bits del administrador de estadísticas en tiempo real de Skype Empresarial Server](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) y especifique lo siguiente:
  
1. Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**.  
    
2. En la página siguiente, indique la información que se indica a continuación:
    
   - **Puerto de servicio**: este es el número de puerto que escuchará el sitio web. Puede cambiarlo posteriormente usando el enlace del administrador de IIS. Durante la instalación, el firewall local permitirá el tráfico por este puerto.
    
   - **Directorio de instalación**: este es el directorio en el que se instalarán los binarios. Puede cambiar el valor predeterminado a través del botón **Examinar...**.
    
   - **Directorio de datos de aplicación**: este es el directorio en el que se almacenarán la carpeta de registros y otros datos. Puede cambiar el valor predeterminado. No se eliminará ni se desinstalará.
    
3. Haga clic en **Instalar**.
    
Para ver el sitio web, abra un explorador y vaya a: http://localhost,webport\>/.
  
Para ver solo información de estado, abra un explorador y vaya a: http://localhost:\<webport\>/healthcheck/.
  
De forma predeterminada, el número de este puerto es 8080. Puede cambiar el enlace del puerto del sitio web usando el administrador de IIS.
  
El instalador web agrega un grupo de seguridad local llamado StatsManWebSiteUsers. Puede agregar cuentas a este grupo de seguridad para concederles acceso al sitio web. 
  
### <a name="install-the-agents"></a>Instalar los agentes

Debe instalar un agente en cada Skype Empresarial Server que desee supervisar. Para hacerlo, ejecute el archivo StatsManPerfAgent.msi y especifique lo siguiente:
  
1. Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**.  
    
2. En la página siguiente, indique la información que se indica a continuación:
    
   - **Contraseña del servicio:** esta es la contraseña que utilizará el agente remoto para autenticarse en el servicio de escucha.
    
   - **URI de servicio**: este es el URI en el que reside el servicio de escucha. Debe usar el formato https://name:port.
    
     Puede usar un nombre NETBIOS o un FQDN. Puede usar el nombre que se especifica también como **Sujeto** o como **Nombres alternativos del sujeto** en el certificado del servicio de escucha, pero no es obligatorio.
    
   - **Huella digital del servicio**: esta es la huella digital del certificado SSL que usa el servicio de escucha. El agente usará esta huella digital para autenticarse en el servicio de escucha. (No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados).
    
   - **Directorio de instalación**: este es el directorio en el que se instalarán los binarios. Puede cambiar el valor predeterminado a través del botón **Examinar...**.
    
   - **Directorio de datos de aplicación**: este es el directorio en el que se almacenarán la carpeta de registros y el archivo password.txt cifrado. Puede cambiar el valor predeterminado. No se eliminará ni se desinstalará.
    
3. Haga clic en **Instalar**.
    
Si va a instalar un agente en varios equipos, probablemente quiera hacerlo de modo desatendido. Por ejemplo: 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importar la topología
<a name="BKMK_ImportTopology"> </a>

Una vez que el administrador de estadísticas esté instalado y en funcionamiento, debe importar la topología de Skype Empresarial Server para que el administrador de estadísticas conozca el sitio, el grupo y la función de cada servidor. Para importar su topología de Skype Empresarial Server, use el cmdlet [Get-CSPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) para recuperar información sobre cada grupo que usa su organización e importe esta información al administrador de estadísticas.
  
Para importar la topología de Skype Empresarial Server, siga estos pasos:
  
1. En un host que tenga los cmdlets de PowerShell de Skype Empresarial Server:
    
    a. Ejecute el siguiente comando: 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Copie el archivo "mypoolinfo.xml" en el servidor que ejecuta el servicio de escucha.
    
2. En el host que ejecuta el servicio de escucha:
    
   a. Ejecute PowerShell.
    
   b. Vaya hasta el directorio en el que está instalado el servicio de escucha. El valor predeterminado es: 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Para confirmar qué servidores se agregan y se actualizan, ejecute el siguiente comando:
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

El comando siguiente le permite ver todas las opciones:
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Para ver la información de servidores que ha importado, ejecute el siguiente script: 
  
```
.\Get-StatsManServerInfo.ps1
```

Si desea supervisar servidores que no se encuentran en su topología de Skype Empresarial Server (un servidor de Exchange, por ejemplo) puede realizar la importación de un único servidor en el host que ejecuta el servicio de escucha. Para realizar la importación de un único servidor, siga estos pasos:
  
1. Vaya hasta el directorio en el que está instalado el servicio de escucha. El valor predeterminado es: 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Ejecute el siguiente comando:
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Solucionar problemas de la implementación
<a name="BKMK_Troubleshoot"> </a>

Si no se puede iniciar un agente, verifique lo siguiente: 
  
- ¿El agente está registrado en el administrador de estadísticas?
    
1. 	Asegúrese de que ha seguido las instrucciones para importar la topología. Consulte [Importar la topología](deploy.md#BKMK_ImportTopology).  
    
2. Si el agente está en un servidor que no se incluye en la topología (por ejemplo, los nodos de un clúster SQL AlwaysOn), tendrá que agregar el agente manualmente siguiendo las instrucciones de [Importar la topología](deploy.md#BKMK_ImportTopology).
    
- ¿El agente puede contactar con el servicio de escucha?
    
1. Asegúrese de que el servicio de escucha está en funcionamiento. 
    
    Si no lo está, compruebe que Redis está en funcionamiento y, a continuación, intente reiniciar el servicio de escucha.
    
2. Asegúrese de que el puerto está abierto para el servicio de escucha y de que el equipo del agente se puede comunicar con el puerto.
    
- Para asegurarse de que el administrador de estadísticas recopila datos, puede comprobar el archivo CSV del siguiente modo. 
    
    El siguiente comando recupera los nombres de almacenamiento de los contadores: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    El siguiente comando recupera los valores de los contadores especificados: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Para obtener información sobre todos los eventos que puede ver en el registro de eventos de la aplicación, consulte [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Crear un certificado autofirmado
<a name="BKMK_SelfCert"> </a>

Microsoft recomienda encarecidamente usar un certificado firmado por una autoridad de certificación de confianza. Sin embargo, si desea usar un certificado autofirmado para realizar pruebas, haga lo siguiente: 
  
1. Desde una consola de PowerShell en la que haya iniciado sesión como administrador, escriba lo siguiente:
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Escriba `certlm.msc`. Se abrirá el administrador de certificados para el equipo local.
    
3. Vaya a **Personal** y abra **Certificados**.
    
4. Haga clic con el botón derecho en **StatsManListener-\>Todas las tareas-\>Administrar claves privadas…**
    
5. Haga clic en **Agregar**.
    
6. En el cuadro **Escribir los nombres de objeto para seleccionar**, escriba Servicio de red.
    
7. Haga clic en **Aceptar**.
    
8. En **Control total**, desmarque la casilla **Permitir**. (Solo se requiere acceso con permiso de lectura).
    
9. Haga clic en **Aceptar**.
    
## <a name="for-more-information"></a>Más información
<a name="BKMK_SelfCert"> </a>

Para obtener más información, vea los artículos siguientes:
  
- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)
    
- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)
    
- [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)
