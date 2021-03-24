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
description: Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con Phone System (PBX en la nube).
ms.openlocfilehash: 536e9b98520e4274e00d43d57224267f5b824dc9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092638"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar el dispositivo de Cloud Connector

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)

Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con Phone System (PBX en la nube).

En esta sección se describe cómo obtener los archivos de instalación de Skype Empresarial Cloud Connector Edition, instalar el software de Cloud Connector y preparar el dispositivo de Cloud Connector para su implementación. Después de completar todos los pasos de esta sección, estará listo para implementar Cloud Connector para un solo sitio o varios sitios. Si tiene una implementación existente de Cloud Connector y aún no ha actualizado [a](upgrade-to-a-new-version-of-cloud-connector.md)Cloud Connector versión 2.1, consulte Upgrade to a new version of Cloud Connector .

> [!NOTE]
> Microsoft admite la versión actual de Cloud Connector Edition, versión 2.1. Si configuró la actualización automática, Cloud Connector se actualizará automáticamente. Si configuró la actualización manual, tendrá que actualizar a la versión 2.1 en un plazo de 60 días desde su lanzamiento. Microsoft admitirá la versión anterior durante 60 días después de la versión 2.1 para permitirte tiempo para actualizar. 

> [!NOTE]
> Para Cloud Connector versión 2.1 y versiones posteriores, el dispositivo host debe tener .NET Framework 4.6.1 o posterior instalado. 

> [!IMPORTANT]
> Para una implementación correcta, cuando ejecute los cmdlets para configurar Skype Empresarial Cloud Connector Edition, use siempre la misma sesión de consola que la que inició. Evite cambiar a diferentes sesiones durante la implementación y configuración. 

> [!NOTE]
> Hay algunos pasos que solo se realizan para el primer dispositivo de la implementación: crear un recurso compartido para el directorio del sitio, descargar los bits y preparar un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Descargar el instalador de Skype Empresarial Cloud Connector Edition

1. En el servidor host donde se ejecutarán las máquinas virtuales de Cloud Connector, descargue los archivos de instalación: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > El servidor host debe poder tener acceso a Internet durante la instalación de Cloud Connector porque se descargan archivos adicionales durante la instalación. 

2. Ejecute el instalador y acepte los valores predeterminados durante la instalación.

3. Confirme que la instalación se completó correctamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Comprobar la instalación y configurar el entorno

1. Abra una consola de PowerShell como administrador y confirme que los cmdlets de Skype Empresarial Cloud Connector Edition están disponibles con el siguiente cmdlet:

   ```powershell
   Get-Command *-Cc*
   ```

    El comando debe devolver una lista de cmdlets para Skype Empresarial Cloud Connector Edition.

2. Los archivos VHD, SfBBits y VersionInfo se almacenarán en el **Directorio del sitio**.

    Puede encontrar la ubicación del Directorio del **sitio** con el siguiente cmdlet:

   ```powershell
   Get-CcSiteDirectory
   ```

    El comando debe devolver una ubicación en el sistema de archivos. La ubicación puede ser una carpeta local o un recurso compartido de archivos. La ubicación predeterminada del **Directorio del sitio** es: %USERPROFILE%\CloudConnector\SiteRoot. La ubicación predeterminada debe cambiarse a un recurso compartido de archivos en el primer dispositivo creado en cada sitio.

    La ubicación que seleccione debe ser:

   - Creado en el primer dispositivo creado en cada sitio.

   - Una carpeta compartida a la que los demás servidores host (dispositivos) tienen acceso en el mismo sitio.

     Para establecer **el Directorio del sitio** en una ubicación que no sea la predeterminada, ejecute el siguiente cmdlet:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Si va a implementar alta disponibilidad (HA) para el sitio,  asegúrese de ejecutar el cmdlet para establecer el Directorio del sitio en la misma ubicación en cada servidor host dentro del sitio.

    Cuando inicie sesión e implemente cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tenga el acceso correcto al **Directorio del sitio**.

3. El **Directorio del dispositivo** es el directorio raíz de trabajo local para Skype Empresarial Cloud Connector Edition y la ubicación donde se guardan certificados, instancias y registros externos. La ubicación predeterminada es: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Para buscar la ubicación del **Directorio de dispositivos,** ejecute el siguiente cmdlet:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Para establecer **el Directorio del dispositivo** en una ubicación que no sea la predeterminada, ejecute el siguiente cmdlet:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    El directorio del dispositivo debe establecerse en una carpeta local del dispositivo. Solo debe establecer el directorio **de dispositivos antes** de iniciar la implementación de Skype Empresarial Cloud Connector Edition. Si lo cambia después de la implementación, tendrá que volver a implementar el servidor host.

    > [!IMPORTANT]
    > La ruta de acceso al **Directorio de dispositivos** no debe contener espacios.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Establecer la ruta de acceso para el certificado perimetral externo

- Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado perimetral externo. Por ejemplo: C:\certs\cce\ap.contoso.com.pfx. El certificado debe contener claves privadas.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Tenga en cuenta que el parámetro -Target es específico de las versiones 1.4.2 y posteriores. 

    Especifique la ruta de acceso completa al certificado externo, incluido el nombre del archivo. El certificado se puede almacenar localmente o en un recurso compartido de archivos. Si el certificado se almacena en una carpeta compartida, la carpeta compartida debe crearse en el primer dispositivo de cada sitio y debe ser accesible por otros dispositivos pertenecientes al mismo sitio. Este cmdlet copia el certificado externo en **el Directorio del dispositivo**.

    > [!IMPORTANT]
    > Si se ha actualizado a Cloud Connector versión **1.4.2** o posterior, asegúrese de que el certificado externo preparado contiene claves privadas y la cadena de certificados completa, incluidos el certificado de CA raíz y los certificados de CA intermedios. Si aún no se ha actualizado a **Cloud Connector versión 1.4.2,** asegúrese de que el certificado externo preparado contiene claves privadas. Este certificado externo debe ser emitido por una entidad de certificación de confianza de Windows de forma predeterminada.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Establecer la ruta de acceso para la puerta de enlace RTC externa/certificado SBC

Si usa TLS entre el servidor de mediación y la puerta de enlace RTC/SBC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre del archivo, en el certificado de puerta de enlace. Por ejemplo: C:\certs\cce\sbc.contoso.com.cer. El certificado debe contener la CA raíz y la cadena intermedia del certificado asignado a la puerta de enlace:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Tenga en cuenta que el parámetro -Target es específico de las versiones 1.4.2 y posteriores. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Crear conmutadores virtuales en el Administrador de Hyper-V

1. Abra el Administrador de conmutador virtual de **Hyper-V Manager**  >  y seleccione Nuevo Administrador **de modificadores virtuales**.

2. Crear un conmutador virtual externo y enlazarlo al adaptador de red físico que está conectado al dominio de red interno:

    Seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

3. Crear un conmutador virtual externo y enlazarlo al adaptador de red físico que se enruta a Internet:

    Des seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

4. Establezca el nombre del conmutador que conecta la red perimetral con el dominio de red interno **SfB CCE Corpnet Switch**.

    Establezca el nombre del conmutador que conecta la red perimetral al conmutador de **Internet Internet SfB CCE .**

## <a name="update-the-cloudconnectorini-configuration-file"></a>Actualizar el archivo CloudConnector.ini de configuración

Prepare el CloudConnector.ini con la información que recopiló en [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema Plan for Skype for Business Cloud Connector [Edition.](plan-skype-for-business-cloud-connector-edition.md)

Para actualizar el archivo, ejecute primero el siguiente cmdlet para obtener la plantilla de ejemplo (CloudConnector.Sample.ini):

```powershell
Export-CcConfigurationSampleFile
```

La plantilla de ejemplo se almacena en el **Directorio de dispositivos**.

Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector.ini en el **Directorio del dispositivo**. Puede ejecutar **Get-CcApplianceDirectory para** determinar la ruta de acceso al **directorio del dispositivo**.

Al actualizar el archivo .ini, tenga en cuenta lo siguiente:

> [!NOTE]
> No todos los valores del archivo .ini se tratan en esta sección, solo los que tienen una consideración especial se tratan aquí. Para obtener una lista completa, vea la [sección Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del tema Plan for Skype for Business Cloud Connector [Edition.](plan-skype-for-business-cloud-connector-edition.md) Para obtener más información acerca de los valores que deben cambiarse para dispositivos adicionales o sitios nuevos, vea [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en el tema Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** El valor predeterminado es **Site1**. Debe actualizarlo antes de implementar Cloud Connector, ya que al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio existente o nuevo, el cmdlet usará **SiteName** para determinar qué sitio registrar.

     Si desea registrar el dispositivo en un nuevo sitio, el valor de **SiteName** debe ser único y diferente de los sitios existentes. Si desea registrar el dispositivo en un sitio existente, el valor de **SiteName** en el archivo .ini debe coincidir con el nombre definido en la configuración de la organización de Microsoft 365 u Office 365. Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **SiteName** para cada sitio en consecuencia.

- **ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe limitarse a 15 caracteres.

- **HardwareType:** Si no establece o deja el valor en null, se usará el valor predeterminado de **Normal.** Use **Normal** si tiene previsto implementar la versión más grande de Cloud Connector para admitir 500 llamadas simultáneas por equipo host, tal como se describe en [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Use **Minimum** para una implementación más pequeña que admita 50 llamadas simultáneas.

- **Conmutadores virtuales de Internet/Corpnet/Management:**: Agregue el nombre de los conmutadores virtuales que haya creado. Para el conmutador virtual de administración, deje el valor predeterminado. El script de implementación creará el conmutador virtual de administración al principio de la implementación y lo eliminará cuando finalice la implementación.

- **ManagementIPPrefix:** ManagementIPPrefix en la sección Red debe ser una subred diferente de otras direcciones IP internas. Por ejemplo, como muestra el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.

    Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una IP de administración y la conectan a un conmutador virtual de administración. Esto permite al servidor host conectarse y administrar cada máquina virtual a través de esta red de administración. El conmutador virtual de administración se elimina cuando finaliza la implementación.

- **Configuraciones específicas de vm base:** La configuración de esta sección debe configurarse para el cmdlet **Convert-CcIsoToVhdx.**

    Durante la preparación de la imagen de vm base, la máquina virtual base se conectará al conmutador de red interno. La siguiente configuración es fundamental para que la máquina virtual pueda tener acceso a Internet:

  - [Common] BaseVMIP: la dirección IP corpnet que se asignará a la máquina virtual base.

  - [Red] CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.

  - [Red] CorpnetDNSIPAddress: la dirección IP DNS que se asignará a la máquina virtual base.

  - [Red] WSUSServer: la dirección IP del servicio Windows Server Update.

  - [Red] WSUSStatusServer: la dirección IP del servidor de estado de Windows Server Update Service.

  - [Red] EnableReferSupport: esto definirá si la compatibilidad con SIP REFER está habilitada o deshabilitada en la configuración de tronco a su IP/PBX.

- **IP internas:**

  - Asegúrese de que la máscara de subred CorpnetIPPrefixLength es correcta.

  - Asegúrese de que no hay conflictos de IP para estas direcciones IP internas.

- **IP externas:**

  - Para IP pública de MR: especifique ExternalMRIPs para NAT o ExternalMRPublicIPs para NAT.

  - ExternalSIPIPs y ExternalMRIPs pueden ser los mismos.

  - Asegúrese de que la máscara de subred InternetIPPrefixLength es correcta.

  - Asegúrese de que no hay conflictos de IP para estas direcciones IP externas.

- **Puertas de enlace:**

  - Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria. Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente y actualizándola.

  - Asegúrese de que la dirección IP y el puerto de las puertas de enlace son correctos.

  - Para admitir ha de nivel de puerta de enlace RTC, deje la puerta de enlace secundaria y agregue las puertas de enlace adicionales que vaya a usar. Puede copiar y pegar una entrada existente y, a continuación, actualizarla.

- Opcionalmente, puede actualizar el valor de LocalRoute para restringir los números de llamadas salientes.

## <a name="download-the-bits-to-the-site-directory"></a>Descargar los bits en el Directorio del sitio

Ejecute el siguiente cmdlet para descargar los bits y los archivos de información de versión en el **Directorio del sitio:**

```powershell
Start-CcDownload
```

> [!NOTE]
> Debe realizar este paso solo para el primer dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar el disco virtual base (VHDX) desde el archivo ISO descargado

Este paso prepara un archivo de disco duro virtual (VHDX) a partir de la imagen ISO de Windows Server 2012. El VHDX se usará para crear máquinas virtuales durante la implementación. Se creará una máquina virtual temporal (VM base) y Windows Server 2012 se instalará desde el archivo ISO. Después de crear la máquina virtual, se instalarán algunos componentes necesarios y se aplicará la actualización más reciente de Windows. Al final, la máquina virtual base se generalizará (sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.

> [!NOTE]
> Debe realizar este paso solo para el primer dispositivo. 

Antes de continuar con este paso, asegúrese de que se crea el modificador corpnet. Asimismo, confirme que las siguientes opciones de configuración están configuradas correctamente en el CloudConnector.ini archivo:

- [Red] CorpnetSwitchName

- [Common] BaseVMIP

- [Red] CorpnetIPPrefixLength

- [Red] CorpnetDefaultGateway

- [Red] CorpnetDNSIPAddress

Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO en un disco duro virtual (VHD):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique la ruta de acceso completa, incluido el nombre de archivo, a la imagen ISO. Por ejemplo: C:\ISO\WindowsServer2012R2.iso.

El archivo VHD creado se almacena en la carpeta Directorio **del sitio** \Bits\VHD. Puede obtener la ruta de acceso al **Directorio del sitio** ejecutando **Get-CcSiteDirectory**.

> [!IMPORTANT]
> De forma predeterminada, la configuración de proxy no está configurada en la máquina virtual base. Si se necesita un proxy en el entorno de red para actualizar la máquina virtual a través de Windows Update, debes agregar el modificador -PauseBeforeUpdate al ejecutar "Convert-CcIsoToVhdx". El script se pausará antes de Windows Update y tendrás la oportunidad de configurar manualmente el proxy en la máquina virtual. Después de configurar el proxy y de que la máquina virtual pueda tener acceso a Internet, puede reanudar el script para completar los pasos restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Crear VHD para una implementación de varios sitios

Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.

Si va a implementar una implementación de varios sitios, no es necesario convertir la ISO en un VHD para cada sitio. Puede copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.

 Copie el archivo en la misma ubicación de archivo **(** Directorio del sitio \Bits\CARPETA VHD) y con el mismo nombre de archivo, en el servidor host de un sitio adicional.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Establecer la directiva de ejecución de PowerShell en RemoteSigned

Los scripts de PowerShell proporcionados requieren que la directiva de ejecución se establezca en RemoteSigned. Para ver la configuración actual, abra una consola de PowerShell como administrador y, a continuación, ejecute el siguiente cmdlet:

```powershell
Get-ExecutionPolicy
```

Si no está establecido en "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Cambiar la directiva de grupo local en el equipo host (versiones 1.4.1 y versiones anteriores)

> [!NOTE]
> Esta tarea no es necesaria para las versiones 1.4.2 y posteriores de Cloud Connector. 

La cuenta CceService se crea durante la implementación de Skype Empresarial Cloud Connector Edition. Ejecuta el servicio de administración de Cloud Connector y requiere permiso para desinstalar el cloudconnector.msi. Debe cambiar la configuración de directiva de grupo en el equipo host de Cloud Connector para especificar que el registro de usuarios no se debe descargar cuando el usuario cierra sesión. Siga los pasos siguientes:

### <a name="to-change-the-group-policy-setting"></a>Para cambiar la configuración de directiva de grupo

1. Abra el **Editor de directivas de grupo** ejecutando gpedit.msc.

2. En el **Editor de directivas** de grupo, vaya a Plantillas administrativas > System > UserProfile > No descargar el registro de usuarios de forma forzar al cerrar sesión de usuario. 

3. Establezca su valor en **Enabled**.

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurar la organización de Microsoft 365 u Office 365

Se requiere una organización de Microsoft 365 u Office 365 con Skype Empresarial Online y sistema telefónico. Asegúrese de que el espacio empresarial está configurado y configurado antes de intentar usar Cloud Connector.

Algunos pasos de configuración de Microsoft 365 y Office 365 requieren que use PowerShell remoto de inquilino (TRPS) para configurar su organización de Microsoft 365 u Office 365. **Esto debe instalarse en el servidor host.** Puede descargar el módulo de Skype Empresarial Online para PowerShell desde: [Skype Empresarial Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).

Cree una cuenta de administrador de Skype Empresarial dedicada para la administración en línea de Cloud Connector, por ejemplo, CceOnlineManagmentAdministrator. El dispositivo usará esta cuenta para agregar o quitar el dispositivo, habilitar o deshabilitar la actualización automática del sistema operativo, habilitar o deshabilitar la actualización binaria automática. Establezca la contraseña de esta cuenta para que nunca expire para que no tenga que cambiarla para el servicio cada vez que expire.