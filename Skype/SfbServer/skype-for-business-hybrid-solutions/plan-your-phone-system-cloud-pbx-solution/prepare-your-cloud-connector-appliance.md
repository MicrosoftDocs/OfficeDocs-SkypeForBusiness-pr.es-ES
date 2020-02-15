---
title: Preparar el dispositivo de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con el sistema telefónico en Office 365 (PBX en la nube).
ms.openlocfilehash: 6dbbc7eb1639859f889d6674e9f000507912d35a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983845"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar el dispositivo de Cloud Connector

Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con el sistema telefónico en Office 365 (PBX en la nube).

En esta sección se describe cómo obtener los archivos de instalación de Skype empresarial Cloud Connector Edition, instalar el software de Cloud Connector y preparar el dispositivo de Cloud Connector para su implementación. Una vez que haya completado todos los pasos de esta sección, estará listo para implementar Cloud Connector para un único sitio o varios sitios. Si tiene una implementación existente de Cloud Connector y aún no ha actualizado a la versión 2,1 de Cloud Connector, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft admite la versión actual de Cloud Connector Edition, versión 2,1. Si ha configurado la actualización automática, Cloud Connector se actualizará automáticamente. Si ha configurado la actualización manual, deberá actualizar a la versión 2,1 en un plazo de 60 días a partir de su publicación. Microsoft admitirá la versión anterior durante 60 días después de la publicación de 2,1 para permitirle el tiempo de actualización. 

> [!NOTE]
> Para la versión 2,1 de Cloud Connector y versiones posteriores, el dispositivo de host debe tener instalado .NET Framework 4.6.1 o posterior. 

> [!IMPORTANT]
> Para una implementación correcta, al ejecutar los cmdlets para configurar Skype empresarial Cloud Connector Edition, use siempre la misma sesión de consola que la que comenzó en. Evite cambiar a sesiones diferentes durante la implementación y la configuración. 

> [!NOTE]
> Hay algunos pasos que debe realizar para el primer dispositivo de la implementación: crear un recurso compartido para el directorio de sitios, descargar los bits y preparar un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Descargar el instalador de Skype empresarial Cloud Connector Edition

1. En el servidor host donde se ejecutarán las máquinas virtuales de Cloud Connector, descargue los [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)archivos de instalación:. 

    > [!IMPORTANT]
    > El servidor host debe poder acceder a Internet durante la instalación de Cloud Connector, ya que los archivos adicionales se descargan durante la instalación. 

2. Ejecute el instalador y acepte los valores predeterminados durante la instalación.

3. Confirme que la instalación se completó correctamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Comprobación de la instalación y configuración del entorno

1. Abra una consola de PowerShell como administrador y confirme que los cmdlets de Skype empresarial Cloud Connector Edition están disponibles mediante el siguiente cmdlet:

   ```powershell
   Get-Command *-Cc*
   ```

    El comando debe devolver una lista de cmdlets para Skype empresarial Cloud Connector Edition.

2. Los archivos VHD, SfBBits y VersionInfo se almacenarán en el **Directorio de sitios**.

    Puede encontrar la ubicación del directorio de **sitios** con el siguiente cmdlet:

   ```powershell
   Get-CcSiteDirectory
   ```

    El comando debe devolver una ubicación en el sistema de archivos. La ubicación puede ser una carpeta local o un recurso compartido de archivos. La ubicación predeterminada del **Directorio de sitios** es:%userprofile%\CloudConnector\SiteRoot. La ubicación predeterminada debe cambiarse a un recurso compartido de archivos en el primer dispositivo creado en cada sitio.

    La ubicación que seleccione debe ser:

   - Se crea en el primer dispositivo creado en cada sitio.

   - Una carpeta compartida a la que tengan acceso los otros servidores host (equipos) en el mismo sitio.

     Para establecer el **Directorio de sitios** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Si va a implementar la alta disponibilidad (HA) para el sitio, asegúrese de ejecutar el cmdlet para establecer el **Directorio de sitios** en la misma ubicación en cada servidor host dentro del sitio.

    Cuando inicie sesión e implemente cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tiene el acceso adecuado al **Directorio de sitios**.

3. El **directorio** de la aplicación es el directorio raíz de trabajo local de Skype empresarial Cloud Connector Edition y la ubicación donde se guardan los certificados, las instancias y los registros externos. La ubicación predeterminada es:%USERPROFILE%\CloudConnector\ApplianceRoot.

    Para encontrar la ubicación del **Directorio de dispositivos**, ejecute el siguiente cmdlet:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Para establecer el **directorio del dispositivo** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    El directorio de la aplicación debe establecerse en una carpeta local del dispositivo. Solo debe establecer el **Directorio de dispositivos** antes de iniciar la implementación de Skype empresarial Cloud Connector Edition. Si lo cambia después de la implementación, tendrá que volver a implementar el servidor host.

    > [!IMPORTANT]
    > La ruta de acceso al directorio de la **aplicación** no debe contener espacios.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Establecer la ruta de acceso para el certificado perimetral externo

- Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado perimetral externo. Por ejemplo: C:\certs\cce\ap.contoso.com.pfx. El certificado debe contener claves privadas.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Tenga en cuenta que el parámetro-Target es específico de las versiones 1.4.2 y posteriores. 

    Especifique la ruta de acceso completa al certificado externo, incluido el nombre de archivo. El certificado se puede almacenar localmente o en un recurso compartido de archivos. Si el certificado se almacena en una carpeta compartida, la carpeta compartida debe crearse en el primer dispositivo de cada sitio y debe ser accesible para otros dispositivos que pertenezcan al mismo sitio. Este cmdlet copia el certificado externo en el **Directorio de dispositivos**.

    > [!IMPORTANT]
    > **Si ha actualizado a Cloud Connector versión 1.4.2 o posterior**, asegúrese de que el certificado externo preparado contenga claves privadas y la cadena de certificados completa, incluidos el certificado de CA raíz y los certificados de CA intermedios. **Si aún no ha actualizado a Cloud Connector versión 1.4.2**, asegúrese de que el certificado externo preparado contenga claves privadas. Este certificado externo debe ser emitido por una entidad de certificación que sea de confianza para Windows de forma predeterminada.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Establecer la ruta de acceso para el certificado de la puerta de enlace RTC/SBC externo

Si está usando TLS entre el servidor de mediación y la puerta de enlace o el SBC RTC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado de puerta de enlace. Por ejemplo: C:\certs\cce\sbc.contoso.com.cer. El certificado debe contener la entidad de certificación raíz y la cadena intermedia para el certificado asignado a la puerta de enlace:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Tenga en cuenta que el parámetro-Target es específico de las versiones 1.4.2 y posteriores. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Crear conmutadores virtuales en el administrador de Hyper-V

1. Abra el administrador de > **conmutadores virtuales**de **Administrador de Hyper-V**y seleccione **nuevo administrador de conmutadores virtuales**.

2. Cree un conmutador virtual externo y enlácelo al adaptador de red físico que está conectado al dominio de red interna:

    Seleccione **permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

3. Cree un conmutador virtual externo y enlácelo al adaptador de red físico que se redirige a Internet:

    Anule la selección de permitir que el **sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

4. Establezca el nombre del conmutador que conecta la red perimetral al dominio de red interno **SfB de CorpNet CorpNet**.

    Establezca el nombre del conmutador que conecta la red perimetral a Internet **SFB CCE Internet switch**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Actualizar el archivo de configuración de CloudConnector. ini

Prepare el archivo CloudConnector. ini con la información que recopiló en [determinar los parámetros de implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .

Para actualizar el archivo, primero ejecute el siguiente cmdlet para obtener la plantilla de ejemplo (CloudConnector. sample. ini):

```powershell
Export-CcConfigurationSampleFile
```

La plantilla de muestra se almacena en el **Directorio de dispositivos**.

Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector. ini en el **Directorio de dispositivos**. Puede ejecutar **Get-CcApplianceDirectory** para determinar la ruta de acceso al **Directorio de dispositivos**.

Al actualizar el archivo. ini, tenga en cuenta lo siguiente:

> [!NOTE]
> No todos los valores del archivo. ini se describen en esta sección, solo se tratan los que tienen una consideración especial. Para obtener una lista completa, consulte la sección [determinar los parámetros de implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del tema [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Para obtener más información sobre los valores que deben cambiarse para dispositivos adicionales o para nuevos sitios, vea [un único sitio con alta disponibilidad (ha) comparado con implementaciones de varios sitios](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en el tema [deploy Multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** El valor predeterminado es **sitio1**. Debe actualizarlo antes de implementar Cloud Connector, ya que al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio nuevo o existente, el cmdlet usará **siteName** para determinar qué sitio registrar.

     Si desea registrar el dispositivo en un sitio nuevo, el valor de **siteName** debe ser único y diferente de los sitios existentes. Si desea registrar el dispositivo en un sitio existente, el valor de **siteName** en el archivo. ini debe coincidir con el nombre definido en la configuración de inquilino de Office 365. Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **siteName** para cada sitio en consecuencia.

- **ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe estar limitado a 15 caracteres.

- **HardwareType:** Si no establece o deja el valor en null, se usará el valor predeterminado de **normal** . Use **normal** si tiene previsto implementar la versión más grande de Cloud Connector para admitir 500 llamadas simultáneas por equipo host, como se describe en [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Use **Minimum** para una implementación más pequeña que admita 50 llamadas simultáneas.

- **Conmutadores virtuales de Internet/red corporativa/administración:** agregue el nombre de los conmutadores virtuales que ha creado. Para el conmutador virtual de administración, deje el valor predeterminado. El script de implementación creará el conmutador virtual de administración al principio de la implementación y lo eliminará cuando finalice la implementación.

- **ManagementIPPrefix:** ManagementIPPrefix en la sección red debe ser una subred diferente de otras IP internas. Por ejemplo, como se muestra el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.

    Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una IP de administración y la conectan a un conmutador virtual de administración. Esto permite que el servidor host se conecte a cada máquina virtual y la administre a través de esta red de administración. El conmutador virtual de administración se elimina al finalizar la implementación.

- **Configuraciones específicas de la máquina virtual base:** La configuración de esta sección debe estar configurada para el cmdlet **Convert-CcIsoToVhdx** .

    Durante la preparación de la imagen de la máquina virtual base, la máquina virtual base se conectará al conmutador de red interna. La siguiente configuración es fundamental para que la máquina virtual pueda acceder a Internet:

  - Comunes BaseVMIP: la dirección IP de CorpNet que se asignará a la máquina virtual base.

  - Red CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.

  - Red Cropnetdnsipaddress: la dirección IP de DNS que se asignará a la máquina virtual base.

  - Red WSUSServer: la dirección IP del servicio de actualización de Windows Server.

  - Red WSUSStatusServer: la dirección IP del servidor de estado del servicio de actualización de Windows Server.

  - Red EnableReferSupport: define si la compatibilidad con SIP REFER está habilitada o deshabilitada en la configuración del tronco de su IP/PBX.

- **IP internas:**

  - Asegúrese de que la máscara de subred Corpnetlpprefixlength es correcta.

  - Asegúrese de que no haya conflictos de IP en estas IP internas.

- **IP externas:**

  - Para la IP pública del MR: especifique ExternalMRIPs para NAT no NAT o ExternalMRPublicIPs para NAT.

  - ExternalSIPIPs y ExternalMRIPs pueden ser iguales.

  - Asegúrese de que la máscara de subred InternetIPPrefixLength es correcta.

  - Asegúrese de que no haya conflictos de IP en estas IP externas.

- **Puertas**

  - Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria. Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente y, a continuación, actualizándolos.

  - Asegúrese de que la dirección IP y el puerto de las puertas de enlace sean correctos.

  - Para admitir el nivel de puerta de enlace RTC, deje la puerta de enlace secundaria y agregue las puertas de enlace adicionales que vaya a usar. Puede copiar y pegar una entrada existente y, a continuación, actualizarla.

- Si lo desea, puede actualizar el valor de LocalRoute para restringir los números de llamadas salientes.

## <a name="download-the-bits-to-the-site-directory"></a>Descargar los bits en el directorio de sitios

Ejecute el siguiente cmdlet para descargar los bits y los archivos de información de la versión en el **Directorio de sitios**:

```powershell
Start-CcDownload
```

> [!NOTE]
> Debe realizar este paso solo para el primer dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar el disco virtual base (VHDX) desde el archivo ISO descargado

Este paso prepara un archivo de disco duro virtual (VHDX) a partir de la imagen ISO de Windows Server 2012. El VHDX se usará para crear máquinas virtuales durante la implementación. Se creará una máquina virtual temporal (VM base) y se instalará Windows Server 2012 desde el archivo ISO. Una vez creada la máquina virtual, se instalarán algunos de los componentes necesarios y se aplicará la última actualización de Windows. Al final, la máquina virtual base se generalizará (Sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.

> [!NOTE]
> Debe realizar este paso solo para el primer dispositivo. 

Antes de continuar con este paso, asegúrese de que se haya creado el conmutador de red corporativa. Además, confirme que las siguientes opciones de configuración están correctamente configuradas en el archivo CloudConnector. ini:

- Red CorpnetSwitchName

- Comunes BaseVMIP

- Red Corpnetlpprefixlength

- Red CorpnetDefaultGateway

- Red Cropnetdnsipaddress

Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO en un disco duro virtual (VHD):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique la ruta de acceso completa, incluido el nombre de archivo, en la imagen ISO. Por ejemplo: C:\ISO\WindowsServer2012R2.iso.

El archivo VHD creado se almacena en la carpeta **Directorio de sitios** \Bits\VHD. Puede obtener la ruta de acceso al **Directorio de sitios** ejecutando el **Get-CcSiteDirectory**.

> [!IMPORTANT]
> De forma predeterminada, la configuración de proxy no está configurada en la máquina virtual base. Si se requiere un proxy en el entorno de red para actualizar la máquina virtual a través de Windows Update, debe agregar el conmutador-PauseBeforeUpdate al ejecutar "Convert-CcIsoToVhdx". El script se hará una pausa antes de Windows Update y tendrá la posibilidad de configurar manualmente el proxy en la máquina virtual. Después de configurar el proxy y de que la máquina virtual pueda acceder a Internet, puede reanudar el script para completar los pasos restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Crear VHD para una implementación de varios sitios

Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.

Si va a implementar una implementación de varios sitios, no es necesario convertir la ISO en un VHD para cada sitio. Puede copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.

 Copie el archivo en la misma ubicación del archivo ( **Directorio de sitios** \Bits\VHD) y con el mismo nombre de archivo, en el servidor host para un sitio adicional.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Establecer la Directiva de ejecución de PowerShell en RemoteSigned

Los scripts de PowerShell proporcionados requieren que la Directiva de ejecución se establezca como RemoteSigned. Para ver la configuración actual, abra una consola de PowerShell como administrador y, a continuación, ejecute el siguiente cmdlet:

```powershell
Get-ExecutionPolicy
```

Si no se establece en "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Cambiar la Directiva de grupo local en el equipo host (versiones 1.4.1 y anteriores)

> [!NOTE]
> Esta tarea no es necesaria para las versiones de Cloud Connector 1.4.2 y posterior. 

La cuenta CceService se crea durante la implementación de Skype empresarial Cloud Connector Edition. Ejecuta el servicio de administración de Cloud Connector y requiere permiso para desinstalar cloudconnector. msi. Debe cambiar la configuración de la Directiva de grupo en la máquina host de Cloud Connector para especificar que el registro de usuarios no se debe descargar cuando el usuario cierra la sesión. Siga los pasos siguientes:

### <a name="to-change-the-group-policy-setting"></a>Para cambiar la configuración de la Directiva de grupo

1. Abra el **Editor de directivas de grupo** ejecutando gpedit. msc.

2. En el **Editor de directivas de grupo**, vaya a plantillas administrativas > System > userprofile > no descargar forzosamente el registro de usuarios al cerrar la sesión de usuario. 

3. Establezca su valor en **habilitado**.

## <a name="set-up-your-office-365-tenant"></a>Configurar el espacio empresarial de Office 365

Se requiere un inquilino de Office 365 con Skype empresarial online y el sistema telefónico en Office 365. Asegúrese de que el inquilino esté configurado y configurado antes de intentar usar Cloud Connector.

Algunos pasos del programa de instalación de Office 365 requieren que use el PowerShell remoto del inquilino (TRPS) para configurar el inquilino de Office 365. **Debe estar instalado en el servidor host.** Puede descargar el módulo de Skype empresarial online para PowerShell desde: [Skype empresarial online, módulo de Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366).

Cree una cuenta de administrador de Skype empresarial dedicado para la administración en línea de Cloud Connector, por ejemplo, Cceonlinemanagmentadministrator. Esta cuenta se usará en el dispositivo para agregar o eliminar el dispositivo, habilitar o deshabilitar la actualización automática del sistema operativo, habilitar o deshabilitar la actualización binaria automática. Establezca la contraseña de esta cuenta para que no expire nunca, de modo que no tenga que cambiarla para el servicio cada vez que expire.


