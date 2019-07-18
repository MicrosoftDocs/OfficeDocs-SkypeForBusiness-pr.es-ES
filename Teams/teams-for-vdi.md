---
title: Teams para la infraestructura de escritorio virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: Aprenda a ejecutar Microsoft Teams en un entorno de infraestructura de escritorio virtual (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 132bd532ae8f7da98edb38a81363b4d5b6501532
ms.sourcegitcommit: 9751f34318119991b1bd32b384b8e1479c83cb0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2019
ms.locfileid: "35768151"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para la infraestructura de escritorio virtualizada

En este artículo se describen los requisitos y las limitaciones para usar Microsoft Teams en un entorno virtualizado.

## <a name="what-is-vdi"></a>¿Qué es VDI?

La infraestructura de escritorio virtual (VDI) es una tecnología de virtualización que hospeda un sistema operativo de escritorio y aplicaciones en un servidor centralizado en un centro de datos. Esto permite una experiencia de escritorio totalmente personalizada para los usuarios con un origen centralizado totalmente seguro y compatible. 
 
Actualmente, Teams en un entorno virtualizado está disponible con soporte técnico para la funcionalidad de colaboración y chats con una máquina virtualizada dedicada (VM). Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo. 

## <a name="teams-requirements"></a>Requisitos de Teams

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Establecer directivas para desactivar las funciones de llamada y de reunión en Teams

La experiencia de llamadas y reuniones de equipos no está optimizada para un entorno de VDI (próximamente). Le recomendamos que establezca directivas de nivel de usuario para desactivar las funciones de llamada y de reunión de Teams.

Aún puede elegir ejecutar Teams por completo en VDI con la aplicación de escritorio de Teams o la aplicación Web. Sin embargo, le recomendamos que establezca las directivas para evitar poner en peligro la experiencia del usuario.  

Los cambios de Directiva pueden tardar un poco (algunas horas) en propagarse. Si no ve los cambios de una cuenta determinada inmediatamente, inténtelo de nuevo en unas pocas horas.

> [!NOTE]
> Cuando las llamadas y las reuniones de Teams están optimizadas para su uso en entornos de escritorio virtuales, puede revertir estas directivas y permitir que los usuarios usen Teams como lo harían normalmente. 

#### <a name="calling"></a>Llamadas

Use los cmdlets de **CSTeamsCallingPolicy** para controlar si los usuarios pueden usar las opciones de llamadas y llamadas en los chats privados y grupales. A continuación se muestra la lista de opciones de directiva y los valores recomendados.

|Nombre de la directiva  |Descripción |Valor recomendado  |
|---------|---------|---------|
|AllowCalling    |Controla las capacidades de llamadas de interoperabilidad. Activar este servicio permite que los usuarios de Skype empresarial tengan llamadas individuales con usuarios de Teams y viceversa.         |Se establece en false para evitar que las llamadas de los usuarios de Skype empresarial se desembarquen en Teams.          |
|AllowPrivateCalling     | Controla si la aplicación de llamada está disponible en la barra de la aplicación en el lado izquierdo del cliente de equipos y si los usuarios ven las opciones de llamadas y videollamadas en una conversación privada         |Se establece en false para quitar la aplicación que llama de la barra de aplicaciones situada en el lado izquierdo de Teams y quitar las opciones de llamadas y videollamadas en la conversación privada.          |

#### <a name="create-and-assign-a-calling-policy"></a>Crear y asignar una directiva de llamadas

1. Inicie una sesión de Windows PowerShell como administrador.
2. Conéctate al conector de Skype online.

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
 
4. Busque la opción de directiva integrada donde todas las directivas de llamadas están deshabilitadas. Tiene el siguiente aspecto.
   
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

5. Aplique la opción de directiva integrada DisallowCalling a todos los usuarios que vayan a usar Teams en un entorno virtualizado.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Para obtener más información sobre las directivas de llamadas de Teams, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Reuniones

Use los cmdlets de **CsTeamsMeetingPolicy** para controlar el tipo de reuniones que los usuarios pueden crear, las características a las que pueden acceder durante una reunión y las características de la reunión que están disponibles para los usuarios anónimos y anónimos. A continuación se muestra la lista de opciones de directiva y los valores recomendados.

|Nombre de la Directiva |Descripción|Valor recomendado                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Determina si un usuario puede programar reuniones privadas.| Se establece en false para impedir que el usuario pueda programar reuniones privadas.  |
|AllowChannelMeetingScheduling  | Determina si un usuario puede programar reuniones de canal. | Se establece en false para impedir que el usuario pueda programar reuniones de canal.                       |
|AllowMeetNow |Determina si un usuario puede crear o iniciar reuniones ad-hoc.              |  Establezca este valor en false para impedir que el usuario pueda iniciar reuniones ad-hoc.                     |
|ScreenSharingMode | Determina el modo en el que un usuario puede compartir su pantalla en llamadas o reuniones. | Establecer en deshabilitado para impedir que el usuario comparta su pantalla                          |
|AllowIPVideo |Determina si el vídeo está habilitado en las reuniones o las llamadas de un usuario.                  |    Se establece en false para impedir que el usuario comparta el vídeo.                                         |
| AllowAnonymousUsersToDialOut | Determina si los usuarios anónimos pueden llamar a un número de RTC. | Se establece en false para impedir que los usuarios anónimos llamen                                  |
| AllowAnonymousUsersToStartMeeting | Determina si los usuarios anónimos pueden iniciar una reunión.     |  Se establece en false para impedir que los usuarios inicien una reunión                                            |
| AllowOutlookAddIn |Determina si un usuario puede programar reuniones de Teams en el cliente de escritorio de Outlook.| Se establece en false para impedir que un usuario programe reuniones de Teams en el cliente de escritorio de Outlook.|
| AllowParticipantGiveRequestControl|Determina si los participantes pueden solicitar o ceder el control de la pantalla compartida.| Se establece en false para impedir que el usuario asigne y solicite el control en una reunión.    |
| AllowExternalParticipantGiveRequestControl | Determina si los participantes externos pueden solicitar o ceder el control de la pantalla compartida.| Se establece en false para impedir que un usuario externo otorgue un control a una reunión|
|AllowPowerPointSharing|Determina si se permite el uso compartido de PowerPoint en las reuniones de un usuario. |Se establece en false para impedir que un usuario comparta archivos de PowerPoint en una reunión  |
|AllowWhiteboard | Determina si se permite la pizarra en las reuniones de un usuario. |   Establecer en falso para prohibir la pizarra en una reunión |
| AllowTranscription |Determina si se permiten las transcripciones y los títulos de tiempo real o posterior a la reunión en las reuniones de un usuario.|    Se establece en false para prohibir transcripción y leyendas en una reunión  |  
| AllowSharedNotes | Determina si los usuarios pueden tomar notas compartidas. | Se establece en false para impedir que los usuarios tomen notas compartidas |
|MediaBitRateKB |Determina la tasa de bits multimedia para transllamadas de uso compartido de audio, vídeo y aplicaciones en reuniones.  | El valor sugerido es 5000 (5 MB). Puede cambiarla en función de las necesidades de su organización.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Crear y asignar una directiva de reunión

1. Inicie una sesión de Windows PowerShell como administrador.
2. Conéctate al conector de Skype online.

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
 
4. Busque la opción de directiva integrada en la que se deshabilitaron todas las directivas de reunión. Tiene el siguiente aspecto.
   
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

5. Aplique la opción de directiva integrada AllOff a todos los usuarios que vayan a usar Teams en un entorno virtualizado. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Para obtener más información sobre las directivas de reunión de Teams, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Requisitos del proveedor de virtualización

La aplicación de Teams se ha validado en los principales proveedores de soluciones de virtualización. Con varios proveedores de mercado, consulte a su proveedor de soluciones de virtualización para asegurarse de que se cumplan los requisitos mínimos.

### <a name="virtual-machine-requirements"></a>Requisitos de la máquina virtual

Con las diversas cargas de trabajo y necesidades de los usuarios en un entorno virtualizado, la configuración de VM mínima recomendada es la siguiente.

|Parámetro  |Cód  |
|---------|---------|
|vCPU    |  2 núcleos       |
|MEMORIAS     |  4 GB      |
|Almacenamiento     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>Requisitos del sistema operativo de la máquina virtual

Los sistemas operativos compatibles con la VM son:

- Windows 10 y versiones posteriores
- Windows Server 2012 R2 y versiones posteriores

## <a name="install-teams-on-vdi"></a>Instalar Teams en VDI

Este es el proceso y las herramientas para implementar la aplicación de escritorio de Teams. 

1. Descargue el paquete de MSI de Teams con uno de los siguientes vínculos en función del entorno. Recomendamos la versión de 64 bits para una VM VDI con un sistema operativo de 64 bits.

    - [versión de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versión de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Ejecute el siguiente comando para instalar el MSI en la máquina virtual de VDI (o actualizarlo).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Instala Teams en archivos de programa. En este momento, la configuración de la imagen de oro está completa.
 
    La siguiente sesión de inicio de sesión interactivo inicia Teams y solicita las credenciales. Tenga en cuenta que no es posible deshabilitar el inicio automático de equipos al instalar Teams en VDI mediante la propiedad ALLUSER. 

3. Ejecute el siguiente comando para desinstalar el MSI de la máquina virtual de VDI (o prepararse para actualizarlo).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Esto desinstalará Teams de archivos de programa.

## <a name="known-issues-and-limitations"></a>Problemas conocidos y limitaciones

A continuación se indican los problemas conocidos y las limitaciones de Teams en VDI.

- **Implementaciones de tipo de host de sesión compartida**: implementaciones de tipo de host de sesión compartida (por ejemplo, configuración de VM no persistente compartida) no están en el ámbito.
- **Llamadas y reuniones**:

    - Los escenarios de llamadas y reuniones no están optimizados para VDI. Estos escenarios no se realizarán correctamente. Le recomendamos que use directivas de nivel de usuario tal y como se describe en la sección [establecer directivas para desactivar la función de llamadas y reuniones de Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .  
    - La aplicación de las directivas descritas en este artículo afecta a la posibilidad de usar la funcionalidad de llamadas y reuniones, que depende de otras directivas, puede afectar a otros usuarios de su organización. Si los usuarios de su organización usan clientes que no son VDI, puede optar por no aplicar las directivas.  

- **Unirse a llamadas y reuniones creadas por otros usuarios**: aunque las directivas restringen la creación de reuniones, aún pueden unirse a ellas si otro usuario llama a ellas desde la reunión. En estas reuniones, la capacidad del usuario de compartir vídeo, usar la pizarra y otras características depende de si ha deshabilitado esas características con TeamsMeetingPolicy.  
- **Contenido almacenado en caché**: Si el entorno virtual en el que se ejecutan los equipos no es persistente (y los datos se limpian al final de cada sesión de usuario), es posible que los usuarios noten una degradación en el rendimiento debido a la actualización del contenido, independientemente de si el usuario tuvo acceso al mismo contenido de una sesión anterior.
- **Actualizaciones de cliente**: Teams en VDI no se actualiza automáticamente con la instalación de MSI por máquina. Tiene que actualizar la imagen de VM instalando un nuevo MSI, como se describe en la sección [instalar Teams en VDI](#install-teams-on-vdi) . Debe desinstalar la versión actual para actualizar a una versión más reciente.
- **Experiencia de usuario**: la experiencia de usuario de los equipos en un entorno de VDI puede diferir de un entorno que no sea de VDI. Las diferencias pueden deberse a la configuración de directivas o a la compatibilidad de características en el entorno.

Para los problemas conocidos de teams que no se relacionan con VDI, consulte [problemas conocidos de Microsoft Teams](Known-issues.md).

## <a name="related-topics"></a>Temas relacionados

- [Instalar Microsoft Teams mediante MSI](msi-deployment.md)
