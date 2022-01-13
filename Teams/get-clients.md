---
title: Obtener clientes para Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo instalar los distintos clientes disponibles para Microsoft Teams en equipos PC, Mac y dispositivos móviles.
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 31bafc1c112d8b50990cc6e92c863c7e242aa5fb
ms.sourcegitcommit: efea3b3b9dceb1a1d82eb7a09a5104dcd6df8abf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61993014"
---
# <a name="get-clients-for-microsoft-teams"></a>Obtener clientes para Microsoft Teams

> [!TIP]
> **¿Quiere instalar Teams en su PC, Mac o dispositivo móvil?** Consulte [Instalar el cliente de Teams](https://www.microsoft.com/microsoft-teams/download-app).

En este artículo se proporciona información sobre cómo instalar Microsoft Teams en dispositivos de su empresa.

Para obtener más detalles sobre las capacidades de los clientes en distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="desktop-client"></a>Cliente de escritorio

> [!TIP]
> Vea la sesión siguiente para conocer las ventajas del cliente de escritorio de Windows, y cómo planearlo e implementarlo: [Cliente de escritorio de Teams para Windows](https://aka.ms/teams-clients)

El cliente de escritorio de Microsoft Teams es una aplicación independiente y está también [disponible en Aplicaciones de Microsoft 365 para empresas](/deployoffice/teams-install). Teams está disponible para las versiones de 32 bits y 64 bits de Windows (8.1 o posterior), ARM64 para Windows 10 en ARM y Windows Server (2012 R2 o posterior), así como para macOS y Linux (en los formatos `.deb` y `.rpm`). En Windows, Teams requiere .NET Framework 4.5 o posterior; el instalador de Teams le ofrecerá instalarlo si no lo tiene. En Linux, los administradores de paquetes como `apt` y `yum` intentarán instalar los requisitos por usted. No obstante, si no lo hacen, deberá instalar todos los requisitos indicados antes de instalar Teams en Linux.

Los clientes de escritorio brindan asistencia en tiempo real para las comunicaciones (audio, vídeo y contenido compartido) para las reuniones de equipo, las llamadas grupales y las llamadas de uno a uno.

Los usuarios pueden descargar e instalar los clientes de escritorio directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos locales adecuados (no se requieren derechos de administrador para instalar el cliente de Teams en PC, pero sí son necesarios para Mac).

> [!NOTE]
> Para obtener más detalles sobre cómo instalar Teams en un Chromebook, consulte [Cómo instalar y ejecutar Microsoft Office en un Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).

Los administradores de TI pueden elegir el método que prefieran para distribuir los archivos de instalación en los equipos de su organización. Por ejemplo: Microsoft Endpoint Configuration Manager (Windows) o Jamf Pro (macOS). Para obtener el paquete de MSI de distribución de Windows, vea [Instalar Microsoft Teams con MSI](msi-deployment.md).

> [!NOTE]
> La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.

### <a name="windows"></a>Windows

La instalación de Microsoft Teams para Windows brinda instaladores que se pueden descargar en arquitecturas de 32 y 64 bits.

> [!NOTE]
> La arquitectura (32 o 64 bits) de Microsoft Teams es independiente de la arquitectura de Windows y Office que esté instalada. Se recomienda la versión de 64 bits de Microsoft Teams en sistemas de 64 bits.

El cliente de Windows se implementará en la carpeta AppData ubicada en el perfil del usuario. Implementar en el perfil de usuario local permite instalar el cliente sin necesidad de tener permisos elevados. El cliente de Windows aprovecha las siguientes ubicaciones:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Cuando los usuarios inician una llamada utilizando el cliente de Microsoft Teams, podrían recibir una advertencia con la configuración del firewall de Windows que les pide que permitan la comunicación. Es posible que se indique a los usuarios que ignoren el mensaje porque la llamada funcionará, incluso si la advertencia se descarta.

![Captura de pantalla de un cuadro de diálogo Alerta de Seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de Permitir para los protocolos TCP y UDP.

Si quiere evitar que Teams pida a los usuarios que creen reglas de firewall cuando los usuarios realicen su primera llamada desde Teams, use el [script de PowerShell de ejemplo: regla de firewall de entrada](#sample-powershell-script---inbound-firewall-rule).

### <a name="mac"></a>Mac

Los usuarios de Mac pueden instalar Teams mediante el uso de un archivo PKG de instalación para equipos macOS. Se requiere acceso administrativo para instalar el cliente de Mac. El cliente de macOS se instala en la carpeta /Applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Instalar Teams con el archivo PKG 

1. Desde la [página de descarga de Teams](https://teams.microsoft.com/downloads), en **Mac**, haga clic en **Descargar**.
2. Haga doble clic en el archivo PKG.
3. Siga los pasos del asistente de instalación para completar la instalación.
4. Se instalará Teams en la carpeta /Applications. Es una instalación de todo el equipo.

> [!NOTE]
> Durante la instalación, el PKG solicitará las credenciales de administrador. El usuario debe escribir las credenciales de administrador, independientemente de si el usuario es un administrador.

Si un usuario actualmente tiene una instalación DMG de Teams y quiere reemplazarla con la instalación del PKG, el usuario debe:

1. Salir de la aplicación de Teams.
2. Desinstalar la aplicación de Teams.
3. Instale el archivo PKG.

Los administradores de TI pueden usar la implementación administrada de Teams para distribuir los archivos de instalación en todos los equipos Mac en su organización, como Jamf Pro.

> [!NOTE]
> Si tiene problemas para instalar el PKG, háganoslo saber. En la sección **Comentarios** al final de este artículo, haga clic en **Comentarios sobre el producto**.

### <a name="linux"></a>Linux

Los usuarios podrán instalar paquetes de Linux nativos en los formatos `.deb` y `.rpm`. Si se instala el paquete DEB o RPM, se instalará automáticamente el repositorio de paquetes.

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

La clave de firma para habilitar la actualización automática mediante el administrador de paquetes del sistema se instala automáticamente. No obstante, también se puede encontrar en: <https://packages.microsoft.com/keys/microsoft.asc>. Microsoft Teams se suministra mensualmente y, si el repositorio se ha instalado correctamente, el administrador de paquetes del sistema debería controlar la actualización automática de la misma manera que otros paquetes del sistema.

> [!NOTE] 
> Si encuentra un error, envíelo mediante `Report a Problem` desde el cliente. Para problemas conocidos, consulte [Soporte para Teams en la organización](/MicrosoftTeams/troubleshoot/teams-welcome).
> Para obtener soporte técnico de Teams para Linux, puede usar el [canal de soporte del foro de Linux en Preguntas y respuestas de Microsoft](/answers/topics/teams.html). Asegúrese de usar la etiqueta `teams-linux` al publicar preguntas. 

#### <a name="install-teams-using-deb-package"></a>Instalación de Teams con el paquete DEB

1. Descargue el paquete desde <https://aka.ms/getteams>.
2. Instálelo mediante uno de los métodos siguientes:
    - Abra la herramienta de administración del paquete correspondiente y siga el proceso autoguiado de instalación de aplicaciones Linux.
    - O bien, si le gusta Terminal, escriba lo siguiente: `sudo dpkg -i **teams download file**`

Para iniciar Teams a través de Actividades o a través de Terminal, escriba `teams`.

#### <a name="install-teams-using-rpm-package"></a>Instalación de Teams con el paquete RPM

1. Descargue el paquete desde <https://aka.ms/getteams>.
2. Instálelo mediante uno de los métodos siguientes:
    - Abra la herramienta de administración del paquete correspondiente y siga el proceso autoguiado de instalación de aplicaciones Linux.
    - O bien, si le gusta Terminal, escriba lo siguiente: `sudo yum install **teams download file**`

Para iniciar Teams a través de Actividades o a través de Terminal, escriba `teams`.

#### <a name="install-manually-from-the-command-line"></a>Instalación manual mediante la línea de comandos

Instalación manual en las distribuciones de Debian y Ubuntu:

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

Instalación manual en las distribuciones basadas en RHEL, Fedora y CentOS:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

También puede usar yum en lugar de dnf:

```bash
yum check-update
sudo yum install teams
```

Instalación manual en las distribuciones basadas en openSUSE:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>Cliente Web

El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo y funcional que puede utilizarse desde una variedad de exploradores. El cliente web es compatible con Llamadas y Reuniones mediante webRTC, por lo que no se requiere ningún complemento o descarga para ejecutar Teams en un explorador web. El explorador debe configurarse para permitir cookies de terceros.

[!INCLUDE [browser-support](includes/browser-support.md)]

El cliente web detecta la versión del explorador al conectarse con [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Si se detecta una versión no admitida, se bloquea el acceso a la interfaz web y se recomienda al usuario que descargue el cliente de escritorio o la aplicación móvil.

## <a name="mobile-clients"></a>Clientes móviles

Las aplicaciones móviles de Microsoft Teams están disponibles para iOS y Android, y están pensadas para que los usuarios que no están en un lugar fijo participen en conversaciones basadas en chat y para permitir las llamadas de audio de par a par. Para las aplicaciones móviles, vaya a la tienda móvil correspondiente: Google Play y App Store de Apple. La aplicación de Windows Phone se retiró el 20 de julio de 2018 y podría no funcionar.

Aquí puede ver cómo [obtener Teams para Android](get-teams-android-in-china.md) en China.

Las siguientes son las plataformas móviles admitidas para Microsoft Teams:

- **Android**: la compatibilidad está limitada a las cuatro versiones principales más recientes de Android. Cuando se publica una nueva versión principal de Android, se admiten oficialmente la nueva versión y las tres versiones anteriores.

- **iOS**: la compatibilidad está limitada a las dos versiones principales más recientes de iOS. Cuando se publica una nueva versión principal de iOS, se admiten oficialmente la nueva versión y las tres versiones anteriores de iOS.

> [!NOTE]
> La versión móvil debe estar disponible para el público para que Teams funcione según lo esperado.

Las aplicaciones móviles solamente se distribuyen y actualizan en la tienda de aplicaciones de la plataforma móvil correspondiente. Microsoft no admite la distribución de las aplicaciones móviles mediante MDM ni instalación de prueba. Una vez que se haya instalado la aplicación móvil en una plataforma móvil compatible, se admitirá la aplicación móvil de Teams, siempre y cuando la versión se encuentre dentro de los tres meses siguientes a la versión actual.

|&nbsp; |&nbsp; |&nbsp; |
|---|---|---|
|![Un icono que representa un punto de decisión.](media/Get_clients_for_Microsoft_Teams_image4.png)|Punto de decisión|¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?|
|![Un icono que representa los pasos siguientes.](media/Get_clients_for_Microsoft_Teams_image5.png)|Pasos siguientes|Si su organización restringe la instalación de software, asegúrese de que el proceso sea compatible con Microsoft Teams. Nota: No se requieren derechos de administrador para instalar el cliente en PC, pero sí son necesarios para Mac.|


## <a name="client-update-management"></a>Administración de actualizaciones del cliente

Actualmente, el servicio de Microsoft Teams actualiza los clientes en forma automática, sin que se necesite la intervención del administrador de TI. Si hay una actualización disponible, el cliente descargará automáticamente la actualización y, cuando la aplicación esté inactiva durante un tiempo, comenzará el proceso de actualización.

## <a name="client-side-configurations"></a>Configuración del lado del cliente

Actualmente, no hay opciones disponibles para configurar el cliente a través del administrador de inquilinos, PowerShell, Group Policy Objects ni el registro.

## <a name="notification-settings"></a>Configuración de notificaciones

En este momento, no hay opciones disponibles para que los administradores de TI puedan configurar las notificaciones para los clientes. Todas las opciones de notificaciones las establece el usuario. En la siguiente figura se detalla la configuración predeterminada del cliente.

![Captura de pantalla de la configuración de Notificaciones.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a>Script de PowerShell de ejemplo: regla de firewall de entrada

Este script de ejemplo, que tiene que ejecutarse en los equipos de cliente en el contexto de una cuenta de administrador con privilegios elevados, creará una nueva regla de firewall de entrada para cada carpeta de usuario que se encuentra en c:\users. Cuando Teams encuentra esta regla, impedirá que la aplicación de Teams solicite a los usuarios crear reglas de firewall cuando los usuarios realicen su primera llamada de Teams.

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions.
   The script will create a new inbound firewall rule for each user folder found in c:\users.
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
