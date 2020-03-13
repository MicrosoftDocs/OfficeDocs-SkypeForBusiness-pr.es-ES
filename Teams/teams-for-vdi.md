---
title: Teams para la infraestructura de escritorio virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Aprenda a ejecutar Microsoft Teams en un entorno de infraestructura de escritorio virtual (VDI).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e009ccfb70e307e4a67f8331deabce51e229c0f
ms.sourcegitcommit: 511238a3550ad0ff8d4bbd4600a252651ab6a654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42615372"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para la infraestructura de escritorio virtualizada

En este artículo se describen los requisitos y las limitaciones para usar Microsoft Teams en un entorno virtualizado.

## <a name="what-is-vdi"></a>¿Qué es VDI?

La infraestructura de escritorio virtual (VDI) es una tecnología de virtualización que hospeda un sistema operativo de escritorio y aplicaciones en un servidor centralizado en un centro de datos. Esto permite una experiencia de escritorio totalmente personalizada para los usuarios con un origen centralizado totalmente seguro y compatible.
 
Microsoft Teams en un entorno virtualizado admite chat y colaboración, y con la plataforma Citrix, también se admiten las funciones de llamada y reunión.

Los equipos de un entorno virtualizado admiten varias configuraciones. Esto incluye VDI, modos dedicados, compartidos, persistentes y no persistentes. Las características están en desarrollo continuo y se agregan con regularidad, y la funcionalidad se expandirá en los próximos meses y años.
 
El uso de Teams en un entorno virtualizado puede variar ligeramente de la utilización de Teams en un entorno no virtualizado. Por ejemplo, es posible que algunas características avanzadas no estén disponibles en un entorno virtualizado y que la resolución de video sea distinta. Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.

## <a name="teams-on-vdi-components"></a>Teams en componentes de VDI

El uso de Teams en un entorno virtualizado requiere los siguientes componentes.

- **Agente de virtualización**: el recurso y el administrador de conexiones en el proveedor de virtualización, como Azure
- **Escritorio virtual**: pila de máquina virtual (VM) que ejecuta Microsoft Teams
- **Cliente ligero**: el extremo con el que el usuario interactúa físicamente
- **Aplicación de escritorio de Teams**: esta es la aplicación cliente de escritorio de Teams

## <a name="teams-on-vdi-requirements"></a>Teams acerca de los requisitos de VDI

### <a name="virtualization-provider-requirements"></a>Requisitos del proveedor de virtualización

La aplicación de escritorio de Teams se validó con los principales proveedores de soluciones de virtualización. Con los proveedores de varios mercados, le recomendamos que consulte a su proveedor de soluciones de virtualización para asegurarse de que se cumplan los requisitos mínimos.
  
Actualmente, los equipos de VDI con la optimización de audio y vídeo (AV) están certificados con Citrix. Revise la información de esta sección para asegurarse de que se cumplan los requisitos de Citrix y de Teams para que funcionen correctamente.

### <a name="partners-certified-for-teams"></a>Socios certificados para equipos

Los siguientes socios tienen soluciones de infraestructura de escritorio virtual para Teams.

|Servidor|Solución de socio|
|----|---|
|![El logotipo representa Citrix](media/citrix.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Aplicaciones virtuales y equipos de escritorio Citrix</a> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos de aplicaciones virtuales y de escritorio de Citrix

Las aplicaciones virtuales y los escritorios de Citrix (anteriormente conocidos como XenApp y XenDesktop) proporcionan optimización de AV para Teams en VDI. Con las aplicaciones virtuales y los equipos de escritorio de Citrix, los equipos de VDI son compatibles con las llamadas y la funcionalidad de reuniones, además de los chats y la colaboración.

[Aquí](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)puede descargar la última versión de las aplicaciones virtuales y equipos de escritorio de Citrix. (Primero deberás iniciar sesión). Los componentes necesarios se agrupan en la [aplicación Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) y virtual Delivery Agent (VDA) de forma predeterminada. No es necesario instalar ningún componente o complemento adicional en CWA o en VDA.

Para obtener los últimos requisitos de servidor y cliente, consulte [este sitio web de Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar o actualizar la aplicación de escritorio de Teams en VDI

Puede implementar la aplicación de escritorio de Teams para VDI con una instalación por equipo o una instalación por usuario con el paquete MSI. Decidir qué método usar depende de si usa una configuración persistente o no persistente y las necesidades de funcionalidad asociada de su organización.
En el caso de una configuración persistente, cualquiera de estos métodos funcionará.  Sin embargo, para una instalación no persistente, es necesaria una instalación por equipo para que los equipos funcionen de forma eficaz. Consulte la sección [configuración no persistente](#non-persistent-setup) .

Con la instalación por equipo, actualizaciones automáticas está deshabilitado. Esto significa que para actualizar la aplicación de Teams, debe desinstalar la versión actual para actualizar a una versión más reciente. Con la instalación por usuario, la característica actualizaciones automáticas está habilitada. Para la mayoría de las implementaciones de VDI, se recomienda implementar Teams con la instalación por equipo.

Para actualizar a la versión más reciente de Teams, comience con el procedimiento de desinstalación seguido de la última implementación de la versión de Teams.

Para que la optimización de AV de Teams en entornos de VDI funcione correctamente, el punto de conexión de cliente ligero debe tener acceso a Internet. Si el acceso a Internet no está disponible en el extremo del cliente ligero, el inicio de la optimización no se realizará correctamente. Esto significa que el usuario se encuentra en un estado de medio no optimizado.

#### <a name="dedicated-persistent-setup"></a>Configuración permanente dedicada

En una configuración persistente, los cambios del sistema operativo local de los usuarios se conservan después de que los usuarios cierren sesión.  Para la configuración persistente, los equipos son compatibles con la instalación por usuario y por equipo.

A continuación se recomienda la configuración de VM mínima.

|Parámetro  |Sistema operativo de estación de trabajo  |Sistema operativo del servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4, 6 u 8<br>Es importante comprender la configuración de acceso a memoria no uniforme (NUMA) subyacente y configurar las máquinas virtuales según corresponda.     |
|MEMORIAS     |   4 GB      | 512 a 1024 MB por usuario        |
|Almacenamiento    | 8 GB        | 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuración no persistente

En una configuración no persistente, los cambios del sistema operativo local de los usuarios no se conservan después de que los usuarios cierren sesión. Dichas configuraciones suelen ser sesiones multiusuario compartidas. La configuración de la VM varía según el número de usuarios y los recursos del cuadro físico disponibles.

Para una instalación no persistente, la aplicación de escritorio de Teams debe instalarse por equipo para la imagen de oro. (Para obtener más información, consulte la sección [instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi) ). Esto asegura un lanzamiento eficaz de la aplicación de Teams durante una sesión de usuario. El uso de equipos con una configuración no persistente también requiere un administrador de almacenamiento en caché para los equipos eficientes de sincronización de datos en tiempo de ejecución. Esto garantiza que la información específica del usuario adecuada (por ejemplo, datos de usuario, perfil y configuración) se almacene en la memoria caché durante la sesión de usuario.  Hay una gran variedad de soluciones de administrador de almacenamiento en caché disponibles. Por ejemplo, [FSLogix](https://docs.microsoft.com/fslogix/overview). Consulte a su proveedor de almacenamiento en caché para obtener instrucciones de configuración específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Lista de exclusión de contenido almacenado en caché de Teams para configuración no persistente

Excluya lo siguiente de la carpeta Team Caching,% AppData%/Microsoft/Teams.  Excluyendo estos ayuda a reducir el tamaño del almacenamiento en caché de usuario para optimizar aún más la configuración no persistente.

- archivos. txt
- Carpeta de la pila de medios

### <a name="office-365-proplus-considerations"></a>Consideraciones sobre Office 365 ProPlus

Tenga en cuenta lo siguiente al implementar Teams con Office 365 ProPlus en VDI.

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a>Nuevas implementaciones de Teams a través de Office 365 ProPlus

Antes de implementar Teams a través de Office 365 ProPlus, primero debe desinstalar cualquier aplicación existente de Teams si se ha implementado con la instalación por equipo.

Los equipos a través de Office 365 ProPlus se instalan por usuario. Para obtener más información, consulte la sección [instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-office-365-proplus-updates"></a>Implementaciones de Teams mediante las actualizaciones de Office 365 ProPlus

Teams también se agrega a las instalaciones existentes de Office 365 ProPlus. Dado que Office 365 ProPlus instala solo equipos por usuario, consulte la sección [instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a>Usar Teams con la instalación por equipo y Office 365 ProPlus

Office 365 ProPlus no es compatible con las instalaciones por máquina de Teams. Para usar la instalación por equipo, debe excluir equipos de Office 365 ProPlus. Vea la [aplicación de escritorio de implementación de Teams en la VM](#deploy-the-teams-desktop-app-to-the-vm) y [Cómo excluir la implementación de Teams a través de las secciones de Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) .

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a>Cómo excluir la implementación de equipos a través de Office 365 ProPlus

Para obtener más información sobre los equipos y Office 365 ProPlus, consulte [Cómo excluir equipos de las nuevas instalaciones de Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) y [use la Directiva de grupo para controlar la instalación de Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implementar la aplicación de escritorio de Teams en la VM

1. Descargue el paquete MSI de teams que coincida con el sistema operativo de la VM de VDI mediante uno de los siguientes vínculos:

    - [versión de 32 bits](https://statics.teams.cdn.office.net/production-windows/1.3.00.4461/Teams_windows.msi)
    - [versión de 64 bits](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.4461/Teams_windows_x64.msi)

    La versión mínima de la aplicación de escritorio de Teams requerida es la versión 1.2.00.31357. (La retención de RTC no es compatible con versiones anteriores).

2. Instale el MSI en la VM de VDI ejecutando uno de los siguientes comandos:

    - Instalación por usuario (predeterminado)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        Esta es la instalación predeterminada, que instala Teams en la carpeta de usuario% AppData%. En este momento, la configuración de la imagen de oro está completa. Teams no funciona correctamente con la instalación por usuario en una configuración no persistente.
    
    - Instalación por equipo

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        Esto instalará Teams en la carpeta archivos de programa (x86) en un sistema operativo de 64 bits y en la carpeta archivos de programa de un sistema operativo de 32 bits. En este momento, la configuración de la imagen de oro está completa. La instalación de equipos por máquina es necesaria para las configuraciones no persistentes.
 
        La siguiente sesión de inicio de sesión interactivo inicia Teams y solicita las credenciales.

3. Desinstale el MSI de la máquina virtual de VDI. 

    Existen dos formas de desinstalar Teams:  
  
    - Script de PowerShell (recomendado)
    
    - Línea de comandos: este enfoque quita Teams, pero impide la reinstalación de Teams. Ejecute el siguiente comando:
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      Esto desinstala equipos de la carpeta archivos de programa (x86) o de la carpeta archivos de programa, según el entorno del sistema operativo.

## <a name="teams-on-vdi-performance-considerations"></a>Consideraciones de rendimiento de Teams en VDI

Hay varias configuraciones de instalación virtualizadas, cada una con un enfoque diferente para la optimización. Por ejemplo, densidad de usuario. Al planear, tenga en cuenta lo siguiente para ayudarle a optimizar la configuración en función de las necesidades de carga de trabajo de su organización:

- Requisito mínimo: algunas cargas de trabajo pueden requerir una configuración que use recursos que estén por encima de los requisitos mínimos. Por ejemplo, cargas de trabajo para los programadores que usan aplicaciones que exigen más recursos informáticos.
- Dependencias: Estas incluyen dependencias de la infraestructura, la carga de trabajo y otras consideraciones ambientales fuera de la aplicación de escritorio de Teams.
- Características deshabilitadas en VDI: Teams deshabilita características de GPU intensiva para VDI, lo que puede ayudar a mejorar el uso de la CPU transitoria. Las siguientes características están deshabilitadas:
    - Animación CSS de Teams
    - Inicio automático de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams en VDI con llamadas y reuniones

Además de los chats y la colaboración, los equipos de VDI con soporte de llamadas y reuniones están disponibles con plataformas basadas en Citrix. Las características compatibles se basan en la pila de medios de WebRTC y en la implementación específica de Citrix. El siguiente diagrama ofrece una descripción general de la arquitectura.

![Diagrama que muestra equipos en arquitectura de VDI](media/teams-on-vdi-architecture.png)

No se admiten estas características de llamadas y reuniones:

- Servicios de emergencia mejorados
- Botones HID y controles LED entre la aplicación de Teams y los dispositivos
- Efectos y desenfoque de fondo
- Eventos de difusión/Live
- Enrutamiento basado en la ubicación (LBR)
- Estacionar llamada
- Cola de llamadas

> [!IMPORTANT]
> Si actualmente ejecuta equipos sin optimización de AV en VDI y usa características que aún no se admiten para la optimización (como conceder y tomar el control al compartir aplicaciones), debe configurar directivas de Citrix para desactivar el redireccionamiento de equipos. Esto significa que las sesiones de Team media no se optimizarán. Para conocer los pasos sobre cómo configurar directivas para desactivar el redireccionamiento de equipos, consulte este [sitio web de Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).

Estamos trabajando para agregar características de llamadas y reuniones que actualmente solo están disponibles en entornos ajenos a VDI. Esto puede incluir más control de administración de la calidad, escenarios de pantalla compartida adicionales y características avanzadas que se han agregado recientemente a teams. Póngase en contacto con el representante de su equipo para obtener más información sobre las próximas características.

### <a name="network-requirements"></a>Requisitos de red

Le recomendamos que evalúe su entorno para identificar los riesgos y los requisitos que pueden influir en la implementación general de voz y video de la nube. Use la [herramienta Evaluación de redes de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si su red está lista para los equipos.

Para obtener más información sobre cómo preparar su red para equipos, consulte [preparar la red de su organización para Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar desde Skype empresarial en VDI a teams en VDI

Si va a migrar desde Skype empresarial en VDI a teams en VDI, además de las diferencias entre las dos aplicaciones, hay algunas diferencias cuando se implementa VDI. Algunas de las funciones que actualmente no se admiten en la VDI de Skype para empresas son las siguientes:

- Control de las experiencias de las llamadas de VDI con directivas para limitar la velocidad de bits de medios
- Directiva por plataforma para deshabilitar algunas características de AV en VDI
- Ceder y tomar el control del uso compartido de aplicaciones
- Compartir pantalla desde una conversación sin audio
- Envío y recepción simultáneos de video y pantalla compartida

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Equipos en el explorador Chrome frente a la aplicación de escritorio de Teams para VDI

El explorador de Teams en Chrome no proporciona un reemplazo para la aplicación de escritorio de Teams para VDI con optimización de AV. La experiencia de chat y colaboración funciona de la forma esperada. Cuando se necesita multimedia, hay algunas experiencias que pueden no cumplir con las expectativas del usuario en el explorador Chrome:

- Es posible que la experiencia de transmisión de audio y vídeo no sea óptima. Los usuarios pueden experimentar retrasos o reducir la calidad.
- La configuración del dispositivo no está disponible en la configuración del explorador.
- La administración de dispositivos se controla a través del explorador y requiere varias opciones de configuración en la configuración del sitio del explorador.
- Es posible que la configuración del dispositivo también deba establecerse en Windows Device Management.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Equipos en VDI con chat y colaboración

Si su organización desea usar únicamente las características de colaboración y chat en Teams, puede establecer directivas de nivel de usuario para desactivar las funciones de llamada y de reunión de Teams. Este nivel de características no requiere aplicaciones virtuales de Citrix y equipos de escritorio.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Establecer directivas para desactivar la funcionalidad de llamadas y reuniones

Puede establecer directivas con el centro de administración de Microsoft Teams o PowerShell. Los cambios de Directiva pueden tardar un poco (algunas horas) en propagarse. Si no ve los cambios de una cuenta determinada inmediatamente, inténtelo de nuevo en unas pocas horas.

[**Llamadas a directivas**](teams-calling-policy.md): Teams incluye la Directiva de llamadas DisallowCalling integrada, en la que se desactivan todas las características de las llamadas. Asigne la Directiva DisallowCalling a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

[**Directivas de reuniones**](meeting-policies-in-teams.md): Teams incluye la Directiva de reunión AllOff integrada, en la que se desactivan todas las características de la reunión. Asigne la Directiva AllOff a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas mediante el centro de administración de Microsoft Teams

Para asignar la Directiva de llamada de DisallowCalling y la Directiva de reunión de AllOff a los usuarios, siga estos pasos:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**.
2. Seleccione el usuario haciendo clic a la izquierda del nombre de usuario y, a continuación, haga clic en **Editar configuración**.
3. Siga este procedimiento:
    1.  En **Directiva de llamada**, haga clic en **DisallowCalling**.
    2.  En **Directiva de reunión**, haga clic en **AllOff**.
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).

También puede hacer lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la Directiva que desea asignar. Por ejemplo:
    - Vaya a **Voice** > **directivas de llamadas**de voz y, a continuación, haga clic en **DisallowCalling**.
    - Vaya a **reuniones** > **Meeting Policies**y, a continuación, haga clic en **AllOff**.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, a continuación, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para asignar la Directiva de llamadas de DisallowCalling a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para obtener más información sobre cómo usar PowerShell para administrar directivas de llamadas, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

En el ejemplo siguiente se muestra cómo usar la [concesión-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la Directiva de reunión de AllOff a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para obtener más información sobre cómo usar PowerShell para administrar directivas de reuniones, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a>Migrar equipos de VDI con chat y colaboración a Citrix con llamadas y reuniones

Si tiene una implementación existente de Teams en VDI con conversaciones y colaboración en las que ha establecido directivas de nivel de usuario para desactivar la funcionalidad de llamadas y reuniones, y migra a Citrix con optimización de AV, debe configurar las directivas para activar las llamadas y cumplimiento de la funcionalidad de los equipos de los usuarios de VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Establecer directivas para activar la funcionalidad de llamadas y reuniones

Puede usar el centro de administración de Microsoft Teams o PowerShell para establecer y asignar directivas de llamada y reunión a los usuarios. Los cambios de Directiva pueden tardar un poco (algunas horas) en propagarse. Si no ve los cambios de una cuenta determinada inmediatamente, inténtelo de nuevo después de algunas horas.

[**Directivas de llamadas: directivas**](teams-calling-policy.md)de llamada en Teams controle qué características de llamadas están disponibles para los usuarios. Teams incluye la Directiva de llamadas AllowCalling integrada, en la que se activan todas las características de las llamadas. Para activar todas las características de llamadas, asigna la Directiva AllowCalling. También puedes crear una directiva de llamadas personalizada para activar las características de llamadas que quieras y asignarla a los usuarios. 

[**Directivas de reuniones**](meeting-policies-in-teams.md): directivas de reuniones en Teams controle los tipos de reuniones que los usuarios pueden crear y las características que están disponibles para los participantes de la reunión programados por los usuarios de su organización. Teams incluye la Directiva de AllOn de reunión integrada, en la que se activan todas las características de la reunión. Para activar todas las características de la reunión, asigne la Directiva AllOn. O bien, cree una directiva de reunión personalizada para activar las características de la reunión que desee y asignarles usuarios.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas mediante el centro de administración de Microsoft Teams

Para asignar la Directiva de llamada de AllowCalling y la Directiva de reunión de AllOn a los usuarios, siga estos pasos:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**.
2. Seleccione el usuario haciendo clic a la izquierda del nombre de usuario y, a continuación, haga clic en **Editar configuración**.
3. Siga este procedimiento:
    1.  En **Directiva de llamada**, haga clic en **AllowCalling**.
    2.  En **Directiva de reunión**, haga clic en **AllOn**.
4. Haga clic en **Aplicar**.

Para asignar una directiva a varios usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).

También puede hacer lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la Directiva que desea asignar. Por ejemplo:
    - Vaya a **Voice** > **directivas de llamadas**de voz y, a continuación, haga clic en **AllowCalling**.
    - Vaya a **reuniones** > **Meeting Policies**y, a continuación, haga clic en **AllOn**.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, a continuación, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para asignar la Directiva de llamadas de AllowCalling a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para obtener más información sobre cómo usar PowerShell para administrar directivas de llamadas, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

En el ejemplo siguiente se muestra cómo usar la [concesión-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la Directiva de reunión de AllOn a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para obtener más información sobre cómo usar PowerShell para administrar directivas de reuniones, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="known-issues-and-limitations"></a>Problemas conocidos y limitaciones

### <a name="client-deployment-installation-and-setup"></a>Implementación de clientes, instalación y configuración

- Con la instalación por equipo, Teams en VDI no se actualiza automáticamente de la manera en que se encuentran los clientes de equipos ajenos a VDI. Tiene que actualizar la imagen de VM instalando un nuevo MSI, tal y como se describe en la sección [instalar o actualizar la aplicación de escritorio de Teams en VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Debe desinstalar la versión actual para actualizar a una versión más reciente.
- Los equipos se deben implementar tanto por usuario como por equipo. No se admite la implementación de equipos para usuarios simultáneos y por equipo.  Para migrar de cualquiera por equipo o por usuario a uno de estos modos, siga el procedimiento de desinstalación y vuelva a implementarlo en cualquiera de los dos.
- En este momento, Citrix no admite los clientes de MacOs y Linux.
- Citrix no admite el uso de proxy HTTP explícitos definidos en un extremo. 

### <a name="calling-and-meetings"></a>Llamadas y reuniones

- La interoperabilidad con Skype empresarial está limitada a las llamadas de audio, sin modalidad de video.
- Actualmente no se admite la interacción de multifrecuencia de tono dual (DTMF) con sistemas de telefonía.
- Unirse a reuniones de Teams como usuario anónimo no está optimizado para AV. El usuario puede unirse a la reunión y tener una experiencia no optimizada.
- En las reuniones o en las llamadas grupales solo se admite una única secuencia de vídeo entrante. Cuando varias personas envían video, solo se muestra el vídeo del altavoz dominante en un momento dado.  
- La resolución de flujo de vídeo entrante y saliente está limitada a la resolución de 720p. Esta es una limitación de WebRTC.
- Solo se admite una secuencia de vídeo de una cámara entrante o una secuencia compartida de pantalla. Cuando hay un uso compartido de pantalla entrante, ese recurso compartido de pantalla lo muestra en lugar del vídeo del altavoz dominante.
- Pantalla compartida saliente:
    - El uso compartido de aplicaciones no es compatible.
- Ceder el control y tomar el control:  
    - No se admite durante una sesión compartida de pantalla o de uso compartido de aplicaciones.
    - Compatible durante una sesión de uso compartido de PowerPoint.
- Cuando se comparte la pantalla en una configuración de varios monitores, solo se comparte el monitor principal.
- No se admite el escalado de PPP alto en CWA.

Para los problemas conocidos de teams que no se relacionan con VDI, consulte [problemas conocidos para Teams](Known-issues.md).

## <a name="troubleshooting"></a>Solución de problemas

#### <a name="troubleshoot-citrix-components"></a>Solución de problemas de componentes de Citrix

Para obtener información sobre cómo solucionar problemas de VDA y CWA, consulte [este sitio web de Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

## <a name="related-topics"></a>Temas relacionados

- [Instalar Microsoft Teams mediante MSI](msi-deployment.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
