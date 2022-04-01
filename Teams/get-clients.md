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
ms.openlocfilehash: 4b922607955d8b825006217bd2fe333eaadbc1ce
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556571"
---
# <a name="get-clients-for-microsoft-teams"></a>Obtener clientes para Microsoft Teams

> [!TIP]
> **¿Quiere instalar Teams en su PC, Mac o dispositivo móvil?** Consulte [Instalar el cliente de Teams](https://go.microsoft.com/fwlink/?linkid=855754).

Microsoft Teams puede instalarse en equipos PC, Mac y dispositivos móviles, y también se puede acceder a través de un explorador web. La mayoría de los usuarios finales pueden empezar a usar Teams simplemente [instalando el cliente.](https://go.microsoft.com/fwlink/?linkid=855754) ellos mismos. Después de instalar el cliente de Teams, lo único que deben hacer es iniciar sesión con su nombre de usuario y contraseña.

Si usted es un profesional de TI y desea obtener más información sobre la experiencia de instalación de Teams y sus requisitos, seleccione un sistema operativo cliente en este artículo para obtener más información.

Para obtener más detalles sobre las capacidades de los clientes en distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="desktop-clients"></a>Clientes de escritorio

El cliente de escritorio de Teams está disponible como una aplicación independiente y como parte de [Aplicaciones de Microsoft 365 para empresas](/deployoffice/teams-install) para los siguientes sistemas operativos:

- Versiones de Windows de 32 y 64 bits (8.1 o posterior)
- ARM64 para Windows 10 en ARM
- Windows Server (2012 R2 o posterior)
- macOS
- Linux (en formato `.deb` y `.rpm` )
- Chrome OS (Para obtener más información, vea [Cómo usar Microsoft Office en un Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad))

Los usuarios finales pueden descargar e instalar los clientes de escritorio directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos locales adecuados. No se requieren permisos de administrador para instalar el cliente de Teams en equipos Windows, pero sí en equipos Mac.

Los profesionales de IT pueden elegir su método preferido para distribuir los archivos de instalación a los equipos de su organización. Por ejemplo: Microsoft Endpoint Configuration Manager (Windows) o Jamf Pro (macOS). Para obtener más información sobre cómo distribuir Teams, vea lo siguiente.

- **Windows** [Instalar Teams usando Endpoint Configuration Manager](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de Teams clientes y no para actualizaciones futuras. Para obtener información sobre el proceso de actualización de Teams, consulte [Proceso de actualización de Teams](teams-client-update.md).

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> Vea la sesión siguiente para conocer las ventajas del cliente de escritorio de Windows, y cómo planearlo e implementarlo: [Cliente de escritorio de Teams para Windows](https://aka.ms/teams-clients)

Teams en Windows proporciona instaladores MSI descargables en arquitecturas de [32](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true) bits, [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true) y [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true). La arquitectura x86 (32 bits frente a 64 bits) de Teams es independiente de la arquitectura de Windows y Office que está instalada. Se recomienda la versión de 64 bits de Teams en sistemas de 64 bits.

Teams requiere .NET Framework 4.5 o posterior. Si .NET Framework o posterior no está instalado, el instalador de Teams le ofrecerá instalarlo.

El cliente de Windows se implementará en la carpeta AppData ubicada en el perfil del usuario. Implementar en el perfil de usuario local permite instalar el cliente sin necesidad de tener permisos elevados. El cliente de Windows aprovecha las siguientes ubicaciones:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Cuando los usuarios inician una llamada utilizando el cliente de Teams, podrían recibir una advertencia con la configuración del firewall de Windows que les pide que permitan la comunicación. Es posible que se indique a los usuarios que ignoren el mensaje porque la llamada funcionará, incluso si la advertencia se descarta.

![Captura de pantalla de un cuadro de diálogo Alerta de Seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de Permitir para los protocolos TCP y UDP.

Si desea impedir que Teams pida a los usuarios que creen reglas de firewall cuando los usuarios realicen su primera llamada desde Teams, use el script de PowerShell en [Script de ejemplo: script de PowerShell de firewall de Microsoft Teams](client-firewall-script.md).

### <a name="mac"></a>[Mac](#tab/Mac)

Los usuarios de Mac pueden instalar Teams mediante el uso de un archivo PKG de instalación para equipos macOS. Se requiere acceso administrativo para instalar el cliente de Mac. El cliente de macOS se instala en la carpeta /Applications.

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

Los profesionales de IT pueden usar una solución de implementación administrada, como Jamf Pro, para distribuir los archivos de instalación Teams a todos los Mac de su organización.

### <a name="linux"></a>[Linux](#tab/Linux)

En Linux, los administradores de paquetes como `apt` y `yum` intentarán instalar los requisitos por usted. No obstante, si no lo hacen, deberá instalar todos los requisitos indicados antes de instalar Teams en Linux.

Los usuarios podrán instalar paquetes de Linux nativos en los formatos `.deb` y `.rpm`. Si se instala el paquete DEB o RPM, se instalará automáticamente el repositorio de paquetes.

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

La clave de firma para habilitar la actualización automática mediante el administrador de paquetes del sistema se instala automáticamente. No obstante, también se puede encontrar en: <https://packages.microsoft.com/keys/microsoft.asc>. Teams se distribuye mensualmente y, si el repositorio se instaló correctamente, el administrador de paquetes del sistema debe controlar la actualización automática de la misma manera que otros paquetes del sistema.

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

---

## <a name="mobile-clients"></a>Clientes móviles

Las aplicaciones móviles de Teams están disponibles para iOS y Android, y están pensadas para que los usuarios que no están en un lugar fijo participen en conversaciones basadas en chat y para permitir las llamadas de audio de par a par. Para las aplicaciones móviles, vaya a la tienda móvil correspondiente: Google Play y App Store de Apple.

Las plataformas móviles compatibles con las aplicaciones móviles de Teams son las siguientes:

- **Android**: la compatibilidad está limitada a las cuatro versiones principales más recientes de Android. Cuando se publica una nueva versión principal de Android, se admiten oficialmente la nueva versión y las tres versiones anteriores.

- **iOS**: la compatibilidad está limitada a las dos versiones principales más recientes de iOS. Cuando se publica una nueva versión principal de iOS, se admiten oficialmente la nueva versión y las tres versiones anteriores de iOS.

> [!NOTE]
> La versión móvil debe estar disponible para el público para que Teams funcione según lo esperado.

Las aplicaciones móviles solamente se distribuyen y actualizan en la tienda de aplicaciones de la plataforma móvil correspondiente. Microsoft no admite la distribución de las aplicaciones móviles mediante MDM ni instalación de prueba. Una vez que se haya instalado la aplicación móvil en una plataforma móvil compatible, se admitirá la aplicación móvil de Teams, siempre y cuando la versión se encuentre dentro de los tres meses siguientes a la versión actual.

Si está en China, puede instalar Teams desde las siguientes tiendas de aplicaciones:

- **Xiaomi** <https://aka.ms/TeamsXiaomi>
- **Huawei** <https://aka.ms/TeamsHuawei>
- **Oppo** Buscar "Teams" en la tienda Oppo
- **Baidu** <https://aka.ms/teams_baidu_direct_dl>

## <a name="browser-client"></a>Cliente del explorador

El cliente del explorador ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente funcional completo que se puede usar desde una variedad de exploradores. El cliente del explorador admite llamadas y reuniones mediante webRTC, por lo que no se requiere ningún complemento ni descarga para ejecutar Teams en un explorador. El explorador debe configurarse para permitir cookies de terceros.

[!INCLUDE [browser-support](includes/browser-support.md)]

El cliente del explorador realiza la detección de la versión del explorador al conectarse a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Si se detecta una versión de explorador no compatible, bloqueará el acceso a la interfaz del explorador y recomendará al usuario que descargue el cliente de escritorio o la aplicación móvil.
