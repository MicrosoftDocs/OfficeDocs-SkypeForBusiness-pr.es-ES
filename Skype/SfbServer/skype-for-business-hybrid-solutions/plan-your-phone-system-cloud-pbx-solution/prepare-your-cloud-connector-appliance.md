---
title: Preparar el dispositivo de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Obtenga información sobre cómo preparar su dispositivo conector en la nube para la implementación y usar con el sistema telefónico en Office 365 (en la nube PBX).
ms.openlocfilehash: 3716c7c4b9d4b8daa0a4995ed7e3d77b400b587f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887319"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar el dispositivo de Cloud Connector

Obtenga información sobre cómo preparar su dispositivo conector en la nube para la implementación y usar con el sistema telefónico en Office 365 (en la nube PBX).

En esta sección se describe cómo obtener los archivos de instalación de Skype Empresarial Cloud Connector Edition, instalar el software Cloud Connector y preparar el dispositivo de Cloud Connector para la implementación. Después de completar todos los pasos de esta sección, estará listo para implementar Cloud Connector para un único sitio o para varios sitios. Si tiene una implementación existente de conector en la nube, y aún no ha actualizado a la nube conector versión 2.1, consulte [actualizar a una nueva versión del conector en la nube](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft admite la versión actual de la nube conector Edition, versión 2.1. Si ha configurado la actualización automática, Cloud Connector se actualizará automáticamente. Si ha configurado la actualización manual, debe actualizar a la versión 2.1 plazo de 60 días de su publicación. Microsoft admitirá la versión anterior para 60 días después del lanzamiento de 2.1 para permitir tiempo para actualizar. 

> [!NOTE]
> Para la nube conector versión 2.1 y versiones posterior, el dispositivo de host debe tener .NET Framework 4.6.1 o posterior instalado. 

> [!IMPORTANT]
> Para una implementación correcta, al ejecutar los cmdlets para configurar Skype para Business Edition de conector en la nube, use siempre la misma sesión de consola que la inició en. Evite cambiar a diferentes sesiones durante la implementación y la configuración. 

> [!NOTE]
> Hay algunos pasos que solo se realizan para el primer dispositivo de la implementación: la creación de un recurso compartido del directorio de sitios, la descarga de los bits y la preparación de un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Descargar el instalador de Skype Empresarial Cloud Connector Edition

1. En el servidor host donde se ejecutará el conector en la nube, las máquinas virtuales, descargue los archivos de instalación: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller). 

    > [!IMPORTANT]
    > El servidor host debe poder acceder a Internet durante la instalación de Cloud Connector porque se descargan archivos adicionales durante la instalación. 

2. Ejecute el instalador y acepte los valores predeterminados durante la instalación.

3. Confirme que la instalación se ha completado correctamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Comprobar la instalación y configurar el entorno

1. Abra una consola de PowerShell como administrador y confirme que la Skype para cmdlets de conector de nube Business Edition están disponibles mediante el siguiente cmdlet:

   ```
   Get-Command *-Cc*
   ```

    El comando debe devolver una lista de cmdlets de Skype para Business Edition de conector en la nube.

2. Los archivos VHDs, SfBBits y VersionInfo se almacenarán en el **Directorio de sitios**.

    Puede encontrar la ubicación del **Directorio de sitios** con el siguiente cmdlet:

   ```
   Get-CcSiteDirectory
   ```

    El comando debe devolver una ubicación de su sistema de archivos. La ubicación puede ser una carpeta local o un recurso compartido de archivos. La ubicación predeterminada del **Directorio de sitios** es: %USERPROFILE%\CloudConnector\SiteRoot. La ubicación predeterminada se debe cambiar a un recurso compartido de archivos en la primera aplicación que se cree en cada sitio.

    La ubicación que seleccione debe:

   - Crearse en el primer dispositivo creado en cada sitio.

   - Ser una carpeta compartida a la que pueden acceder los servidores host (dispositivos) del mismo sitio.

     Para establecer el **Directorio de sitios** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:

   ```
   Set-CcSiteDirectory <UNC File path>
   ```

    Si va a implementar la alta disponibilidad (HA) para el sitio, asegúrese de ejecutar el cmdlet para establecer el **Directorio de sitios** en la misma ubicación en cada servidor host del sitio.

    Al inicio de sesión e implementar cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tiene el derecho de acceso al **Directorio de sitios**.

3. El **Directorio del dispositivo** es el directorio raíz de trabajo local para Skype para Business Edition de conector en la nube y la ubicación donde se guardan los certificados externos, instancias y los registros. La ubicación predeterminada es: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Para encontrar la ubicación del **Directorio de aplicaciones**, ejecute el siguiente cmdlet:

   ```
   Get-CcApplianceDirectory
   ```

    Para establecer el **Directorio de aplicaciones** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:

   ```
   Set-CcApplianceDirectory <File path>
   ```

    El directorio de dispositivos debe establecerse en una carpeta local del dispositivo. Sólo debe establecer el **Directorio de dispositivo** antes de empezar la Skype para la implementación de Business Edition de conector en la nube. Si lo cambia después, tendrá que volver a implementar el servidor host.

    > [!IMPORTANT]
    > La ruta de acceso al **Directorio de aplicaciones** no puede contener espacios.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Establecer la ruta de acceso del certificado perimetral externo

- Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre del archivo, al certificado perimetral externo. Por ejemplo: C:\certs\cce\ap.contoso.com.pfx. El certificado no puede contener claves privadas.

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Tenga en cuenta que el parámetro -Target es específico de la versión 1.4.2 y las versiones posteriores. 

    Especifique la ruta de acceso completa al certificado externo, incluido el nombre del archivo. El certificado se puede almacenar localmente o en un recurso compartido de archivos. Si el certificado se almacena en una carpeta compartida, esta deberá crearse en el primer dispositivo de cada sitio y los demás dispositivos que pertenezcan al mismo sitio deben poder acceder a ella. Este cmdlet copia el certificado externo en el **directorio de dispositivos**.

    > [!IMPORTANT]
    > **Si ha actualizado a Cloud Connector versión 1.4.2 o posterior**, asegúrese de que el certificado externo preparado contenga claves privadas y la cadena de certificados completa, incluidos el certificado de CA raíz y los certificados de CA intermedios. **Si aún NO ha actualizado a Cloud Connector versión 1.4.2**, asegúrese de que el certificado externo preparado contenga claves privadas. Este certificado externo lo debe emitir una entidad de certificación en la que Windows confíe de manera predeterminada.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Establecer la ruta de acceso del certificado de la puerta de enlace RTC/SBC

Si va a utilizar TLS entre el servidor de mediación y la puerta de enlace RTC/SBC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, al certificado de la puerta de enlace. Por ejemplo: C:\certs\cce\sbc.contoso.com.cer. El certificado debe contener la CA raíz y la cadena intermedia del certificado asignado a la puerta de enlace:

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Tenga en cuenta que el parámetro -Target es específico de la versión 1.4.2 y las versiones posteriores. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Crear conmutadores virtuales en el Administrador de Hyper-V

1. Abra el **Administrador de Hyper-V** > **Virtual Switch Manager**y seleccione **Nuevo administrador de conmutador Virtual**.

2. Cree un conmutador virtual externo y enlácelo al adaptador de red físico que está conectado al dominio de red interno:

    Seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

3. Cree un conmutador virtual externo y enlazar al adaptador de red físico que se enruta a Internet:

    Anule la selección **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

4. Establecer el nombre del conmutador que se conecta a la red perimetral a su dominio de red interna **SfB CCE Corpnet cambiar**.

    Establecer el nombre del conmutador que se conecta a la red perimetral a la Internet **SfB CCE Internet cambiar**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Actualizar el archivo de configuración CloudConnector.ini

Preparar el archivo de CloudConnector.ini con la información recopilada en [los parámetros de implementación Determine](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema de [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md) .

Para actualizar el archivo, ejecute primero el siguiente cmdlet para obtener la plantilla de muestra (CloudConnector.Sample.ini):

```
Export-CcConfigurationSampleFile
```

La plantilla de muestra está almacenada en el **Directorio de aplicaciones**.

Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector.ini en el **Directorio de aplicaciones**. Puede ejecutar **Get-CcApplianceDirectory** para determinar la ruta de acceso al **Directorio de aplicaciones**.

Al actualizar el archivo .ini, tenga en cuenta lo siguiente:

> [!NOTE]
> No todos los valores del archivo .ini se tratan en esta sección, solo los que tengan una consideración especial. Para obtener una lista completa, vea la sección [parámetros de implementación Determine](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del tema de [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md) . Para obtener más información acerca de los valores que se deben cambiar para los dispositivos adicionales o los sitios nuevos, consulte [Sitio único con HA comparado con implementaciones de varios sitios](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en el tema [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** El valor predeterminado es **Site1**. Debe actualizarlo antes de implementar Cloud Connector, porque al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio nuevo o existente, el cmdlet usará **SiteName** para determinar qué sitio se debe registrar.

     Si desea registrar el dispositivo en un sitio nuevo, el valor de **SiteName** debe ser único y diferente de los sitios existentes. Si desea registrar el dispositivo a un sitio existente, el valor de **nombre del sitio** en el archivo .ini debe coincidir con el nombre definido en la configuración del inquilino de Office 365. Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **SiteName** para cada sitio tal como corresponda.

- **ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe estar limitado a 15 caracteres. 

- **HardwareType:** Si no establece o deje el valor en null, se usará el valor predeterminado de **Normal** . Utilice **Normal** si tiene previsto implementar la versión mayor del conector en la nube para admitir llamadas simultáneas 500 por máquina del host como se describe en [Plan for Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md). Use **Minimum** para una versión más pequeña que admita 50 llamadas simultáneas.

- **Modificadores virtuales de Internet/Corpnet de administración:**: agregar el nombre de los modificadores virtuales que haya creado. Para el modificador virtual de administración, deje el valor predeterminado. El script de implementación creará el conmutador virtual administración al principio de la implementación y eliminarlo cuando finalice la implementación.

- **ManagementIPPrefix:** ManagementIPPrefix en la sección de Red debe ser una subred diferente de otras IP internas. Por ejemplo, tal como muestra el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.

    Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una IP de administración y lo conectan a un conmutador virtual de administración. Esto permite al servidor host conectarse a cada máquina virtual y administrarlas mediante esta red de administración. El conmutador virtual de administración se elimina cuando finaliza la administración.

- **Configuraciones específicas de la máquina virtual base:** La configuración de esta sección debe estar configurada para el cmdlet **Convert-CcIsoToVhdx**.

    Durante la preparación de la imagen de la máquina virtual base, esta se conectará al conmutador de red interno. Las siguiente configuración es fundamental para que la máquina virtual pueda acceder a Internet:

  - [Common]BaseVMIP: la dirección IP de la red corporativa que se asignará a la máquina virtual base.

  - [Network]CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.

  - [Network]CorpnetDNSIPAddress: la dirección IP de DNS IP que se asignará a la máquina virtual base.

  - [Network]WSUSServer: la dirección IP de Windows Server Update Service.

  - [Network]WSUSStatusServer: la dirección IP del servidor de estado de Windows Server Update Service.

  - [Network]EnableReferSupport: define si se habilita o se deshabilita el soporte de SIP REFER en la configuración de tronco de su IP/PBX.

- **IP internas:**

  - Asegúrese de que la máscara de subred CorpnetIPPrefixLength es correcta.

  - Asegúrese de que no hay ningún conflicto IP para estas direcciones IP interna.

- **IP externas:**

  - Para IP públicas MR: especifique ExternalMRIPs para que no sean de NAT o ExternalMRPublicIPs para NAT.

  - ExternalSIPIPs y ExternalMRIPs puede ser la misma.

  - Asegúrese de que la máscara de subred InternetIPPrefixLength es correcta.

  - Asegúrese de que no hay ningún conflicto IP para estas direcciones IP externas.

- **Puertas de enlace:**

  - Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria. Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente, y después actualizándola.

  - Asegúrese de que la dirección IP y los puertos de las puertas de enlace sean correctos.

  - Para que la puerta de enlace RTC de alta disponibilidad sea compatible, deje la puerta de enlace secundaria y agregue las puertas de enlace secundarias que vaya a usar. Puede copiar y pegar una entrada existente y, a continuación, actualizarlo.

- Opcionalmente, puede actualizar el valor de LocalRoute para restringir los números de llamada salientes.

## <a name="download-the-bits-to-the-site-directory"></a>Descargar los bits en el Directorio de sitios

Ejecute el siguiente cmdlet para descargar los bits y los archivos de información de la versión en el **Directorio de sitios**:

```
Start-CcDownload
```

> [!NOTE]
> Deberá realizar este paso solo para el primer dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar el disco virtual base (VHDX) desde el archivo ISO descargado

Este paso prepara un archivo de disco duro virtual (VHDX) de la imagen ISO de Windows Server 2012. El VHDX se usará para crear máquinas virtuales durante la implementación. Se creará una máquina virtual temporal (base VM) y Windows Server 2012 se va a instalar desde el archivo ISO. Una vez creada la máquina virtual, se instalarán algunos componentes necesarios y se aplicará la actualización de Windows más reciente. Al final, la máquina virtual base se generalizará (Sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.

> [!NOTE]
> Deberá realizar este paso solo para el primer dispositivo. 

Antes de continuar con este paso, asegúrese de que se haya creado el conmutador de red corporativa. Además, confirme que las siguientes opciones se hayan configurado correctamente en el archivo CloudConnector.ini:

- [Network]CorpnetSwitchName

- [Common]BaseVMIP

- [Network]CorpnetIPPrefixLength

- [Network]CorpnetDefaultGateway

- [Network]CorpnetDNSIPAddress

Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO a un disco duro virtual (VHD):

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique la ruta de acceso completa, incluido el nombre del archivo, a la imagen ISO. Por ejemplo: C:\ISO\WindowsServer2012R2.iso.

El archivo VHD creado se almacena en la carpeta de \Bits\VHD del **Directorio de sitios** . Puede obtener la ruta de acceso al **Directorio de sitios** ejecutando **Get-CcSiteDirectory**.

> [!IMPORTANT]
> De manera predeterminada, la configuración del proxy no se configura en la máquina virtual base. Si se requiere un servidor proxy en su entorno de red para actualizar la máquina virtual a través de Windows Update, debe agregar el modificador - PauseBeforeUpdate cuando se ejecuta "Convert-CcIsoToVhdx". La secuencia de comandos hará una pausa antes de la actualización de Windows y tendrá una oportunidad para configurar manualmente el proxy en la máquina virtual. Después de que se configure el proxy y que la máquina virtual pueda acceder a Internet, podrá reanudar el script para completar los pasos restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Crear VHD para una implementación de varios sitios

Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.

Si va a realizar una implementación de varios sitios, no necesita convertir el ISO en VHD para cada sitio. Puede copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.

 Copie el archivo en la misma ubicación de archivo ( **Directorio de sitios** \Bits\VHD carpeta) y con el mismo nombre de archivo, en el servidor host para un sitio adicional.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Establecer la directiva de ejecución de PowerShell en RemoteSigned

Los scripts de PowerShell proporcionados requieren que la directiva de ejecución se establezca en RemoteSigned. Para ver la configuración actual, abra una consola de PowerShell como administrador y después ejecute el siguiente cmdlet:

```
Get-ExecutionPolicy
```

Si no se establece como "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:

```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Cambiar la directiva de grupo local del equipo host (versiones 1.4.1 y anteriores)

> [!NOTE]
> Esta tarea no se requiere para la versión 1.4.2 de Cloud Connector y otras versiones posteriores. 

La cuenta CceService se crea durante la implementación de Skype Empresarial Cloud Connector Edition. Se ejecuta el servicio de administración del conector de la nube y requiere permiso para desinstalar el cloudconnector.msi. Debe cambiar la configuración de la directiva de grupo del equipo host de Cloud Connector para especificar que el registro de usuarios no se descargue cuando el usuario cierre sesión. Siga los pasos siguientes:

### <a name="to-change-the-group-policy-setting"></a>Para cambiar la configuración de la directiva de grupo

1. Abra el **Editor de directiva de grupo** mediante la ejecución de gpedit.msc.

2. En el **Editor de directivas de grupo**, navegue a Plantillas administrativas > Sistema > Perfil de usuario > No descargar forzosamente el Registro de usuarios al cerrar la sesión de usuario.  

3. Establezca su valor en **habilitado**.

## <a name="set-up-your-office-365-tenant"></a>Configurar el inquilino de Office 365

Se requiere un inquilino de Office 365 con Skype para profesionales en línea y el sistema de teléfono en Office 365. Asegúrese de que el inquilino es y que esté configurado antes de intentar usar el conector de la nube.

Algunos pasos del programa de instalación de Office 365 requieren que se use PowerShell remoto de inquilino (TRPS) para configurar al inquilino de Office 365. **Se debe instalar en el servidor host.** Puede descargar el Skype para módulo empresarial en línea para PowerShell desde: [Skype para Online de negocio, módulo de Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Crear un Skype dedicada para la cuenta de administrador empresarial para la administración en línea de conector en la nube, por ejemplo CceOnlineManagmentAdministrator. Esta cuenta la usará la aplicación para agregar o quitar aplicaciones, habilitar o deshabilitar actualizaciones automáticas del sistema operativo, habilitar o deshabilitar actualizaciones automáticas de archivos binarios. Establezca la contraseña para que esta cuenta no expire nunca y no haya que cambiarla para el servicio cada vez que expire.


