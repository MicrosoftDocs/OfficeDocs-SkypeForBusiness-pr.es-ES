---
title: Implementar salas de Microsoft Teams con Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo implementar salas de Microsoft Teams en implementaciones a gran escala con Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662425"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Implementar salas de Microsoft Teams con Microsoft Endpoint Configuration Manager

En este artículo se proporciona toda la información necesaria para crear las implementaciones de Microsoft Teams Rooms con Microsoft Endpoint Configuration Manager.

Con los métodos fáciles de usar proporcionados por Configuration Manager, puede implementar el sistema operativo y otras aplicaciones en varios dispositivos de destino.

Use el método que se muestra a continuación para guiarlo a través de la configuración de Configuration Manager y personalizar los paquetes y scripts de ejemplo proporcionados a lo largo de esta guía según sea necesario para su organización.

![Proceso de implementación de salas de Microsoft Teams con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Esta solución solo se ha probado con implementaciones basadas en Surface Pro. Sigue las instrucciones del fabricante para las configuraciones que no están basadas en Surface Pro.

## <a name="validate-prerequisites"></a>Validar requisitos previos

Para implementar salas de Microsoft Teams con Configuration Manager, asegúrese de que cumple los siguientes requisitos previos y requisitos.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Requisitos de Microsoft Endpoint Configuration Manager

-   La versión de Microsoft Endpoint Configuration Manager debe ser de al menos 1706 o superior. Se recomienda usar 1710 o posterior. Consulte la [compatibilidad con Windows 10 en Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para obtener información sobre las versiones de Windows 10 que admite Configuration Manager.

-   Es necesario instalar una versión compatible del Kit de implementación y evaluación de Windows (ADK) para Windows 10. Consulta las versiones del [ADK de Windows 10](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que puedes usar con diferentes versiones de Configuration Manager y asegúrate de que la implementación incluye la versión correcta.

-   Los servidores del sistema del sitio deben tener asignado el rol de punto de distribución y las imágenes de arranque deben habilitarse para la compatibilidad con el entorno de ejecución [preboot (PXE)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar implementaciones iniciadas por la red. Si la compatibilidad con PXE no está habilitada, puede usar medios [de arranque](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones.

-   Es necesario configurar una cuenta de acceso a la red para que admita nuevos escenarios de implementación en equipos (metálicos vacíos). Para obtener más información sobre la configuración de una cuenta de acceso de red, vea [Cuentas usadas en Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   Le recomendamos que habilite [el](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)soporte técnico técnico, si es probable que implemente la misma imagen de Microsoft Teams Rooms en varias unidades al mismo tiempo.

### <a name="networking-requirements"></a>Requisitos de redes

-   La red debe tener un servidor de Protocolo de configuración de host dinámico (KERBEROS) configurado para la distribución automática de direcciones IP a las subredes donde se implementarán las unidades de Salas de Microsoft Teams.

    > [!NOTE]
    > La duración de la concesión de BOOLEAN debe establecerse en un valor superior a la duración de la implementación de imágenes. En caso contrario, puede producirse un error en la implementación.

-   La red, incluidos los conmutadores y las laN virtuales (VLANs), debe configurarse para que admita PXE. Consulte a su proveedor de red para obtener más información sobre la configuración de IP Helper y PXE. Como alternativa, puede usar medios [de arranque](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones, si la compatibilidad con PXE no está habilitada.

    > [!NOTE]
    > Para dispositivos Surface Pro, solo se admite el inicio desde la red (arranque PXE) cuando se usa un adaptador Ethernet o una estación de acoplamiento de Microsoft. Los adaptadores de Ethernet de terceros no admiten el arranque PXE con Surface Pro. Para [obtener más información, consulta adaptadores de Ethernet](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) e implementación de Surface.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Configurar Microsoft Endpoint Configuration Manager para la implementación de sistemas operativos

En este artículo se supone que ya tiene una implementación correcta de Configuration Manager y no detalla todos los pasos necesarios para implementar y configurar Configuration Manager desde cero. La [documentación y las instrucciones de configuración](https://docs.microsoft.com/configmgr/) de Microsoft Endpoint Configuration Manager son un gran recurso; le recomendamos que empiece con estos recursos si aún no ha implementado Configuration Manager.

Use las siguientes instrucciones para comprobar que las características de implementación de sistema operativo (OSD) están configuradas correctamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Validar y actualizar Configuration Manager

1.  En la consola de Configuration Manager, vaya **a Actualizaciones** y mantenimiento \> **de administración.**

2.  Compruebe la compilación instalada y las actualizaciones aplicables que aún no se han instalado.

3.  Revise [la compatibilidad con Windows 10 en Configuration Manager;](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) si necesita actualizar la implementación, seleccione la actualización que desea instalar y, a continuación, seleccione **Descargar.**

4.  Una vez completada la descarga, seleccione la actualización y, después, **instale el paquete de actualización.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurar puntos de distribución para que admitan PXE y grupos

1.  En la consola de Configuration Manager, vaya a Puntos **de distribución** \> **de administración.**

2.  Seleccione el servidor de punto de distribución que va a servir a la implementación de salas de Microsoft Teams y, a continuación, **seleccione Propiedades.**

3.  Seleccione la **pestaña PXE** y asegúrese de que la siguiente configuración está habilitada:
    -   Habilitar la compatibilidad con PXE para clientes
    -   Permitir que este punto de distribución responda a solicitudes PXE entrantes
    -   Habilitar la compatibilidad con equipos desconocidos

4.  *Opcional:* Para habilitar la compatibilidad con opciones de soporte técnico, seleccione la pestaña **Privacidad** y asegúrese de que las siguientes opciones de configuración están habilitadas:
    -   Habilitar la opción para enviar datos a varios clientes de forma simultánea
    -   Configure el intervalo de puertos UDP según lo recomendado por su equipo de red.

### <a name="configure-the-network-access-account"></a>Configurar la cuenta de acceso de red

1.  En la consola del Administrador de configuración, vaya a Sitios **de** configuración del sitio de administración \>  \> y, a continuación, seleccione el sitio.

2.  En el **grupo Configuración,** seleccione **Configurar distribución de** software de componentes del \> **sitio.**

3.  Seleccione la pestaña **Cuenta de acceso de** red. Configure una o más cuentas y, a continuación, seleccione **Aceptar.**

> [!NOTE]
> Las cuentas no necesitan ningún derecho especial, excepto para **obtener Acceso** a este equipo desde la red directamente en el servidor del punto de distribución. Una cuenta de usuario de dominio genérica será apropiada. Para obtener más información, vea [Cuentas usadas en Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Configurar una imagen de arranque

1.  En la consola de Configuration Manager, vaya a imágenes **de** arranque del sistema operativo de la biblioteca \>  \> **de software.**

2.  Seleccione **Imagen de arranque (x64) y,** a continuación, seleccione **Propiedades.**

3.  Seleccione la **pestaña Origen de** datos y habilite Implementar esta imagen de inicio desde el punto de distribución habilitado para **PXE.**

4.  Seleccione la **pestaña Componentes opcionales** para instalar los componentes necesarios:

    1.  Seleccione el icono de estrella y busque **HTML (WinPE-HTA).**

    2.  Seleccione **Aceptar para** agregar compatibilidad con la aplicación HTML a la imagen de inicio.

5.  *Opcional:* Para personalizar la experiencia de implementación, seleccione la **pestaña Personalización.**
    -   Habilite **la compatibilidad de comandos (solo pruebas)** si quiere tener acceso a un símbolo del sistema durante la implementación. Cuando está habilitado, puede iniciar un símbolo del sistema **seleccionando F8** en cualquier momento durante la implementación.
    -   También puede especificar una imagen de fondo personalizada que se mostrará durante la implementación. Para establecer una imagen, habilite Especificar el archivo de imagen de **fondo personalizado (ruta de acceso UNC** y seleccione el fondo.

6.  Cuando se le pida, **seleccione Sí** y distribuya la imagen de arranque actualizada en los puntos de distribución.

Para obtener más información, vea [Administrar imágenes de arranque con Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> Puede crear un medio USB de arranque para iniciar implementaciones basadas en secuencia de tareas de Configuration Manager para entornos que no admiten PXE. Los elementos multimedia de arranque solo contienen la imagen de arranque, los comandos de arranque opcionales y sus archivos necesarios, y los archivos binarios de Configuration Manager para admitir el inicio en Windows PE y la conexión a Configuration Manager durante el resto del proceso de implementación. Para obtener más información, vea [Crear medios de arranque.](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Crear paquetes de Configuration Manager

> [!IMPORTANT]
> La versión de sistema operativo necesaria para cada versión del instalador SRS cambia con cada versión de MSI. Para determinar la mejor versión de sistema operativo para un MSI determinado, ejecute el script de configuración de la consola una vez. Para obtener más información, vea [Implementar salas de Microsoft Teams con Microsoft Endpoint Configuration Manager.](rooms-scale.md)

Configuration Manager requiere una serie de paquetes para implementar y configurar las unidades de Microsoft Teams Rooms.

Necesita crear y configurar los paquetes siguientes y, después, distribuirlos a los sistemas de sitio de Configuration Manager a los que se les ha asignado el rol de servidor de punto de distribución.

| **Nombre del paquete**                     | **Tipo**               | **Descripción**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - Paquete de aplicaciones SRS     | Paquete de software       | Paquete del kit de implementación de Salas de Microsoft Teams                                      |
| SRS v2 - Paquete Sysprep             | Paquete de software       | Empaquetar el paquete para el Unattended.xml para configurar unidades de salas de Microsoft Teams            |
| SRS v2 - Set-SRSComputerName paquete | Paquete de software       | Empaquetar para la aplicación HTML (HTA) para asignar un nombre de equipo durante la implementación    |
| SRS v2- Configurar el programa de instalación srs         | Paquete de software       | Paquete para configurar la implementación de la aplicación Salas de Microsoft Teams                          |
| SRS v2: paquete de actualizaciones del sistema operativo          | Paquete de software       | Paquete para implementar actualizaciones obligatorias del sistema operativo                                      |
| SRS v2 - Paquete de certificados raíz    | Paquete de software       | Opcional: paquete para implementar el certificado raíz (no necesario para las unidades unida a un dominio)  |
| SRS v2: paquete de agente de supervisión de Microsoft | Paquete de software       | Opcional: paquete para implementar y configurar el agente de Microsoft Operations Management Suite|
| SRS v2 - Paquete de fondo de WinPE    | Paquete de software       | Empaquetar para que la imagen de fondo personalizada se use con imágenes de arranque                           |
| Windows 10 Enterprise                | Imagen de sistema operativo | Paquete para el archivo de instalación del sistema operativo (install.wim)                          |
| Surface Pro                          | Paquete de controlador         | Paquete para los controladores de dispositivo y firmware para Microsoft Surface Pro                     |
| Surface Pro 4                        | Paquete de controlador         | Paquete para los controladores de dispositivo y firmware para Microsoft Surface Pro 4                   |

Para obtener más información, consulta [Paquetes y programas en Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>Crear carpetas para los archivos de origen del paquete

Configuration Manager requiere que los archivos de origen del paquete se organice en una estructura de carpetas específica cuando se crean por primera vez y cuando se actualizan.

Cree la siguiente estructura de carpetas en el sitio de administración central o el sitio principal de Microsoft Endpoint Configuration Manager, o en un recurso compartido de servidor que use para hospedar archivos de origen del paquete:

-   SRS v2: paquete de agente de supervisión de Microsoft
-   SRS v2: paquete de actualizaciones del sistema operativo
-   SRS v2 - Paquete de certificados raíz
-   SRS v2 - Set-SRSComputerName paquete
-   SRS v2 - Paquete de aplicaciones SRS
-   SRS v2- Configurar el programa de instalación srs
-   SRS v2 - Paquete Sysprep
-   Controladores
    -   Surface Pro
    -   Surface Pro 4
-   Sistemas operativos
    -   Windows 10 Enterprise

> [!TIP]
> También puede [descargar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) y usar el archivo zip que incluye la estructura de carpetas de los paquetes, los scripts que necesita usar y la plantilla de secuencia de tareas que necesita importar.

### <a name="create-the-monitoring-agent-package"></a>Crear el paquete de agente de supervisión

1. Descargue el agente de supervisión <https://go.microsoft.com/fwlink/?LinkId=828603> desde.

2. Extraiga el paquete en **la srs v2:** carpeta paquete de agente de supervisión de Microsoft abriendo una ventana del símbolo del sistema y especificando **MMASetup-AMD64.exe /C:**     en el símbolo del sistema.

3. En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**

4. Escribe la siguiente información para crear el paquete:

   - Nombre<strong>: SRS v2 - Paquete de agente de supervisión de Microsoft</strong>

   - Fabricante:<strong>Microsoft Corporation</strong>

   - Versión:<strong>8.1.11081.0</strong> (escriba la versión del archivo de instalación descargado)

   - Selecciona la **casilla Este paquete contiene** archivos de origen, escribe la ruta de acceso a la carpeta **SRS v2-** Paquete del agente de supervisión de Microsoft y, a continuación, **selecciona Siguiente.**

5. Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**

6. Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**

7. Seleccione **Cerrar.**

### <a name="create-the-operating-system-updates-package"></a>Crear el paquete de actualizaciones del sistema operativo

1. En la carpeta del paquete de actualizaciones del sistema operativo **SRS v2,** cree un nuevo script de PowerShell denominado **Install-SRSv2-OS-Updates.ps1.**

2. Copie el script siguiente en el **Install-SRSv2-OS-Updates.ps1** script. Como alternativa, puede descargar el script Install-SRSv2-OS-Updates.ps1 desde [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. Descarga los paquetes de Windows Update obligatorios en la misma carpeta.
   > [!NOTE]
   > En el momento en que se publicó este artículo, solo se requería [KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) Compruebe [Configurar una consola de Salas de Microsoft Teams](console.md)para ver si se necesitan otras actualizaciones.

4. En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**

5. Escribe la siguiente información para crear el paquete:
   -   Nombre: **SRS v2 - Paquete de actualizaciones del sistema operativo**
   -   Fabricante: **Microsoft Corporation**
   -   Versión: **1.0.0**
   -   Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta **SRS v2 - Paquete** de actualizaciones del sistema operativo y, a continuación, seleccione **Siguiente.**

6. Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**

7. Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**

8. Seleccione **Cerrar.**

### <a name="create-the-root-certificate-package-optional"></a>Crear el paquete de certificado raíz (opcional)

Cree este paquete para distribuir el certificado raíz de los dispositivos que no se unirán a un dominio de Active Directory. Crea este paquete solo si se cumplen las dos condiciones siguientes:
-   La implementación incluye Lync local o Skype Empresarial Server.
-   Las unidades de salas de Microsoft Teams están configuradas para trabajar en un grupo de trabajo en lugar de en un miembro del dominio.

1.  Copie el certificado raíz en la **SRS v2: carpeta Paquete de certificados raíz.**

2.  En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**

3.  Escribe la siguiente información para crear el paquete:
    -   Nombre: **SRS v2 - Paquete de certificados raíz**
    -   Fabricante: *el nombre de su organización*
    -   Versión: **1.0.0**
    -   Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta **SRS v2 -** Paquete de certificados raíz y, a continuación, seleccione **Siguiente.**

4.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**

5.  Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**

6.  Seleccione **Cerrar.**

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Crear el paquete de kit de implementación de salas de Microsoft Teams

1.  Descargue la última versión del kit de implementación de Salas de **Microsoft Teams desde** e <https://go.microsoft.com/fwlink/?linkid=851168> instálelo en una estación de trabajo.

2.  Copie el contenido de **C: \\ Program Files (x86) \\ del Kit** de implementación de Sistemas de sala de Skype en la carpeta paquete de aplicaciones **SRS v2 - SRS.**

3.  En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**

4.  Escribe la siguiente información para crear el paquete:
    -   Nombre: **SRS v2 – Paquete de aplicaciones SRS**
    -   Fabricante: **Microsoft Corporation**
    -   Versión: **3.1.104.0** (escriba la versión del archivo de instalación descargado)
    -   Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta del paquete de aplicaciones **SRS v2 – SRS** y, a continuación, **seleccione Siguiente.**
5.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**

6.  Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**

7.  Seleccione **Cerrar.**

### <a name="create-the-computer-name-assignment-package"></a>Crear el paquete de asignación de nombres de equipo

1.  En **srs v2 - Set-SRSComputerName carpeta** paquete, cree una nueva aplicación HTML denominada **Set-SRSComputerName.hta** .

2.  Copie el script siguiente en **el archivo Set-SRSComputerName.hta.** Como alternativa, puede descargar el archivo Set-SRSComputerName.hta desde [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**

4.  Escribe la siguiente información para crear el paquete:

    -   Nombre: **SRS v2 - Set-SRSComputerName paquete**

    -   Fabricante: **Microsoft Corporation**

    -   Versión: **1.0.0**

    -   Selecciona la **casilla Este paquete contiene** archivos de origen, escribe la ruta de acceso a **SRS v2 - Set-SRSComputerName** del paquete y, a continuación, selecciona **Siguiente.**

5.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**

6.  Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**

7.  Seleccione **Cerrar.**

### <a name="create-the-sysprep-package"></a>Crear el paquete Sysprep

1. En la **carpeta del paquete SRS v2 – Sysprep,** cree un nuevo archivo XML denominado **Unattend.xml.**

2. Copie el siguiente texto en el **Unattend.xml** archivo. Como alternativa, puede descargar el archivo Unattend.xml desde [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**

4. Escribe la siguiente información para crear el paquete:
   -   Nombre: **SRS v2 - paquete Sysprep**
   -   Fabricante: **Microsoft Corporation**
   -   Versión: **1.0.0**
   -   Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta del paquete **SRS v2 – Sysprep** y, a continuación, **seleccione Siguiente.**
5. Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**

6. Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**

7. Seleccione **Cerrar.**

### <a name="create-the-windows-10-enterprise-package"></a>Crear el paquete de Windows 10 Enterprise

1.  Obtenga un medio x64 de Windows 10 Enterprise y copie el archivo **install.wim** en la carpeta Sistemas operativos **\\ windows 10 Enterprise.**

2.  En la consola del Administrador de configuración, vaya a Imágenes de sistema operativo de la biblioteca de **software** y, a continuación, \>  \> seleccione Agregar **imagen de sistema operativo.**

3.  Especifique la ruta de acceso al **archivo install.wim** que acaba de copiar y, a continuación, seleccione **Siguiente.**

4.  Actualice el **campo** Versión para que coincida con el número de compilación de la imagen de Windows 10 Enterprise y, a continuación, **seleccione Siguiente.**

5.  Revise la **página** detalles y, a continuación, seleccione **Siguiente.**

6.  Seleccione **Cerrar.**

Para obtener más información, vea [Administrar imágenes del sistema operativo con Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Crear paquetes de controlador de dispositivo Surface Pro

Salas de Microsoft Teams es compatible tanto con Surface Pro como con Surface Pro 4. Debes crear un paquete de controlador para cada modelo de Surface Pro que tienes en tu entorno.

> [!IMPORTANT]
> Los controladores deben ser compatibles con la compilación de Windows 10 Enterprise y la versión del kit de implementación de Microsoft Teams Rooms. Para obtener más información, consulte Descargar el firmware y los controladores más recientes para [dispositivos Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) y [Configurar una consola.](console.md)

1.  Descargue los controladores y el firmware más recientes.
    -   Para Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484>
    -   Para Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extraiga el controlador y el firmware descargados. Abra una ventana del símbolo del sistema y, en el símbolo del sistema, escriba uno de los siguientes comandos:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  En la consola del Administrador de configuración, vaya **a Controladores** de sistemas operativos de la biblioteca de software y, a \>  \> continuación, seleccione **Importar controlador.**

4.  Seleccione Importar todos los controladores en la siguiente ruta de red **(UNC),** seleccione la carpeta de origen (por ejemplo, C: _Sources Controladores surface Pro) y, a continuación, \\ \\ seleccione \\ **Siguiente.**

5.  En la **página Especificar los detalles** de los controladores importados, seleccione todos los controladores de la lista y, a continuación, seleccione Habilitar estos controladores y permitir que los equipos los **instalen.**

6.  Selecciona **Categorías,** crea una nueva categoría que coincida con el modelo de Surface, **selecciona** Aceptar y, a continuación, selecciona **Siguiente.**

7.  Seleccione **Nuevo paquete.**

8.  Especifica el nombre del paquete que coincida con el modelo de Surface Pro, escribe una ruta de carpeta en la que almacenar los archivos del paquete del controlador, selecciona Aceptar **y,** a continuación, **selecciona Siguiente.**

9.  En la **página de imágenes de** arranque, asegúrese de que no haya imágenes de arranque seleccionadas y, después, seleccione **Siguiente.**

10. Seleccione **Cerrar.**

11. Ve a **Controladores de** sistemas operativos de biblioteca de \>  \> **software,** selecciona **\>** Crear carpeta y escribe un nombre de carpeta que coincida con el modelo de Surface Pro del que has importado los controladores.

12. Mueva todos los controladores importados a la carpeta recién creada para facilitar la navegación y la operación.

> [!NOTE]
> Repite los mismos pasos para otros modelos de Surface Pro que podrías tener. Para obtener más información, vea [Administrar controladores en Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Paquete de configuración Crear salas de Microsoft Teams

1.  En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**

2.  Escribe la siguiente información para crear el paquete:

    -   Nombre: **SRS v2 - Configurar paquete de instalación SRS**

    -   Fabricante: **Microsoft Corporation**

    -   Versión: **1.0.0**

    -   Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta configuración SRS v2 - Configurar **SRS y,** a continuación, **seleccione Siguiente.**

3.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**

4.  Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**

5.  Seleccione **Cerrar.**



## <a name="distribute-configuration-manager-packages"></a>Distribuir paquetes de Configuration Manager

Todos los paquetes deben distribuirse a los servidores a los que se les haya asignado el rol de punto de distribución en la jerarquía de Configuration Manager. Siga las instrucciones siguientes para iniciar la distribución de paquetes.

1.  Distribuir paquetes de software.

    1.  En la consola del Administrador de configuración, vaya a Paquetes **de administración** de aplicaciones de \> **biblioteca de** \> **software.** Selecciona todos los paquetes de software que quieras distribuir y, a continuación, **selecciona Distribuir contenido.**

    2.  Revisa la lista de paquetes y, a continuación, selecciona **Siguiente.**

    3.  Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, después, seleccione **Siguiente.**

    4.  Seleccione **Siguiente** y, a continuación, **seleccione Cerrar.**

2.  Distribuir paquetes de controlador.

    1.  En la consola de Configuration Manager, vaya a paquetes **de** controlador \> **de sistemas operativos de biblioteca** \> **de software.** Selecciona todos los paquetes de controlador que quieras distribuir y, a continuación, **selecciona Distribuir contenido.**

    2.  Revisa la lista de paquetes y, a continuación, selecciona **Siguiente.**

    3.  Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, después, seleccione **Siguiente.**

    4.  Seleccione **Siguiente** y, a continuación, **seleccione Cerrar.**

3.  Distribuir paquetes de sistema operativo.

    1.  En la consola de Configuration Manager, vaya **a** Imágenes de sistema operativo de la biblioteca de \>  \> **software.** Seleccione todas las imágenes del sistema operativo que quiera distribuir y, después, **seleccione Distribuir contenido.**

    2.  Revisa la lista de paquetes y, a continuación, selecciona **Siguiente.**

    3.  Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, después, seleccione **Siguiente.**

    4.  Seleccione **Siguiente** y, a continuación, **seleccione Cerrar.**

> [!NOTE]
> La distribución de paquetes puede tardar algún tiempo, dependiendo del tamaño del paquete, la jerarquía de Configuration Manager, el número de servidores de puntos de distribución y el ancho de banda disponible en su red.
> 
> Todos los paquetes deben distribuirse antes de empezar a implementar una unidad de Microsoft Teams Rooms.
> 
> Para revisar el estado de la distribución de paquetes en la consola de Configuration Manager, vaya a Supervisar **el estado** \> **del contenido de la** \> **distribución.**

## <a name="configuration-manager-task-sequences"></a>Secuencias de tareas de Configuration Manager

Use secuencias de tareas con Configuration Manager para automatizar los pasos para implementar una imagen de sistema operativo en un equipo de destino. Para implementar una unidad de Salas de Microsoft Teams de forma automatizada, cree una secuencia de tareas que haga referencia a la imagen de arranque usada para iniciar el equipo de Microsoft Teams Rooms de destino, la imagen del sistema operativo Windows 10 Enterprise que desea instalar y cualquier otro contenido adicional, como otras aplicaciones o actualizaciones de software.

### <a name="import-the-sample-task-sequence"></a>Importar la secuencia de tareas de ejemplo

Puede descargar e importar fácilmente una secuencia de tareas de ejemplo y personalizarla para satisfacer sus necesidades.

1.  [**Descargue**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la secuencia de tareas de ejemplo y copie el archivo zip descargado en una ubicación compartida.
2.  En la consola del Administrador de configuración, vaya **a** Secuencias de tareas de sistemas operativos de la biblioteca de software y, a \>  \> continuación, seleccione **Importar secuencia de tareas.**

3.  Seleccione **Examinar,** vaya a la ubicación de la carpeta compartida que usó en el paso 1, seleccione el archivo zip Implementación de Salas de **Microsoft Teams (EN-US)** y, después, seleccione **Siguiente.**

4.  Establezca **la** acción **en Crear** nuevo y, a continuación, seleccione **Siguiente.**

5.  Confirme la configuración y, a continuación, seleccione **Siguiente.**

6.  Seleccione **Cerrar.**

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Valide que los paquetes de referencia están vinculados correctamente a cada paso de secuencia de tareas.

1. Seleccione la secuencia de tareas importada y, a continuación, **seleccione Editar.**

    El Editor de secuencia de tareas se abre y muestra cada paso secuencial que necesita para implementar y configurar una unidad de Salas de Microsoft Teams.

2. Siga cada paso y complete las actualizaciones recomendadas:

   1. **Reiniciar en Windows PE:** este paso se reinicia y, a continuación, se reactiva el equipo a PXE de Windows. No es necesario realizar ningún cambio en este paso.

   2. **Partición del disco 0 - UEFI:** este paso borra la configuración del disco y crea particiones según la configuración configurada. Le recomendamos que no realice ningún cambio en este paso.

   3. Establecer el nombre del equipo **SRS:** en este paso se incluye una aplicación HTML para proporcionar una interfaz de usuario con el fin de establecer un nombre de equipo para las unidades de salas de Microsoft Teams durante la implementación.
      -  Este paso es opcional, pero solo se puede deshabilitar si desea administrar los nombres del equipo a través de un proceso alternativo.
      -  Compruebe que el **paquete SRS v2 - Set-SRSComputerName** está seleccionado. Si no es así, busca el paquete y selecciónelo.

   4. **Aplicar sistema operativo:** en este paso se especifica la imagen del sistema operativo que se va a implementar y el archivo de respuesta Sysprep desatendida que se usará.
      -  Compruebe que está seleccionado el archivo de imagen del sistema operativo Windows 10 Enterprise correcto.
      -  Compruebe que está habilitado el uso de un archivo de respuesta **de sysprep** o desatendida para una instalación personalizada y que el **paquete SRS v2 - Sysprep** está seleccionado. Asegúrese también de que **el nombre de** archivo esté **unattend.xml.**

   5. **Aplicar la configuración de Windows:** este paso recopila información sobre la instalación de Windows.
      -  Proporcione información de licencias y registro, incluida la clave de producto, la contraseña de la cuenta de administrador local y la zona horaria (según sus necesidades).

   6. **Aplicar la configuración de** red: este paso le permite especificar un grupo de trabajo o un nombre de dominio de Active Directory y una unidad organizativa.
      > [!NOTE]
      > Consulte [consideraciones para unirse](domain-joining-considerations.md) a un dominio de Sistema de salas de Skype para conocer las acciones recomendadas que debe realizar al implementar unidades de Salas de Microsoft Teams como miembros de un dominio del directorio de Actve.
   7. **Aplicar controladores:** Este paso y sus sub steps se usan para implementar el firmware y los controladores de dispositivo aplicables en función del modelo de Surface Pro que tenga. Actualice cada paso para especificar el paquete de controlador relevante asociado a esta implementación.
      -   Cada paquete de controlador se configura para aprovechar los filtros de Windows Management Se ha personalizado (ODBC) para implementar controladores y firmware relevantes en función de la marca y el modelo de Surface Pro.
      -   Recomendamos encarecidamente no modificar la configuración de estos controladores, de lo contrario, la implementación podría producir un error.

   8. **Configurar Windows y Configuration Manager:** este paso implementa y configura el cliente de Configuration Manager. Actualice este paso para especificar el paquete de cliente integrado de Configuration Manager.

   9. **Instalar certificado raíz:** este paso distribuye el certificado raíz para dispositivos que no están unidos a un dominio y, por lo tanto, es opcional e deshabilitado de forma predeterminada.
      -   Habilite este paso si necesita implementar un certificado raíz en las unidades de Salas de Microsoft Teams.
      -   Si necesita realizar este paso, compruebe que la **srs v2 :** paquete de certificado raíz y deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionados.

   10. **Instalar y configurar** el agente de supervisión: este paso instala la versión de 64 bits del agente de Microsoft Azure Monitor y configura el agente para conectarse a su área de trabajo de Log Analytics.
       -   Este paso está deshabilitado de forma predeterminada. Habilite este paso solo si va a usar el agente de supervisión para supervisar el estado de las unidades de Microsoft Teams Rooms.
       -   Edite este paso y actualice los parámetros de la línea de comandos para especificar el **id. del área de trabajo y** la clave del área de **trabajo.**
       -   Vea [Configurar dispositivos de prueba de Azure Monitoring para](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) obtener más información sobre cómo obtener el id. de área de trabajo del conjunto de aplicaciones de administración de operaciones y la clave principal.
       -   Compruebe que las **funciones SRS v2 : Paquete del agente** de supervisión de Microsoft y Deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionadas.
       -   Para obtener más información sobre cómo supervisar el mantenimiento de la implementación de salas de Microsoft Teams, vea Planear la administración de salas de Microsoft Teams con [Azure Monitor,](azure-monitor-plan.md)Implementar la administración de salas de Microsoft Teams con [Azure Monitor](azure-monitor-deploy.md) y administrar dispositivos de Salas de Microsoft Teams con [Azure Monitor.](azure-monitor-manage.md)

   11. **Copiar archivos de configuración SRS v2:** este paso copia los archivos de configuración y configuración necesarios del kit de implementación de Salas de Microsoft Teams en la unidad de disco duro local. No se requiere personalización para este paso.
       -   Compruebe que las **aplicaciones SRS v2 – SRS Application Package** y Disable **64-bit file system redirection** are selected.

   12. **Install-SRSv2-OS-Updates:** en este paso se implementan las actualizaciones obligatorias del sistema operativo necesarias en la implementación de Salas de Microsoft Teams. Haga lo siguiente:
       -   Compruebe [Configurar una consola de Salas de Microsoft Teams](console.md) para ver qué actualizaciones son necesarias.
       -   Compruebe que el paquete de actualizaciones del sistema operativo **SRS v2** incluye todas las actualizaciones necesarias.
       -   Compruebe que el **paquete de actualizaciones de SRS v2 - OS está** seleccionado.
       -   Compruebe que la directiva de ejecución de PowerShell esté establecida en **Omitir.**

   13. **Reiniciar Equipo:** este paso reinicia el equipo después de instalar las actualizaciones de sistema operativo obligatorias. No se requiere personalización para este paso.

   14. **Configurar componentes de Windows:** este paso configura las características de Windows necesarias. No se requiere personalización para este paso.

   15. **Reiniciar Equipo:** este paso reinicia el equipo después de configurar las características de Windows. No se requiere personalización para este paso.

   16. **Agregar usuario de Skype local:** este paso crea la cuenta de Skype local que se usa para iniciar sesión automáticamente en Windows e iniciar la aplicación Salas de Microsoft Teams. Este paso no tiene ningún paquete de software asociado y no se requiere personalización para él.

   17. **Configurar y configurar la aplicación SRS:** este paso configura la instalación de la aplicación Salas de Microsoft Teams para el próximo arranque del sistema operativo.
       -   Compruebe que la **versión SRS v2:** configurar el paquete de instalación SRS y deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionadas.

> [!IMPORTANT]
> Es muy importante que los pasos de la secuencia de tareas deben estar en el orden proporcionado. Modificar el orden de los pasos o configurar pasos adicionales puede interrumpir la implementación.
>
> **El paso de la aplicación SRS** de configuración y configuración debe ser el último paso de la secuencia de tareas; de lo contrario, podría producirse un error en la implementación.

### <a name="create-deployment-for-the-task-sequence"></a>Crear una implementación para la secuencia de tareas

1. Seleccione la secuencia de tareas y, después, seleccione **Implementar.**

2. Seleccione **Examinar para** seleccionar una colección de destino para la implementación.

3. Seleccione **Todos los equipos desconocidos** y, después, haga clic en **Aceptar.**

4. Seleccione **Siguiente.**

5. Seleccione **Disponible** en la **lista desplegable** Propósito.

6. Seleccione **Solo multimedia y PXE** en Hacer que esté disponible en la **siguiente** lista y, a continuación, seleccione **Siguiente.**
   > [!WARNING]
   > Es muy importante que **Purpose se** establezca en **Disponible.** Asegúrese de que **la finalidad** **no esté** establecida en **Obligatorio.** Asegúrese también de seleccionar Solo **multimedia y PXE** en **Hacer disponible para lo siguiente.**
   >
   > Si establece estos valores en otra cosa, es posible que todos los equipos obtengan la imagen de implementación de Salas de Microsoft Teams al iniciarse.
7. No especifique ninguna programación y seleccione **Siguiente.**

8. No cambie nada en la sección **Experiencia del** usuario y seleccione **Siguiente.**

9. No cambie nada en la sección **Alertas** y seleccione **Siguiente.**

10. No cambie nada en la sección **Puntos de distribución** y seleccione **Siguiente.**

11. Confirme la configuración y, a continuación, **seleccione Siguiente.**

12. Seleccione **Cerrar.**

<a name="validate-and-troubleshoot-the-solution"></a>Validar y solucionar problemas de la solución
--------------------------------------

Después de completar las secuencias de tareas de Microsoft Endpoint Configuration Manager, deberá realizar una ejecución de prueba para validar que la secuencia de tareas pueda implementar y configurar unidades de Salas de Microsoft Teams.

1.  Conecta el dispositivo de prueba a la red cableada usando uno de los adaptadores Ethernet compatibles o mediante Surface Dock. Si la funcionalidad de arranque PXE no se ha configurado para su [](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) entorno, puede usar la imagen de arranque en la unidad flash USB que creó anteriormente para iniciar desde USB y conectarse a Configuration Manager.

2.  Obtenga acceso al firmware e inicie el inicio de PXE:

    1.  Asegúrate de que el dispositivo Surface esté apagado.

    2.  Mantenga presionado el botón **Subir** volumen.

    3.  Presione y suelte el **botón Inicio/Apagado.**

    4.  Cuando se empiece a iniciar el dispositivo, suelta el **botón Subir** volumen.

    5.  Seleccione **Configuración de arranque.**

    6.  Realice una de las siguientes acciones:

        -   Seleccione **el arranque PXE** y arrástrelo hasta la parte superior de la lista. Como alternativa, puedes deslizar a la izquierda en el adaptador de red para iniciar en el dispositivo inmediatamente. Esto no afectará al orden de arranque.
        -   Selecciona la unidad flash USB que contiene el medio de arranque.

3.  Seleccione **Salir** y, a continuación, **seleccione Reiniciar ahora.**

4.  Cuando se le solicite, seleccione **Entrar para el** servicio de arranque de red.

5.  Windows PE se cargará en la memoria y se iniciará el Asistente para secuencia de tareas. Selecciona **Siguiente** para continuar.

6.  Seleccione la secuencia de tareas que importó anteriormente y, a continuación, seleccione **Siguiente.**

7.  Después de aplicar la configuración de disco, se le pedirá que especifique un nombre de equipo para el dispositivo. La interfaz de usuario mostrará un nombre de equipo recomendado según el número de serie del dispositivo Surface Pro. Puede aceptar el nombre propuesto o especificar uno nuevo. Siga las instrucciones que aparecen en la pantalla de asignación de nombres de equipo. Al seleccionar **Aceptar,** se inicia la implementación.

8.  El resto del proceso de implementación es automático y no pide más entrada de usuarios.

9.  Cuando la secuencia de tareas de implementación termine de configurar el dispositivo, verá la pantalla de configuración siguiente que le pide que configure las opciones de la aplicación Microsoft Teams Rooms.

    ![Pantalla de configuración inicial de la aplicación Salas de Microsoft Teams](../media/room-systems-scale-image2.png)

10.  Conecte Surface Pro a la consola Microsoft Teams Rooms y configure la configuración de la aplicación.

11.  Valide que las funcionalidades enumeradas [en salas de Microsoft Teams funcionan](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) en el dispositivo implementado.


Para solucionar problemas de instalación con errores, consulte el **archivo SMSTS.log,** que registra todos los pasos ejecutados en una secuencia de tareas de Configuration Manager.

El archivo SMSTS.log se almacena en una de varias rutas de acceso, según la fase del proceso de compilación. Compruebe la tabla siguiente para identificar la ruta de acceso al archivo SMSTS.log.


| **Fase de implementación**                                                            | **Ruta de registro de secuencia de tareas**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, antes del formato JPEG                                                        | X: \\ Windows \\ Temp \\ smstslog \\ smsts.log             |
| WinPE, después del formato JPEG                                                         | C: \\ _SMSTaskSequence \\ Registros \\ smstslog \\ smsts.log    |
| Sistema operativo implementado, antes de instalar el agente de Configuration Manager | c: \\ _SMSTaskSequence \\ Registros \\ smstslog \\ smsts.log    |
| Sistema operativo y agente de Configuration Manager implementados                   | %windir% \\ System32 \\ ccm logs \\ \\ Smstslog \\ smsts.log |
| Ejecución completada de la secuencia de tareas                                                | %windir% \\ System32 \\ ccm logs \\ \\ smsts.log           |

> [!TIP]
> Puedes seleccionar **F8 en cualquier** momento durante la secuencia de tareas para abrir una consola de comandos y, a continuación, obtener acceso al archivo SMSTS.log.

Para solucionar problemas de arranque pxe, compruebe los dos archivos de registro en el servidor de Configuration Manager que son específicos de las acciones de PXE:

-   **Pxecontrol.log,** ubicado en el directorio de registros de instalación de Configuration Manager

-   **Smspxe.log,** ubicado en el directorio de registros del Punto de administración del Administrador de configuración (MP).

Para obtener una lista completa de los archivos de registro que puede usar para solucionar más problemas en la instalación de Configuration Manager, consulte la referencia del archivo de registro de Microsoft Endpoint Configuration [Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)
