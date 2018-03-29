---
title: Implementar el administrador de estadísticas para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumen: Leer este tema para aprender a implementar el administrador estadísticas de Skype para Business Server 2015.'
ms.openlocfilehash: 7730a6b933bbe1d627bffe175a24a60273be3a88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-statistics-manager-for-skype-for-business-server-2015"></a>Implementar el administrador de estadísticas para Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a implementar el administrador estadísticas de Skype para Business Server 2015.
  
 Administrador de estadísticas de Skype para Business Server es una eficaz herramienta que permite ver Skype para los datos de rendimiento y la salud de Business Server en tiempo real. Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web del Administrador de estadísticas.
  
Antes de intentar instalar el Administrador de las estadísticas, asegúrese de que está familiarizado con los requisitos de hardware, redes y software. Para obtener más información, consulte [Plan Administrador de estadísticas para Skype para Business Server 2015](plan.md).
  
> [!NOTE]
> Si está actualizando desde una versión anterior del Administrador de estadísticas, vea [Actualizar estadísticas Administrador de Skype para Business Server 2015](upgrade.md). 
  
> [!NOTE]
> El sitio web del administrador de estadísticas se ha probado y funciona correctamente en Internet Explorer 11+, Edge 20.10240+ y Chrome 46+ (versión actual con actualización automática). 
  
Puede encontrar el administrador estadísticas descargables en [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload). 
  
Este tema incluye las secciones siguientes:
  
- [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy)
    
- [Solucionar problemas de la implementación](deploy.md#BKMK_Troubleshoot)
    
- [Crear un certificado autofirmado](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Implementar el administrador de estadísticas
<a name="BKMK_Deploy"> </a>

Para implementar el administrador estadísticas, siga estos pasos:
  
1. Prepare el equipo host de escucha instalando el sistema de almacenamiento en caché en memoria Redis y asegurándose de que están instalados los certificados adecuados.
    
2. Instale el servicio de escucha en el equipo host.  
    
3. Instale el servicio de sitio web en el equipo host.
    
4. Instalar a un agente en cada Skype para máquina Business Server que desea supervisar.
    
5. Importe la topología para los servidores que va a supervisar.
    
> [!NOTE]
> Redis, el servicio de escucha y el servicio de sitio web deben estar instalados en el mismo equipo host. Asegúrese de que el equipo host no tiene Skype para Business Server instalado. 
  
### <a name="prepare-the-listener-host-machine"></a>Preparar el equipo host de escucha

Para preparar el equipo host, debe instalar el sistema de almacenamiento en caché en memoria Redis y asegurarse de que el equipo cuenta con un certificado válido. Microsoft recomienda instalar la compilación estable más reciente de Redis 3.0. Estadísticas Manager versión 1.1 se ha probado con Redis Redis 2.8.2400 y 3.0.501. 
  
1. Descargar Redis desde el siguiente sitio: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    Sin firmar instaladores pueden descargarse desde[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Si es necesario, los archivos binarios firmados están disponibles a través de los jefes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) y [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Ejecute el msi proporcionado y siga las instrucciones.
    
   - No marque la casilla para agregar una regla de firewall.
    
2. El servicio de escucha requiere un certificado. Microsoft recomienda encarecidamente que tiene un certificado firmado por una autoridad de certificados de confianza. 
    
    Si desea usar un certificado autofirmado para realizar pruebas en un entorno de laboratorio, por ejemplo, consulte [Crear un certificado autofirmado](deploy.md#BKMK_SelfCert).
    
    Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena). No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.
    
### <a name="install-the-listener-service"></a>Instalar el servicio de escucha

Instalar el servicio de escucha en la máquina host ejecutando el StatsManPerfAgentListener.msi y especificando lo siguiente:
  
1. Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**.  
    
2. En la página siguiente, indique la información que se indica a continuación:
    
    - **Contraseña del servicio:** esta es la contraseña que utilizarán los agentes remotos para autenticarse en el servicio de escucha.
    
    - **Puerto de servicio:** Esto es el número de puerto HTTPS que utiliza el agente de escucha para comunicarse con los agentes. Durante la instalación, este puerto se permitirá a través del firewall local, se creará una ACL de dirección URL y un certificado SSL se enlazará a este puerto. El valor predeterminado es 8443.
    
    - **Huella digital de certificado:** Se trata de la huella digital del certificado que del agente de escucha se utilizará para cifrar el protocolo HTTPS. Servicio de red debe tener acceso de lectura a la clave privada.
    
    Haga clic en el botón **Seleccionar...** para elegir la huella digital.
    
    Puede buscar la huella digital del certificado usando el administrador de certificados o con el siguiente comando de PowerShell:
    
  ```
  Get-ChildItem -path cert:\LocalMachine\My
  ```

   - **Instalar Dir:** Éste es el directorio en el que se instalarán los archivos binarios. Puede cambiar el valor predeterminado mediante el botón **Examinar...** .
    
   - **AppData Dir:** Éste es el directorio donde se almacenará la carpeta de registros y otros datos. Se puede cambiar el valor predeterminado. No se eliminará en desinstalar.
    
3. Haga clic en **Instalar**.
    
Para validar la instalación, realice los siguientes pasos:
  
1. Abra un explorador y vaya a https://localhost: \<puerto de servicio\>/healthcheck/
    
    De forma predeterminada, el puerto del servicio es 8443 (a no ser que especifique otro).
    
2. Para asegurarse de que el servicio de escucha se ha instalado correctamente, busque lo siguiente:
    
   - Si se muestra la página de comprobación de estado, la instalación del servicio de escucha se ha realizado correctamente.
    
   - Si el valor de KnownServersCount es 1 o superior, se ha establecido la conexión con Redis.
    
   - Tras esperar unos minutos y después de instalar al menos un agente, compruebe si crece el valor de ValuesWritten.
    
### <a name="install-the-website"></a>Instalar el servicio de sitio web

Instalar el sitio Web en el equipo host ejecutando el StatsManWebSite.msi y especificando lo siguiente:
  
1. Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**.  
    
2. En la página siguiente, indique la información que se indica a continuación:
    
   - **Puerto de servicio:** Es el número de puerto que escucha en el sitio web. Puede cambiar más tarde mediante el Administrador de IIS de enlace. Durante la instalación, este puerto se permitirá a través del firewall local.
    
   - **Instalar Dir:** Éste es el directorio donde se instalarán los archivos binarios. Puede cambiar el valor predeterminado mediante el botón **Examinar...** .
    
   - **AppData Dir:** Éste es el directorio donde se almacenará la carpeta de registros y otros datos. Se puede cambiar el valor predeterminado. No se eliminará en desinstalar.
    
3. Haga clic en **Instalar**.
    
Para ver la página Web, abra un explorador y vaya a: http://localhost, webport\>/.
  
Para ver sólo la información de salud, abra un explorador y vaya a: http://localhost: \<webport\>/healthcheck.
  
De forma predeterminada, el número de este puerto es 8080. Puede cambiar el enlace del puerto del sitio web usando el administrador de IIS.
  
El instalador web agrega un grupo de seguridad local llamado StatsManWebSiteUsers. Puede agregar cuentas a este grupo de seguridad para concederles acceso al sitio web. 
  
### <a name="install-the-agents"></a>Instalar los agentes

Instalar a un agente en cada Skype para Business Server que desea supervisar ejecutando el StatsManPerfAgent.msi y especificando lo siguiente:
  
1. Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**.  
    
2. En la página siguiente, indique la información que se indica a continuación:
    
   - **Contraseña del servicio:** esta es la contraseña que utilizará el agente remoto para autenticarse en el servicio de escucha.
    
   - **Servicio URI:** Esto es el URI en el que reside el agente de escucha. Debe utilizar el https://name:port formato.
    
    Puede usar un nombre NETBIOS o un FQDN. Puede utilizar el nombre que también se especifica como el **asunto** o **Nombres alternativos del sujeto** del certificado en el servicio de agente de escucha, pero esto no es un requisito.
    
   - **Servicio de huella digital:** Se trata de la huella digital del certificado SSL que está utilizando el agente de escucha. El agente utilizará esta huella digital para autenticar al agente de escucha. (No lo hará completa validación de certificados, ya que es posible usar certificados autofirmados.)
    
   - **Instalar Dir:** Éste es el directorio en el que se instalarán los archivos binarios. Puede cambiar el valor predeterminado mediante el botón **Examinar...** .
    
   - **AppData Dir:** Éste es el directorio donde se almacenará la carpeta de registros y el archivo password.txt cifrados. Usted pueden gracias cambiarlo al valor predeterminado. No se eliminará en desinstalar.
    
3. Haga clic en **Instalar**.
    
Si va a instalar un agente en varios equipos, probablemente quiera hacerlo de modo desatendido. Por ejemplo:   
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importar la topología
<a name="BKMK_ImportTopology"> </a>

Después de estadísticas Manager está instalado y en ejecución, debe importar el Skype para la topología de servidores de negocios así que ese administrador estadísticas sabe el sitio, grupo y función de cada servidor. Para importar su Skype para la topología de servidores de la empresa, se usa el cmdlet [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) para recuperar información acerca de cada grupo que se utilizan en su organización, luego importar esta información en el Gestor de estadísticas.
  
Para importar el Skype para topología Business Server, siga estos pasos:
  
1. En un host que tiene el Skype para cmdlets de PowerShell de Business Server:
    
    a. Ejecute el siguiente comando: 
    
  ```
  Get-CsPool | Export-Clixml -Path mypoolinfo.xml
  ```
    b. Copie el archivo "mypoolinfo.xml" en el servidor que ejecuta el agente de escucha.
    
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

Por ejemplo, si desea supervisar los servidores que no están en su Skype para la topología de servidores de negocios--un Exchange Server, puede hacer una importación de servidor único en el host que ejecuta el agente de escucha. Para realizar la importación de un único servidor, siga estos pasos:
  
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
  
- ¿Es el agente registrado en el Administrador de las estadísticas?
    
1. 	Asegúrese de que ha seguido las instrucciones para importar la topología. Consulte [Importar la topología](deploy.md#BKMK_ImportTopology).  
    
2. Si el agente está en un servidor que no se incluye en la topología (por ejemplo, los nodos de un clúster SQL AlwaysOn), tendrá que agregar el agente manualmente siguiendo las instrucciones de [Importar la topología](deploy.md#BKMK_ImportTopology).
    
- ¿El agente puede contactar con el servicio de escucha?
    
1. Asegúrese de que el servicio de escucha está en funcionamiento.   
    
    Si no lo está, compruebe que Redis está en funcionamiento y, a continuación, intente reiniciar el servicio de escucha.
    
2. Asegúrese de que el puerto está abierto para el servicio de agente de escucha, y que el equipo del agente puede comunicarse con el puerto.
    
- Para asegurarse de que el Gestor de estadísticas está recopilando datos, puede comprobar el archivo CSV como sigue. 
    
    El siguiente comando recupera los nombres de almacenamiento de los contadores:   
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    El siguiente comando recupera los valores de los contadores especificados:  
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Para obtener información acerca de todos los eventos que puede ver en el registro de sucesos de aplicación, vea [Solucionar problemas de administrador de estadísticas de Skype para Business Server 2015](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Crear un certificado autofirmado
<a name="BKMK_SelfCert"> </a>

Microsoft recomienda encarecidamente usar un certificado firmado por una autoridad de certificación de confianza. Sin embargo, si desea usar un certificado autofirmado para realizar pruebas, haga lo siguiente: 
  
1. Desde una consola de PowerShell en la que haya iniciado sesión como administrador, escriba lo siguiente:
    
  ```
  New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
  ```

2. Tipo de `certlm.msc`. Se abrirá el administrador de certificados para el equipo local.
    
3. Vaya a **Personal**y abra **certificados**.
    
4. Haga clic con el botón secundario en **StatsManListener -\>todas las tareas -\>administrar claves privadas...**
    
5. Haga clic en **Agregar**.
    
6. En el cuadro **Escribir los nombres de objeto para seleccionar**, escriba Servicio de red.
    
7. Haga clic en **Aceptar**.
    
8. En **Control total**, desmarque la casilla **Permitir**. (Solo se requiere acceso con permiso de lectura).
    
9. Haga clic en **Aceptar**.
    
## <a name="for-more-information"></a>Para más información
<a name="BKMK_SelfCert"> </a>

Para obtener más información, consulte lo siguiente:
  
- [Plan para el Gestor de estadísticas de Skype para Business Server 2015](plan.md)
    
- [Actualizar estadísticas Administrador de Skype para Business Server 2015](upgrade.md)
    
- [Solucionar problemas de administrador de estadísticas de Skype para Business Server 2015](troubleshoot.md)
    
- [Skype para blog Business Manager de estadísticas de servidor](https://blogs.technet.microsoft.com/skypestatsman/)
    

