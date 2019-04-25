---
title: Teams para la infraestructura de escritorio virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Obtenga información sobre cómo ejecutar Microsoft Teams en un entorno virtualizado de Desktop Infrastructure (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223427"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para la infraestructura de escritorio virtualizada

En este artículo se describen los requisitos y limitaciones para el uso de Microsoft Teams en un entorno virtualizado.

## <a name="what-is-vdi"></a>¿Qué es VDI?

Infraestructura de escritorio virtual (VDI) es la tecnología de virtualización que hospeda un sistema operativo de escritorio y las aplicaciones en un servidor centralizado en un centro de datos. Esto permite una experiencia de escritorio totalmente personalizada a los usuarios con un origen centralizado totalmente compatibles con y protegido. 
 
Actualmente, los equipos en un entorno virtualizado está disponible con soporte para la funcionalidad de colaboración y chat con un equipo virtualizado persistente dedicado (VM). Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo. 

## <a name="teams-requirements"></a>Requisitos de los equipos

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Establecer directivas para desactivar la opción de llamada y funcionalidad en los equipos de la reunión

Los equipos de llamada y la experiencia de la reunión no está optimizado para un entorno VDI (próximamente). Se recomienda que establecer directivas de nivel de usuario para desactivar la opción de llamada y funcionalidad en los equipos de la reunión.

Aún puede elegir ejecutar los equipos totalmente en VDI con la aplicación de escritorio de los equipos o la aplicación web. Sin embargo, le recomendamos que configure las directivas para evitar poner en peligro la experiencia del usuario.  

Puede tardar cierto tiempo (unas cuantas horas) propagar los cambios de directiva. Si no ve inmediatamente los cambios para una cuenta determinada, inténtelo de nuevo en unas cuantas horas.

> [!NOTE]
> Al llamar a los equipos y las reuniones están optimizadas para su uso en entornos de escritorio virtuales, puede revertir estas directivas y permitir a los usuarios utilizar los equipos como de costumbre. 

#### <a name="calling"></a>Llamar a

Use los cmdlets **CSTeamsCallingPolicy** para controlar si los usuarios pueden usar al llamar a y las opciones de llamada en privado y grupo de chat. Aquí es la lista de configuración de directiva y valores recomendados.

|Nombre de la directiva  |Descripción |Valor recomendado  |
|---------|---------|---------|
|AllowCalling    |Interoperabilidad de controles al llamar a funciones. Activar Esto permite Skype para los usuarios de negocios que las llamadas proporcionó con los usuarios de los equipos y viceversa.         |Se establece en False para evitar que las llamadas de Skype para los usuarios de negocio en los equipos de destino.          |
|AllowPrivateCalling     | Controla si la aplicación de llamada está disponible en la barra de la aplicación en el lado izquierdo del cliente para los equipos y si los usuarios ven llamadas y las opciones de llamadas de chat privado de vídeo         |Se establece en False para quitar la aplicación de llamada de la barra de la aplicación en el lado izquierdo de los equipos y para quitar las opciones de llamada de llamadas y vídeo de chat privado.          |

#### <a name="create-and-assign-a-calling-policy"></a>Crear y asignar una directiva de llamada

1. Iniciar una sesión de Windows PowerShell como administrador.
2. Conectar con el conector de Skype en línea.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Ver una lista de las opciones de directiva de llamada.

       Get-CsTeamsCallingPolicy
 
4. Busque la opción de directiva integrada donde se deshabilitan todas las directivas de llamada. El siguiente aspecto.
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. Aplicar la opción de directiva integrada DisallowCalling a todos los usuarios que van a usar los equipos en un entorno virtualizado.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Para obtener más información acerca de los equipos al llamar a las directivas, vea [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Reuniones

Use los cmdlets **CsTeamsMeetingPolicy** para controlar el tipo de las reuniones que los usuarios pueden crear, las características que puede tener acceso a mientras está en una reunión y las características de reunión que están disponibles para los usuarios anónimos y externos. Aquí es la lista de configuración de directiva y valores recomendados.

|Nombre de la directiva |Descripción|Valor recomendado                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Determina si se permite a un usuario para programar las conferencias privadas.| Se establece en False para prohibir al usuario la posibilidad de programar reuniones privadas.  |
|AllowChannelMeetingScheduling  | Determina si se permite a un usuario para programar reuniones de canal. | Se establece en False para prohibir al usuario la posibilidad de programar reuniones de canal.                       |
|AllowMeetNow |Determina si se permite a un usuario para crear o iniciar reuniones ad hoc.              |  Establézcalo en False para prohibir al usuario la posibilidad de iniciar reuniones ad hoc.                     |
|ScreenSharingMode | Determina el modo en que un usuario se permite compartir su pantalla en las llamadas o reuniones. | Establecido en deshabilitado para prohibir el usuario de uso compartido de sus pantallas                          |
|AllowIPVideo |Determina si el vídeo está habilitado en las reuniones o las llamadas de un usuario.                  |    Se establece en False para prohibir al usuario de uso compartido de su vídeo                                         |
| AllowAnonymousUsersToDialOut | Determina si los usuarios anónimos pueden marcar un número RTC. | Se establece en False para prohibir a los usuarios anónimos llamadas de salida                                  |
| AllowAnonymousUsersToStartMeeting | Determina si los usuarios anónimos pueden iniciar una reunión.     |  Se establece en False para prohibir a los usuarios iniciar una reunión                                            |
| AllowOutlookAddIn |Determina si un usuario puede programar reuniones en los equipos en el cliente de escritorio de Outlook.| Se establece en False para prohibir a un usuario de programación de reuniones de los equipos en el cliente de escritorio de Outlook|
| AllowParticipantGiveRequestControl|Determina si los participantes pueden solicitar o ceder el control de uso compartido de la pantalla.| Se establece en False para prohibir al usuario proporcionar y solicitar el control en una reunión    |
| AllowExternalParticipantGiveRequestControl | Determina si los participantes externos pueden solicitar o ceder el control de uso compartido de la pantalla.| Establece en False para prohibir a un usuario externo que proporciona, solicitar el control en una reunión|
|AllowPowerPointSharing|Determina si se permite el uso compartido de PowerPoint en las reuniones de un usuario. |Se establece en False para prohibir a un usuario de uso compartido de archivos de PowerPoint en una reunión  |
|AllowWhiteboard | Determina si se permite la Pizarra en las reuniones de un usuario. |   Se establece en False para prohibir la Pizarra en una reunión |
| AllowTranscription |Determina si se permiten los títulos en tiempo real o posteriores a la reunión y transcripciones en las reuniones de un usuario.|    Se establece en False para prohibir la transcripción y títulos en una reunión  |  
| AllowSharedNotes | Determina si los usuarios pueden tomar notas compartidas. | Se establece en False para prohibir a los usuarios tomar notas compartidas |
|MediaBitRateKB |Determina la velocidad de bits de medios de audio/vídeo/aplicación de uso compartido de las transmisiones de reuniones  | Valor sugerido es 5000 (5 MB). Se puede cambiar en función de las necesidades de su organización.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Crear y asignar una directiva de reunión

1. Iniciar una sesión de Windows PowerShell como administrador.
2. Conectar con el conector de Skype en línea.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Ver una lista de opciones de directiva de reunión.

       Get-CsTeamsMeetingPolicy
 
4. Busque la opción de directiva integrada donde se deshabilitan todas las directivas de reunión. El siguiente aspecto.
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. Aplicar la opción de directiva integrada AllOff a todos los usuarios que van a usar los equipos en un entorno virtualizado. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Para obtener más información acerca de las directivas de reunión de los equipos, vea [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Requisitos de virtualización de proveedor

La aplicación de los equipos ha sido validada en proveedores de soluciones de virtualización a la izquierda. Con varios proveedores de mercado, consulte a su proveedor de soluciones de virtualización para asegurarse de que se cumplen los requisitos mínimos.

### <a name="virtual-machine-requirements"></a>Requisitos de máquina virtual

Con las diversas cargas de trabajo y las necesidades del usuario en un entorno virtualizado, el siguiente es el mínimo recomendado de configuración de máquina virtual.

|Parámetro  |Medida  |
|---------|---------|
|vCPU    |  2 núcleos       |
|MEMORIA RAM     |  4 GB      |
|Almacenamiento     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>Requisitos de sistema operativo de la máquina virtual

Los sistemas operativos admitidos para la máquina virtual son:

- 10 y versiones posteriores de Windows
- Windows Server 2012 R2 y versiones posteriores

## <a name="install-teams-on-vdi"></a>Instalar los equipos de la VDI

Este es el proceso y las herramientas necesarias para implementar la aplicación de escritorio de los equipos. 

1. Descargar el paquete de MSI de los equipos mediante uno de los siguientes vínculos según el entorno. Se recomienda la versión de 64 bits para una VM de VDI con un sistema operativo de 64 bits.

    - [versión de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versión de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Ejecute el siguiente comando para instalar el archivo MSI en la VM VDI (o completar su actualización).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Este archivo instala los equipos a los archivos de programa. En este momento, la configuración de imagen oro está completa.
 
    La sesión de inicio de sesión interactivo siguiente inicia los equipos y solicita credenciales. Tenga en cuenta que no es posible deshabilitar el inicio automático de los equipos al instalar los equipos de la VDI mediante la propiedad correspondiente a. 

3. Ejecute el siguiente comando para desinstalar el archivo MSI de la VM VDI (o preparar para su actualización).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Esto desinstala los equipos de los archivos de programa.

## <a name="known-issues-and-limitations"></a>Limitaciones y problemas conocidos

Los siguientes son problemas conocidas y limitaciones para los equipos de la VDI.

- **Implementaciones de tipo de host de sesión de compartidos**: implementaciones de tipo de host de sesión de compartidos (por ejemplo, que no son persistentes VM configuración compartida) no están en el ámbito.
- **Llamadas y reuniones**:

    - Llamada y escenarios de la reunión no están optimizados para VDI. Estos escenarios realizará mal. Se recomienda usar las directivas de nivel de usuario, tal como se describe en la sección [establecer directivas para desactivar la opción de llamada y funcionalidad en los equipos de la reunión](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .  
    - Aplicar las directivas que se describen en este artículo afecta a la capacidad de usar la funcionalidad de llamada y convocatorias de reunión que según otras directivas, puede afectar a otros usuarios de la organización. Si los usuarios de la organización utilizan a los clientes que no sean de VDI, puede elegir no aplicar las directivas.  

- **Unirse a las llamadas y las reuniones creadas por otros usuarios**: aunque las directivas de restringen a los usuarios de la creación de las reuniones, todavía pueden unirse a reuniones si otro usuario marca a ellos desde la reunión. En estas reuniones, la capacidad del usuario para compartir vídeo, usar la Pizarra y otras características dependen de si deshabilita las características mediante TeamsMeetingPolicy.  
- **Contenido en caché**: si es el entorno virtual en los equipos que se ejecuten no es persistente (y se limpian de datos al final de cada sesión de usuario), los usuarios pueden observar la degradación del rendimiento debido a la actualización de contenido, independientemente de si el usuario tiene acceso a la misma contenido en una sesión anterior.
- **Actualizaciones de cliente**: no se actualizan automáticamente los equipos de la VDI similar al modo en que los clientes de equipos que no sean de VDI.  Se debe actualizar la imagen de la máquina virtual mediante la instalación de un nuevo MSI tal como se describe en la sección [Instalación de los equipos de la VDI](#install-teams-on-vdi) . Debe desinstalar la versión actual para actualizar a una versión más reciente.
- **Experiencia del usuario**: los equipos de la experiencia del usuario en un entorno VDI puede ser distinta de un entorno que no sean VDI. Las diferencias se pueden debido a la configuración de directiva o cuentan con soporte en el entorno.

Para los equipos de los problemas conocidos que no están relacionados con VDI, consulte [problemas para los equipos de Microsoft conocidos](Known-issues.md).

## <a name="related-topics"></a>Temas relacionados

- [Instalar Teams Microsoft con MSI](msi-deployment.md)