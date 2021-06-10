---
title: Teams para la infraestructura de escritorio virtualizada
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Obtenga información sobre cómo ejecutar Microsoft Teams en un entorno de infraestructura de escritorio virtualizada (VDI).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39150cc5ff6a64c17bad660b4df4b74610399cd1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717741"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para la infraestructura de escritorio virtualizada

En este artículo se describen los requisitos y limitaciones para usar Microsoft Teams en un entorno virtualizado.

## <a name="what-is-vdi"></a>¿Qué es VDI?

Infraestructura de escritorio virtual (VDI) es una tecnología de virtualización que hospeda un sistema operativo de escritorio y aplicaciones en un servidor centralizado en un centro de datos. Esto permite una experiencia de escritorio totalmente personalizada para los usuarios con un origen centralizado totalmente protegido y compatible.

Microsoft Teams en un entorno virtualizado admite chat y colaboración. Además, con las Windows escritorio virtual, Citrix y VMware, también se admite la funcionalidad de llamadas y reuniones.

Teams en un entorno virtualizado admite varias configuraciones. Estos incluyen modos VDI, dedicado, compartido, persistente y no persistente. Las características están en desarrollo continuo y se agregan de forma periódica, y la funcionalidad se expandirá en los próximos meses y años.

Usar Teams en un entorno virtualizado puede ser algo diferente del uso de Teams en un entorno no virtualizado. Por ejemplo, es posible que algunas características avanzadas no estén disponibles en un entorno virtualizado y que la resolución de vídeo sea diferente.

Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.

> [!Note]
> Para obtener más información sobre Teams VDI en diferentes plataformas, [vea Teams características por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams componentes de VDI

El Teams en un entorno virtualizado requiere los siguientes componentes.

- **Agente de virtualización:** el administrador de recursos y conexiones del proveedor de virtualización, como Azure
- **Escritorio virtual:** la pila de máquina virtual (VM) que se ejecuta Microsoft Teams
- **Cliente ligero:** el punto de conexión con el que el usuario se interfaz físicamente
- **Teams de escritorio:** la Teams cliente de escritorio

## <a name="teams-on-vdi-requirements"></a>Teams requisitos de VDI

### <a name="virtualization-provider-requirements"></a>Requisitos del proveedor de virtualización

La Teams de escritorio se validó con los principales proveedores de soluciones de virtualización. Con varios proveedores de mercado, le recomendamos que consulte a su proveedor de soluciones de virtualización para asegurarse de que cumple los requisitos mínimos.
  
Actualmente, Teams en VDI con optimización de audio/vídeo (AV) está certificado con Windows escritorio virtual, Citrix y VMware. Revise la información de esta sección para asegurarse de que cumple todos los requisitos para la funcionalidad adecuada.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para Teams

Las siguientes plataformas tienen soluciones de infraestructura de escritorio virtual para Teams.

|Plataforma|Solución|
|----|---|
|![El logotipo que representa a Microsoft](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Escritorio virtual</a> |
|![El logotipo que representa Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Aplicaciones virtuales y equipos de escritorio de Citrix</a> |
|![El logotipo que representa VMware](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Windows Escritorio virtual

Windows Escritorio virtual proporciona optimización AV para Teams en VDI. Para obtener más información sobre los requisitos y la instalación, [vea Usar Teams en Windows escritorio virtual.](/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos de Citrix Virtual Apps y Escritorios

Citrix Virtual Apps and Desktops (anteriormente conocido como XenApp y XenDesktop) proporciona optimización av para Teams en VDI. Con Citrix Virtual Apps y Desktops, Teams en VDI admite la funcionalidad de llamadas y reuniones, además de chat y colaboración.

Puede descargar la versión más reciente de Citrix Virtual Apps and Desktops en [el sitio de descargas de Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Primero tendrá que iniciar sesión). Los componentes necesarios se agrupan en la aplicación [Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) y el Agente de entrega virtual (VDA) de forma predeterminada. No es necesario instalar componentes o complementos adicionales en CWA o en el VDA.

Para obtener los requisitos de cliente y servidor más recientes, [consulte este sitio web de Citrix.](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos de escritorio y área de trabajo de VMware Horizon

VMware Horizon es una plataforma moderna para la entrega segura de escritorios virtuales y aplicaciones en toda la nube híbrida. Para ofrecer una gran experiencia de usuario final, VMware Horizon proporciona optimización de medios para Teams. Esta optimización mejora la productividad general en escritorios y aplicaciones virtuales, y mejora la experiencia del usuario al llamar y reunirse con Teams.

Puede descargar la versión más reciente de VMware Horizon desde la [página Descargas de VMware.](https://my.vmware.com/web/vmware/downloads/#all_products) Los componentes de optimización multimedia necesarios forman parte de Horizon Agent y Horizon Client de forma predeterminada y no es necesario instalar ningún complemento adicional para usar la característica de optimización para Teams.

Para obtener los requisitos e instrucciones más recientes sobre cómo configurar la optimización de medios para Teams, vea [este sitio web de VMware.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar o actualizar la Teams de escritorio en VDI

Puede implementar la aplicación Teams escritorio para VDI con una instalación por equipo o una instalación por usuario con el paquete MSI. Decidir qué enfoque usar depende de si usa una configuración persistente o no persistente y las necesidades de funcionalidad asociadas de su organización.

Para una configuración persistente dedicada, cualquiera de los dos métodos funcionaría. Sin embargo, para una configuración no persistente, Teams requiere una instalación por equipo para poder funcionar de forma eficiente. Vea la [sección Configuración no persistente.](#non-persistent-setup)

Con la instalación por equipo, las actualizaciones automáticas están deshabilitadas. Esto significa que para actualizar la aplicación Teams, debe desinstalar la versión actual para actualizar a una versión más reciente. Con la instalación por usuario, las actualizaciones automáticas están habilitadas. Para la mayoría de las implementaciones de VDI, le recomendamos que implemente Teams mediante la instalación por equipo.

Para actualizar a la versión Teams, empiece con el procedimiento de desinstalación seguido de la implementación Teams versión.

Para Teams av en entornos VDI funcione correctamente, el punto de conexión de cliente ligero debe tener acceso a Internet. Si el acceso a Internet no está disponible en el punto de conexión de cliente ligero, el inicio de optimización no se realiza correctamente. Esto significa que el usuario se encuentra en un estado multimedia no optimizado.

#### <a name="dedicated-persistent-setup"></a>Configuración persistente dedicada

En una configuración persistente dedicada, los cambios del sistema operativo local de los usuarios se conservan después de que los usuarios cierren sesión. Para la configuración persistente, Teams es compatible con la instalación por usuario y por equipo.

A continuación se muestra la configuración mínima de vm recomendada.

|Parámetro  |Sistema operativo de estaciones de trabajo  |Sistema operativo del servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4,6 u 8<br>Es importante comprender la configuración subyacente de acceso a memoria no uniforme (NUMA) y configurar las máquinas virtuales en consecuencia.     |
|RAM     |   4 GB      | De 512 a 1024 MB por usuario        |
|Almacenamiento    | 8 GB        | De 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuración no persistente

En una configuración no persistente, los cambios del sistema operativo local de los usuarios no se conservan después de que los usuarios cierren sesión. Estas configuraciones son sesiones compartidas de varios usuarios. La configuración de la máquina virtual varía según el número de usuarios y los recursos de cuadro físico disponibles.

Para una configuración no persistente, la Teams de escritorio debe instalarse por equipo en la imagen dorada. (Para obtener más información, vea la sección Instalar o actualizar Teams [aplicación de escritorio en VDI).](#install-or-update-the-teams-desktop-app-on-vdi) Esto garantiza un inicio eficaz de la aplicación Teams durante una sesión de usuario.

Usar Teams en una configuración no persistente también requiere un administrador de almacenamiento en caché de perfiles, para una sincronización de datos eficaz Teams tiempo de ejecución. La sincronización eficiente de datos garantiza que la información específica del usuario adecuada (como los datos, el perfil o la configuración de un usuario) se almacena en caché durante la sesión del usuario. Asegúrese de que los datos de estas dos carpetas están sincronizados:<br>
- C:\Usuarios\nombreusuario\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Usuarios\nombreusuario\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Se requiere una carpeta itinerante (o, si usa el redireccionamiento de carpetas, un administrador de almacenamiento en caché) para asegurarse de que la aplicación Teams tiene los datos y archivos en tiempo de ejecución necesarios para ejecutar la aplicación. Esto es necesario para mitigar problemas de latencia de red o problemas de red, lo que de lo contrario causaría errores de aplicación y una experiencia lenta debido a datos y archivos no disponibles.

Hay una variedad de soluciones de administrador de almacenamiento en caché disponibles. Por ejemplo, [FSLogix](/fslogix/overview). Consulte a su proveedor de administrador de almacenamiento en caché para obtener instrucciones de configuración específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams lista de exclusión de contenido en caché para la configuración no persistente

Excluya lo siguiente de Teams carpeta de almacenamiento en caché, %appdata%/Microsoft/Teams. Excluir estos elementos ayuda a reducir el tamaño del almacenamiento en caché del usuario para optimizar aún más la configuración no persistente.

- .txt archivos
- Carpeta De pila de medios
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Aplicaciones Microsoft 365 para empresas consideraciones

Tenga en cuenta lo siguiente al implementar Teams con Aplicaciones Microsoft 365 para empresas en VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nuevas implementaciones de Teams Aplicaciones Microsoft 365 para empresas

Antes de implementar Teams a través de Aplicaciones Microsoft 365 para empresas, primero debe desinstalar las aplicaciones Teams existentes si se implementaron con la instalación por equipo.

Teams a Aplicaciones Microsoft 365 para empresas se instala por usuario. Para obtener más información, vea la sección Instalar o actualizar Teams [aplicación de escritorio en VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams a través de Aplicaciones Microsoft 365 para empresas actualizaciones

Teams también se está agregando a las instalaciones existentes de Aplicaciones Microsoft 365 para empresas. Puesto que Aplicaciones Microsoft 365 para empresas instala Teams por usuario, vea la sección Instalar o actualizar la aplicación de escritorio Teams [en VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Usar Teams con instalación por equipo y Aplicaciones Microsoft 365 para empresas

Aplicaciones Microsoft 365 para empresas no admite las instalaciones por equipo de Teams. Para usar la instalación por equipo, debe excluir Teams de Aplicaciones Microsoft 365 para empresas. Consulte Implementar [la aplicación Teams escritorio](#deploy-the-teams-desktop-app-to-the-vm) en la máquina virtual y Cómo excluir Teams implementación mediante [Aplicaciones Microsoft 365 para empresas](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) secciones.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Cómo excluir la Teams a través de Aplicaciones Microsoft 365 para empresas

Para obtener más información sobre Teams y Aplicaciones Microsoft 365 para empresas, vea Cómo excluir Teams de las nuevas instalaciones de [Aplicaciones Microsoft 365 para empresas](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) y Usar directiva de grupo para controlar la instalación de [Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implementar la Teams de escritorio en la máquina virtual

1. Descargue el Teams MSI que coincida con su sistema operativo VDI VM con uno de los vínculos siguientes:

    - [Versión de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versión de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Para las nubes gubernamentales, [vea Instalar Microsoft Teams usar Microsoft Endpoint Configuration Manager](msi-deployment.md) para los vínculos de descarga a los archivos MSI.

    La versión mínima de la Teams de escritorio necesaria es la 1.3.00.4461. (La retención RTC no es compatible con versiones anteriores).

2. Instale msi en la máquina virtual VDI ejecutando uno de los siguientes comandos:

    - Instalación por usuario (predeterminada)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Este proceso es la instalación predeterminada, que se instala Teams la carpeta de usuario %AppData%. En este punto, se ha completado la configuración de la imagen dorada. Teams no funcionará correctamente con la instalación por usuario en una configuración no persistente.

    - Instalación por equipo

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```
        Este proceso agrega una clave de registro necesaria al equipo que permite al Teams de instalación saber que es una instancia de VDI.  Sin él, se producirá un error en el instalador, que indica: "Se ha producido un error en la instalación.  No se puede instalar para todos los usuarios cuando no se detecta un entorno VDI".

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Este proceso se instala Teams la carpeta Archivos de programa (x86) en un sistema operativo de 64 bits y en la carpeta Archivos de programa en un sistema operativo de 32 bits. En este punto, se ha completado la configuración de la imagen dorada. La Teams por equipo es necesaria para las configuraciones no persistentes.

        La siguiente sesión interactiva de inicio de sesión Teams y pide credenciales.

        > [!NOTE]
        > Estos ejemplos también usan el **parámetro ALLUSERS=1.** Cuando establece este parámetro, el Instalador Teams de todo el equipo aparece en Programas y características y en el Panel de control y en Aplicaciones y características en la Configuración de Windows para todos los usuarios del equipo. Todos los usuarios pueden desinstalar Teams si tienen credenciales de administrador.
        Es importante comprender la diferencia entre **ALLUSERS=1** y **ALLUSER=1**. El parámetro **ALLUSERS=1** se puede usar en entornos no VDI y VDI, mientras que el parámetro **ALLUSER=1** solo se usa en entornos VDI para especificar una instalación por equipo.

3. Desinstale el MSI de la máquina virtual VDI. Hay dos formas de desinstalar Teams.

    - Script de PowerShell: puede usar este script de [PowerShell](scripts/powershell-script-deployment-cleanup.md) para desinstalar Teams y quitar la carpeta Teams para un usuario. Ejecute el script de cada perfil de usuario en el que Teams se instaló en el equipo.
    - Línea de comandos: ejecute el siguiente comando.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Este proceso desinstala Teams de la carpeta Archivos de programa (x86) o archivos de programa, según el entorno del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Teams consideraciones de rendimiento de VDI

Hay una variedad de configuraciones de configuración virtualizadas, cada una con un enfoque diferente para la optimización. Por ejemplo, una configuración puede centrarse en la densidad de usuarios. Al planear, tenga en cuenta lo siguiente para ayudar a optimizar la configuración en función de las necesidades de carga de trabajo de su organización.

- Requisito mínimo: Es posible que algunas cargas de trabajo requieran una configuración con recursos superiores a los requisitos mínimos. Por ejemplo, cargas de trabajo para desarrolladores que usan aplicaciones que demandan más recursos informáticos.
- Dependencias: incluyen dependencias de infraestructura, carga de trabajo y otras consideraciones ambientales fuera de Teams aplicación de escritorio.
- Características deshabilitadas en VDI: Teams deshabilita las características de uso intensivo de GPU para VDI, lo que puede ayudar a mejorar el uso transitorio de la CPU. Las siguientes características están deshabilitadas:
    - Teams Animación CSS
    - Inicio automático de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams en VDI con llamadas y reuniones

Además del chat y la colaboración, Teams en VDI con llamadas y reuniones está disponible con plataformas de proveedores de virtualización compatibles. Las características compatibles se basan en la implementación del proveedor de virtualización y la pila de medios webRTC. El siguiente diagrama proporciona información general sobre la arquitectura.

![Diagrama que muestra Teams arquitectura VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si actualmente ejecuta Teams sin optimización AV en VDI y usa características que aún no son compatibles con la optimización (como Ceder y tomar el control al compartir aplicaciones), debe establecer directivas de proveedor de virtualización para desactivar Teams redireccionamiento. Esto significa que las Teams multimedia no se optimizarán. Para obtener instrucciones sobre cómo establecer directivas para desactivar Teams, póngase en contacto con su proveedor de virtualización.

### <a name="network-requirements"></a>Requisitos de red

Le recomendamos que evalúe su entorno para identificar los riesgos y requisitos que puedan influir en la implementación general de voz y vídeo en la nube. Use la Skype Empresarial de evaluación [de red](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si su red está lista para Teams.

Para obtener más información sobre cómo preparar la red para Teams, vea Preparar la red de su organización [para Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar de Skype Empresarial en VDI a Teams en VDI

Si va a migrar de Skype Empresarial en VDI a Teams en VDI, además de las diferencias entre las dos aplicaciones, hay algunas diferencias cuando también se implementa VDI. Algunas funcionalidades que actualmente no son compatibles con Teams VDI que se encuentran en Skype Empresarial VDI son las siguientes:

- Directiva por plataforma para deshabilitar algunas características av en VDI
- Ceder y tomar el control al compartir aplicaciones
- Compartir pantalla desde un chat sin audio
- Vídeo y pantalla compartida simultánea enviar y recibir

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams explorador Chrome frente Teams aplicación de escritorio para VDI

Teams en el explorador Chrome no proporciona un reemplazo para la aplicación de escritorio Teams para VDI con optimización av. La experiencia de chat y colaboración funciona según lo esperado. Cuando se necesitan medios, hay algunas experiencias que podrían no cumplir las expectativas de los usuarios en el explorador Chrome:

- Es posible que la experiencia de streaming de audio y vídeo no sea óptima. Los usuarios pueden tener retrasos o una calidad reducida.
- La configuración del dispositivo no está disponible en la configuración del explorador.
- La administración de dispositivos se administra a través del explorador y requiere varias configuraciones en la configuración del sitio del explorador.
- Es posible que también sea necesario establecer la configuración del dispositivo Windows administración de dispositivos.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams en VDI con chat y colaboración

Si su organización solo desea usar las características de chat y colaboración en Teams, puede establecer directivas de nivel de usuario para desactivar la funcionalidad de llamadas y reuniones en Teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Establecer directivas para desactivar la funcionalidad de llamadas y reuniones

Puede establecer directivas mediante el centro Microsoft Teams de administración o PowerShell. Los cambios de directiva pueden tardar algún tiempo (unas horas) en propagarse. Si no ve cambios para una cuenta determinada inmediatamente, inténtelo de nuevo en unas horas.

[**Directivas de llamadas:**](teams-calling-policy.md)Teams incluye la directiva de llamadas Desautorizado integrada, en la que todas las características de llamadas están desactivadas. Asigne la directiva DisallowCalling a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

[**Directivas de**](meeting-policies-in-teams.md)reunión: Teams incluye la directiva de reunión de AllOff integrada, en la que todas las características de la reunión están desactivadas. Asigne la directiva AllOff a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas con el Centro Microsoft Teams administración

Para asignar la directiva de llamadas Desautorizado y la directiva de reunión AllOff a un usuario:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Usuarios.**
2. Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.
3. Haga lo siguiente:
    1.  En **Directiva de llamadas,** haga clic **en No permitir la llamada.**
    2.  En **Directiva de reunión,** haga clic **en AllOff**.
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.
3. Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.

También puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a la directiva que desea asignar. Por ejemplo:
    - Vaya a **Directivas de llamadas**  >  **de** voz y, a continuación, haga clic **en No permitir la llamada.**
    - Vaya a **Directivas de reunión de**  >  **reuniones** y, a continuación, haga clic **en AllOff**.
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, haga clic en **Guardar.**

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para asignar la directiva de llamadas Desautor a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de llamadas, vea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la directiva de reunión AllOff a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, vea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar Teams en VDI con chat y colaboración para optimizar Teams con llamadas y reuniones

Si tiene una implementación existente de Teams en VDI con chat y colaboración en la que había establecido directivas de nivel de usuario para desactivar la funcionalidad de llamadas y reuniones, y está migrando a Teams con optimización av, debe establecer directivas para activar la funcionalidad de llamadas y reuniones para los usuarios de Teams en VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Establecer directivas para activar la funcionalidad de llamadas y reuniones

Puede usar el centro de Microsoft Teams o PowerShell para establecer y asignar directivas de llamadas y reuniones a los usuarios. Los cambios de directiva pueden tardar algún tiempo (unas horas) en propagarse. Si no ve cambios para una cuenta determinada inmediatamente, vuelva a intentarlo después de unas horas.

[**Directivas de llamadas:**](teams-calling-policy.md)las directivas de llamadas Teams controlar qué características de llamadas están disponibles para los usuarios. Teams incluye la directiva de llamadas AllowCalling integrada, en la que todas las características de llamadas están activadas. Para activar todas las características de llamadas, asigne la directiva AllowCalling. O bien, cree una directiva de llamadas personalizada para activar las características de llamada que desee y asígnela a los usuarios. 

[**Directivas de**](meeting-policies-in-teams.md)reunión: las directivas de reunión de Teams controlan los tipos de reuniones que los usuarios pueden crear y las características que están disponibles para los participantes de la reunión programadas por los usuarios de su organización. Teams incluye la directiva de reunión de AllOn integrada, en la que todas las características de la reunión están activadas. Para activar todas las características de la reunión, asigne la directiva AllOn. O bien, cree una directiva de reunión personalizada para activar las características de la reunión que desee y asígnele usuarios.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas con el Centro Microsoft Teams administración

Para asignar la directiva de llamadas AllowCalling y la directiva de reunión AllOn a un usuario:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Usuarios.**
2. Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.
3. Haga lo siguiente:
    1.  En **Directiva de llamadas,** haga clic **en Permitir llamada.**
    2.  En **Directiva de reunión,** haga clic **en AllOn**.
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, **haga clic&#x2713;** (marca de verificación) en la parte superior de la tabla.
3. Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.

También puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a la directiva que desea asignar. Por ejemplo:
    - Vaya a **Directivas de llamadas**  >  **de** voz y, a continuación, haga clic en Permitir **llamada.**
    - Vaya a **Directivas de reunión de** reuniones  >  **y,** a continuación, haga clic en **AllOn**.
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, haga clic en **Guardar.**

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para asignar la directiva de llamadas AllowCalling a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de llamadas, vea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la directiva de reunión AllOn a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, vea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Controlar el modo de reserva en Teams

Cuando los usuarios se conectan desde un punto de conexión no compatible, los usuarios están en modo de reserva, en el que AV no está optimizado. Puede deshabilitar o habilitar el modo de reserva estableciendo uno de los siguientes valores DWORD del Registro:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Para deshabilitar el modo de reserva, establezca el valor en **1**. Para habilitar solo el audio, establezca el valor en **2**. Si el valor no está presente o se establece en **0** (cero), el modo de reserva está habilitado.

Esta característica está disponible en Teams versión 1.3.00.13565 y posteriores.

## <a name="known-issues-and-limitations"></a>Problemas y limitaciones conocidos

### <a name="client-deployment-installation-and-setup"></a>Implementación, instalación y configuración del cliente

- Con la instalación por equipo, Teams en VDI no se actualiza automáticamente de la forma en que no son clientes Teams VDI. Tiene que actualizar la imagen de la máquina virtual instalando un nuevo MSI como se describe en la sección Instalar o actualizar la aplicación de escritorio Teams [en VDI.](#install-or-update-the-teams-desktop-app-on-vdi) Debe desinstalar la versión actual para actualizar a una versión más reciente.
- En entornos Citrix, si el usuario se desconecta de la máquina virtual mientras Teams se está ejecutando, las actualizaciones de Teams pueden hacer que el usuario esté en un estado no optimizado para AV cuando se vuelva a conectar. Se recomienda a los usuarios que Teams antes de desconectarse de Citrix Virtual Machine para evitar este escenario.
- Teams debe implementarse por usuario o por equipo. No se Teams la implementación de Teams por usuario y por equipo. Para migrar de una máquina o de un usuario a uno de estos modos, siga el procedimiento de desinstalación y vuelva a implementarlo en ambos modos.
- Windows El escritorio virtual no es compatible con macOS y clientes basados en Linux en este momento.

### <a name="calling-and-meetings"></a>Llamadas y reuniones

Las siguientes características de llamadas y reuniones no son compatibles:

- Cualquier funcionalidad de varias ventanas, como las nuevas experiencias de reunión o cualquier funcionalidad que viene con la nueva experiencia de reunión
- Servicios de emergencia mejorados
- Botones HID y controles LED entre la Teams y los dispositivos
- Efectos y desenfoque de fondo
- Roles de productor y moderador de eventos en directo y de difusión
- Location-Based enrutamiento (LBR)
- Estacionar llamada
- Sonido del equipo/audio del sistema compartido
- Desvío de medios para enrutamiento directo
- Control de zoom 

> [!NOTE]
> Estamos trabajando en agregar características de llamadas y reuniones que actualmente solo están disponibles en entornos que no son VDI. Esto puede incluir más control de administración sobre la calidad, escenarios de uso compartido de pantalla adicionales y características avanzadas agregadas recientemente a Teams. Póngase en contacto Teams representante para obtener más información sobre las próximas características.

Los siguientes son problemas conocidos y limitaciones para llamadas y reuniones:

- La interoperabilidad con Skype Empresarial está limitada a las llamadas de audio; no hay ninguna modalidad de vídeo.
- La resolución de transmisión de vídeo entrante y saliente está limitada a una resolución de 720p.
- Solo se admite una transmisión de vídeo desde una cámara entrante o una transmisión de pantalla compartido. Cuando hay un recurso compartido de pantalla entrante, se muestra ese recurso compartido de pantalla, en lugar del vídeo del orador dominante.
- Teams no cambia a usar el último dispositivo de audio que seleccionó un usuario, si el dispositivo está desconectado y, después, se vuelve a conectar.
- Uso compartido de pantalla saliente:
    - El uso compartido de aplicaciones no es compatible.
- Dar control y tomar el control:
    - No se admite durante una sesión de uso compartido de pantalla o de uso compartido de aplicaciones.
    - Compatible durante una sesión PowerPoint de uso compartido.
- Limitaciones de Solo Citrix
    - Cuando se comparte la pantalla en una configuración de varios monitores, solo se comparte el monitor principal.
    - No se admite el escalado alto de PPP en CWA.

Para Teams problemas conocidos que no están relacionados con VDI, vea Soporte [técnico Teams su organización.](/MicrosoftTeams/troubleshoot/teams-welcome)

## <a name="troubleshooting"></a>Solución de problemas

### <a name="troubleshoot-citrix-components"></a>Solucionar problemas de componentes de Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se bloquea o la Teams de inicio de sesión está en blanco

Este es un problema conocido con las versiones 1906 y 1909 de Citrix VDA. Para evitar este problema, agregue el siguiente valor DWORD del registro y establezca el valor en 204 (hexadecimal).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

A continuación, reinicie VDA. Para obtener más información, vea este artículo de soporte técnico de Citrix, Solución de problemas de optimización [HDX para Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Temas relacionados

- [Instalar Microsoft Teams con MSI](msi-deployment.md)
- [Información general de PowerShell para Teams](teams-powershell-overview.md)
- [Usar Microsoft Teams en Windows escritorio virtual](/azure/virtual-desktop/teams-on-wvd)
