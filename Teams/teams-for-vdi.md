---
title: Teams para la infraestructura de escritorio virtualizada
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Obtenga información sobre cómo ejecutar Microsoft Teams en un entorno de infraestructura de escritorio virtualizado (VDI).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8022e6b1c4d6ebcaeb70ec7cc23e1f4cad5d929a
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110293"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para la infraestructura de escritorio virtualizada

En este artículo se describen los requisitos y limitaciones para usar Microsoft Teams en un entorno virtualizado.

## <a name="what-is-vdi"></a>¿Qué es VDI?

Infraestructura de escritorio virtual (VDI) es tecnología de virtualización que hospeda un sistema operativo de escritorio y aplicaciones en un servidor centralizado en un centro de datos. Esto permite una experiencia de escritorio totalmente personalizada para los usuarios con un origen centralizado totalmente protegido y compatible.

Microsoft Teams en un entorno virtualizado admite chat y colaboración. Además, con las plataformas Windows Virtual Desktop, Citrix y VScale, también se admiten llamadas y reuniones.

Teams en un entorno virtualizado admite varias configuraciones. Entre ellos se incluyen los modos VDI, dedicado, compartido, persistente y no persistente. Las características están en desarrollo continuo y se agregan de forma periódica, y la funcionalidad se ampliará en los próximos meses y años.

El uso de Teams en un entorno virtualizado puede ser algo distinto del uso de Teams en un entorno no virtualizado. Por ejemplo, es posible que algunas características avanzadas no estén disponibles en un entorno virtualizado y que la resolución del vídeo sea diferente.

Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.

> [!Note]
> Para obtener más información sobre VDI de Teams en distintas plataformas, consulte [Características de Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Equipos en componentes de VDI

El uso de Teams en un entorno virtualizado requiere los siguientes componentes.

- **Agente de virtualización:** el administrador de recursos y conexiones al proveedor de virtualización, como Azure
- **Escritorio virtual:** pila de máquina virtual (VM) que ejecuta Microsoft Teams
- **Cliente ligero:** el punto de conexión con el que el usuario se interface físicamente
- **Aplicación de escritorio de Teams:** la aplicación de cliente de escritorio de Teams

## <a name="teams-on-vdi-requirements"></a>Requisitos de Teams en VDI

### <a name="virtualization-provider-requirements"></a>Requisitos del proveedor de virtualización

La aplicación de escritorio de Teams se validó con los principales proveedores de soluciones de virtualización. Con varios proveedores de mercado, le recomendamos que consulte con su proveedor de soluciones de virtualización para asegurarse de que cumple los requisitos mínimos.
  
Actualmente, Teams en VDI con optimización de audio/vídeo (AV) está certificado con Windows Virtual Desktop, Citrix y VVr. Revise la información de esta sección para asegurarse de que cumple todos los requisitos para una funcionalidad correcta.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para Teams

Las siguientes plataformas tienen soluciones de infraestructura de escritorio virtual para Teams.

|Plataforma|Solución|
|----|---|
|![Logotipo que representa a Microsoft](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Escritorio virtual de Windows</a> |
|![Logotipo que representa a Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Aplicaciones virtuales Citrix y escritorios</a> |
|![El logotipo que representa VWare](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VWare Horizon</a> |

### <a name="windows-virtual-desktop"></a>Escritorio virtual de Windows

El escritorio virtual de Windows proporciona optimización de AV para Teams en VDI. Para obtener más información sobre los requisitos y la instalación, [consulte Usar Teams en el escritorio virtual de Windows.](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos de aplicaciones virtuales y escritorios Citrix

Citrix Virtual Apps and Desktops (anteriormente conocido comoAvapp yDesktopDesktop) proporciona optimización de AV para Teams en VDI. Con las aplicaciones virtuales Citrix y los escritorios, Teams en VDI admite la funcionalidad de llamadas y reuniones, además del chat y la colaboración.

Puede descargar la última versión de las aplicaciones virtuales y equipos de escritorio Citrix en [el sitio de descargas Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Tendrá que iniciar sesión primero). Los componentes necesarios se incluyen en la aplicación [Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) y el Agente de entrega virtual (VDA) de forma predeterminada. No es necesario instalar ningún componente o complemento adicional en CWA o VDA.

Para ver los requisitos de cliente y servidor más recientes, consulte [este sitio web Citrix.](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos del área de trabajo y del escritorio de VWare Horizon

VWare Horizon es una plataforma moderna para la entrega segura de escritorios virtuales y aplicaciones en la nube híbrida. Para ofrecer una excelente experiencia al usuario final, V Horizon proporciona optimización de medios para Teams. Esta optimización mejora la productividad general en escritorios virtuales y aplicaciones, y mejora la experiencia del usuario al llamar y reunirse con Teams.

Puede descargar la versión más reciente de VWare Horizon desde la página [Descargas de VWare.](https://my.vmware.com/web/vmware/downloads/#all_products) Los componentes de optimización multimedia necesarios forman parte de Horizon Agent y Horizon Client de forma predeterminada y no es necesario instalar ningún complemento adicional para usar la característica de optimización de Teams.

Para obtener los requisitos e instrucciones más recientes sobre cómo configurar la optimización de medios para Teams, consulte [este sitio web de VWare.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar o actualizar la aplicación de escritorio de Teams en VDI

Puede implementar la aplicación de escritorio de Teams para VDI con una instalación por equipo o por usuario mediante el paquete MSI. Decidir qué enfoque usar depende de si usa una configuración persistente o no persistente y las necesidades de funcionalidad asociadas de su organización.

Para una configuración persistente dedicada, cualquiera de los enfoques funcionaría. Sin embargo, para una configuración no persistente, Teams requiere una instalación por equipo para poder trabajar de forma eficiente. Vea la [sección Configuración no persistente.](#non-persistent-setup)

Con la instalación por equipo, las actualizaciones automáticas están deshabilitadas. Esto significa que para actualizar la aplicación Teams, debe desinstalar la versión actual para actualizar a una versión más reciente. Con la instalación por usuario, las actualizaciones automáticas están habilitadas. Para la mayoría de las implementaciones de VDI, le recomendamos que implemente Teams con la instalación por equipo.

Para actualizar a la versión más reciente de Teams, empiece con el procedimiento de desinstalación seguido de la última implementación de la versión de Teams.

Para que la optimización de AV de Teams en entornos VDI funcione correctamente, el extremo cliente ligero debe tener acceso a Internet. Si el acceso a Internet no está disponible en el extremo del cliente ligero, el inicio de optimización no tendrá éxito. Esto significa que el usuario se encuentra en un estado multimedia no optimizado.

#### <a name="dedicated-persistent-setup"></a>Configuración persistente dedicada

En una configuración persistente dedicada, los cambios del sistema operativo local de los usuarios se conservan cuando los usuarios lo cierran. Para la configuración persistente, Teams admite tanto la instalación por usuario como por equipo.

A continuación se muestra la configuración mínima de máquina virtual recomendada.

|Parámetro  |Sistema operativo de la estación de trabajo  |Sistema operativo del servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4, 6 u 8<br>Es importante comprender la configuración subyacente de acceso a la memoria no uniforme (NUMA) y configurar las máquinas virtuales en consecuencia.     |
|RAM     |   4 GB      | De 512 a 1024 MB por usuario        |
|Almacenamiento    | 8 GB        | 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuración no persistente

En una configuración no persistente, los cambios del sistema operativo local de los usuarios no se conservan una vez que los usuarios lo cierran. Estas configuraciones son sesiones compartidas habitualmente de varios usuarios. La configuración de la máquina virtual varía según el número de usuarios y los recursos de caja físicos disponibles.

Para una configuración no persistente, la aplicación de escritorio de Teams debe instalarse por equipo en la imagen dorada. (Para obtener más información, consulte [Instalar o actualizar la aplicación de escritorio de Teams en la sección VDI).](#install-or-update-the-teams-desktop-app-on-vdi) Esto garantiza un inicio eficaz de la aplicación Teams durante una sesión de usuario.

El uso de Teams en una configuración no persistente también requiere un administrador de almacenamiento en caché de perfiles, para una sincronización eficiente de los datos en tiempo de ejecución de Teams. Una sincronización de datos eficiente garantiza que la información específica del usuario (como los datos, el perfil o la configuración de un usuario) se almacene en caché durante la sesión del usuario. Asegúrese de que los datos de estas dos carpetas están sincronizados:<br>
- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Usuarios\nombreusuario\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Se requiere una carpeta de itinerancia (o, si usa el redireccionamiento de carpetas, un administrador de almacenamiento en caché) para asegurarse de que la aplicación Teams tiene los datos y archivos en tiempo de ejecución necesarios para ejecutar la aplicación. Esto es necesario para mitigar problemas de latencia de red o fallos de red, lo que, de lo contrario, produciría errores en la aplicación y una experiencia lenta debido a archivos y datos no disponibles.

Hay una variedad de soluciones de administrador de almacenamiento en caché disponibles. Por ejemplo, [FSLogix](https://docs.microsoft.com/fslogix/overview). Consulte con su proveedor del administrador de almacenamiento en caché para obtener instrucciones de configuración específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Lista de exclusiones del contenido almacenado en caché de Teams para la configuración no persistente

Excluya lo siguiente de la carpeta de almacenamiento en caché de Teams, %appdata%/Microsoft/Teams. Excluir estos elementos ayuda a reducir el tamaño del almacenamiento en caché del usuario para optimizar aún más la configuración no persistente.

- Archivos .txt
- Carpeta De archivos multimedia
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Aplicaciones de Microsoft 365 para consideraciones empresariales

Tenga en cuenta lo siguiente al implementar Teams con aplicaciones de Microsoft 365 para empresas en VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nuevas implementaciones de Teams a través de las aplicaciones de Microsoft 365 para empresas

Antes de implementar Teams a través de aplicaciones de Microsoft 365 para empresas, primero debe desinstalar las aplicaciones de Teams existentes si se implementaron con la instalación por equipo.

Teams a través de las aplicaciones de Microsoft 365 para empresas se instala por usuario. Para obtener más información, consulte [instalar o actualizar la aplicación de escritorio de Teams en la sección VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Implementaciones de Teams a través de las aplicaciones de Microsoft 365 para actualizaciones empresariales

Teams también se está agregando a las instalaciones existentes de las aplicaciones de Microsoft 365 para empresas. Puesto que las aplicaciones de Microsoft 365 para empresas instala Teams solo por usuario, consulte la sección Instalar o actualizar la aplicación de escritorio de [Teams en la sección VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Usar Teams con instalación por equipo y aplicaciones de Microsoft 365 para empresas

Las aplicaciones de Microsoft 365 para empresas no son compatibles con las instalaciones por equipo de Teams. Para usar la instalación por equipo, debe excluir Teams de las aplicaciones de Microsoft 365 para empresas. Consulte implementar [la aplicación de escritorio de Teams en](#deploy-the-teams-desktop-app-to-the-vm) la máquina virtual y cómo excluir la implementación de Teams a través de las aplicaciones de Microsoft [365 para secciones](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) empresariales.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Cómo excluir la implementación de Teams a través de aplicaciones de Microsoft 365 para empresas

Para obtener más información sobre Teams y las aplicaciones de Microsoft 365 para empresas, consulte Cómo excluir Teams de las nuevas instalaciones de aplicaciones de [Microsoft 365](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) para empresas y Usar directiva de grupo para controlar la instalación de [Teams.](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implementar la aplicación de escritorio de Teams en la máquina virtual

1. Descargue el paquete MSI de Teams que coincida con su sistema operativo VDI VM mediante uno de los vínculos siguientes:

    - [Versión de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versión de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Para las nubes gubernamentales, vea [Instalar Microsoft Teams con Microsoft Endpoint Configuration Manager](msi-deployment.md) para ver los vínculos de descarga a los archivos MSI.

    La versión mínima de la aplicación de escritorio de Teams necesaria es la versión 1.3.00.4461. (La retención RTC no es compatible con versiones anteriores).

2. Instale el MSI en la máquina virtual VDI ejecutando uno de los siguientes comandos:

    - Instalación por usuario (predeterminado)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Este proceso es la instalación predeterminada, que instala Teams en la carpeta de usuario %AppData%. En este punto, se ha completado la configuración de la imagen dorada. Teams no funcionará correctamente con la instalación por usuario en una configuración no persistente.

    - Instalación por equipo

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Este proceso instala Teams en la carpeta Archivos de programa (x86) en un sistema operativo de 64 bits y en la carpeta Archivos de programa en un sistema operativo de 32 bits. En este punto, se ha completado la configuración de la imagen dorada. Para las configuraciones no persistentes es necesario instalar Teams por máquina.

        La siguiente sesión interactiva de inicio de sesión inicia Teams y le pide las credenciales.

        > [!NOTE]
        > En estos ejemplos también se usa **el parámetro ALLUSERS=1.** Cuando establece este parámetro, el Instalador Teams de todo el equipo aparece en Programas y características y en el Panel de control y en Aplicaciones y características en la Configuración de Windows para todos los usuarios del equipo. Todos los usuarios pueden desinstalar Teams si tienen credenciales de administrador.
        Es importante comprender la diferencia entre **ALLUSERS=1** y **ALLUSER=1.** El parámetro **ALLUSERS=1** se puede usar en entornos que no sean VDI y VDI, mientras que el parámetro **ALLUSER=1** solo se usa en entornos VDI para especificar una instalación por equipo.

3. Desinstale el MSI de la máquina virtual VDI. Hay dos formas de desinstalar Teams.

    - Script de PowerShell: Puede usar este script de [PowerShell](scripts/powershell-script-deployment-cleanup.md) para desinstalar Teams y quitar la carpeta Teams de un usuario. Ejecute el script para cada perfil de usuario en el que Teams se instaló en el equipo.
    - Línea de comandos: ejecute el comando siguiente.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Este proceso desinstala Teams de la carpeta Archivos de programa (x86) o de archivos de programa, según el entorno del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Consideraciones de rendimiento de Teams sobre VDI

Hay una amplia variedad de configuraciones de configuración virtualizadas, cada una con un enfoque diferente para la optimización. Por ejemplo, una configuración podría centrarse en la densidad del usuario. A la hora de planear, tenga en cuenta lo siguiente para optimizar la configuración en función de las necesidades de carga de trabajo de su organización.

- Requisito mínimo: algunas cargas de trabajo pueden requerir una configuración con recursos que están por encima de los requisitos mínimos. Por ejemplo, las cargas de trabajo para desarrolladores que usan aplicaciones que exigen más recursos informáticos.
- Dependencias: incluyen dependencias de la infraestructura, carga de trabajo y otras consideraciones medioambientales fuera de la aplicación de escritorio de Teams.
- Características deshabilitadas en VDI: Teams deshabilita las características de GPU intensivas para VDI, que pueden ayudar a mejorar la utilización de la CPU deshabilitada. Las siguientes características están deshabilitadas:
    - Animación CSS de Teams
    - Inicio automático de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams en VDI con llamadas y reuniones

Además del chat y la colaboración, Teams en VDI con llamadas y reuniones está disponible con plataformas de proveedor de virtualización compatibles. Las características compatibles se basan en la implementación de proveedores de virtualización y pila de medios WebRTC. El siguiente diagrama proporciona una descripción general de la arquitectura.

![Diagrama que muestra la arquitectura de Teams en VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si actualmente ejecuta Teams sin optimización de AV en VDI y usa características que no son compatibles todavía para la optimización (como Ceder y tomar el control al compartir aplicaciones), debe establecer directivas de proveedor de virtualización para desactivar el redireccionamiento de Teams. Esto significa que las sesiones multimedia de Teams no se optimizarán. Para obtener información sobre cómo establecer directivas para desactivar el redireccionamiento de Teams, póngase en contacto con su proveedor de virtualización.

### <a name="network-requirements"></a>Requisitos de red

Le recomendamos que evalúe su entorno para identificar los riesgos y requisitos que pueden influir en la implementación general de voz en la nube y vídeo. Use la Herramienta [de evaluación de la red de Skype Empresarial](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si su red está preparada para Teams.

Para obtener más información sobre cómo preparar su red para Teams, vea Preparar la [red de su organización para Teams.](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar de Skype Empresarial en VDI a Teams en VDI

Si está migrando de Skype Empresarial en VDI a Teams en VDI, además de las diferencias entre las dos aplicaciones, hay algunas diferencias cuando también se implementa VDI. Algunas funciones que actualmente no son compatibles con VDI de Teams que están en VDI para Skype Empresarial son las siguientes:

- Directiva por plataforma para deshabilitar algunas características de AV en VDI
- Ceder y tomar el control cuando se comparten aplicaciones
- Compartir pantalla desde un chat sin audio
- Envío y recepción de vídeo y pantalla compartida simultáneas

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams en el explorador Chrome y la aplicación de escritorio de Teams para VDI

Teams en el explorador Chrome no proporciona un reemplazo para la aplicación de escritorio de Teams para VDI con la optimización av. La experiencia de chat y colaboración funciona según lo esperado. Cuando se necesitan medios, hay algunas experiencias que es posible que no cumplan las expectativas del usuario en el explorador Chrome:

- Es posible que la experiencia de streaming de audio y vídeo no sea óptima. Los usuarios podrían estar experimentando retrasos o una calidad reducida.
- La configuración del dispositivo no está disponible en la configuración del explorador.
- La administración de dispositivos se controla a través del explorador y requiere varias configuraciones en la configuración del sitio del explorador.
- Es posible que la configuración del dispositivo también tenga que establecerse en la administración de dispositivos de Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams en VDI con chat y colaboración

Si su organización desea usar solo las características de chat y colaboración en Teams, puede establecer directivas a nivel de usuario para desactivar la funcionalidad de llamadas y reuniones en Teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Establecer directivas para desactivar la funcionalidad de llamadas y reuniones

Puede establecer directivas mediante el Centro de administración de Microsoft Teams o PowerShell. Es posible que los cambios de la directiva tarden algún tiempo (unas horas) en propagarse. Si no ve los cambios de una cuenta determinada inmediatamente, inténtelo de nuevo en unas horas.

[**Directivas de llamadas:**](teams-calling-policy.md)Teams incluye la directiva de llamadas DisallowCalling integrada, en la que todas las características de llamada están desactivadas. Asigne la directiva DisallowCalling a todos los usuarios de su organización que usan Teams en un entorno virtualizado.

[**Directivas de reunión:**](meeting-policies-in-teams.md)Teams incluye la directiva de reunión AllOff integrada, en la que todas las características de la reunión están desactivadas. Asigne la directiva AllOff a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas mediante el Centro de administración de Microsoft Teams

Para asignar la directiva de llamada DisallowCalling y la directiva de reunión AllOff a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios.**
2. Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.
3. Haga lo siguiente:
    1.  En **Directiva de llamada,** haga **clic en No permitir llamada.**
    2.  En **Directiva de reunión,** haga clic **en AllOff.**
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.
3. Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.

También puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la directiva que desea asignar. Por ejemplo:
    - Vaya a directivas  >  **de llamadas de** voz y, a continuación, haga clic en No permitir **llamada.**
    - Vaya a **Directivas de reuniones**  >  **y,** a continuación, haga clic en **AllOff.**
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, haga clic en **Guardar.**

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para asignar la directiva de llamada DisallowCalling a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para obtener más información sobre cómo usar PowerShell para administrar directivas de llamadas, consulte [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la directiva de reunión AllOff a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, vea [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar Teams en VDI con chat y colaboración para optimizar Teams con llamadas y reuniones

Si ya tiene una implementación de Teams en VDI con chat y colaboración en la que tenía establecidas directivas a nivel de usuario para desactivar la funcionalidad de llamadas y reuniones, y va a migrar a Teams con la optimización de AV, debe establecer directivas para activar la funcionalidad de llamadas y reuniones para los usuarios de Teams en VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Establecer directivas para activar la funcionalidad de llamadas y reuniones

Puede usar el Centro de administración de Microsoft Teams o PowerShell para establecer y asignar directivas de llamadas y reuniones a los usuarios. Los cambios de directiva pueden tardar algún tiempo (unas horas) en propagarse. Si no ve los cambios de una cuenta determinada inmediatamente, inténtelo de nuevo después de unas horas.

[**Directivas de llamadas: las**](teams-calling-policy.md)directivas de llamadas de Teams controlan qué características de llamadas están disponibles para los usuarios. Teams incluye la directiva de llamadas AllowCalling integrada, en la que todas las características de llamada están activadas. Para activar todas las características de llamada, asigne la directiva AllowCalling. O bien, cree una directiva de llamadas personalizada para activar las características de llamada que desee y asignarla a los usuarios. 

[**Directivas de reunión:**](meeting-policies-in-teams.md)las directivas de reuniones de Teams controlan los tipos de reuniones que los usuarios pueden crear y las características que están disponibles para los participantes de la reunión programadas por los usuarios de su organización. Teams incluye la directiva de reuniones AllOn integrada, en la que están activadas todas las características de la reunión. Para activar todas las características de la reunión, asigne la directiva AllOn. O bien, cree una directiva de reunión personalizada para activar las características de la reunión que desee y asignarles usuarios.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas mediante el Centro de administración de Microsoft Teams

Para asignar la directiva de llamada AllowCalling y la directiva de reunión AllOn a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios.**
2. Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.
3. Haga lo siguiente:
    1.  En **Directiva de llamada,** haga clic **en Permitir llamada.**
    2.  En **Directiva de reunión,** haga clic **en AllOn.**
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic **en&#x2713;** (marca de verificación) en la parte superior de la tabla.
3. Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.

También puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la directiva que desea asignar. Por ejemplo:
    - Vaya a directivas  >  **de llamadas de** voz y, a continuación, haga clic en Permitir **llamada.**
    - Vaya a **Directivas de reuniones**  >  **y,** a continuación, haga clic en **AllOn.**
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, haga clic en **Guardar.**

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para asignar la directiva de llamadas AllowCalling a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para obtener más información sobre cómo usar PowerShell para administrar directivas de llamadas, consulte [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la directiva de reunión AllOn a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, vea [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="control-fallback-mode-in-teams"></a>Controlar el modo de reserva en Teams

Cuando los usuarios se conectan desde un punto de conexión no compatible, los usuarios están en modo de reserva, en el que AV no está optimizado. Puede deshabilitar o habilitar el modo de reserva estableciendo uno de los siguientes valores DWORD del Registro:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Para deshabilitar el modo de reserva, establezca el valor en **1.** Para habilitar solo el audio, establezca el valor en **2.** Si el valor no está presente o se establece en **0** (cero), se habilita el modo de reserva.

Esta característica está disponible en Teams versión 1.3.00.13565 y posteriores.

## <a name="known-issues-and-limitations"></a>Problemas conocidos y limitaciones

### <a name="client-deployment-installation-and-setup"></a>Implementación, instalación y configuración de clientes

- Con la instalación por equipo, Teams en VDI no se actualiza automáticamente de la forma en que lo son los clientes de equipos que no son de VDI. Tiene que actualizar la imagen de máquina virtual mediante la instalación de un nuevo MSI como se describe en la sección Instalar o actualizar la aplicación de escritorio de [Teams en la sección VDI.](#install-or-update-the-teams-desktop-app-on-vdi) Debe desinstalar la versión actual para actualizar a una versión más reciente.
- Teams debe implementarse por usuario o equipo. No se admite la implementación de Teams para versiones simultáneas por usuario y equipo. Para migrar de uno de estos modos por equipo o por usuario, siga el procedimiento de desinstalación y vuelva a implementarlo a ambos modos.
- El escritorio virtual de Windows y VMay no admiten clientes basados en MacOS y Linux en este momento.
- Citrix no es compatible con clientes MacOs en este momento.
- Citrix no admite el uso de servidores proxy HTTP explícitos definidos en un punto de conexión.

### <a name="calling-and-meetings"></a>Llamadas y reuniones

No se admiten las siguientes características de llamadas y reuniones:

- Cualquier funcionalidad de varias ventanas, como las nuevas experiencias de reunión o cualquier funcionalidad que se incluye con la nueva experiencia de reunión
- Servicios de emergencia mejorados
- Botones HID y controles LED entre la aplicación Teams y los dispositivos
- Efectos y desenfoque del fondo
- Roles de productor y moderador de eventos en directo y difusión
- Location-Based de enrutamiento de red (LBR)
- Estacionar llamada
- Cola de llamadas
- Sonido del sistema compartido/equipo
- Desvío de medios para enrutamiento directo

> [!NOTE]
> Estamos trabajando para agregar características de llamadas y reuniones que actualmente solo están disponibles en entornos que no son VDI. Pueden incluir más control de administración sobre la calidad, escenarios adicionales de pantalla compartida y características avanzadas agregadas recientemente a Teams. Póngase en contacto con su representante de Teams para obtener más información sobre las próximas características.

Los siguientes son problemas conocidos y limitaciones para las llamadas y reuniones:

- La interoperabilidad con Skype Empresarial se limita a las llamadas de audio; no hay ninguna modalidad de vídeo.
- Solo se admite una única secuencia de vídeo entrante en reuniones o llamadas grupales. Cuando varias personas envían vídeo, solo se muestra el vídeo del orador dominante en un momento determinado.
- La resolución de las transmisiones de vídeo entrantes y salientes está limitada a una resolución de 720p. Esta es una limitación de WebRTC.
- Solo se admite una secuencia de vídeo de una cámara entrante o de compartir pantalla. Cuando hay un uso compartido de pantalla entrante, se muestra ese uso compartido de pantalla, en lugar del vídeo del altavoz dominante.
- Teams no cambia a usar el último dispositivo de audio que ha seleccionado un usuario, si el dispositivo está desconectado y, a continuación, se vuelve a conectar.
- Pantalla compartida saliente:
    - El uso compartido de aplicaciones no es compatible.
- Ceder el control y tomar el control:
    - No se admite durante una sesión de uso compartido de aplicaciones o pantalla compartida.
    - Compatible durante una sesión de uso compartido de PowerPoint.
- Limitaciones solo de Citrix
    - Cuando se comparte la pantalla en una configuración de varios monitores, solo se comparte el monitor principal.
    - No se admite el escalado alto de PPP en CWA.

Para ver los problemas conocidos de Teams que no están relacionados con VDI, consulte Equipos [de soporte técnico de su organización.](Known-issues.md)

## <a name="troubleshooting"></a>Solución de problemas

### <a name="troubleshoot-citrix-components"></a>Solucionar problemas de componentes Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se bloquea o la pantalla de inicio de sesión de Teams está en blanco

Este es un problema conocido con las versiones 1906 y 1909 de Citrix VDA. Para evitar este problema, agregue el siguiente valor DWORD del Registro y estadúzcalo en 204 (hexadecimal).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

A continuación, reinicia VDA. Para obtener más información, consulte este artículo de soporte técnico de Citrix, [solución de problemas de optimización HDX para Teams.](https://support.citrix.com/article/CTX253754)

## <a name="related-topics"></a>Temas relacionados

- [Instalar Microsoft Teams con MSI](msi-deployment.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Usar Microsoft Teams en el escritorio virtual de Windows](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
