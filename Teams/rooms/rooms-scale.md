---
title: Implementar Salas de Microsoft Teams con Microsoft Endpoint Configuration Manager
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
description: Obtenga información sobre cómo implementar Salas de Microsoft Teams implementaciones a gran escala con Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 1dabc8e4b3f2e238945bf68fdbad73cebebd7fd5
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646681"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Implementar Salas de Microsoft Teams mediante Microsoft Endpoint Configuration Manager

En este artículo se proporciona toda la información necesaria para crear Salas de Microsoft Teams implementaciones mediante Microsoft Endpoint Configuration Manager.

Con los métodos fáciles de usar proporcionados por Configuration Manager, puede implementar el sistema operativo y otras aplicaciones en varios dispositivos de destino.

Use el método que se muestra a continuación para guiarlo por la configuración de Configuration Manager y personalizar los paquetes y scripts de ejemplo proporcionados a lo largo de esta guía según sea necesario para su organización.

![Salas de Microsoft Teams de implementación con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Esta solución solo se ha probado con Surface Pro implementaciones basadas en aplicaciones. Siga las directrices del fabricante para las configuraciones que no se basan en Surface Pro.

## <a name="validate-prerequisites"></a>Validar requisitos previos

Para implementar Salas de Microsoft Teams con Configuration Manager, asegúrese de que cumple los siguientes requisitos previos y requisitos.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager requisitos

-   Microsoft Endpoint Configuration Manager versión debe ser como mínimo 1706 o superior. Se recomienda usar 1710 o posterior. Consulte Soporte [técnico para Windows 10 en Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para obtener información sobre las Windows 10 compatibles con Configuration Manager.

-   Debe instalarse una versión compatible Windows de evaluación e implementación (ADK) para Windows 10 instalación. Consulte las versiones del [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que puede usar con diferentes versiones de Configuration Manager y asegúrese de que la implementación incluye la versión correcta.

-   Los servidores del sistema de sitio deben tener asignado el rol de punto de distribución y las imágenes de inicio deben estar habilitadas para la compatibilidad con el entorno de ejecución previa al inicio [(PXE)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar las implementaciones iniciadas por la red. Si la compatibilidad con PXE no está habilitada, puede usar medios [de inicio](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones.

-   Se debe configurar una cuenta de acceso de red para admitir nuevos escenarios de implementación de equipos (sin formato). Para obtener más información sobre la configuración de una cuenta de acceso de red, vea [Cuentas usadas en Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   Le recomendamos que habilite la compatibilidad con [multidifusión](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)si es probable que implemente la misma imagen Salas de Microsoft Teams en varias unidades al mismo tiempo.

### <a name="networking-requirements"></a>Requisitos de red

-   La red debe tener un servidor de Protocolo de configuración dinámica de host (DHCP), configurado para la distribución automática de direcciones IP en las subredes donde se implementarán Salas de Microsoft Teams unidades.

    > [!NOTE]
    > La duración de la concesión de DHCP debe establecerse en un valor mayor que la duración de la implementación de la imagen. En caso contrario, la implementación podría producir un error.

-   La red, incluidos los modificadores y las LAN virtuales (VLAN), debe configurarse para admitir PXE. Consulte a su proveedor de red para obtener más información sobre ayuda IP y configuración PXE. Como alternativa, puede usar medios [de](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) inicio para las implementaciones, si la compatibilidad con PXE no está habilitada.

    > [!NOTE]
    > Para Surface Pro dispositivos, el inicio desde la red (arranque PXE) solo es compatible cuando se usa un adaptador Ethernet o una estación de acoplamiento de Microsoft. Los adaptadores Ethernet de terceros no admiten el arranque PXE con Surface Pro. Vea [Adaptadores Ethernet e implementación de Surface](/surface/ethernet-adapters-and-surface-device-deployment) para obtener más información.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Configurar Microsoft Endpoint Configuration Manager para la implementación del sistema operativo

En este artículo se supone que ya tiene una implementación de Configuration Manager en buen estado y no detalla todos los pasos necesarios para implementar y configurar Configuration Manager desde cero. La [documentación y las instrucciones de configuración](/configmgr/) del Microsoft Endpoint Configuration Manager es un gran recurso; Le recomendamos que empiece con estos recursos si aún no ha implementado Configuration Manager.

Use las siguientes instrucciones para comprobar que las características de implementación del sistema operativo (OSD) están configuradas correctamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Validar y actualizar Configuration Manager

1.  En la consola de Configuration Manager, vaya **a Actualizaciones** de administración \> **y mantenimiento.**

2.  Compruebe la compilación instalada y las actualizaciones aplicables que aún no se han instalado.

3.  Revisar [el soporte técnico Windows 10 en Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); si necesita actualizar la implementación, seleccione la actualización que desea instalar y, a continuación, **seleccione Descargar**.

4.  Una vez completada la descarga, seleccione la actualización y, a continuación, **seleccione Instalar paquete de actualización.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurar puntos de distribución para admitir PXE y multidifusión

1.  En la consola de Configuration Manager, vaya a **Puntos de distribución** de \> **administración.**

2.  Seleccione el servidor de punto de distribución que servirá a la Salas de Microsoft Teams y, a continuación, seleccione **Propiedades.**

3.  Seleccione la **pestaña PXE** y asegúrese de que las opciones de configuración siguientes están habilitadas:
    -   Habilitar la compatibilidad con PXE para clientes
    -   Permitir que este punto de distribución responda a las solicitudes PXE entrantes
    -   Habilitar la compatibilidad con equipos desconocidos

4.  *Opcional:* Para habilitar la compatibilidad con multidifusión, seleccione la pestaña **Multidifusión** y asegúrese de que la siguiente configuración está habilitada:
    -   Habilitar multidifusión para enviar datos simultáneamente a varios clientes
    -   Configurar el rango de puertos UDP según la recomendación de su equipo de red

### <a name="configure-the-network-access-account"></a>Configurar la cuenta de acceso a la red

1.  En la consola de Configuration Manager, vaya a Sitios **de** configuración del sitio \> **de** \> **administración** y, a continuación, seleccione el sitio.

2.  En el **Configuración,** seleccione **Configurar la distribución** de software de componentes \> **del sitio.**

3.  Seleccione la **pestaña Cuenta de acceso a la** red. Configure una o más cuentas y, a continuación, seleccione **Aceptar.**

> [!NOTE]
> Las cuentas no necesitan ningún derecho especial, excepto el acceso a este equipo desde **la** red directamente en el servidor de punto de distribución. Una cuenta de usuario de dominio genérico será apropiada. Para obtener más información, vea [Cuentas usadas en Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Configurar una imagen de inicio

1.  En la consola de Configuration Manager, vaya a **Imágenes** de inicio del \> **sistema operativo biblioteca** \> **de** software.

2.  Seleccione **Imagen de inicio (x64)** y, a continuación, propiedades. 

3.  Seleccione la **pestaña Origen de** datos y habilite Implementar esta imagen de inicio desde el punto de distribución habilitado para **PXE.**

4.  Seleccione la **pestaña Componentes opcionales** para instalar los componentes necesarios:

    1.  Seleccione el icono de estrella y busque **HTML (WinPE-HTA)**

    2.  Seleccione **Aceptar** para agregar compatibilidad con aplicaciones HTML a la imagen de inicio.

5.  *Opcional:* Para personalizar la experiencia de implementación, seleccione la **pestaña Personalización.**
    -   Habilite **la compatibilidad con comandos (solo pruebas)** si quiere tener acceso a un símbolo del sistema durante la implementación. Cuando esté habilitado, puede iniciar un símbolo del sistema **seleccionando F8** en cualquier momento durante la implementación.
    -   También puede especificar una imagen de fondo personalizada que se mostrará durante la implementación. Para establecer una imagen, habilite Especificar el archivo de imagen de **fondo personalizado (ruta UNC** y seleccione el fondo.

6.  Cuando se le pregunte, **seleccione Sí** y distribuya la imagen de inicio actualizada a los puntos de distribución.

Para obtener más información, vea [Administrar imágenes de inicio con Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> Puede crear un medio USB de inicio para iniciar implementaciones basadas en secuencias de tareas de Configuration Manager para entornos que no admiten PXE. El medio de inicio contiene solo la imagen de inicio, los comandos de prearranco opcionales y sus archivos necesarios, y los archivos binarios de Configuration Manager para admitir el inicio en Windows PE y la conexión a Configuration Manager durante el resto del proceso de implementación. Para obtener más información, vea [Crear medios de inicio.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Crear paquetes de Configuration Manager

> [!IMPORTANT]
> La versión del sistema operativo necesaria para cada versión del instalador SRS cambia con cada versión de MSI. Para determinar la mejor versión del sistema operativo para un MSI determinado, ejecute el script de configuración de la consola una vez. Para obtener más información, vea [Implementar Salas de Microsoft Teams mediante Microsoft Endpoint Configuration Manager](rooms-scale.md).

Configuration Manager requiere una serie de paquetes para implementar y configurar las Salas de Microsoft Teams unidades.

Debe crear y configurar los paquetes siguientes y, a continuación, distribuirlos a los sistemas de sitio de Configuration Manager a los que se les ha asignado el rol de servidor de punto de distribución.

| **Nombre del paquete**                     | **Tipo**               | **Descripción**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 : paquete de aplicaciones SRS     | Paquete de software       | Paquete para el kit Salas de Microsoft Teams implementación                                      |
| SRS v2 : paquete sysprep             | Paquete de software       | Paquete para el Unattended.xml personalizado para configurar Salas de Microsoft Teams unidades            |
| SRS v2: Set-SRSComputerName paquete | Paquete de software       | Paquete para la aplicación HTML (HTA) para asignar un nombre de equipo durante la implementación    |
| SRS v2: Configurar la configuración de SRS         | Paquete de software       | Paquete para configurar la implementación de la Salas de Microsoft Teams aplicación                          |
| SRS v2: paquete de actualizaciones del sistema operativo          | Paquete de software       | Paquete para implementar actualizaciones obligatorias del sistema operativo                                      |
| SRS v2: paquete de certificado raíz    | Paquete de software       | Opcional: paquete para implementar el certificado raíz (no necesario para unidades unidas a dominios)  |
| SRS v2: Microsoft Monitoring Agent paquete | Paquete de software       | Opcional: paquete para implementar y configurar el agente de Microsoft Operations Management Suite|
| SRS v2: paquete de fondo de WinPE    | Paquete de software       | Paquete para que la imagen de fondo personalizada se use con imágenes de inicio                           |
| Windows 10 Enterprise                | Imagen del sistema operativo | Paquete para el archivo de instalación del sistema operativo (install.wim)                          |
| Surface Pro                          | Paquete de controladores         | Paquete para los controladores de dispositivo y firmware para Microsoft Surface Pro                     |
| Surface Pro 4                        | Paquete de controladores         | Paquete para los controladores de dispositivo y firmware para Microsoft Surface Pro 4                   |

Para obtener más información, vea [Paquetes y programas en Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>Crear carpetas para los archivos de origen del paquete

Configuration Manager requiere que los archivos de origen de paquetes se organice en una estructura de carpetas específica cuando se crean por primera vez y cuando se actualizan.

Cree la siguiente estructura de carpetas en el Microsoft Endpoint Configuration Manager de administración central o en un sitio principal, o en un recurso compartido de servidor que usa para hospedar archivos de origen de paquetes:

-   SRS v2: Microsoft Monitoring Agent paquete
-   SRS v2: paquete de actualizaciones del sistema operativo
-   SRS v2: paquete de certificado raíz
-   SRS v2: Set-SRSComputerName paquete
-   SRS v2 : paquete de aplicaciones SRS
-   SRS v2: Configurar la configuración de SRS
-   SRS v2 : paquete sysprep
-   Controladores
    -   Surface Pro
    -   Surface Pro 4
-   Sistemas operativos
    -   Windows 10 Enterprise

> [!TIP]
> También puede [descargar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) y usar el archivo zip que incluye la estructura de carpetas para los paquetes, los scripts que necesita usar y la plantilla de secuencia de tareas que necesita importar.

### <a name="create-the-monitoring-agent-package"></a>Crear el paquete del agente de supervisión

1. Descargue el agente de supervisión desde <https://go.microsoft.com/fwlink/?LinkId=828603> .

2. Extraiga el paquete en **srs v2 - Microsoft Monitoring Agent carpeta** paquete abriendo una ventana del símbolo del sistema yMMASetup-AMD64.exe **/C:** en el símbolo del sistema.

3. En la consola de Configuration Manager, vaya a **Paquetes** de administración de aplicaciones de biblioteca de software y, a \>  \> continuación, **seleccione Crear paquete.**

4. Escriba la siguiente información para crear el paquete:

   - Nombre:<strong>SRS v2 - Microsoft Monitoring Agent paquete</strong>

   - Fabricante:<strong>Microsoft Corporation</strong>

   - Versión:<strong>8.1.11081.0</strong> (escriba la versión del archivo de instalación descargado)

   - Active la casilla Este paquete contiene archivos **de origen,** escriba la ruta de acceso a la **carpeta SRS v2 - Microsoft Monitoring Agent Paquete** y, a continuación, seleccione **Siguiente**.

5. Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente**.

6. Revise la **página Confirmar la configuración** y, a continuación, seleccione **Siguiente.**

7. Seleccione **Cerrar**.

### <a name="create-the-operating-system-updates-package"></a>Crear el paquete de actualizaciones del sistema operativo

1. En la carpeta Paquete de actualizaciones del sistema operativo **SRS v2,** cree un nuevo script de PowerShell denominado **Install-SRSv2-OS-Updates.ps1**.

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
3. Descargue los paquetes de actualización Windows obligatorios en la misma carpeta.
   > [!NOTE]
   > En el momento en que se publicó este artículo, solo se requería [KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) Active [Configurar una Salas de Microsoft Teams de](console.md)datos para ver si se necesitan otras actualizaciones.

4. En la consola de Configuration Manager, vaya a **Paquetes** de administración de aplicaciones de biblioteca de software y, a \>  \> continuación, **seleccione Crear paquete.**

5. Escriba la siguiente información para crear el paquete:
   -   Nombre: **SRS v2: paquete de actualizaciones del sistema operativo**
   -   Fabricante: **Microsoft Corporation**
   -   Versión: **1.0.0**
   -   Active la **casilla Este paquete contiene archivos de origen,** escriba la ruta de acceso a la carpeta Paquete de actualizaciones del sistema operativo **SRS v2** y, a continuación, **seleccione Siguiente.**

6. Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente**.

7. Revise la **página Confirmar la configuración** y, a continuación, seleccione **Siguiente.**

8. Seleccione **Cerrar**.

### <a name="create-the-root-certificate-package-optional"></a>Crear el paquete de certificado raíz (opcional)

Cree este paquete para distribuir el certificado raíz para dispositivos que no se unirán a un dominio de Active Directory. Cree este paquete solo si se aplican las dos condiciones siguientes:
-   Su implementación incluye Lync local o Skype Empresarial Server.
-   Salas de Microsoft Teams unidades están configuradas para trabajar en un grupo de trabajo en lugar de en un miembro del dominio.

1.  Copie el certificado raíz en la carpeta Paquete de certificado raíz **SRS v2.**

2.  En la consola de Configuration Manager, vaya a **Paquetes** de administración de aplicaciones de biblioteca de software y, a \>  \> continuación, **seleccione Crear paquete.**

3.  Escriba la siguiente información para crear el paquete:
    -   Nombre: **SRS v2: paquete de certificado raíz**
    -   Fabricante: *el nombre de su organización*
    -   Versión: **1.0.0**
    -   Active la **casilla Este paquete contiene archivos de origen,** escriba la ruta de acceso a la carpeta **SRS v2 – Paquete** de certificado raíz y, a continuación, seleccione **Siguiente.**

4.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente**.

5.  Revise la **página Confirmar la configuración** y, a continuación, seleccione **Siguiente.**

6.  Seleccione **Cerrar**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Crear el paquete Salas de Microsoft Teams kit de implementación

1.  Descargue la última versión del Salas de Microsoft Teams **de implementación de** e <https://go.microsoft.com/fwlink/?linkid=851168> inscártelo en una estación de trabajo.

2.  Copie el contenido de C: Archivos de programa **\\ \\ (x86)** Skype kit de implementación del sistema de sala en la carpeta Paquete de aplicaciones **SRS v2 - SRS.**

3.  En la consola de Configuration Manager, vaya a **Paquetes** de administración de aplicaciones de biblioteca de software y, a \>  \> continuación, **seleccione Crear paquete.**

4.  Escriba la siguiente información para crear el paquete:
    -   Nombre: **SRS v2 : paquete de aplicaciones SRS**
    -   Fabricante: **Microsoft Corporation**
    -   Versión: **3.1.104.0** (escriba la versión del archivo de instalación descargado)
    -   Active la **casilla Este paquete contiene archivos de origen,** escriba la ruta de acceso a la carpeta **SRS v2 – Paquete** de aplicaciones SRS y, a continuación, seleccione **Siguiente.**
5.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente**.

6.  Revise la **página Confirmar la configuración** y, a continuación, seleccione **Siguiente.**

7.  Seleccione **Cerrar**.

### <a name="create-the-computer-name-assignment-package"></a>Crear el paquete de asignación de nombres de equipo

1.  En **srs v2 - Set-SRSComputerName paquete,** cree una nueva aplicación HTML denominada **Set-SRSComputerName.hta** .

2.  Copie el siguiente script en el **archivo Set-SRSComputerName.hta.** Como alternativa, puede descargar el archivo Set-SRSComputerName.hta desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3.  En la consola de Configuration Manager, vaya a **Paquetes** de administración de aplicaciones de biblioteca de software y, a \>  \> continuación, **seleccione Crear paquete.**

4.  Escriba la siguiente información para crear el paquete:

    -   Nombre: **SRS v2 - Set-SRSComputerName paquete**

    -   Fabricante: **Microsoft Corporation**

    -   Versión: **1.0.0**

    -   Active la **casilla Este paquete contiene archivos de origen,** escriba la ruta de acceso a la carpeta **SRS v2 - Set-SRSComputerName Paquete** y, a continuación, seleccione **Siguiente.**

5.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente**.

6.  Revise la **página Confirmar la configuración** y, a continuación, seleccione **Siguiente.**

7.  Seleccione **Cerrar**.

### <a name="create-the-sysprep-package"></a>Crear el paquete Sysprep

1. En la **carpeta SRS v2 : paquete sysprep,** cree un nuevo archivo XML denominado **Unattend.xml** .

2. Copie el texto siguiente en el **Unattend.xml** archivo. Como alternativa, puede descargar el archivo Unattend.xml desde [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
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
3. En la consola de Configuration Manager, vaya a **Paquetes** de administración de aplicaciones de biblioteca de software y, a \>  \> continuación, **seleccione Crear paquete.**

4. Escriba la siguiente información para crear el paquete:
   -   Nombre: **SRS v2 - Paquete Sysprep**
   -   Fabricante: **Microsoft Corporation**
   -   Versión: **1.0.0**
   -   Active la casilla Este paquete contiene archivos **de origen,** escriba la ruta de acceso a la **carpeta PAQUETE SRS v2 – Sysprep y,** a continuación, **seleccione Siguiente.**
5. Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente**.

6. Revise la **página Confirmar la configuración** y, a continuación, seleccione **Siguiente.**

7. Seleccione **Cerrar**.

### <a name="create-the-windows-10-enterprise-package"></a>Crear el Windows 10 Enterprise paquete

1.  Obtenga un Windows 10 Enterprise x64 y copie el **archivo install.wim** en la carpeta **Windows 10 Enterprise \\ sistemas** operativos.

2.  En la consola de Configuration Manager, vaya a Biblioteca de **software** Imágenes del sistema operativo Sistemas operativos y, a continuación, \>  \> seleccione Agregar **imagen de sistema operativo.**

3.  Especifique la ruta de acceso al **archivo install.wim** que acaba de copiar y, a continuación, seleccione **Siguiente**.

4.  Actualice el **campo** Versión para que coincida con el número de compilación de la Windows 10 Enterprise y, después, seleccione **Siguiente.**

5.  Revise la **página Detalles** y, a continuación, **seleccione Siguiente.**

6.  Seleccione **Cerrar**.

Para obtener más información, vea [Administrar imágenes del sistema operativo con Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Crear Surface Pro paquetes de controlador de dispositivo

Salas de Microsoft Teams es compatible tanto con Surface Pro como Surface Pro 4. Debe crear un paquete de controlador para cada Surface Pro modelo que tenga en su entorno.

> [!IMPORTANT]
> Los controladores deben ser compatibles con la Windows 10 Enterprise y la Salas de Microsoft Teams del kit de implementación. Para obtener más información, vea Descargar el firmware y los controladores más recientes para [dispositivos Surface](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) y [Configurar una consola.](console.md)

1.  Descargue los controladores y el firmware más recientes.
    -   Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extraiga el controlador y el firmware descargados. Abra una ventana del símbolo del sistema y, en el símbolo del sistema, escriba uno de los siguientes comandos:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  En la consola de Configuration Manager, vaya **a Controladores** de sistemas operativos de biblioteca de software y, a \>  \> continuación, seleccione **Importar controlador.**

4.  Seleccione Importar todos los controladores en la siguiente ruta de red **(UNC),** seleccione la carpeta de origen (por ejemplo, C: _Sources Controladores Surface Pro) y, a continuación, seleccione \\ \\ \\ **Siguiente**.

5.  En la **página Especificar los detalles** de los controladores importados, seleccione todos los controladores enumerados y, a continuación, seleccione Habilitar estos controladores y permita que los equipos los **instalen.**

6.  Selecciona **Categorías**, crea una nueva categoría que coincida con el modelo de Surface, selecciona **Aceptar** y, a continuación, **selecciona Siguiente.**

7.  Seleccione **Nuevo paquete**.

8.  Especifique el nombre del paquete que coincida con el modelo Surface Pro, escriba una ruta de carpeta en la que almacenar los archivos del paquete del controlador, seleccione Aceptar **y,** a continuación, **seleccione Siguiente**.

9.  En la **página imágenes de** inicio, asegúrese de que no se selecciona ninguna imagen de inicio y, a continuación, seleccione **Siguiente.**

10. Seleccione **Cerrar**.

11. Vaya a **Controladores** de sistemas operativos de biblioteca de software, seleccione Crear carpeta y escriba un nombre de carpeta que coincida con el modelo de Surface Pro para el que acaba de importar \>  \> los controladores. **\>**

12. Mueva todos los controladores importados a la carpeta recién creada para facilitar la navegación y el funcionamiento.

> [!NOTE]
> Repita los mismos pasos para otros Surface Pro modelos que pueda tener. Para obtener más información, vea [Administrar controladores en Configuration Manager.](/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Crear Salas de Microsoft Teams de configuración

1.  En la consola de Configuration Manager, vaya a **Paquetes** de administración de aplicaciones de biblioteca de software y, a \>  \> continuación, **seleccione Crear paquete.**

2.  Escriba la siguiente información para crear el paquete:

    -   Nombre: **SRS v2: Configurar el paquete de configuración srs**

    -   Fabricante: **Microsoft Corporation**

    -   Versión: **1.0.0**

    -   Active la casilla Este paquete contiene archivos **de origen,** escriba la ruta de acceso a la carpeta **SRS v2 - Configurar** configuración SRS y, a continuación, seleccione **Siguiente.**

3.  Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente**.

4.  Revise la **página Confirmar la configuración** y, a continuación, seleccione **Siguiente.**

5.  Seleccione **Cerrar**.



## <a name="distribute-configuration-manager-packages"></a>Distribuir paquetes de Configuration Manager

Todos los paquetes deben distribuirse a los servidores a los que se les ha asignado el rol de punto de distribución en la jerarquía de Configuration Manager. Siga las instrucciones siguientes para iniciar la distribución de paquetes.

1.  Distribuir paquetes de software.

    1.  En la consola de Configuration Manager, vaya **a Paquetes de** administración de aplicaciones de biblioteca \> **de** \> **software.** Seleccione todos los paquetes de software que desea distribuir y, a continuación, **seleccione Distribuir contenido.**

    2.  Revise la lista de paquetes y, a continuación, **seleccione Siguiente.**

    3.  Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, a continuación, **seleccione Siguiente.**

    4.  Seleccione **Siguiente** y, a continuación, **seleccione Cerrar**.

2.  Distribuir paquetes de controladores.

    1.  En la consola de Configuration Manager, vaya **a Paquetes** de controladores de sistemas operativos de biblioteca de \>  \> software. Seleccione todos los paquetes de controlador que desea distribuir y, a continuación, **seleccione Distribuir contenido.**

    2.  Revise la lista de paquetes y, a continuación, **seleccione Siguiente.**

    3.  Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, a continuación, **seleccione Siguiente.**

    4.  Seleccione **Siguiente** y, a continuación, **seleccione Cerrar**.

3.  Distribuir paquetes de sistema operativo.

    1.  En la consola de Configuration Manager, vaya **a Biblioteca de software** Imágenes \> **del** sistema operativo sistemas \> **operativos.** Seleccione todas las imágenes del sistema operativo que desea distribuir y, a continuación, **seleccione Distribuir contenido.**

    2.  Revise la lista de paquetes y, a continuación, **seleccione Siguiente.**

    3.  Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, a continuación, **seleccione Siguiente.**

    4.  Seleccione **Siguiente** y, a continuación, **seleccione Cerrar**.

> [!NOTE]
> La distribución de paquetes puede tardar algún tiempo, según el tamaño del paquete, la jerarquía de Configuration Manager, el número de servidores de puntos de distribución y el ancho de banda disponible en la red.
> 
> Todos los paquetes deben distribuirse antes de empezar a implementar una Salas de Microsoft Teams unidad.
> 
> Para revisar el estado de la distribución de paquetes en la consola de Configuration Manager, vaya **a** Supervisar el estado \> **del contenido de** \> **la distribución.**

## <a name="configuration-manager-task-sequences"></a>Secuencias de tareas de Configuration Manager

Use secuencias de tareas con Configuration Manager para automatizar los pasos para implementar una imagen de sistema operativo en un equipo de destino. Para implementar una unidad Salas de Microsoft Teams de forma automatizada, cree una secuencia de tareas que haga referencia a la imagen de inicio usada para iniciar el equipo Salas de Microsoft Teams de destino, la imagen del sistema operativo Windows 10 Enterprise que desea instalar y cualquier otro contenido adicional, como otras aplicaciones o actualizaciones de software.

### <a name="import-the-sample-task-sequence"></a>Importar la secuencia de tareas de ejemplo

Puede descargar e importar fácilmente una secuencia de tareas de ejemplo y personalizarla para satisfacer sus necesidades.

1.  [**Descargue**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la secuencia de tareas de ejemplo y copie el archivo zip descargado en una ubicación compartida.
2.  En la consola de Configuration Manager, vaya a **Secuencias** de tareas de sistemas operativos de biblioteca de software y, a \>  \> continuación, seleccione **Importar secuencia de tareas.**

3.  Seleccione **Examinar,** vaya a la ubicación de carpeta compartida que usó en el paso 1, seleccione el archivo Salas de Microsoft Teams **Implementación (EN-EE.UU.).zipy, a** continuación, seleccione **Siguiente**.

4.  Establezca **Acción** en **Crear nuevo** y, a continuación, seleccione **Siguiente.**

5.  Confirme la configuración y, a continuación, **seleccione Siguiente.**

6.  Seleccione **Cerrar**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Valide que los paquetes de referencia están correctamente vinculados a cada paso de secuencia de tareas.

1. Seleccione la secuencia de tareas importada y, a continuación, **seleccione Editar**.

    El Editor de secuencias de tareas se abre y muestra cada paso secuencial que necesita para implementar y configurar una unidad Salas de Microsoft Teams tarea.

2. Siga cada paso y complete las actualizaciones recomendadas:

   1. **Reiniciar en Windows PE:** este paso se reinicia y, a continuación, inicia el equipo en Windows PXE. No se necesitan cambios para este paso.

   2. **Disco de partición 0 : UEFI:** este paso elimina la configuración del disco y crea particiones en función de la configuración configurada. Le recomendamos que no realice ningún cambio en este paso.

   3. Establecer el nombre del equipo **SRS:** este paso incluye una aplicación HTML para proporcionar una interfaz de usuario para establecer un nombre de equipo para la unidad Salas de Microsoft Teams durante la implementación.
      -  Este es un paso opcional, pero solo se puede deshabilitar si desea administrar el nombre del equipo a través de un proceso alternativo.
      -  Compruebe que el **paquete SRS v2 - Set-SRSComputerName** está seleccionado. Si no es así, busque el paquete y selecciónelo.

   4. **Aplicar sistema operativo:** en este paso se especifica la imagen del sistema operativo que se va a implementar y el archivo de respuesta desatendida sysprep que se va a usar.
      -  Compruebe que el archivo de imagen Windows 10 Enterprise sistema operativo correcto está seleccionado.
      -  Compruebe que usar un archivo de respuesta desatendida o **Sysprep** para una instalación personalizada está habilitado y el **paquete SRS v2 - Sysprep** está seleccionado. Asegúrese también de que **nombre de** archivo está establecido **enunattend.xml**.

   5. **Aplicar Windows Configuración:** este paso recopila información sobre la Windows instalación.
      -  Proporcione información de licencias y registro, incluida la clave de producto, la contraseña de la cuenta de administrador local y la zona horaria (según sus necesidades).

   6. **Aplicar Configuración** de red: este paso le permite especificar un grupo de trabajo o un nombre de dominio de Active Directory y una unidad organizativa.
      > [!NOTE]
      > Consulte Skype de unirse a un dominio de room system para ver las acciones [recomendadas](domain-joining-considerations.md) que debe realizar en la implementación de Salas de Microsoft Teams unidades como miembros de un dominio de Directorio de Actve.
   7. **Aplicar controladores:** Este paso y sus subescalones se usan para implementar controladores de dispositivo y firmware aplicables en función del Surface Pro modelo que tiene. Actualice cada paso para especificar el paquete de controladores relevante asociado a esta implementación.
      -   Cada paquete de controlador está configurado para aprovechar Windows de instrumentación de administración (WMI) para implementar controladores y firmware relevantes en función de la Surface Pro y el modelo.
      -   Le recomendamos encarecidamente que no altere la configuración de estos controladores, de lo contrario, podría producirse un error en la implementación.

   8. **Configurar Windows y Configuration Manager:** este paso implementa y configura el cliente de Configuration Manager. Actualice este paso para especificar el paquete de cliente integrado de Configuration Manager.

   9. **Instalar certificado raíz:** este paso distribuye el certificado raíz para dispositivos que no están unidos a un dominio y, por lo tanto, es opcional y está deshabilitado de forma predeterminada.
      -   Habilite este paso si necesita implementar un certificado raíz en las Salas de Microsoft Teams unidades.
      -   Si necesita realizar este paso, compruebe que el **SRS v2 :** paquete de certificado raíz y deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionados.

   10. **Instalar y configurar** el agente de supervisión: este paso instala la versión de 64 bits del agente de Microsoft Azure Monitor y configura el agente para conectarse al área de trabajo de Log Analytics.
       -   Este paso está deshabilitado de forma predeterminada. Habilite este paso solo si va a usar el Agente de supervisión para supervisar el estado de sus Salas de Microsoft Teams unidades.
       -   Edite este paso y actualice los parámetros de la línea de comandos para especificar el **id. del** área de trabajo y la clave **del área de trabajo.**
       -   Consulte [Configurar dispositivos de prueba para Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obtener más información sobre cómo obtener el id. del área de trabajo del conjunto de tareas de administración de operaciones y la clave principal.
       -   Compruebe que el redireccionamiento del sistema de archivos **SRS v2 Microsoft Monitoring Agent y** Deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionados.
       -   Para obtener más información sobre cómo supervisar el estado de la implementación de Salas de Microsoft Teams, vea Planear la administración Salas de Microsoft Teams con [Azure Monitor,](azure-monitor-plan.md)Implementar una administración Salas de Microsoft Teams con [Azure Monitor](azure-monitor-deploy.md) y Administrar dispositivos Salas de Microsoft Teams con [Azure Monitor.](azure-monitor-manage.md)

   11. **Copiar archivos de configuración srs v2:** este paso copia los archivos de configuración y configuración necesarios del kit de implementación de Salas de Microsoft Teams en la unidad de disco duro local. No se requiere personalización para este paso.
       -   Compruebe que el redireccionamiento del sistema de archivos **SRS v2: PAQUETE DE APLICACIONES SRS** y Deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionados.

   12. **Install-SRSv2-OS-Updates:** este paso implementa las actualizaciones obligatorias del sistema operativo necesarias con la Salas de Microsoft Teams implementación. Haga lo siguiente:
       -   Active [Configurar una Salas de Microsoft Teams para](console.md) ver qué actualizaciones son necesarias.
       -   Compruebe que el paquete de actualizaciones del sistema operativo **SRS v2** incluye todas las actualizaciones necesarias.
       -   Compruebe que el **paquete SRS v2 – Actualizaciones del sistema operativo** está seleccionado.
       -   Compruebe que la directiva de ejecución de PowerShell está establecida en **Omitir**.

   13. **Reiniciar equipo:** este paso reinicia el equipo después de instalar las actualizaciones obligatorias del sistema operativo. No se requiere personalización para este paso.

   14. **Configurar Windows componentes:** este paso configura las características Windows necesarias. No se requiere personalización para este paso.

   15. **Reiniciar equipo:** este paso reinicia el equipo después de Windows se configuran las características. No se requiere personalización para este paso.

   16. **Agregar usuario Skype** local: este paso crea la cuenta de Skype local que se usa para iniciar sesión automáticamente en Windows e iniciar la Salas de Microsoft Teams aplicación. Este paso no tiene ningún paquete de software asociado y no se requiere personalización para él.

   17. **Configurar y configurar la aplicación SRS:** este paso configura la Salas de Microsoft Teams de la aplicación para el siguiente inicio del sistema operativo.
       -   Compruebe que el **SRS v2: configurar** el paquete de configuración SRS y deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionados.

> [!IMPORTANT]
> Es muy importante que los pasos de la secuencia de tareas deben estar en el orden proporcionado. Modificar el orden de los pasos o configurar pasos adicionales puede interrumpir la implementación.
>
> **Configurar y configurar el paso de la** aplicación SRS debe ser el último paso de la secuencia de tareas, de lo contrario, podría producirse un error en la implementación.

### <a name="create-deployment-for-the-task-sequence"></a>Crear implementación para la secuencia de tareas

1. Seleccione la secuencia de tareas y, a continuación, **seleccione Implementar**.

2. Seleccione **Examinar para** seleccionar la colección de destino para la implementación.

3. Seleccione **Todos los equipos desconocidos** y, a continuación, haga clic en **Aceptar.**

4. Seleccione **Siguiente**.

5. Seleccione **Disponible** en la **lista** desplegable Propósito.

6. Seleccione **Solo multimedia y PXE** en la lista Hacer disponible para **la** siguiente lista y, a continuación, **seleccione Siguiente**.
   > [!WARNING]
   > Es muy importante que **Purpose** se establezca en **Disponible.** Asegúrese de que **El propósito** **no está** establecido en **Obligatorio.** Asegúrese también de seleccionar Solo multimedia **y PXE** en **el cuadro Hacer disponible para los siguientes**.
   >
   > Establecer estos valores en otra cosa puede hacer que todos los equipos obtengan la Salas de Microsoft Teams de implementación al iniciar.
7. No especifique ninguna programación y seleccione **Siguiente**.

8. No cambie nada en la sección **Experiencia de usuario** y seleccione **Siguiente.**

9. No cambie nada en la sección **Alertas** y seleccione **Siguiente.**

10. No cambie nada en la sección **Puntos de distribución** y seleccione **Siguiente.**

11. Confirme la configuración y, a continuación, **seleccione Siguiente**.

12. Seleccione **Cerrar**.

**Validar y solucionar problemas de la solución**

Después de completar las Microsoft Endpoint Configuration Manager de tareas, deberá realizar una ejecución de prueba para validar que la secuencia de tareas puede implementar y configurar Salas de Microsoft Teams unidades.

1.  Conectar el dispositivo de prueba a la red cableada con uno de los adaptadores Ethernet compatibles o con surface dock. Si la funcionalidad de inicio PXE no se ha configurado para su [](/configmgr/osd/deploy-use/create-bootable-media) entorno, puede usar la imagen de inicio en la unidad flash USB que creó anteriormente para iniciar desde USB y conectarse a Configuration Manager.

2.  Acceda al firmware e inicie el arranque PXE:

    1.  Asegúrate de que el dispositivo Surface esté apagado.

    2.  Mantenga presionado el botón **Subir** volumen.

    3.  Presione y suelte el **botón De** encendido.

    4.  Cuando el dispositivo empiece a iniciarse, suelte el **botón Subir** volumen.

    5.  Seleccione **Configuración de inicio**.

    6.  Realice una de las siguientes acciones:

        -   Seleccione **Inicio PXE** y arrástrelo a la parte superior de la lista. Como alternativa, puede deslizar el dedo hacia la izquierda en el adaptador de red para iniciar el dispositivo inmediatamente. Esto no afectará al orden de inicio.
        -   Seleccione la unidad flash USB que contiene el medio de inicio.

3.  Seleccione **Salir** y, a continuación, **seleccione Reiniciar ahora**.

4.  Cuando se le solicite, seleccione **Entrar para el** servicio de inicio de red.

5.  Windows PE se cargará en la memoria y se iniciará el Asistente para secuencia de tareas. Seleccione **Siguiente** para continuar.

6.  Seleccione la secuencia de tareas que importó anteriormente y, a continuación, seleccione **Siguiente.**

7.  Después de aplicar la configuración del disco, se le pedirá que especifique un nombre de equipo para el dispositivo. La interfaz de usuario mostrará un nombre de equipo recomendado en función del número de serie del Surface Pro dispositivo. Puede aceptar el nombre propuesto o especificar uno nuevo. Siga las instrucciones en la pantalla de asignación de nombres de equipo. Al seleccionar **Aceptar,** comienza la implementación.

8.  El resto del proceso de implementación es automático y no pide más entradas de usuario.

9.  Cuando la secuencia de tareas de implementación termine de configurar el dispositivo, verá la siguiente pantalla de configuración en la que se le pedirá que configure la configuración Salas de Microsoft Teams aplicación.

    ![Pantalla de configuración inicial para Salas de Microsoft Teams aplicación](../media/room-systems-scale-image2.png)

10.  Conecta el Surface Pro a la Salas de Microsoft Teams y configura la configuración de la aplicación.

11.  Valide que las funcionalidades [enumeradas Salas de Microsoft Teams ayuda](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estén trabajando en el dispositivo implementado.


Para solucionar un error de instalación, compruebe el archivo **SMSTS.log,** que registra todos los pasos ejecutados en una secuencia de tareas de Configuration Manager.

El archivo SMSTS.log se almacena en una de varias rutas de acceso, dependiendo de la fase del proceso de compilación. Compruebe la tabla siguiente para identificar la ruta de acceso al archivo SMSTS.log.


| **Fase de implementación**                                                            | **Ruta de registro de secuencia de tareas**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, antes del formato DISCO DURO                                                        | X: \\ Windows \\ \\ smstslog \\ smsts.log temp             |
| WinPE, después del formato DISCO DURO                                                         | C: \\ _SMSTaskSequence \\ registros \\ smstslog \\ smsts.log    |
| Sistema operativo implementado antes de instalar el agente de Configuration Manager | c: \\ _SMSTaskSequence \\ registros \\ Smstslog \\ smsts.log    |
| Sistema operativo y el agente de Configuration Manager implementado                   | %windir% \\ System32 \\ ccm registra \\ \\ Smstslog \\ smsts.log |
| Ejecución de secuencia de tareas completada                                                | %windir% \\ System32 \\ ccm registra \\ \\ smsts.log           |

> [!TIP]
> Puede seleccionar **F8** en cualquier momento durante la secuencia de tareas para abrir una consola de comandos y, a continuación, obtener acceso al archivo SMSTS.log.

Para solucionar problemas de inicio pxe, compruebe los dos archivos de registro en el servidor de Configuration Manager que son específicos de las acciones pxe:

-   **Pxecontrol.log**, ubicado en el directorio de registros de instalación de Configuration Manager

-   **Smspxe.log**, ubicado en el directorio de registros de Puntos de administración (MP) de Configuration Manager

Para obtener una lista completa de los archivos de registro que puede usar para solucionar más problemas con la instalación de Configuration Manager, vea la referencia Microsoft Endpoint Configuration Manager [archivo de registro.](/configmgr/core/plan-design/hierarchy/log-files)
