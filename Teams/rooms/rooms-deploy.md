---
title: Implementar Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este artículo para obtener información sobre cómo implementar salas de Microsoft Teams, incluidas las fases de implementación.
ms.openlocfilehash: 53c4c94717f10dadbad802cff3f233a3a771d166
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662255"
---
# <a name="deployment-overview"></a>Introducción general a la implementación

Básicamente, la implementación de salas de Microsoft Teams se divide en fases:

- Confirmar que las ubicaciones de implementación (salas) cumplen las dependencias de implementación
- Crear cuentas de Microsoft Teams o Skype Empresarial y Exchange y asignarlas a los dispositivos de la consola (consulte Configurar cuentas de [Salas de Microsoft Teams)](rooms-configure-accounts.md)
- Redisnar las tabletas Microsoft Surface para que funcionen como consolas de salas de Microsoft Teams (consulte Configurar una consola de Salas de [Microsoft Teams](console.md) o Implementar salas de Microsoft Teams, guía de implementación masiva de salas de [Microsoft Teams)](rooms-scale.md)
- (Opcional) Configurar Microsoft Operations Management Suite para sus sistemas (vea Implementar la administración de salas de [Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
- Configurar consolas en salas de reuniones y conectar los dispositivos periféricos que necesita (consulte la documentación OEM de su conjunto de dispositivos)

Los técnicos de AV pueden usarse para la última tarea, pero el departamento de TI de su organización tendrá que realizar las demás partes del proceso. 


## <a name="site-readiness"></a>Disponibilidad del sitio 

Mientras los dispositivos ordenados se entregan a la organización, trabaje con sus redes e instalaciones y con los equipos de AV para asegurarse de que se cumplen las dependencias de implementación y de que cada sitio y sala está preparado en términos de energía, redes y visualización. Además, asegúrese de que se cumplen los requisitos de instalación física. Para las consideraciones de instalación física, visite el sitio del proveedor y aproveche la experiencia de su equipo de AV al instalar y montar pantallas y ejecutar cableado.

Puede obtener más información sobre estas dependencias en los siguientes vínculos de orientación de planeación:

-   [Comprobar la disponibilidad de red](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Sugerencia profesional:** Si su intención es usar servidores proxy para proporcionar acceso a Teams o Skype Empresarial Online, [revise primero este artículo.](../proxy-servers-for-skype-for-business-online.md) Tenga en cuenta que cuando se trata de tráfico de Skype Empresarial a través de servidores proxy, se recomienda omitir los servidores proxy por completo. El tráfico de Skype Empresarial ya está cifrado, por lo que los servidores proxy no lo hacen más seguro. Como parte de la implementación más amplia, le recomendamos que siga las instrucciones de Preparar la red para [Teams](../prepare-network.md) para planear el ancho de banda y evaluar la idoneidad de su red para el tráfico en tiempo real.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos principales de Salas de Microsoft Teams.</li><li>Confirme que ha proporcionado ancho de banda suficiente para cada sitio.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la configuración y la implementación del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Preparación del servicio

Para prepararse para la implementación de Salas de Microsoft Teams, realice las siguientes tareas centrales clave:

-   Defina las características de cuenta de servicio de salas de Microsoft Teams.
-   Prepare una unidad organizativa y un grupo de Active Directory para tener sus cuentas de equipo y servicio de salas de Microsoft Teams y, opcionalmente, prepare objetos de directiva de grupo (GPO) para habilitar la opción de reterse de PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir las características de cuenta de servicio de salas de Microsoft Teams 

En función de los escenarios de colaboración que haya decidido habilitar con la implementación de Salas de Microsoft Teams, tendrá que determinar las características y capacidades que asigne a cada cuenta de servicio de Salas de Microsoft Teams que habilite.

| **Escenario** | **Descripción** | **Característica de cuenta de servicio salas de Microsoft Teams** |
|---------- |------------- | --- |
| Reuniones interactivas            | Usar voz, vídeo y pantalla compartida; convertir las salas de Microsoft Teams en un recurso que se puede reservar                     | Habilitado para Skype Empresarial, habilitado para Exchange (buzón de recursos) |
| Conferencia de acceso telefónico local            | Habilitar las reuniones que se *inician directamente* desde la consola de salas de Microsoft Teams con coordenadas de conferencias de acceso telefónico local | Habilitado para Audioconferencia                                          |
| Llamadas RTC de entrada y salida | Habilitar la consola de salas de Microsoft Teams para realizar y recibir llamadas RTC                                         | Habilitado para Sistema telefónico                                                |

Para obtener más información sobre las cuentas de Salas de Microsoft Teams, vea [Configurar cuentas de Salas de Microsoft Teams.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida los escenarios que admitirá e identifique los requisitos de licencia para sus cuentas de servicio de Salas de Microsoft Teams.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepárese para hospedar cuentas de máquina y servicio.</li></ul>| 


_Tabla de planificación de la cuenta de servicio de salas de Microsoft Teams de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de sala** | **Capacidades futuras de las sala**                                                 | **Características de la cuenta salas de Microsoft Teams**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | Medio        | 1 pantalla, audio y vídeo más presentación <br>Acceso a conferencias de acceso telefónico local<br> Acceso de RTC  | Habilitado para Skype Empresarial, habilitado para Exchange (buzón de recursos) <br>Habilitado para Audioconferencia <br>Habilitado para Sistema telefónico |
| Sydney HQ | Hill          | Grande         | 2 pantallas, audio y vídeo más presentación<br>Acceso a conferencias de acceso telefónico local<br> Acceso de RTC  | Habilitado para Skype Empresarial, habilitado para Exchange (buzón de recursos)<br> Habilitado para Audioconferencia <br>Habilitado para Sistema telefónico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Prepararse para hospedar cuentas de máquinas y servicio de salas de Microsoft Teams (opcional)

Para que pueda administrar y crear informes sobre las cuentas de servicio y del equipo de salas de Microsoft Teams, prepare su Active Directory local o Azure Active Directory (Azure AD). 

Defina un grupo de Azure AD o Active Directory local al que agregar todas las cuentas de servicio de salas de Microsoft Teams (usuario) y, a continuación, cree informes de uso mediante el cmdlet de PowerShell de Get-CSUserSession en la implementación de Microsoft Teams Rooms. Por ejemplo, cree un grupo llamado SkypeRoomSystemsv2-Service-Accounts. 


Defina una unidad organizativa en su jerarquía local de Active Directory o Azure AD para tener todas las cuentas de equipo de Microsoft Teams Rooms (si se han unido al dominio) y una unidad organizativa para tener todas las cuentas de usuario de Salas de Microsoft Teams. Si crea una unidad organizativa para las cuentas de equipo de Salas de Microsoft Teams, puede deshabilitar la herencia para asegurarse de que solo aplica las directivas que pretende aplicar a los salas de Microsoft Teams que se han unido al dominio. 

Cree un objeto de directiva de grupo asignado a la unidad de organización que contenga sus cuentas de equipo de Microsoft Teams Rooms. Use esta opción para: 

-   [Establecer la configuración de la cuenta local y de energía.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Habilite Windows Update.
-   Habilitar la opción de reoje de PowerShell. Puede configurar un script de inicio para ejecutar un script sencillo: Enable-PSRemoting -Force

Puede usar PowerShell para realizar varias actividades de administración remota, como obtener y configurar la información de configuración. La retención de PowerShell debe habilitarse antes de que se pueda llevar a cabo cualquier administración remota de PowerShell y debe considerarse como parte de los procesos de implementación o configurarse a través de una directiva de grupo.  Para obtener más información sobre estas funcionalidades y habilitarlas, vea [Mantenimiento y operaciones.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configuración e implementación 

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

-   Aprovisionamiento de cuenta
-   Instalación de software del dispositivo
-   Implementación de dispositivos
-   Configuración del dispositivo periférico y la aplicación Microsoft Teams Rooms
-    Pruebas
-   Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de cuenta 

Cada dispositivo de Salas de Microsoft Teams requiere una cuenta de recursos única y dedicada que debe habilitarse tanto para Microsoft Teams como para Skype Empresarial y Exchange. Esta cuenta debe tener un buzón de sala hospedado en Exchange y estar habilitado como una sala de reuniones en la implementación de Teams o Skype Empresarial. En el lado de Exchange, el procesamiento del calendario debe configurarse para que el dispositivo pueda aceptar automáticamente las solicitudes de reunión entrantes. Para obtener más información sobre cómo crear estas cuentas, consulte [Configurar cuentas de Salas de Microsoft Teams.](rooms-configure-accounts.md) 

**Sugerencia profesional:** haga que los nombres para mostrar de estas cuentas descriptivos y fáciles de entender. Estos son los nombres que verán los usuarios al buscar y agregar sistemas de salas de Microsoft Teams a las reuniones. Algunas organizaciones usan el nombre para mostrar de la sala del sitio de la convención (capacidad máxima de la sala), por lo que, por ejemplo, Curie, una sala de conferencias de 12 personas en Londres, podría tener el nombre para mostrar - LON-CURIE(12)-RS. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura para sus cuentas de Salas de Microsoft Teams.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la implementación del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalación de software del dispositivo 

A la hora de planear la implementación de Salas de Microsoft Teams, tiene varias opciones para considerar instalar el software necesario. En la tabla siguiente se describen escenarios y enfoques comunes. 

| **Escenario**            | **Enfoque**         |
|-------------------------|-----------------------|   
|Implementar un número reducido de dispositivos de Salas de Microsoft Teams (<10). | Si usa salas de Microsoft Teams basadas en Surface Pro, siga las instrucciones de [instalación para una instalación por dispositivo.](console.md) [Este práctico vídeo le guiará por el proceso.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si usa una solución integrada, implemente con la imagen del proveedor y configure las opciones según sea necesario. |
| Implementar entre 10 y 50 dispositivos de un único proveedor.     | Cree una imagen basada en WIM, haga una pausa después del paso [6](console.md)de la guía y capture una imagen de distribución para usar con la tecnología de distribución de clonación.    |
| Implementar más de 50 dispositivos de Salas de Microsoft Teams, implementar dispositivos de más de un proveedor o requerir agentes específicos de la organización como parte de la implementación. | Use una plataforma de distribución y compilación de software basada en secuencia de tareas, como [Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Sugerencia profesional:** cada salas de Microsoft Teams debe tener un nombre de equipo válido y único en la red. Muchos sistemas de supervisión y alertas muestran el nombre del equipo como un identificador clave, por lo que es importante desarrollar una convención de nomenclatura para las implementaciones de Microsoft Teams Rooms que permita al personal de soporte técnico localizar fácilmente los salas de Microsoft Teams que se ha marcado como que requiere una acción. Un ejemplo podría ser usar un patrón de MTR:*nombre* del salón del sitio -  (MTR-LON-CURIE). 

Como parte de la implementación, también debe tener en cuenta su estrategia para administrar y configurar las cuentas [locales](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) creadas por el instalador de aplicaciones de Microsoft Teams Rooms.

Le proporcionamos instrucciones sobre cómo usar el Monitor de [Microsoft Azure](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para supervisar la implementación de salas de Microsoft Teams e informar sobre la disponibilidad, errores de software y hardware, y la versión de la aplicación Salas de Microsoft Teams. Si decide usar Microsoft Operations Management Suite, debe instalar el agente de Operations Management Suite como parte del proceso de instalación de software y configurar la información de conexión del área de trabajo para su área de trabajo. 

Una consideración adicional es si los salas de Microsoft Teams estarán unidos a un dominio. La información sobre las ventajas de la unión a dominios puede encontrarse en las consideraciones de unión de dominios de Sistema de sala [de Skype.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura de los salas de Microsoft Teams que se usará durante la implementación.</li><li>Decida si quiere unir los dispositivos de salas de Microsoft Teams a su dominio y cómo administrar y configurar cuentas locales. </li><li>Decida si usará el Conjunto de administración de operaciones para supervisar la implementación de salas de Microsoft Teams.</li><li>Decida qué método usará para implementar el software y los agentes en el sistema de Salas de Microsoft Teams en preparación para la implementación del dispositivo. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear el enfoque de implementación de dispositivos.</li></ul>| 


### <a name="device-deployment"></a>Implementación de dispositivos

Una vez implementado el software en las unidades de salas de Microsoft Teams, cree su plan para enviar los dispositivos y sus dispositivos periféricos asignados a sus salas y, después, continúe con la instalación y configuración. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará la implementación de sitio por sitio.</li><li> Identifique los recursos que instalarán los dispositivos de Salas de Microsoft Teams en el sitio y realicen la configuración y las pruebas.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Iniciar pruebas de dispositivo.</li></ul>| 

_Tabla de implementación de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de sala** | **Sistema de salas de Microsoft Teams**  | **Dispositivos periféricos**  | **Nombre del equipo de salas de Microsoft Teams**  | **Cuenta de recursos de Salas de Microsoft Teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | Medio        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configuración del dispositivo periférico y la aplicación Microsoft Teams Rooms 

Después de implementar físicamente cada sistema de salas de Microsoft Teams y de conectar los dispositivos periféricos admitidos, tendrá que configurar la aplicación Salas de Microsoft Teams para asignar la cuenta de recursos y la contraseña de salas de Microsoft Teams creada anteriormente para permitir que el sistema de salas de Microsoft Teams inicie sesión en Microsoft Teams o en Skype Empresarial y Exchange. Es clave aprovechar los periféricos certificados de audio y vídeo USB vinculados en otra parte del documento. Si no lo hace, puede generar un comportamiento impredecible. 

Puede configurar manualmente cada sistema de salas de Microsoft Teams. Como alternativa, puede usar un archivo de configuración XML almacenado de forma centralizada cada uno de los salas de Microsoft Teams para administrar la configuración de la aplicación y usar un script de GPO de inicio para volver a aplicar la configuración que desee, cada vez que se doble el sistema de Salas de Microsoft Teams. 

Para obtener más información sobre cómo usar el archivo de configuración XML, vea Administrar de forma remota una configuración de consola de [Microsoft Teams Rooms con un archivo de configuración XML.](xml-config-file.md) 

Puede usar [PowerShell remoto para](rooms-operations.md#remote-management-using-powershell) extraer la configuración de Salas de Microsoft Teams para crear informes de necesidades. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si configurará manualmente cada sistema de salas de Microsoft Teams o si usará un archivo XML central (uno por dispositivo de Salas de Microsoft Teams).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Defina su enfoque de administración remota.</li></ul>| 

### <a name="testing"></a> Pruebas

Una vez implementado el sistema de salas de Microsoft Teams, debería probarlo. Compruebe que las funciones enumeradas en [salas de Microsoft Teams ayudan](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) a trabajar en el dispositivo implementado. Recomendamos encarecidamente que el equipo de implementación compruebe que Microsoft Teams Rooms inicia sesión en Microsoft Operations Management Suite (si se usa). También es importante que realice varias llamadas de prueba y reuniones para comprobar la calidad. Para obtener más información, vea esta útil lista [de comprobación de la implementación.](console.md#microsoft-teams-rooms-deployment-checklist)

Le recomendamos que, como parte de la implementación general de Teams o Skype Empresarial, configure la creación de archivos para el panel de calidad de llamadas, supervisar tendencias de calidad y participar en el proceso de revisión de la calidad de la experiencia. Para obtener más información, vea [Mejorar y supervisar la calidad de las llamadas de Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, tendrá que actualizar el registro de activos con el nombre del salón, el nombre del dispositivo de salas de Microsoft Teams, la cuenta de recursos de salas de Microsoft Teams con la sesión firmada y los dispositivos periféricos asignados (y los puertos USB que usan). 

_Tabla de activos de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de sala** | **Salas de Microsoft Teams n.ó 1.**  | **Dispositivos periféricos/Nos de serie./Puertos**  | **Nombre del equipo de salas de Microsoft Teams**  | **Cuenta de servicio de Salas de Microsoft Teams**  | **Fecha de implementación** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | Medio        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


