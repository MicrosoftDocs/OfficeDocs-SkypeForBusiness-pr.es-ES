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
description: Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con sistema telefónico (PBX en la nube).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358946"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Preparar el dispositivo de Cloud Connector

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con sistema telefónico (PBX en la nube).

En esta sección se describe cómo obtener los archivos de instalación de Skype Empresarial Cloud Connector Edition, instalar el software de Cloud Connector y preparar el dispositivo de Cloud Connector para la implementación. Después de completar todos los pasos de esta sección, estará listo para implementar Cloud Connector para un único sitio o varios sitios. Si tiene una implementación existente de Cloud Connector y aún no ha actualizado a Cloud Connector versión 2.1, consulte Actualizar a una nueva versión [de Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)

> [!NOTE]
> Microsoft admite la versión actual de Cloud Connector Edition, versión 2.1. Si configuró la actualización automática, Cloud Connector se actualizará automáticamente. Si configuró la actualización manual, tendrá que actualizar a la versión 2.1 en un plazo de 60 días desde su lanzamiento. Microsoft admitirá la versión anterior durante 60 días después de la versión 2.1 para permitirle tener tiempo para actualizar. 

> [!NOTE]
> Para Cloud Connector versión 2.1 y versiones posteriores, el dispositivo host debe tener instalado .NET Framework 4.6.1 o posterior. 

> [!IMPORTANT]
> Para una implementación correcta, cuando ejecute los cmdlets para configurar Skype Empresarial Cloud Connector Edition, use siempre la misma sesión de consola que la que inició. Evite cambiar a distintas sesiones durante la implementación y la configuración. 

> [!NOTE]
> Hay algunos pasos que solo se realizan para el primer dispositivo de la implementación: crear un recurso compartido para el directorio de sitios, descargar los bits y preparar un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Descargar el instalador de Skype Empresarial Cloud Connector Edition

1. En el servidor host donde se ejecutarán las máquinas virtuales de Cloud Connector, descargue los archivos de instalación: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > El servidor host debe poder acceder a Internet durante la instalación de Cloud Connector porque se descargan archivos adicionales durante la instalación. 

2. Ejecute el instalador y acepte los valores predeterminados durante la instalación.

3. Confirme que la instalación se ha completado correctamente.

## <a name="verify-the-installation-and-configure-the-environment"></a>Comprobar la instalación y configurar el entorno

1. Abra una consola de PowerShell como administrador y confirme que los cmdlets de Skype Empresarial Cloud Connector Edition están disponibles con el siguiente cmdlet:

   ```powershell
   Get-Command *-Cc*
   ```

    El comando debe devolver una lista de cmdlets para Skype Empresarial Cloud Connector Edition.

2. Los archivos VHD, SfBBits y VersionInfo se almacenarán en el **Directorio de sitios.**

    Puede encontrar la ubicación del Directorio de **sitios** con el siguiente cmdlet:

   ```powershell
   Get-CcSiteDirectory
   ```

    El comando debe devolver una ubicación en el sistema de archivos. La ubicación puede ser una carpeta local o un recurso compartido de archivos. La ubicación predeterminada del directorio **de sitios** es: %USERPROFILE%\CloudConnector\SiteRoot. La ubicación predeterminada debe cambiarse a un recurso compartido de archivos en el primer dispositivo creado en cada sitio.

    La ubicación que seleccione debe ser:

   - Se creó en el primer dispositivo creado en cada sitio.

   - Una carpeta compartida a la que pueden acceder los demás servidores host (dispositivos) en el mismo sitio.

     Para establecer el **Directorio de sitios** en una ubicación que no sea la predeterminada, ejecute el siguiente cmdlet:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Si va a implementar alta disponibilidad (HA) para el sitio,  asegúrese de ejecutar el cmdlet para establecer el Directorio de sitios en la misma ubicación en cada servidor host dentro del sitio.

    Cuando inicie sesión e implemente cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tiene el acceso correcto al **Directorio de sitios.**

3. El **Directorio de dispositivos** es el directorio raíz de trabajo local para Skype Empresarial Cloud Connector Edition y la ubicación donde se guardan certificados, instancias y registros externos. La ubicación predeterminada es: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Para encontrar la ubicación del **directorio de dispositivos,** ejecute el siguiente cmdlet:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Para establecer el **Directorio de dispositivos** en una ubicación que no sea la predeterminada, ejecute el siguiente cmdlet:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    El directorio de dispositivos debe establecerse en una carpeta local del dispositivo. Solo debe establecer el directorio **de dispositivos antes** de iniciar la implementación de Skype Empresarial Cloud Connector Edition. Si lo cambia después de la implementación, deberá volver a implementar el servidor host.

    > [!IMPORTANT]
    > La ruta de acceso **al directorio de** dispositivos no debe contener espacios.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Establecer la ruta de acceso para el certificado perimetral externo

- Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado perimetral externo. Por ejemplo: C:\certs\cce\ap.contoso.com.pfx. El certificado debe contener claves privadas.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Tenga en cuenta que el parámetro -Target es específico de las versiones 1.4.2 y posteriores. 

    Especifique la ruta de acceso completa al certificado externo, incluido el nombre de archivo. El certificado se puede almacenar localmente o en un recurso compartido de archivos. Si el certificado se almacena en una carpeta compartida, la carpeta compartida debe crearse en el primer dispositivo de cada sitio y deben ser accesibles por otros dispositivos que pertenezcan al mismo sitio. Este cmdlet copia el certificado externo en el **Directorio de dispositivos.**

    > [!IMPORTANT]
    > Si ha actualizado a Cloud Connector versión **1.4.2** o posterior, asegúrese de que el certificado externo preparado contiene claves privadas y la cadena de certificados completa, incluidos el certificado de ca raíz y los certificados de CA intermedia. **Si aún no ha actualizado a Cloud Connector versión 1.4.2,** asegúrese de que el certificado externo preparado contiene claves privadas. Este certificado externo debe ser emitido por una entidad de certificación que sea de confianza para Windows de forma predeterminada.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Establecer la ruta de acceso para el certificado de SBC/puerta de enlace RTC externa

Si usa TLS entre el servidor de mediación y la puerta de enlace RTC/SBC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado de puerta de enlace. Por ejemplo: C:\certs\cce\sbc.contoso.com.cer. El certificado debe contener la CA raíz y la cadena intermedia para el certificado asignado a la puerta de enlace:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Tenga en cuenta que el parámetro -Target es específico de las versiones 1.4.2 y posteriores. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Crear conmutadores virtuales en el Administrador de Hyper-V

1. Abra el Administrador de conmutador virtuales de **Hyper-V**  >  **y** seleccione **Nuevo administrador de conmutador virtual.**

2. Crear un conmutador virtual externo y enlazarlo al adaptador de red físico que está conectado a su dominio de red interno:

    Selecciona **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

3. Crear un conmutador virtual externo y enlazarlo al adaptador de red físico que se enruta a Internet:

    Des seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.

4. Establezca el nombre del conmutador que conecta la red perimetral con el dominio de red interno **SfB CCE Corpnet Switch**.

    Establezca el nombre del conmutador que conecta la red perimetral al conmutador de **Internet SfB CCE internet.**

## <a name="update-the-cloudconnectorini-configuration-file"></a>Actualizar el archivo CloudConnector.ini de configuración

Prepare el CloudConnector.ini con la información recopilada en [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema Plan for Skype for Business Cloud Connector [Edition.](plan-skype-for-business-cloud-connector-edition.md)

Para actualizar el archivo, ejecute primero el siguiente cmdlet para obtener la plantilla de ejemplo (CloudConnector.Sample.ini):

```powershell
Export-CcConfigurationSampleFile
```

La plantilla de ejemplo se almacena en el **Directorio de dispositivos.**

Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector.ini en el **Directorio de dispositivos.** Puede ejecutar **Get-CcApplianceDirectory para** determinar la ruta de acceso al directorio **de aplicaciones.**

Al actualizar el archivo .ini, tenga en cuenta lo siguiente:

> [!NOTE]
> No todos los valores del archivo .ini se tratan en esta sección, solo los que tienen una consideración especial se tratan aquí. Para obtener una lista completa, consulte la sección [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del tema Plan for Skype for Business Cloud Connector [Edition.](plan-skype-for-business-cloud-connector-edition.md) Para obtener más información acerca de los valores que deben cambiarse para dispositivos adicionales o sitios nuevos, vea Sitio único con alta disponibilidad [(HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en comparación con las implementaciones de varios sitios en el tema Implementar varios sitios en [Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** El valor predeterminado es **Site1**. Debe actualizarlo antes de implementar Cloud Connector, ya que al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio nuevo o existente, el cmdlet usará **SiteName** para determinar qué sitio registrar.

     Si desea registrar el dispositivo en un nuevo sitio, el valor de **SiteName** debe ser único y diferente de los sitios existentes. Si desea registrar el dispositivo en un sitio existente, el valor de **SiteName** en el archivo .ini debe coincidir con el nombre definido en la configuración de la organización de Microsoft 365 u Office 365. Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **SiteName** para cada sitio en consecuencia.

- **ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe limitarse a 15 caracteres.

- **HardwareType:** Si no establece o deja el valor en null, se usará el valor predeterminado de **Normal.** Use **Normal** si planea implementar la versión más grande de Cloud Connector para admitir 500 llamadas simultáneas por equipo host, tal como se describe en [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Use **Minimum** para una implementación más pequeña que admita 50 llamadas simultáneas.

- **Conmutadores virtuales de Internet/Corpnet/Administración:**: agregue el nombre de los conmutadores virtuales que ha creado. Para el conmutador virtual de administración, deje el valor predeterminado. El script de implementación creará el conmutador virtual de administración al principio de la implementación y lo eliminará cuando finalice la implementación.

- **ManagementIPPrefix:** ManagementIPPrefix en la sección Red debe ser una subred diferente de otras DIRECCIONES IP internas. Por ejemplo, como se muestra en el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.

    Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una DIRECCIÓN IP de administración y la conectan a un conmutador virtual de administración. Esto permite al servidor host conectarse a cada máquina virtual y administrarla a través de esta red de administración. El conmutador virtual de administración se elimina cuando finaliza la implementación.

- **Configuraciones específicas de vm base:** Las opciones de esta sección deben configurarse para el cmdlet **Convert-CcIsoToVhdx.**

    Durante la preparación de la imagen de máquina virtual base, la máquina virtual base se conectará al conmutador de red interno. La siguiente configuración es fundamental para que la máquina virtual pueda acceder a Internet:

  - [Común] BaseVMIP: la dirección IP de la red corpnet que se asignará a la máquina virtual base.

  - [Red] CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.

  - [Red] CorpnetDNSIPAddress: la dirección IP DNS que se asignará a la máquina virtual base.

  - [Red] WSUSServer: la dirección IP de Windows Server Update Service.

  - [Red] WSUSStatusServer: la dirección IP del servidor de estado de Windows Server Update Service.

  - [Red] EnableReferSupport: esto definirá si la compatibilidad con SIP REFER está habilitada o deshabilitada en la configuración del tronco para su IP/PBX.

- **Ip internas:**

  - Asegúrese de que la máscara de subred CorpnetIPPrefixLength sea correcta.

  - Asegúrese de que no haya ningún conflicto de IP para estas direcciones IP internas.

- **IP externas:**

  - Para LA IP pública de MR: especifique ExternalMRIPs para no NAT o ExternalMRPublicIPs para NAT.

  - ExternalSIPIPs y ExternalMRIPs pueden ser los mismos.

  - Asegúrese de que la máscara de subred InternetIPPrefixLength sea correcta.

  - Asegúrese de que no haya ningún conflicto de IP para estas DIRECCIONES IP externas.

- **Puertas de enlace:**

  - Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria. Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente y actualizándola.

  - Asegúrese de que la dirección IP y el puerto de las puertas de enlace sean correctos.

  - Para admitir el nivel de puerta de enlace RTC HA, deje la puerta de enlace secundaria y agregue las puertas de enlace adicionales que vaya a usar. Puede copiar y pegar una entrada existente y, a continuación, actualizarla.

- Opcionalmente, puede actualizar el valor de LocalRoute para restringir los números de llamadas salientes.

## <a name="download-the-bits-to-the-site-directory"></a>Descargar los bits en el Directorio de sitios

Ejecute el siguiente cmdlet para descargar los archivos de información de bits y versiones en el **Directorio de sitios:**

```powershell
Start-CcDownload
```

> [!NOTE]
> Debe realizar este paso solo para el primer dispositivo. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Preparar el disco virtual base (VHDX) desde el archivo ISO descargado

Este paso prepara un archivo de disco duro virtual (VHDX) de la imagen ISO de Windows Server 2012. El VHDX se usará para crear máquinas virtuales durante la implementación. Se creará una máquina virtual temporal (VM base) y Windows Server 2012 se instalará desde el archivo ISO. Después de crear la máquina virtual, se instalarán algunos componentes necesarios y se aplicará la última actualización de Windows. Al final, la máquina virtual base se generalizará (sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.

> [!NOTE]
> Debe realizar este paso solo para el primer dispositivo. 

Antes de continuar con este paso, asegúrese de que se crea el conmutador de red de red. Asimismo, confirme que las siguientes opciones están configuradas correctamente en el CloudConnector.ini archivo:

- [Red] CorpnetSwitchName

- [Común] BaseVMIP

- [Red] CorpnetIPPrefixLength

- [Red] CorpnetDefaultGateway

- [Red] CorpnetDNSIPAddress

Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO en un disco duro virtual (VHD):

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Especifique la ruta de acceso completa, incluido el nombre de archivo, a la imagen ISO. Por ejemplo: C:\ISO\WindowsServer2012R2.iso.

El archivo VHD creado se almacena en la carpeta **Directorio de sitios** \Bits\VHD. Puede obtener la ruta de acceso al **Directorio de sitios** ejecutando **Get-CcSiteDirectory**.

> [!IMPORTANT]
> De forma predeterminada, las opciones de proxy no están configuradas en la máquina virtual base. Si se necesita un proxy en el entorno de red para actualizar la máquina virtual a través de Windows Update, debes agregar el modificador -PauseBeforeUpdate cuando ejecutes "Convert-CcIsoToVhdx". El script se pausará antes de Windows Update y tendrás la oportunidad de configurar manualmente el proxy en la máquina virtual. Después de configurar el proxy y de que la máquina virtual pueda acceder a Internet, puedes reanudar el script para completar los pasos restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Crear VHD para una implementación de varios sitios

Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.

Si va a implementar una implementación de varios sitios, no es necesario convertir la ISO en un VHD para cada sitio. Puedes copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.

 Copie el archivo en la misma ubicación de archivo **(directorio** del sitio \Bits\carpeta VHD) y con el mismo nombre de archivo, en el servidor host de un sitio adicional.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Establecer la directiva de ejecución de PowerShell en RemoteSigned

Los scripts de PowerShell proporcionados requieren que la directiva de ejecución se establezca en RemoteSigned. Para ver la configuración actual, abra una consola de PowerShell como administrador y, a continuación, ejecute el siguiente cmdlet:

```powershell
Get-ExecutionPolicy
```

Si no está establecido en "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Cambiar la directiva de grupo local en el equipo host (versiones 1.4.1 y anteriores)

> [!NOTE]
> Esta tarea no es necesaria para las versiones 1.4.2 y posteriores de Cloud Connector. 

La cuenta CceService se crea durante la implementación de Skype Empresarial Cloud Connector Edition. Ejecuta el servicio de administración de Cloud Connector y requiere permiso para desinstalar el cloudconnector.msi. Debe cambiar la configuración de directiva de grupo en el equipo host de Cloud Connector para especificar que el registro de usuarios no se debe descargar cuando el usuario cierra sesión. Siga los pasos siguientes:

### <a name="to-change-the-group-policy-setting"></a>Para cambiar la configuración de directiva de grupo

1. Abre el **Editor de directivas de grupo** ejecutando gpedit.msc.

2. En el Editor de **directivas** de grupo, vaya a Plantillas administrativas > System > UserProfile > No descargar de forma forzar el registro de usuarios al cerrar sesión del usuario. 

3. Establezca su valor en **Habilitado**.

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurar su organización de Microsoft 365 u Office 365

Se requiere una organización de Microsoft 365 u Office 365 con Skype Empresarial Online y sistema telefónico. Asegúrese de que el espacio empresarial está configurado antes de intentar usar Cloud Connector.

Algunos pasos de configuración de Microsoft 365 y Office 365 requieren que use El PowerShell remoto de inquilino (TRPS) para configurar su organización de Microsoft 365 u Office 365. **Debe instalarse en el servidor host.** You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).

Cree una cuenta de administrador de Skype Empresarial dedicada para la administración en línea de Cloud Connector, por ejemplo, CceOnlineManagmentAdministrator. Esta cuenta la usará el dispositivo para agregar o quitar el dispositivo, habilitar o deshabilitar la actualización automática del sistema operativo, habilitar o deshabilitar la actualización binaria automática. Establezca la contraseña de esta cuenta para que nunca expire, de modo que no necesite cambiarla para el servicio cada vez que expire.


