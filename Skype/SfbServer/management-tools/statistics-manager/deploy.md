---
title: Implementar el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumen: lea este tema para obtener información sobre cómo implementar el Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675992"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Implementar el administrador de estadísticas para Skype Empresarial Server

**Resumen:** Lea este tema para obtener información sobre cómo implementar el Administrador de estadísticas para Skype Empresarial Server.

 El Administrador de estadísticas para Skype Empresarial Server es una herramienta eficaz que le permite ver Skype Empresarial Server datos de estado y rendimiento en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas.

Antes de intentar instalar el Administrador de estadísticas, asegúrese de que está familiarizado con los requisitos de software, redes y hardware. Para obtener más información, vea [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md).

> [!NOTE]
> Si va a actualizar desde una versión anterior del Administrador de estadísticas, consulte Actualizar administrador de [estadísticas para Skype Empresarial Server](upgrade.md).

> [!NOTE]
> El sitio web del Administrador de estadísticas se ha probado y funciona correctamente en Internet Explorer 11+, Edge 20.10240+ y Chrome 46+ (versión actual de evergreen).

Puede encontrar el Administrador de estadísticas descargable en [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).

En este tema se presentan las siguientes secciones:

- [Implementación del Administrador de estadísticas](deploy.md#BKMK_Deploy)

- [Solución de problemas de la implementación](deploy.md#BKMK_Troubleshoot)

- [Creación de un certificado autofirmado](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>Implementación del Administrador de estadísticas
<a name="BKMK_Deploy"> </a>

Para implementar el Administrador de estadísticas, siga estos pasos:

1. Prepare la máquina host del agente de escucha instalando el sistema de almacenamiento en caché en memoria de Redis y asegurándose de que ha instalado los certificados adecuados.

2. Instale el servicio de escucha en el equipo host.

3. Instale el sitio web en el equipo host.

4. Instale un agente en cada máquina Skype Empresarial Server que desee supervisar.

5. Importe la topología de los servidores que está supervisando.

> [!NOTE]
> Redis, el servicio de escucha y el sitio web deben estar instalados en la misma máquina host. Asegúrese de que la máquina host no tiene Skype Empresarial Server instalado.

### <a name="prepare-the-listener-host-machine"></a>Preparación de la máquina host del agente de escucha

Para preparar la máquina host, deberá instalar el sistema de almacenamiento en caché en memoria de Redis y asegurarse de que hay un certificado válido en la máquina. Microsoft recomienda instalar la compilación estable más reciente de Redis 3.0. La versión 2.0 del Administrador de estadísticas se probó con Redis 3.2.100.

1. Descargue Redis desde el siguiente sitio: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).

    Los instaladores sin firmar se pueden descargar desde [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    Los archivos binarios firmados están disponibles a través de administradores de paquetes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) y [Choclatey](https://chocolatey.org/packages/redis-64).

   - Ejecute el archivo MSI proporcionado y siga las indicaciones.

   - No active la casilla para agregar una regla de firewall.

2. El servicio de escucha requiere un certificado. Microsoft recomienda encarecidamente que tenga un certificado firmado por una entidad de certificación de confianza.

    Si desea usar un certificado autofirmado(para fines de prueba en un laboratorio, por ejemplo), consulte [Creación de un certificado autofirmado](deploy.md#BKMK_SelfCert).

    El agente usa la comprobación de huella digital del certificado (en lugar de la verificación en cadena). No realizará la validación completa de certificados porque es posible usar certificados autofirmados.

### <a name="install-the-listener-service"></a>Instalación del servicio de escucha

Instale el servicio de escucha en la máquina host ejecutando el StatsManPerfAgentListener.msi y especificando lo siguiente:

1. Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.

2. En la página siguiente, especifique la siguiente información:

   - **Contraseña del servicio:** Los agentes remotos usan esta contraseña para autenticarse en el servicio de escucha.

   - **Puerto de servicio:** El agente de escucha usa este número de puerto HTTPS para comunicarse con los agentes. Durante la instalación, este puerto se permitirá a través del firewall local, se creará una ACL de dirección URL y se enlazará un certificado SSL a este puerto. El valor predeterminado es 8443.

   - **Huella digital del certificado:** El agente de escucha usa este certificado para cifrar el protocolo HTTPS. El servicio de red debe tener acceso de lectura a la clave privada.

     Haga clic en el botón **Seleccionar...** para elegir la huella digital.

     Puede encontrar la huella digital del certificado mediante el Administrador de certificados o mediante el siguiente comando de PowerShell:

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **Instalar Dir:** Este directorio es donde se instalarán los archivos binarios. Puede cambiarlo del valor predeterminado mediante el botón **Examinar...**

   - **AppData Dir:** Este directorio es donde se almacenarán la carpeta Registros y otros datos. Puede cambiarlo del valor predeterminado. No se eliminará al desinstalar.

3. Haga clic en **Instalar**.

Para validar la instalación, siga estos pasos:

1. Abra un explorador y vaya a `https://localhost:<service-port>/healthcheck/`.

    De forma predeterminada, el puerto de servicio es 8443 (a menos que especifique otro puerto).

2. Para asegurarse de que el agente de escucha se ha instalado correctamente, busque lo siguiente:

   - Si se muestra la página healthcheck, la instalación del agente de escucha se realizó correctamente.

   - Si KnownServerCount es 1 o superior, se establece la conexión a Redis.

   - Después de esperar unos minutos y después de instalar al menos un agente, compruebe que el contador ValuesWritten se está incrementando.

### <a name="install-the-website"></a>Instalación del sitio web

Instale el sitio web en el equipo host ejecutando el StatsManWebSite.msi (incluido con [Skype Empresarial Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/download/details.aspx?id=57518)):

1. Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.

2. En la página siguiente, especifique la siguiente información:

   - **Puerto de servicio:** Este puerto TCP es donde escuchará el sitio web. Puede cambiarlo más adelante mediante el enlace del administrador de IIS. Durante la instalación, este puerto se permitirá a través del firewall local.

   - **Instalar Dir:** Este directorio es donde se instalarán los archivos binarios. Puede cambiarlo del valor predeterminado mediante el botón **Examinar...**

   - **AppData Dir:** Este directorio es donde se almacenarán la carpeta Registros y otros datos. Puede cambiarlo del valor predeterminado. No se eliminará al desinstalar.

3. Haga clic en **Instalar**.

Para ver el sitio web, abra un explorador y vaya a: `http://<localhost:webport/>`.

Para ver solo la información de mantenimiento, abra un explorador y vaya a: `http://localhost:<webport>/healthcheck/`.

De forma predeterminada, el número de puerto web es 8080. Puede cambiar el enlace de puerto del sitio web mediante el administrador de IIS.

El instalador web agrega un grupo de seguridad local, denominado StatsManWebSiteUsers. Puede agregar cuentas a este grupo de seguridad para conceder acceso al sitio web.

### <a name="install-the-agents"></a>Instalación de los agentes

Instale un agente en cada Skype Empresarial Server que desee supervisar mediante la ejecución del StatsManPerfAgent.msi:

1. Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.

2. En la página siguiente, especifique la siguiente información:

   - **Contraseña del servicio:** El agente remoto usa esta contraseña para autenticarse en el servicio de escucha.

   - **URI del servicio:** Esta dirección URL es donde reside el agente de escucha. Use el `https://name:port` formato .

     Puede usar un nombre NETBIOS o un FQDN. Puede usar el nombre que también se especifica como el **firmante** o **los nombres alternativos del firmante** del certificado en el servicio de escucha, pero esto no es un requisito.

   - **Huella digital del servicio:** El agente de escucha usa este certificado SS: . El agente usará esta huella digital para autenticarse en el agente de escucha. No realizará la validación completa de certificados porque es posible usar certificados autofirmados.

   - **Instalar Dir:** Este directorio es donde se instalarán los archivos binarios. Puede cambiarlo del valor predeterminado mediante el botón **Examinar...**

   - **AppData Dir:** Este directorio es donde se almacenarán la carpeta Registros y el archivo password.txt cifrado. Puede que gracias cámbielo del valor predeterminado. No se eliminará al desinstalar.

3. Haga clic en **Instalar**.

Si va a instalar un agente en numerosas máquinas, probablemente querrá hacerlo en modo desatendido. Por ejemplo:

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importación de la topología
<a name="BKMK_ImportTopology"> </a>

Una vez instalado y en ejecución el Administrador de estadísticas, debe importar la topología Skype Empresarial Server para que el Administrador de estadísticas conozca el sitio, el grupo y el rol de cada servidor. Para importar la topología de Skype Empresarial Server, usará el cmdlet [Get-CsPool](/powershell/module/skype/get-cspool) para recuperar información sobre cada grupo en uso en su organización y, a continuación, importar esta información en el Administrador de estadísticas.

Para importar la topología de Skype Empresarial Server, siga estos pasos:

1. En un host que tiene los cmdlets de PowerShell Skype Empresarial Server:

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

3. Para confirmar qué servidores se agregan y actualizan, ejecute el siguiente comando:

   ```console
   .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

El siguiente comando le permite ver todas las opciones:

```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed
```

Para ver la información del servidor importado actualmente, ejecute el siguiente script:

```powershell
.\Get-StatsManServerInfo.ps1
```

Si desea supervisar los servidores que no están en la topología de Skype Empresarial Server (un Exchange Server, por ejemplo), puede realizar una importación de servidor único en el host que ejecuta el agente de escucha. Para realizar una importación de servidor único, siga estos pasos:

1. Vaya al directorio en el que está instalado el agente de escucha. El valor predeterminado es:

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Ejecute el siguiente comando:

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Solución de problemas de la implementación
<a name="BKMK_Troubleshoot"> </a>

Si un agente no se inicia, compruebe si hay los siguientes problemas:

- ¿El agente está registrado en el Administrador de estadísticas?

   1. Asegúrese de seguir las instrucciones para importar la topología. Consulte [Importación de la topología](deploy.md#BKMK_ImportTopology).

   2. Si el agente está en un servidor que no aparece en la topología (por ejemplo, los nodos de un clúster de AlwaysOn SQL), deberá agregar el agente manualmente siguiendo las instrucciones de [Importación de la topología](deploy.md#BKMK_ImportTopology).

- ¿Puede el agente ponerse en contacto con el agente de escucha?

   1. Asegúrese de que el servicio de escucha está en ejecución.

      Si no se está ejecutando, asegúrese de que Redis se está ejecutando y, a continuación, intente reiniciar el agente de escucha.

   2. Asegúrese de que el puerto está abierto al servicio de escucha y de que el equipo del agente puede comunicarse con el puerto.

- Para asegurarse de que el Administrador de estadísticas está recopilando datos, puede comprobar el archivo CSV como se indica a continuación.

    El siguiente comando recupera los nombres de almacenamiento del contador:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    El siguiente comando recupera los valores de los contadores especificados:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Para obtener información sobre todos los eventos que puede ver en el registro de eventos de la aplicación, consulte [Solución de problemas del Administrador de estadísticas para Skype Empresarial Server](troubleshoot.md).

## <a name="create-a-self-signed-certificate"></a>Creación de un certificado autofirmado
<a name="BKMK_SelfCert"> </a>

Microsoft recomienda encarecidamente usar un certificado firmado por una entidad de certificación de confianza. Sin embargo, si desea usar un certificado autofirmado con fines de prueba, siga estos pasos:

1. Desde una consola de PowerShell mientras ha iniciado sesión como administrador, ejecute el siguiente comando:

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Escriba  `certlm.msc`. Se abrirá el Administrador de certificados de la máquina local.

3. Vaya a **Personal** y abra **Certificados**.

4. Haga clic con el botón derecho en **StatsManListener- \> Todas las tareas- \>Administrar claves privadas...**

5. Haga clic en **Agregar**.

6. En el cuadro **Escribir los nombres de objeto que se van a seleccionar** , escriba el texto siguiente: Servicio de red

7. Haga clic en **Aceptar**.

8. En **Control total**, des active la casilla **Permitir** . (Solo es necesario el acceso de lectura).

9. Haga clic en **Aceptar**.

## <a name="for-more-information"></a>Más información
<a name="BKMK_SelfCert"> </a>

Para obtener más información, consulte los siguientes temas:

- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)

- [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md)

- [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)
