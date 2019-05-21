---
title: Implementar salas de Microsoft Teams con System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Lea este tema para obtener información sobre la implementación de salas de Microsoft Teams en implementaciones de gran escala.
ms.openlocfilehash: 34bd984d16da4eeb1934c7fda7bbadb0837240be
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305446"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a>Implementar salas de Microsoft Teams con System Center Configuration Manager

Este artículo le proporciona toda la información necesaria para crear implementaciones de salas de Microsoft Teams mediante System Center Configuration Manager.

Con los métodos fáciles de usar proporciona System Center Configuration Manager, puede implementar el sistema operativo y otras aplicaciones en varios dispositivos de destino.

Use el método que se muestra a continuación para guiarse a través de la configuración de Configuration Manager y personalizar los paquetes de ejemplo y los scripts proporcionados en esta guía según sea necesario para su organización.

![Proceso de implementación de salas de Microsoft Teams con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Esta solución solo ha sido probada con implementaciones basadas en Surface Pro. Siga las instrucciones del fabricante para configuraciones que no se basan en Surface Pro.

## <a name="validate-prerequisites"></a>Validar los requisitos previos

Para implementar salas de Microsoft Teams con Configuration Manager, asegúrese de cumplir los siguientes requisitos y requisitos.

### <a name="system-center-configuration-manager-requirements"></a>Requisitos de System Center Configuration Manager

-   La versión de System Center Configuration Manager debe tener al menos 1706 o superior. Le recomendamos que use 1710 o una versión posterior. Consulte [soporte técnico para Windows 10 en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para obtener información sobre las versiones de Windows 10 compatibles con Configuration Manager.

-   Debe instalarse una versión compatible de Windows Assessment and Deployment Kit (ADK) para Windows 10. Vea las versiones de [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que puede usar con diferentes versiones de Configuration Manager y asegúrese de que su implementación incluya la versión correcta.

-   Los servidores del sistema de sitio deben tener asignado el rol de punto de distribución y las imágenes de arranque deben estar habilitadas para [admitir el entorno de ejecución de inicio previo (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar implementaciones iniciadas por la red. Si la compatibilidad con PXE no está habilitada, puede usar [medios de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones.

-   Una cuenta de acceso a la red debe estar configurada para admitir nuevos escenarios de implementación de equipos. Para obtener más información sobre la configuración de una cuenta de acceso a la red, consulte [administrar cuentas para obtener acceso al contenido en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Le recomendamos que habilite la [compatibilidad con multidifusión](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si es probable que implemente la misma imagen de salas de Microsoft Teams en varias unidades al mismo tiempo.

### <a name="networking-requirements"></a>Requisitos de red

-   Su red debe tener un servidor de protocolo de configuración dinámica de host (DHCP), configurado para la distribución automática de direcciones IP a las subredes donde se implementarán las unidades de salas de Microsoft Teams.

    > [!NOTE]
    > La duración de la concesión DHCP debe establecerse en un valor superior a la duración de la implementación de la imagen. De lo contrario, la implementación podría fallar.

-   Su red, incluidos los conmutadores y las LANs virtuales (VLAN), debe estar configurada para admitir PXE. Para obtener más información sobre la ayuda de IP y la configuración de PXE, consulte su proveedor de red. Como alternativa, puede usar [medios de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones, si la compatibilidad con PXE no está habilitada.

    > [!NOTE]
    > Para los dispositivos Surface Pro, el arranque desde la red (arranque PXE) solo se admite al usar un adaptador Ethernet o una estación de acoplamiento de Microsoft. Los adaptadores Ethernet de terceros no admiten el arranque PXE con Surface Pro. Para obtener más información [, consulte adaptadores de Ethernet e implementación de superficies](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>Configurar System Center Configuration Manager para la implementación de sistemas operativos

En este artículo se supone que ya tiene una implementación correcta de System Center Configuration Manager y no se detallan todos los pasos necesarios para implementar y configurar Configuration Manager desde cero. La [documentación y la guía de configuración](https://docs.microsoft.com/sccm/) de System Center Configuration Manager es un excelente recurso; le recomendamos que comience con estos recursos si todavía no ha implementado Configuration Manager.

Use las siguientes instrucciones para comprobar que las características de la implementación del sistema operativo (OSD) están configuradas correctamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Validar y actualizar Configuration Manager

1.  En la consola del administrador de configuración, vaya a **actualizaciones y mantenimiento**de la **Administración** \> .

2.  Compruebe la compilación instalada y las actualizaciones aplicables que aún no se han instalado.

3.  Revise el [soporte técnico para Windows 10 en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). Si necesita actualizar su implementación, seleccione la actualización que quiera instalar y, después, haga clic en **Descargar**.

4.  Una vez completada la descarga, seleccione la actualización y, a continuación, seleccione **instalar paquete de actualización**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurar puntos de distribución para admitir PXE y multicast

1.  En la consola del administrador de configuración, vaya a **puntos de distribución**de **Administración** \> .

2.  Seleccione el servidor del punto de distribución que servirá a la implementación de salas de Microsoft Teams y, a continuación, seleccione **propiedades**.

3.  Seleccione la pestaña **PXE** y asegúrese de que estén habilitadas las siguientes opciones:
    -   Habilitar la compatibilidad con PXE para clientes
    -   Permitir que este punto de distribución responda a solicitudes PXE entrantes
    -   Habilitar compatibilidad con equipos desconocidos

4.  *Opcional:* Para habilitar la compatibilidad con multidifusión **** , seleccione la pestaña multidifusión y asegúrese de que estén habilitadas las siguientes opciones:
    -   Habilitar la multidifusión para enviar datos simultáneamente a varios clientes
    -   Configurar el intervalo de puertos UDP según la recomendación del equipo de red

### <a name="configure-the-network-access-account"></a>Configurar la cuenta de acceso a la red

1.  En la consola del administrador de configuración, vaya a **sitios**de **configuración** \> del sitio de **Administración** \> y, después, seleccione el sitio.

2.  En el grupo **configuración** , seleccione **Configurar componentes** \> de sitio de **distribución de software**.

3.  Seleccione la pestaña **cuenta de acceso a la red** . configure una o más cuentas y, a continuación, seleccione **Aceptar**.

> [!NOTE]
> Las cuentas no necesitan derechos especiales, excepto **tener acceso a este equipo desde la red** en el servidor del punto de distribución. Una cuenta de usuario de dominio genérico será adecuada. Para obtener más información, vea [administrar cuentas para obtener acceso al contenido de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Configurar una imagen de arranque

1.  En la consola del administrador de configuración, vaya a **imágenes de inicio** **del sistema** \> operativo de la **biblioteca** \> de software.

2.  Seleccione **imagen de arranque (x64)** y, a continuación, haga clic en **propiedades**.

3.  Seleccione la pestaña **origen de datos** y habilite **implementar esta imagen de inicio desde el punto de distribución habilitado para PXE**.

4.  Seleccione la pestaña **componentes opcionales** para instalar los componentes necesarios:

    1.  Seleccione el icono de estrella y busque **HTML (WinPE-HTA)** .

    2.  Seleccione **Aceptar** para agregar compatibilidad de aplicaciones HTML en la imagen de inicio.

5.  *Opcional:* Para personalizar la experiencia de implementación, seleccione **** la pestaña personalización.
    -   Habilite la **compatibilidad con comandos (solo pruebas)** si desea tener acceso a un símbolo del sistema durante la implementación. Cuando esta opción está habilitada, puede iniciar un símbolo del sistema seleccionando **F8** en cualquier momento de la implementación.
    -   También puede especificar una imagen de fondo personalizada para que se muestre durante la implementación. Para establecer una imagen, habilite **especificar el archivo de imagen de fondo personalizado (ruta de acceso UNC** y seleccione el fondo.

6.  Cuando se le pida, seleccione **sí** y distribuir la imagen de arranque actualizada a los puntos de distribución.

Para obtener más información, consulte [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).

> [!NOTE]
> Puede crear un medio USB de arranque para iniciar implementaciones basadas en secuencias de tareas de Configuration Manager para entornos que no tienen compatibilidad con PXE. El medio de arranque contiene solo la imagen de arranque, los comandos de preinicio opcionales y los archivos necesarios, y los binarios de Configuration Manager para admitir el inicio en Windows PE y la conexión con Configuration Manager durante el resto del proceso de implementación. Para obtener más información, consulte [Cómo crear medios de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Crear paquetes de Configuration Manager

Configuration Manager requiere varios paquetes para implementar y configurar las unidades de salas de Microsoft Teams.

Debe crear y configurar los siguientes paquetes y, a continuación, distribuirlos a los sistemas de sitio de Configuration Manager a los que se les haya asignado el rol de servidor del punto de distribución.

| **Nombre del paquete**                     | **Tipo**               | **Descripción**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS V2: paquete de aplicaciones para SRS     | Paquete de software       | Paquete para el kit de implementación de Microsoft Teams Rooms                                      |
| SRS V2: paquete de Sysprep             | Paquete de software       | Paquete para el. XML personalizado desatendido para configurar las unidades de salas de Microsoft Teams            |
| SRS V2-Set-SRSComputerName | Paquete de software       | Paquete para la aplicación HTML (HTA) para asignar un nombre de equipo durante la implementación    |
| SRS V2: configurar la configuración de SRS         | Paquete de software       | Paquete para configurar la implementación de la aplicación salas de Microsoft Teams                          |
| Paquete de actualizaciones para SRS V2-OS          | Paquete de software       | Paquete para implementar actualizaciones obligatorias del sistema operativo                                      |
| SRS V2: paquete de certificados raíz    | Paquete de software       | Paquete opcional para implementar el certificado raíz (no es necesario para las unidades Unidas al dominio)  |
| SRS V2-paquete de Microsoft Monitoring Agent | Paquete de software       | Opcional: paquete para implementar y configurar el agente de Microsoft Operations Management Suite|
| SRS V2: paquete de fondo WinPE    | Paquete de software       | Paquete para la imagen de fondo personalizada que se usa con imágenes de arranque                           |
| Windows 10 Enterprise                | Imagen de sistema operativo | Paquete para el archivo de instalación del sistema operativo (install. wim)                          |
| Surface Pro                          | Paquete de controladores         | Paquete para los drivers de dispositivo y firmware para Microsoft Surface Pro                     |
| Surface Pro 4                        | Paquete de controladores         | Paquete para los drivers de dispositivo y firmware para Microsoft Surface Pro 4                   |

Para obtener más información, consulte [paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Crear carpetas para los archivos de origen del paquete

El administrador de configuración requiere que los archivos de origen del paquete se organicen en una estructura de carpetas específica cuando se crean por primera vez y cuando se actualizan.

Cree la siguiente estructura de carpetas en el sitio de administración central de System Center Configuration Manager o en el sitio primario, o en un recurso compartido de servidor que esté usando para hospedar los archivos de origen del paquete:

-   SRS V2-paquete de Microsoft Monitoring Agent
-   Paquete de actualizaciones para SRS V2-OS
-   SRS V2: paquete de certificados raíz
-   SRS V2-Set-SRSComputerName
-   SRS V2: paquete de aplicaciones para SRS
-   SRS V2: configurar la configuración de SRS
-   SRS V2: paquete de Sysprep
-   Conductores
    -   Surface Pro
    -   Surface Pro 4
-   Sistemas operativos
    -   Windows 10 Enterprise

> [!TIP]
> También puede [Descargar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) y usar el archivo zip que incluye la estructura de carpetas de los paquetes, los scripts que necesita usar y la plantilla de secuencia de tareas que necesita importar.

### <a name="create-the-monitoring-agent-package"></a>Crear el paquete del agente de supervisión

1. Descarga el agente de supervisión <https://go.microsoft.com/fwlink/?LinkId=828603>de.

2. Extraiga el paquete a la carpeta del **paquete SRS V2-Microsoft Monitoring Agent** abriendo una ventana del símbolo del sistema y escribiendo **MMASetup-AMD64. exe/c:** en el símbolo del sistema.

3. En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.

4. Escriba la siguiente información para crear el paquete:

   - Nombre<strong>: SRS V2: paquete del agente de supervisión de Microsoft</strong>

   - Fabricante<strong>: Microsoft Corporation</strong>

   - Versión<strong>: 8.1.11081.0</strong> (escriba la versión del archivo de instalación descargado)

   - Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete SRS V2-Microsoft Monitoring Agent** y, a continuación, seleccione **siguiente**.

5. Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.

6. Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.

7. Seleccione **cerrar**.

### <a name="create-the-operating-system-updates-package"></a>Crear el paquete de actualizaciones del sistema operativo

1. En la carpeta del **paquete de actualizaciones de SRS V2-os** , cree un nuevo script de PowerShell denominado **install-SRSv2-os-updates. PS1**.

2. Copie el script siguiente en el script **install-SRSv2-os-updates. PS1** . Como alternativa, puedes descargar el script Install-SRSv2-OS-Updates. PS1 desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Descargue los paquetes de Windows Update obligatorios en la misma carpeta.
   > [!NOTE]
   > En el momento en que se publicó este artículo, solo se necesitaba [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) . Marque [configurar una consola de salas de Microsoft Teams](console.md)para ver si se necesitan otras actualizaciones.

4. En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.

5. Escriba la siguiente información para crear el paquete:
   -   Nombre: **SRS V2: paquete de actualizaciones del sistema operativo**
   -   Fabricante: **Microsoft Corporation**
   -   Versión: **1.0.0**
   -   Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete de actualizaciones de SRS V2-os** y, a continuación, seleccione **siguiente**.

6. Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.

7. Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.

8. Seleccione **cerrar**.

### <a name="create-the-root-certificate-package-optional"></a>Crear el paquete de certificados raíz (opcional)

Cree este paquete para distribuir el certificado raíz de los dispositivos que no se unirán a un dominio de Active Directory. Cree este paquete solo si se aplican las dos condiciones siguientes:
-   Su implementación incluye Lync local o Skype empresarial Server.
-   Las unidades de salas de Microsoft Teams están configuradas para trabajar en un grupo de trabajo en lugar de un miembro del dominio.

1.  Copie el certificado raíz en la carpeta del **paquete de certificados raíz de SRS V2** .

2.  En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.

3.  Escriba la siguiente información para crear el paquete:
    -   Nombre: **SRS V2: paquete de certificados raíz**
    -   Fabricante: *nombre de la organización*
    -   Versión: **1.0.0**
    -   Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete de certificados raíz** y, a continuación, seleccione **siguiente**.

4.  Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.

5.  Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.

6.  Seleccione **cerrar**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Crear el paquete del kit de implementación de Microsoft Teams Rooms

1.  Descargue la versión más reciente del **Kit de implementación de Microsoft Teams Rooms** desde e instálela en una estación de <https://go.microsoft.com/fwlink/?linkid=851168>trabajo.

2.  Copie el contenido de **C:\\archivos de programa (x86\\) kit de implementación de sistemas de salas de Skype** en la carpeta del **paquete de la aplicación SRS V2** .

3.  En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.

4.  Escriba la siguiente información para crear el paquete:
    -   Nombre: **SRS V2: paquete de aplicación para SRS**
    -   Fabricante: **Microsoft Corporation**
    -   Versión: **3.1.104.0** (escriba la versión del archivo de instalación descargado)
    -   Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS V2 – paquete de la aplicación SRS** y, a continuación, seleccione **siguiente**.
5.  Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.

6.  Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.

7.  Seleccione **cerrar**.

### <a name="create-the-computer-name-assignment-package"></a>Crear el paquete de asignación de nombre de equipo

1.  En la carpeta del **paquete SRS V2-Set-SRSComputerName** , cree una nueva aplicación HTML denominada **set-SRSComputerName. HTA** .

2.  Copie el script siguiente en el archivo **set-SRSComputerName. HTA** . También puedes descargar el archivo Set-SRSComputerName. HTA desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
    ```
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
3.  En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.

4.  Escriba la siguiente información para crear el paquete:

    -   Nombre: **SRS V2-Set-SRSComputerName paquete**

    -   Fabricante: **Microsoft Corporation**

    -   Versión: **1.0.0**

    -   Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta de **paquete SRSComputerName SRS V2** y, a continuación, seleccione **siguiente**.

5.  Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.

6.  Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.

7.  Seleccione **cerrar**.

### <a name="create-the-sysprep-package"></a>Crear el paquete de Sysprep

1. En la carpeta del **paquete SRS V2-Sysprep** , cree un nuevo archivo XML denominado Unattend **. XML** .

2. Copie el texto siguiente en el archivo Unattend **. XML** . También puede descargar el archivo Unattend. XML desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```
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
3. En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.

4. Escriba la siguiente información para crear el paquete:
   -   Nombre: **SRS V2-paquete de Sysprep**
   -   Fabricante: **Microsoft Corporation**
   -   Versión: **1.0.0**
   -   Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete SRS V2-Sysprep** y, a continuación, seleccione **siguiente**.
5. Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.

6. Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.

7. Seleccione **cerrar**.

### <a name="create-the-windows-10-enterprise-package"></a>Crear el paquete de Windows 10 Enterprise

1.  Obtenga un medio de Windows 10 Enterprise x64 y copie el archivo **install. Wim** en la carpeta **sistemas\\operativos de Windows 10 Enterprise** .

2.  En la consola del administrador de configuración, vaya a **imágenes del sistema**operativo de **sistemas** \> operativos de la **biblioteca** \> de software y, a continuación, seleccione **Agregar imagen de sistema operativo**.

3.  Especifique la ruta de acceso al archivo **install. Wim** que acaba de copiar y, a continuación, seleccione **siguiente**.

4.  Actualice el campo de **versión** para que coincida con el número de compilación de la imagen de Windows 10 Enterprise y, a continuación, seleccione **siguiente**.

5.  Revise la página **detalles** y, a continuación, seleccione **siguiente**.

6.  Seleccione **cerrar**.

Para obtener más información, vea [administrar imágenes del sistema operativo con System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Crear paquetes de controladores de dispositivo Surface Pro

Las salas de Microsoft Teams son compatibles con Surface Pro y Surface Pro 4. Necesita crear un paquete de controladores para cada modelo de Surface Pro que tenga en su entorno.

> [!IMPORTANT]
> Los drivers deben ser compatibles con la compilación de Windows 10 Enterprise y la versión del kit de implementación de Microsoft Teams Rooms. Para obtener más información, vea [descargar el firmware y los drivers más recientes para dispositivos de Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) y [configurar una consola](console.md).

1.  Descargar los últimos drivers y firmware.
    -   Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extraiga el controlador y el firmware descargados. Abra una ventana del símbolo del sistema y, en el símbolo del sistema, escriba uno de los siguientes comandos:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  En la consola del administrador de configuración, vaya a \> **drivers**de **sistemas operativos** de la **biblioteca** \> de software y, después, seleccione **importar controlador**.

4.  Seleccione **importar todos los drivers en la siguiente ruta de acceso de red (UNC)**, seleccione la carpeta de origen (\\por\\ejemplo\\, C: _Sources drivers Surface Pro) y, a continuación, seleccione **siguiente**.

5.  En la página **especifique los detalles de los drivers importados** , seleccione todos los drivers que aparecen en la lista y, a continuación, seleccione **Habilitar estos drivers y permitir que los equipos los instalen**.

6.  Seleccione **categorías**, cree una nueva categoría que coincida con el modelo de superficie, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.

7.  Seleccione **nuevo paquete**.

8.  Especifique el nombre del paquete que coincida con el modelo de Surface Pro, escriba una ruta de carpeta para almacenar los archivos de paquete de controladores en, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.

9.  En la página **imágenes de arranque** , asegúrese de que no hay ninguna imagen de inicio seleccionada y, a continuación, seleccione **siguiente**.

10. Seleccione **cerrar**.

11. Vaya a los **drivers**de **los sistemas** \> operativos de la **biblioteca** \> de software, seleccione ** \> crear carpeta**y escriba un nombre de carpeta que coincida con el modelo de Surface Pro para el que ha importado los drivers.

12. Mueva todos los drivers importados a la carpeta recién creada para facilitar la navegación y la operación.

> [!NOTE]
> Repita los mismos pasos para otros modelos de Surface Pro que pueda tener. Para obtener más información, vea [administrar drivers en System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Crear un paquete de configuración de Microsoft Teams Rooms

1.  En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.

2.  Escriba la siguiente información para crear el paquete:

    -   Nombre: **SRS V2-configurar el paquete de instalación de SRS**

    -   Fabricante: **Microsoft Corporation**

    -   Versión: **1.0.0**

    -   Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS V2-configure SRS Setup** y, a continuación, seleccione **Next**.

3.  Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.

4.  Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.

5.  Seleccione **cerrar**.



## <a name="distribute-configuration-manager-packages"></a>Distribuir paquetes de Configuration Manager

Todos los paquetes deben distribuirse a los servidores a los que se les ha asignado el rol de punto de distribución en la jerarquía de Configuration Manager. Siga las instrucciones a continuación para iniciar la distribución del paquete.

1.  Distribuir paquetes de software.

    1.  En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software. Seleccione todos los paquetes de software que desea distribuir y, a continuación, seleccione **distribuir contenido**.

    2.  Revise la lista de paquetes y, a continuación, seleccione **siguiente**.

    3.  Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.

    4.  Seleccione **siguiente**y, después, haga clic en **cerrar**.

2.  Distribuir paquetes de controladores.

    1.  En la consola del administrador de configuración, vaya a **paquetes de controladores**de **sistemas** \> operativos de la **biblioteca** \> de software. Seleccione todos los paquetes de controladores que desea distribuir y, a continuación, seleccione **distribuir contenido**.

    2.  Revise la lista de paquetes y, a continuación, seleccione **siguiente**.

    3.  Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.

    4.  Seleccione **siguiente**y, después, haga clic en **cerrar**.

3.  Distribuir paquetes del sistema operativo.

    1.  En la consola del administrador de configuración, vaya a **imágenes del sistema**operativo de **los sistemas** \> operativos de la **biblioteca** \> de software. Seleccione todas las imágenes del sistema operativo que desea distribuir y, a continuación, seleccione **distribuir contenido**.

    2.  Revise la lista de paquetes y, a continuación, seleccione **siguiente**.

    3.  Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.

    4.  Seleccione **siguiente**y, después, haga clic en **cerrar**.

> [!NOTE]
> La distribución de paquetes puede llevar algún tiempo, según el tamaño del paquete, la jerarquía del administrador de configuración, el número de servidores de punto de distribución y el ancho de banda disponible en la red.
> 
> Todos los paquetes deben distribuirse antes de que pueda empezar a implementar una unidad de salas de Microsoft Teams.
> 
> Puede revisar el estado de la distribución de paquetes en la consola de Configuration Manager si va a **supervisar** \> el **Estado de contenido**de estado \> de **distribución** .

## <a name="configuration-manager-task-sequences"></a>Secuencias de tareas de Configuration Manager

Use las secuencias de tareas con System Center Configuration Manager para automatizar los pasos para implementar una imagen de sistema operativo en un equipo de destino. Para implementar una unidad de salas de Microsoft Teams en un modo automatizado, cree una secuencia de tareas que haga referencia a la imagen de arranque utilizada para iniciar el equipo de destino Microsoft Team salas, la imagen del sistema operativo Windows 10 Enterprise que desea instalar y cualquier otro contenido adicional, como otras aplicaciones o actualizaciones de software.

### <a name="import-the-sample-task-sequence"></a>Importar la secuencia de tareas de ejemplo

Puede descargar y importar fácilmente una secuencia de tareas de muestra y personalizarla para satisfacer sus necesidades.

1.  [**Descargue**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la secuencia de tareas de ejemplo y copie el archivo zip descargado en una ubicación compartida.
2.  En la consola del administrador de configuración, vaya a **secuencias de tareas**de **sistemas** \> operativos de **bibliotecas** \> de software y, a continuación, seleccione **importar secuencia de tareas**.

3.  Seleccione **examinar**, vaya a la ubicación de la carpeta compartida que usó en el paso 1, seleccione el archivo **. zip Microsoft Team Rooms Deployment (en-EE.UU.)** y, a continuación, seleccione **siguiente**.

4.  Establezca **acción** como **crear nueva**y, a continuación, seleccione **siguiente**.

5.  Confirme la configuración y, a continuación, seleccione **siguiente**.

6.  Seleccione **cerrar**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Valide que los paquetes de referencia estén vinculados correctamente a cada paso de secuencia de tareas.

1. Seleccione la secuencia de tareas importada y, después, haga clic en **Editar**.

    El editor de secuencias de tareas se abrirá y mostrará cada paso secuencial que necesita implementar y configurar una unidad de salas de Microsoft Teams.

2. Recorra cada paso y complete las actualizaciones recomendadas:

   1. **Reiniciar en Windows PE**: este paso se reiniciará y arrancará el equipo en Windows PXE. No es necesario realizar cambios en este paso.

   2. **Partición disco 0: UEFI**: este paso borra la configuración del disco y crea particiones basadas en la configuración configurada. Le recomendamos que no realice ningún cambio en este paso.

   3. **Establecer el nombre del equipo SRS**: este paso incluye una aplicación HTML para proporcionar una interfaz de usuario para establecer un nombre de equipo para la unidad de salas de Microsoft Teams durante la implementación.
      -  Este paso es opcional, pero solo se puede deshabilitar si desea administrar el nombre del equipo mediante un proceso alternativo.
      -  Compruebe que está seleccionado el paquete de **SRS V2-Set-SRSComputerName** . Si no lo está, vaya al paquete y selecciónelo.

   4. **Aplicar sistema operativo**: este paso especifica la imagen del sistema operativo que se va a implementar y el archivo de respuesta de Sysprep desatendida que se va a usar.
      -  Compruebe que esté seleccionada la imagen correcta del sistema operativo Windows 10 Enterprise.
      -  Compruebe que está habilitado el **uso de un archivo de respuesta Sysprep o desatendida para una instalación personalizada** y que el **paquete SRS V2-Sysprep** está seleccionado. Asegúrese también de que **nombre de archivo** está establecido en Unattend **. XML**.

   5. **Aplicar configuración de Windows**: este paso recopila información sobre la instalación de Windows.
      -  Proporcione la información de licencias y registro, incluida la clave de producto, la contraseña de la cuenta de administrador local y la zona horaria (según sus necesidades).

   6. **Aplicar configuración de red**: este paso le permite especificar un grupo de trabajo o un nombre de dominio de Active Directory y una unidad organizativa.
      > [!NOTE]
      > Consulta el [dominio del sistema de la sala de Skype consideraciones](domain-joining-considerations.md) para la Unión de las acciones recomendadas que necesita tomar en la implementación de las unidades de salas de Microsoft Teams como miembros de un dominio de directorio de actve.
   7. **Aplicar drivers:** Este paso y sus subpasos se usan para implementar el firmware y los drivers de dispositivos aplicables según el modelo Surface Pro que tenga. Actualice cada paso para especificar el paquete de controladores correspondiente asociado a esta implementación.
      -   Cada paquete de controladores está configurado para aprovechar los filtros de instrumental de administración de Windows (WMI) para implementar drivers y firmware relevantes en función de la marca y el modelo de Surface Pro.
      -   Le recomendamos encarecidamente que no modifique la configuración de estos drivers; de lo contrario, la implementación podría fallar.

   8. **Configurar Windows y el administrador de configuración**: este paso implementa y configura el cliente de Configuration Manager. Actualice este paso para especificar el paquete de cliente de Configuration Manager integrado.

   9. **Instalar certificado raíz**: este paso distribuye el certificado raíz para los dispositivos que no están Unidos a un dominio y, por lo tanto, es opcional y está deshabilitado de forma predeterminada.
      -   Habilite este paso si necesita implementar un certificado raíz en las unidades de salas de Microsoft Teams.
      -   Si necesita realizar este paso, compruebe que esté seleccionada la redirección del sistema de archivos del servicio **raíz SRS V2** y deshabilite el redireccionamiento **del sistema de archivos de 64 bits** .

   10. **Instalar y configurar el agente de supervisión**: este paso instala la versión de 64 bits del agente de Microsoft Azure monitor y configura el agente para que se conecte al área de trabajo del análisis de registros.
       -   Este paso está deshabilitado de forma predeterminada. Habilite este paso solo si va a usar el agente de supervisión para supervisar el estado de las unidades de salas de Microsoft Teams.
       -   Edite este paso y actualice los parámetros de la línea de comandos para especificar el **identificador del área de trabajo** y la **clave del área de trabajo**.
       -   Vea [configurar dispositivos de prueba para la supervisión de Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obtener más información sobre cómo obtener el identificador del área de trabajo de Operations Management Suite y la clave principal.
       -   Compruebe que esté seleccionada la redirección del sistema de archivos de **SRS V2-Microsoft Monitoring Agent** y deshabilitar el redireccionamiento **del sistema de archivos de 64** bits.
       -   Para obtener más información sobre cómo supervisar el estado de la implementación de salas de Microsoft Teams, vea [planear la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-plan.md), [implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md) y [administrar Microsoft Los dispositivos de salas de equipos con el monitor de Azure](azure-monitor-manage.md).

   11. **Copie los archivos de configuración de SRS V2**: en este paso, se copian los archivos de configuración y configuración necesarios del kit de implementación de Microsoft Teams Rooms en la unidad de disco duro local. No se necesita ninguna personalización para este paso.
       -   Compruebe que se seleccione el **paquete de aplicación SRS V2-SRS** y deshabilitar el redireccionamiento **del sistema de archivos de 64 bits** .

   12. **Install-SRSv2-os-updates**: este paso implementa todas las actualizaciones de sistema operativo obligatorias necesarias para la implementación de salas de Microsoft Teams. Siga este procedimiento:
       -   Marque [configurar una consola de salones de Microsoft Teams](console.md) para ver qué actualizaciones son necesarias.
       -   Compruebe que el **paquete de actualizaciones para el sistema operativo SRS V2** incluye todas las actualizaciones necesarias.
       -   Compruebe que esté seleccionado el **paquete SRS V2 – os updates** .
       -   Compruebe que la Directiva de ejecución de PowerShell esté **** configurada para omitir.

   13. **Reiniciar equipo**: este paso reinicia el equipo después de instalar las actualizaciones obligatorias del sistema operativo. No se necesita ninguna personalización para este paso.

   14. **Configurar componentes de Windows**: este paso configura las características necesarias de Windows. No se necesita ninguna personalización para este paso.

   15. **Reiniciar equipo**: este paso reinicia el equipo después de configurar las características de Windows. No se necesita ninguna personalización para este paso.

   16. **Agregar usuario local de Skype**: este paso crea la cuenta de Skype local que se usa para iniciar sesión automáticamente en Windows e iniciar la aplicación salas de Microsoft Teams. Este paso no tiene ningún paquete de software asociado, y no se necesita ninguna personalización para él.

   17. **Instalar y configurar la aplicación SRS**: este paso configura la instalación de la aplicación salas de Microsoft Teams para el siguiente arranque del sistema operativo.
       -   Compruebe que esté seleccionada la **configuración de SRS V2-configure SRS Setup Package** and disable **64-bit File System** .

> [!IMPORTANT]
> Es muy importante que los pasos de la secuencia de tareas estén en el orden indicado. Modificar el orden de los pasos o configurar pasos adicionales puede estropear la implementación.
>
> **Configurar y configurar** el paso de la aplicación SRS debe ser el último paso de la secuencia de tareas; de lo contrario, la implementación podría fallar.

### <a name="create-deployment-for-the-task-sequence"></a>Crear una implementación para la secuencia de tareas

1. Seleccione la secuencia de tareas y, a continuación, seleccione **implementar**.

2. Seleccione **examinar** para seleccionar recopilación de destino para la implementación.

3. Seleccione **todos los equipos** desconocidos y, después, haga clic en **Aceptar**.

4. Seleccione **siguiente**.

5. Seleccione **disponible** en la lista desplegable **propósito** .

6. Seleccione **solo medios y PXE** en la lista **hacer disponible hasta el siguiente** y, a continuación, seleccione **siguiente**.
   > [!WARNING]
   > Es muy importante que el **propósito** esté establecido en **disponible**. Asegúrese de que el **propósito** **no** esté establecido en **requerido**. Además, asegúrese de que selecciona **solo medios y PXE** en la forma **disponible para lo siguiente**.
   >
   > La configuración de estos valores en algo diferente puede hacer que todos los equipos obtengan la imagen de implementación de salas de Microsoft Teams al arrancar.
7. No especifique ninguna programación y seleccione **siguiente**.

8. No cambie nada en la sección **experiencia del usuario** y seleccione **siguiente**.

9. No cambie nada dentro de la sección **alertas** y seleccione **siguiente**.

10. No cambie nada en la sección de **puntos de distribución** y seleccione **siguiente**.

11. Confirme la configuración y, a continuación, seleccione **siguiente**.

12. Seleccione **cerrar**.

<a name="validate-and-troubleshoot-the-solution"></a>Validar y solucionar problemas de la solución
--------------------------------------

Una vez completadas las secuencias de tareas de System Center Configuration Manager, tendrá que realizar una ejecución de prueba para validar que la secuencia de tareas puede implementar y configurar las unidades de salas de Microsoft Teams.

1.  Conecte el dispositivo de prueba a la red cableada mediante uno de los adaptadores Ethernet compatibles o usando la superficie del Dock. Si la funcionalidad de arranque PXE no se ha configurado para su entorno, puede usar la imagen de arranque de la unidad flash USB [que creó anteriormente](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) para arrancar desde USB y conectarse a Configuration Manager.

2.  Acceda al firmware e inicie el inicio PXE:

    1.  Cerciórese de que el dispositivo Surface esté apagado.

    2.  Mantén pulsado el botón **subir volumen** .

    3.  Presione y suelte el botón **Power (encendido** ).

    4.  Cuando el dispositivo empiece a arrancar, suelte el botón **subir volumen** .

    5.  Seleccione **configuración de arranque**.

    6.  Siga uno de estos pasos:

        -   Seleccione **arranque PXE**y arrástrelo hasta la parte superior de la lista. Como alternativa, puedes deslizar el dedo hacia la izquierda en el adaptador de red para arrancar el dispositivo inmediatamente. Esto no afectará el orden de inicio.
        -   Seleccione la unidad flash USB que contiene el medio de inicio.

3.  Seleccione **salir**y, a continuación, **reiniciar ahora**.

4.  Cuando se le solicite, seleccione **entrar** para el servicio de inicio de red.

5.  Windows PE se cargará en la memoria y se iniciará el Asistente para secuencia de tareas. Seleccione **siguiente** para continuar.

6.  Seleccione la secuencia de tareas que importó anteriormente y, a continuación, seleccione **siguiente**.

7.  Después de aplicar la configuración del disco, se le pedirá que especifique un nombre de equipo para el dispositivo. La interfaz de usuario mostrará un nombre de equipo recomendado según el número de serie del dispositivo Surface Pro. Puede aceptar el nombre propuesto o especificar uno nuevo. Siga las instrucciones de la pantalla asignación de nombre de equipo. Al seleccionar **Aceptar**, comienza la implementación.

8.  El resto del proceso de implementación es automático y no pide más entradas del usuario.

9.  Después de que la secuencia de tareas de implementación termine de configurar el dispositivo, verá la siguiente pantalla de configuración que le pedirá que configure las opciones de la aplicación salas de Microsoft Teams.

    ![Pantalla inicial de la aplicación salas de Microsoft Teams](../media/room-systems-scale-image2.png)

10.  Conecte la Surface Pro a la consola de salas de Microsoft Teams y configure las opciones de la aplicación.

11.  Compruebe que las capacidades enumeradas en la [ayuda de Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estén funcionando en el dispositivo implementado.


Para solucionar un error de instalación, consulte el archivo **SMSTS. log** , en el que se registran todos los pasos ejecutados en una secuencia de tareas de Configuration Manager.

El archivo SMSTS. log se almacena en una de varias rutas, dependiendo de la fase del proceso de compilación. Consulte la tabla siguiente para identificar la ruta de acceso al archivo SMSTS. log.


| **Fase de implementación**                                                            | **Ruta de registro de secuencia de tareas**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, antes del formato HDD                                                        | X:\\Windows\\Temp\\smstslog\\smsts. log             |
| WinPE, después de formato HDD                                                         | C:\\_SMSTaskSequence\\registra\\Smstslog\\smsts. log    |
| Sistema operativo implementado antes de instalar el agente de administrador de configuración | c:\\_SMSTaskSequence\\registra\\Smstslog\\smsts. log    |
| Sistema operativo y el agente de Configuration Manager implementado                   | % WINDIR%\\system32\\CCM\\registra\\Smstslog\\smsts. log |
| Ejecución de la secuencia de tareas completada                                                | % WINDIR%\\system32\\CCM\\registra\\smsts. log           |

> [!TIP]
> Puede seleccionar **F8** en cualquier momento durante la secuencia de tareas para abrir una consola de comandos y, a continuación, obtener acceso al archivo SMSTS. log.

Para solucionar problemas de inicio PXE, consulte los dos archivos de registro en el servidor de Configuration Manager que son específicos de las acciones de PXE:

-   **Pxecontrol. log**, ubicado en el directorio de registros de instalación de Configuration Manager

-   **Smspxe. log**, que se encuentra en el directorio de registros del punto de administración de Configuration Manager (MP)

Para obtener una lista completa de los archivos de registro que puede usar para solucionar problemas en la instalación de Configuration Manager, consulte [archivos de registro en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).
