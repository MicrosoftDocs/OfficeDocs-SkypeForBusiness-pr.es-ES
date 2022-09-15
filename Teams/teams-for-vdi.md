---
title: Teams para la infraestructura de escritorio virtualizada
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Obtenga información sobre cómo ejecutar Microsoft Teams en un entorno de infraestructura de escritorio virtualizada (VDI).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92d46cacd510f448943deba86a6ed25d4f4360ab
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706517"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para la infraestructura de escritorio virtualizada

En este artículo se describen los requisitos y limitaciones del uso de Microsoft Teams en un entorno virtualizado.

## <a name="what-is-vdi"></a>¿Qué es VDI?

Infraestructura de escritorio virtual (VDI) es la tecnología de virtualización que hospeda un sistema operativo de escritorio y aplicaciones en un servidor centralizado en un centro de datos. Esto permite una experiencia de escritorio completa y personalizada para los usuarios con un origen centralizado totalmente seguro y compatible.

Teams en un entorno virtualizado admite el chat y la colaboración. Además, con las plataformas Azure Virtual Desktop, Citrix y VMware, también se admiten las funciones de llamadas y reuniones.

Teams también admite varias configuraciones en entornos virtuales. Entre ellos se incluyen los modos VDI, dedicados, compartidos, persistentes y no persistentes. Las características se encuentran en desarrollo continuo y se agregan de forma periódica, y la funcionalidad se ampliará con el tiempo.

El uso de Teams en un entorno virtualizado puede ser algo diferente al uso de Teams en un entorno no virtualizado. Por ejemplo, es posible que algunas características avanzadas no estén disponibles en un entorno virtualizado y que la resolución de vídeo sea diferente.

Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.

> [!Note]
> Para obtener más información sobre VDI de Teams en distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams en componentes VDI

El uso de Teams en un entorno virtualizado requiere los siguientes componentes.

- **Agente de virtualización**: el administrador de recursos y conexiones del proveedor de virtualización, como Azure
- **Escritorio virtual**: La pila de máquina virtual (VM) que ejecuta Teams
- **Thin Client**: El dispositivo con el que el usuario interactúa físicamente
- **Aplicación de escritorio de Teams**: La aplicación cliente de escritorio de Teams

## <a name="teams-on-vdi-requirements"></a>Requisitos de Teams para VDI

### <a name="virtualization-provider-requirements"></a>Requisitos del proveedor de virtualización

La aplicación de escritorio de Teams se validó con proveedores líderes de soluciones de virtualización. Con varios proveedores de mercado, le recomendamos que consulte con su proveedor de soluciones de virtualización para asegurarse de que cumple los requisitos mínimos.
  
Actualmente, Teams en VDI con optimización de audio/vídeo (AV) está certificado con Azure Virtual Desktop, Citrix y VMware. Revise la información de esta sección para asegurarse de que cumple todos los requisitos de funcionalidad adecuada.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para Teams

Las siguientes plataformas tienen soluciones de infraestructura de escritorio virtual para Teams.

|Plataforma|Solución|
|----|---|
|![El logotipo que representa a Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure Virtual Desktop</a>, <a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![El logotipo que representa a Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps y Desktops</a> |
|![El logotipo que representa VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure Virtual Desktop

Azure Virtual Desktop proporciona optimización de AV para Teams en VDI. Para obtener más información sobre los requisitos y la instalación, consulte [Usar Teams en Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 usa la optimización de AV proporcionada por Azure Virtual Desktop para garantizar unas experiencias óptimas de Teams desde equipos en la nube. Para obtener más información sobre los requisitos y la instalación, consulte [Usar Teams en UN EQUIPO en la nube](/windows-365/enterprise/teams-on-cloud-pc).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos de Citrix Virtual Apps y Desktops

Citrix Virtual Apps and Desktops (anteriormente conocido como XenApp y XenDesktop) proporciona optimización de AV para Teams en VDI. Con Citrix Virtual Apps y Desktops, Teams en VDI admite la funcionalidad de llamadas y reuniones, además del chat y la colaboración.

Puede descargar la última versión de Citrix Virtual Apps y Desktops en el [sitio de descargas de Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Tendrás que iniciar sesión primero). Los componentes necesarios se agrupan de forma predeterminada en [Citrix Workspace App (CWA)](https://www.citrix.com/downloads/workspace-app/) y Virtual Delivery Agent (VDA). No es necesario instalar ningún componente o complemento adicional en CWA o VDA.

Para conocer los últimos requisitos de servidor y cliente, consulte el artículo [Optimización para Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) en el sitio web de Citrix.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos de VMware Horizon Workspace y Escritorio

VMware Horizon es una plataforma moderna para la entrega segura de aplicaciones y escritorios virtuales en la nube híbrida. Para ofrecer una excelente experiencia para el usuario final, VMware Horizon proporciona optimización de medios para Teams. Esta optimización mejora la productividad general en todas las aplicaciones y escritorios virtuales, y mejora la experiencia del usuario al llamar y realizar reuniones con Teams.

Puede descargar la última versión de VMware Horizon desde la página [descargas de VMware](https://customerconnect.vmware.com/downloads/#all_products) . Los componentes de optimización de medios necesarios forman parte de Horizon Agent y Horizon Client de forma predeterminada y no es necesario instalar ningún complemento adicional para usar la característica de optimización para Teams.

Para obtener los últimos requisitos e instrucciones sobre cómo configurar la optimización de medios para Teams, consulte el artículo [Configuración de optimización de medios para Microsoft Teams](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) en el sitio web de VMware.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar o actualizar la aplicación de escritorio de Teams en VDI

Puede implementar la aplicación de escritorio de Teams para VDI con una instalación por equipo o por usuario con el paquete MSI. Decidir qué enfoque usar depende de si usa una configuración persistente o no persistente y de las necesidades de funcionalidad asociadas de su organización.

Para una configuración persistente dedicada, funcionará tanto por equipo como por usuario. Sin embargo, para una configuración no persistente, Teams requiere una instalación por equipo para poder trabajar de forma eficaz. Consulte la sección [Configuración no persistente](#non-persistent-setup) .

Con la instalación por equipo, se deshabilitan las actualizaciones automáticas. Esto significa que, para actualizar la aplicación Teams, debe desinstalar la versión actual para actualizar a una versión más reciente. Con la instalación por usuario, se habilitan las actualizaciones automáticas.

> [!IMPORTANT]
> Mantenga actualizada la aplicación de escritorio de Teams en su entorno VDI. No se admiten las versiones de la aplicación de escritorio de Teams con fechas de lanzamiento con más de 90 días de antigüedad que la [fecha de lanzamiento de la versión actual](/officeupdates/teams-app-versioning) . Las versiones no compatibles de la aplicación de escritorio de Teams muestran una página de bloqueo a los usuarios y solicitan que actualicen su aplicación.

Para la mayoría de las implementaciones de VDI, le recomendamos que implemente Teams mediante la instalación por equipo. Para actualizar a la última versión de Teams, comience con el procedimiento de desinstalación seguido de la implementación más reciente de la versión de Teams.

Para que la optimización de AV de Teams en entornos VDI funcione correctamente, el dispositivo de cliente fino debe tener acceso a Internet. Si el acceso a Internet no está disponible en el dispositivo de cliente fino, el inicio de optimización no se realizará correctamente. Esto significa que el usuario está en un estado multimedia no optimizado.

#### <a name="dedicated-persistent-setup"></a>Configuración persistente dedicada

En una configuración persistente dedicada, los cambios en el sistema operativo local de los usuarios se conservan después de cerrar la sesión de los usuarios. Para una configuración persistente, Teams admite la instalación tanto por usuario como por equipo.

A continuación se muestra la configuración mínima de VM recomendada.

|Parámetro  |Sistema operativo de estación de trabajo  |Sistema operativo del servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4, 6 u 8 núcleos<br>Es importante comprender la configuración subyacente de acceso no uniforme a la memoria (NUMA) y configurar las máquinas virtuales en consecuencia.     |
|RAM     |   4 GB      | De 512 MB a 1 GB por usuario        |
|Almacenamiento    | 8 GB        | De 40 GB a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuración no persistente

En una configuración no persistente, los cambios en el sistema operativo local de los usuarios no se conservan después de cerrar la sesión de los usuarios. Estas configuraciones son sesiones multiusuario compartidas habitualmente. La configuración de la máquina virtual varía en función del número de usuarios y de los recursos del servidor físico disponibles.

Para una configuración no persistente, la aplicación de escritorio de Teams debe instalarse por equipo en la imagen dorada. Esto garantiza un inicio eficaz de la aplicación Teams durante una sesión de usuario. Para obtener más información, consulte la sección [Instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

El uso de Teams en una configuración no persistente también requiere un administrador de almacenamiento en caché de perfil para una sincronización eficaz de los datos en tiempo de ejecución de Teams. La sincronización eficaz de datos garantiza que la información específica del usuario (como los datos, el perfil o la configuración de un usuario) se almacene en caché durante la sesión del usuario. Asegúrese de que se sincronizan los datos de estas dos carpetas:<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Se requiere una carpeta de itinerancia (o, si usa el redireccionamiento de carpetas, un administrador de almacenamiento en caché) para asegurarse de que la aplicación teams tiene los datos en tiempo de ejecución y los archivos necesarios para ejecutar la aplicación. Esto es necesario para mitigar problemas de latencia de red o problemas de red, lo que, de lo contrario, provocaría errores de aplicación y una experiencia lenta debido a los archivos y datos no disponibles.

Hay una variedad de soluciones de administrador de almacenamiento en caché disponibles, como [FSLogix](/fslogix/overview). Consulte con el proveedor del administrador de almacenamiento en caché para obtener instrucciones de configuración específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Lista de exclusión de contenido en caché de Teams para la configuración no persistente

Excluya lo siguiente de la carpeta de almacenamiento en caché de Teams, `%AppData%/Microsoft/Teams`. Excluir estos elementos ayuda a reducir el tamaño del almacenamiento en caché del usuario para optimizar aún más la configuración no persistente.

- .txt archivos
- Carpeta de pila de medios
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Aplicaciones Microsoft 365 para empresas consideraciones

Tenga en cuenta lo siguiente al implementar Teams con Aplicaciones Microsoft 365 para empresas en VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nuevas implementaciones de Teams a través de Aplicaciones Microsoft 365 para empresas

Antes de implementar Teams a través de Aplicaciones Microsoft 365 para empresas, primero debe desinstalar cualquier aplicación de Teams preexistente si se implementó mediante la instalación por equipo.

Teams a través de Aplicaciones Microsoft 365 para empresas se instala por usuario. Para obtener más información, consulte la sección [Instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Implementaciones de Teams a través de actualizaciones de Aplicaciones Microsoft 365 para empresas

Teams también se agrega a las instalaciones existentes de Aplicaciones Microsoft 365 para empresas. Como Aplicaciones Microsoft 365 para empresas instala Teams solo por usuario, consulte la sección [Instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Uso de Teams con instalación por equipo y Aplicaciones Microsoft 365 para empresas

Aplicaciones Microsoft 365 para empresas no admite instalaciones por equipo de Teams. Para usar la instalación por equipo, debe excluir Teams de Aplicaciones Microsoft 365 para empresas. Consulte [Implementar la aplicación de escritorio de Teams en la máquina virtual](#deploy-the-teams-desktop-app-to-the-vm) y [Cómo excluir la implementación de Teams a través de secciones de Aplicaciones Microsoft 365 para empresas](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise).

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Cómo excluir la implementación de Teams a través de Aplicaciones Microsoft 365 para empresas

Para obtener más información sobre Teams y Aplicaciones Microsoft 365 para empresas, vea [Cómo excluir Teams de las nuevas instalaciones de Aplicaciones Microsoft 365 para empresas](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) y [Usar directiva de grupo para controlar la instalación de Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implementar la aplicación de escritorio de Teams en la máquina virtual

⁠1. Descargue el paquete MSI de Teams que coincida con su sistema operativo de VDI VM mediante uno de los siguientes vínculos:
    - [Versión de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versión de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)
    > [!NOTE]
    > Para las nubes gubernamentales, consulte [Instalar equipos en masa con Windows Installer (MSI)](msi-deployment.md) para ver los vínculos de descarga a los archivos MSI.

2. Ejecute uno de los siguientes comandos para instalar EL MSI en la vm de VDI:

    - Instalación por usuario (predeterminada)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Este proceso es la instalación predeterminada, que instala Teams en la carpeta de `%AppData%` usuario. En este punto, la configuración de la imagen dorada está completa.

        > [!IMPORTANT]
        > Teams no funcionará correctamente con la instalación por usuario en una configuración no persistente.

    - Instalación por equipo

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Este proceso agrega una clave del Registro necesaria al equipo que permite al instalador de Teams saber que es una instancia de VDI.  Sin él, el instalador producirá un error, indicando: "Error en la instalación.  No se puede instalar para todos los usuarios cuando no se detecta un entorno VDI".

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Este proceso instala Teams en la `%ProgramFiles(x86)%` carpeta de un sistema operativo de 32 bits y en la `%ProgramFiles%` carpeta de un sistema operativo de 64 bits. En este punto, la configuración de la imagen dorada está completa.

        > [!IMPORTANT]
        >  Es necesario instalar Teams por equipo para las configuraciones no persistentes.

        Cuando se inicia la siguiente sesión interactiva, Teams se inicia y le pide las credenciales.

        > [!NOTE]
        > En estos ejemplos también se usa el `ALLUSERS=1` parámetro. Al establecer este parámetro, **Teams Machine-Wide Installer** aparece en **Programas y características** en **Panel de control** y en **Aplicaciones & características** en **Configuración de Windows** para todos los usuarios del equipo. Después, todos los usuarios pueden desinstalar Teams si tienen credenciales de administrador.
        >
        > Es importante comprender la diferencia entre `ALLUSERS=1` y `ALLUSER=1`. El `ALLUSERS=1` parámetro se puede usar en entornos que no sean VDI y VDI, mientras que el `ALLUSER=1` parámetro solo se usa en entornos VDI para especificar una instalación por equipo.

3. Desinstale el MSI de la VM de VDI. Hay dos formas de desinstalar Teams.

    - **Script de PowerShell**: Puede usar el script de PowerShell de [limpieza de implementación de Teams](scripts/powershell-script-deployment-cleanup.md) para desinstalar Teams y quitar la carpeta teams de un usuario. Ejecute el script para cada perfil de usuario en el que teams se instaló en el equipo.
    - **Línea de comandos**: ejecute el comando siguiente.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Este proceso desinstala Teams de la `%ProgramFiles(x86)%` carpeta o `%ProgramFiles%` carpeta, según el entorno del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Teams sobre consideraciones de rendimiento de VDI

Hay una variedad de configuraciones de configuración virtualizadas, cada una con un enfoque diferente para la optimización. Por ejemplo, una configuración podría centrarse en la densidad del usuario. Al planear, tenga en cuenta lo siguiente para ayudar a optimizar la configuración en función de las necesidades de carga de trabajo de su organización.

- **Requisito mínimo**: algunas cargas de trabajo pueden requerir una configuración con recursos que están por encima de los requisitos mínimos. Por ejemplo, cargas de trabajo para desarrolladores que usan aplicaciones que requieren más recursos informáticos.
- **Dependencias**: incluyen dependencias de infraestructura, carga de trabajo y otras consideraciones ambientales fuera de la aplicación de escritorio de Teams.
- **Características deshabilitadas en VDI**: Teams deshabilita las características que consumen muchos GPU para VDI, lo que puede ayudar a mejorar el uso transitorio de la CPU. Las siguientes características están deshabilitadas:
    - Animación css de Teams
    - Inicio automático de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams en VDI con llamadas y reuniones

Además del chat y la colaboración, Teams en VDI con llamadas y reuniones está disponible con plataformas de proveedores de virtualización compatibles. Las características compatibles se basan en la pila de medios WebRTC y en la implementación del proveedor de virtualización. El siguiente diagrama proporciona información general sobre la arquitectura.

![Diagrama que muestra Teams en arquitectura VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si actualmente ejecuta Teams sin optimización de AV en VDI y usa características que aún no se admiten para la optimización (como Ceder y tomar el control cuando se comparte una aplicación), tiene que establecer directivas de proveedores de virtualización para desactivar el redireccionamiento de Teams. Esto significa que las sesiones multimedia de Teams no se optimizarán. Para conocer los pasos para establecer directivas para desactivar el redireccionamiento de Teams, póngase en contacto con su proveedor de virtualización.

### <a name="network-requirements"></a>Requisitos de red

Le recomendamos que evalúe su entorno para identificar los riesgos y requisitos que pueden influir en la implementación general de voz y vídeo en la nube. Use la [herramienta de evaluación](https://www.microsoft.com/download/details.aspx?id=53885) de red Skype Empresarial para comprobar si su red está lista para Teams.

Para obtener más información sobre cómo preparar su red para Teams, consulte [Preparar la red de su organización para Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar desde Skype Empresarial en VDI a Teams en VDI

Si va a migrar de Skype Empresarial en VDI a Teams en VDI, además de las diferencias entre las dos aplicaciones, existen algunas diferencias cuando también se implementa VDI. Algunas funcionalidades que actualmente no son compatibles con VDI de Teams que están en Skype Empresarial VDI son las siguientes:

- Directiva por plataforma para deshabilitar algunas características av en VDI
- Ceder y tomar el control cuando se comparte aplicaciones
- Compartir pantalla desde el chat sin audio
- Envío y recepción de vídeo y pantalla compartida simultáneas

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams en el explorador Chrome frente a la aplicación de escritorio de Teams para VDI

Teams en el explorador Chrome no proporciona un reemplazo para la aplicación de escritorio de Teams para VDI con la optimización de AV. La experiencia de chat y colaboración funciona según lo esperado. Cuando se necesitan medios, hay algunas experiencias que podrían no cumplir las expectativas del usuario en el explorador Chrome:

- Es posible que la experiencia de streaming de audio y vídeo no sea óptima. Los usuarios pueden experimentar retrasos o una calidad reducida.
- La configuración del dispositivo no está disponible en la configuración del explorador.
- La administración de dispositivos se gestiona a través del explorador y requiere varias configuraciones en la configuración del sitio del explorador.
- Es posible que también deba establecerse la configuración del dispositivo en la administración de dispositivos de Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams en VDI con chat y colaboración

Si su organización quiere usar solo las características de chat y colaboración en Teams, puede establecer directivas a nivel de usuario para desactivar las funciones de llamadas y reuniones en Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Establecer directivas para desactivar la funcionalidad de llamadas y reuniones

Puede establecer directivas mediante el Centro de administración de Teams o PowerShell. Hasta unas horas para que los cambios de directiva se propaguen. Si no ves los cambios de una cuenta determinada inmediatamente, vuelve a intentarlo en unas pocas horas.

[**Directivas de llamada:**](teams-calling-policy.md) Teams incluye la directiva de llamadas **DisallowCalling** integrada, en la que se desactivan todas las características de llamada. Asigne la directiva **No permitir llamada** a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

[**Directivas de reunión**](meeting-policies-overview.md): Teams incluye la directiva de reunión **AllOff** integrada, en la que se desactivan todas las características de reunión. Asigne la directiva **AllOff** a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Asignar directivas mediante el Centro de administración de Teams

Para asignar la directiva de llamada **DisallowCalling** y la directiva de reunión **AllOff** a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Usuarios**.
2. Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.
3. Haga lo siguiente:
    1. En **Directiva de llamadas**, haga clic en **No permitir Llamada**.
    2. En **Directiva de reunión**, haga clic en **AllOff**.
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Usuarios** y busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en la **&#x2713;** (marca de verificación) de la parte superior de la tabla.
3. Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.

O bien, también puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a la directiva que quiera asignar. Por ejemplo:
    - Vaya a las **directivas de llamadas** de **voz** >  y, a continuación, haga clic en **No permitir llamadas**.
    - Vaya a **Directivas** >  de **reunión de** reuniones y, a continuación, haga clic en **AllOff**.
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando termine de agregar usuarios, haga clic en **Guardar**.

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para asignar la `DisallowCalling` directiva de llamada a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de llamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la `AllOff` directiva de reunión a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar Teams en VDI con chat y colaboración para optimizar Teams con llamadas y reuniones

Si tiene una implementación existente de Teams en VDI con chat y colaboración en la que tenía establecidas directivas a nivel de usuario para desactivar las funciones de llamadas y reuniones, y está migrando a Teams con optimización de AV, debe establecer directivas para activar la funcionalidad de llamadas y reuniones para esos equipos en usuarios de VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Establecer directivas para activar la funcionalidad de llamadas y reuniones

Puede usar el Centro de administración de Teams o PowerShell para establecer y asignar directivas de llamadas y reuniones a los usuarios. Los cambios de directiva pueden tardar algún tiempo (algunas horas) en propagarse. Si no ves cambios en una cuenta determinada inmediatamente, inténtalo de nuevo después de unas horas.

[**Directivas de llamadas: las directivas**](teams-calling-policy.md) de llamadas de Teams controlan qué características de llamada están disponibles para los usuarios. Teams incluye la directiva de llamadas **AllowCalling** integrada, en la que todas las características de llamada están activadas. Para activar todas las características de llamada, asigne la directiva **AllowCalling** . O bien, cree una directiva de llamada personalizada para activar las características de llamada que desee y asignarla a los usuarios.

[**Directivas de reunión**](meeting-policies-overview.md): las directivas de reunión de Teams controlan los tipos de reuniones que los usuarios pueden crear y las características que están disponibles para los participantes de la reunión programadas por los usuarios de su organización. Teams incluye la directiva de reunión **AllOn** integrada, en la que todas las características de la reunión están activadas. Para activar todas las características de reunión, asigne la directiva **AllOn** . O bien, cree una directiva de reunión personalizada para activar las características de la reunión que desee y asignarla usuarios.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Asignar directivas mediante el Centro de administración de Teams

Para asignar la directiva **de llamada AllowCalling** y la directiva de reunión **AllOn** a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Usuarios**.
2. Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.
3. Haga lo siguiente:
    1. En **Directiva de llamadas**, haga clic en **Permitir llamada**.
    2. En **Directiva de reunión**, haga clic en **AllOn**.
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Usuarios** y busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en la **&#x2713;** (marca de verificación) de la parte superior de la tabla.
3. Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.

O bien, también puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a la directiva que quiera asignar. Por ejemplo:
    - Vaya a directivas de **llamadas** de **voz** >  y, a continuación, haga clic en **AllowCalling**.
    - Vaya a **Directivas** >  de **reunión de** reuniones y, a continuación, haga clic en **AllOn**.
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando termine de agregar usuarios, haga clic en **Guardar**.

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para asignar la `AllowCalling` directiva de llamada a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de llamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la `AllOn` directiva de reunión a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Control del modo de reserva en Teams

Cuando los usuarios se conectan desde un punto de conexión no compatible, los usuarios están en modo de reserva, en el que AV no está optimizado. Puede deshabilitar o habilitar el modo de reserva estableciendo uno de los siguientes valores del Registro `DWORD` :

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

Para deshabilitar el modo de reserva, establezca el valor en **1**. Para habilitar solo el audio, establezca el valor en **2**. Si el valor no está presente o está establecido en **0** (cero), se habilita el modo de reserva.

Esta característica está disponible en la versión 1.3.00.13565 y posteriores de Teams.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Deshabilitar la configuración de audio y vídeo para VDI

Las directivas de VDI de Teams están disponibles en el módulo Teams. Estas directivas están activas y se aplican en entornos VDI no optimizados.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> Esto es solo para entornos no optimizados.

### <a name="connect-to-microsoft-teams-powershell"></a>Conectarse a Microsoft Teams PowerShell

Siga las instrucciones [de Instalar el módulo de Microsoft Teams PowerShell](/Teams/teams-powershell-install.md) para conectarse al módulo de Microsoft Teams PowerShell. A continuación, ejecute el siguiente comando para confirmar que todos los cmdlets VDI están disponibles:

```PowerShell
Get-Command -Noun *VDI*
```

### <a name="set-policies-to-limit-calling-features"></a>Establecer directivas para limitar las características de llamada

Cuando los usuarios cuya directiva de VDI `DisableCallsAndMeetings` está configurada para `$true` iniciar sesión en Teams en VDI, no pueden:

- Hacer llamadas.
- Unirse a reuniones.
- Compartir pantalla desde el chat.

Se deben deshabilitar todos los tipos de llamadas.

> [!NOTE]
> Esto es solo para entornos no optimizados.

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

Cuando los usuarios cuya directiva de VDI `DisableAudioVideoInCallsAndMeetings` está configurada para `$true` iniciar sesión en Teams en VDI,:

- Puede compartir la pantalla desde el chat.
- Puede unirse a una reunión, compartir una pantalla y mover su audio a un teléfono.
- No se pueden realizar llamadas de audio y vídeo de persona a persona desde VDI.

> [!NOTE]
> Esto es solo para entornos no optimizados.

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>Problemas conocidos y limitaciones

### <a name="client-deployment-installation-and-setup"></a>Implementación, instalación y configuración de clientes

- Con la instalación por equipo, Teams en VDI no se actualiza automáticamente de la forma en que se actualizan los clientes que no son de VDI Teams. Tiene que actualizar la imagen de máquina virtual instalando un nuevo MSI, como se describe en la sección [Instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Debe desinstalar la versión actual para actualizar a una versión más reciente.
- En entornos Citrix, si el usuario se desconecta de la máquina virtual mientras se ejecuta Teams, las actualizaciones de Teams pueden provocar que el usuario se encuentre en un estado no optimizado para AV cuando vuelva a conectarse. Se recomienda que los usuarios salgan de Teams antes de desconectarse de Citrix Virtual Machine para evitar este escenario.
- Teams debe implementarse por usuario o por equipo. No se admite la implementación de Teams para cada usuario y equipo simultáneos. Para migrar desde cada equipo o por usuario a uno de estos modos, siga el procedimiento de desinstalación y vuelva a implementarlo a cualquier modo.
- Azure Virtual Desktop no admite clientes basados en Linux en este momento.
- El cambio rápido de inquilino puede provocar problemas relacionados con las llamadas en VDI, como el uso compartido de la pantalla, que no está disponible. Reiniciar el cliente mitigará estos problemas.

### <a name="notifications"></a>Notificaciones

- Las notificaciones y la presencia del recuento de mensajes en la barra de tareas de Windows no se admiten en un host de Windows Server 2016.

### <a name="calling-and-meetings"></a>Llamadas y reuniones

Las siguientes características de llamadas y reuniones no son compatibles:

- Botones HID y controles LED entre la aplicación teams y los dispositivos para Citrix y VMware
- Desenfoque de fondo y efectos para Citrix y VMware
- Roles de productor y moderador de eventos y difusión en directo
- Enrutamiento Location-Based (LBR)
- Tono de devolución de llamada RTC
- Sonido de audio/equipo compartido del sistema
- Desvío de medios para enrutamiento directo
- Control de zoom

> [!NOTE]
> Estamos trabajando para agregar características de llamadas y reuniones que actualmente solo están disponibles en entornos que no son de VDI. Pueden incluir más control de administración sobre la calidad, escenarios adicionales de uso compartido de la pantalla y características avanzadas agregadas recientemente a Teams. Póngase en contacto con su representante de Teams para obtener más información sobre las próximas características.

Los siguientes son problemas conocidos y limitaciones para las llamadas y reuniones:

- La interoperabilidad con Skype Empresarial se limita a las llamadas de audio; no hay ninguna modalidad de vídeo.
- La resolución de la transmisión de vídeo entrante y saliente está limitada a 720p de resolución.
- Teams no cambia a usar el último dispositivo de audio seleccionado por un usuario, si el dispositivo está desconectado y, a continuación, se vuelve a conectar.
- Los eventos en directo no están optimizados.
- Pantalla compartida saliente:
  - El uso compartido de aplicaciones no es compatible con VMware y AVD/W365.
- Ceder el control y tomar el control:
  - No se admite durante la sesión de uso compartido de aplicaciones.

Para ver los problemas conocidos de Teams que no están relacionados con VDI, consulte [Equipos de soporte técnico de su organización](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Solución de problemas

### <a name="troubleshoot-citrix-components"></a>Solución de problemas de componentes Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se bloquea o la pantalla de inicio de sesión de Teams está en blanco

Este es un problema conocido de las versiones 1906 y 1909 de Citrix VDA. Para solucionar este problema, agregue el siguiente valor del Registro `DWORD` y establézalo en `204` (hexadecimal).

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

A continuación, reinicie VDA. Para obtener más información, consulte este artículo de soporte técnico de Citrix, [Solución de problemas de optimización HDX para Microsoft Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Temas relacionados

- [Instalar teams en masa con Windows Installer (MSI)](msi-deployment.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Usar Microsoft Teams en Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd)
