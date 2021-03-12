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
ms.openlocfilehash: 87ded33b464d6f5248fe1fb71d579d5f191bb6b6
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726311"
---
# <a name="deployment-overview"></a>Introducción general a la implementación

La implementación de salas de Microsoft Teams básicamente se divide en fases:

- Confirmar que las ubicaciones de implementación (salas) cumplen las dependencias de implementación
- Crear cuentas de Microsoft Teams o Skype Empresarial y Exchange y asignarlas a los dispositivos de la consola (consulte Configurar cuentas para [salas de Microsoft Teams)](rooms-configure-accounts.md)
- Reimaging Microsoft Surface tablets to work as Microsoft Teams Rooms consoles (see [Configure a Microsoft Teams Rooms console](console.md) or Deploy Microsoft Teams Rooms mass deployment [guide)](rooms-scale.md)
- (Opcional) Configurar Microsoft Operations Management Suite para sus sistemas (consulte Implementar la administración de salas [de Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
- Configurar consolas en salas de reuniones y conectar los dispositivos periféricos que necesita (consulte la documentación oem de su conjunto de dispositivos)

Las tecnologías AV se pueden usar para la última tarea, pero el departamento de TI de su organización tendrá que realizar las otras partes del proceso. 


## <a name="site-readiness"></a>Preparación del sitio 

Mientras los dispositivos ordenados se entregan a su organización, trabaje con sus redes e instalaciones y equipos av para asegurarse de que se cumplen las dependencias de implementación y que cada sitio y salón está listo en términos de potencia, redes y pantalla. Además, asegúrese de que se cumplen los requisitos de instalación física. Para conocer las consideraciones de instalación física, visite el sitio del proveedor y aproveche la experiencia de su equipo de AV al instalar y montar pantallas y ejecutar cableado.

Puede obtener más información sobre estas dependencias en los siguientes vínculos de orientación de planeación:

-   [Comprobar la disponibilidad de red](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Sugerencia profesional:** si tiene la intención de usar servidores proxy para proporcionar acceso a Teams o Skype Empresarial Online, [primero revise este artículo.](../proxy-servers-for-skype-for-business-online.md) Cuando se trata de tráfico de Skype Empresarial a través de servidores proxy, se recomienda omitir los servidores proxy por completo. El tráfico de Skype Empresarial ya está cifrado, por lo que los servidores proxy no lo hacen más seguro. Como parte de su implementación más amplia, le recomendamos que siga las instrucciones de Preparar su red para [Teams](../prepare-network.md) para la planificación del ancho de banda y la evaluación de la idoneidad de su red para el tráfico en tiempo real.

|    |     |
|-----------|------------|
| ![confirmar sitios](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos clave para salas de Microsoft Teams.</li><li>Confirme que ha proporcionado ancho de banda suficiente para cada sitio.</li></ul>| 
| ![planear la implementación de dispositivos](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la configuración y la implementación del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Preparación del servicio

Para prepararse para la implementación de Salas de Microsoft Teams, realice las siguientes tareas centrales clave:

-   Definir las características de la cuenta de servicio salas de Microsoft Teams.
-   Prepare una unidad organizativa y un grupo de Active Directory para mantener sus cuentas de equipo y servicio de Salas de Microsoft Teams y, opcionalmente, prepare los objetos de directiva de grupo (GPO) para habilitar la comunicación remota de PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir características de la cuenta de servicio salas de Microsoft Teams 

En función de los escenarios de colaboración que haya decidido habilitar con la implementación de Salas de Microsoft Teams, deberá determinar las características y capacidades que asigne a cada cuenta de servicio de Salas de Microsoft Teams que habilite.

| **Escenario** | **Descripción** | **Característica de cuenta de servicio salas de Microsoft Teams** |
|---------- |------------- | --- |
| Reuniones interactivas            | Usar la voz, el vídeo y el uso compartido de pantalla; convertir las Salas de Microsoft Teams en un recurso que se puede reservar                     | Habilitado para Skype Empresarial, habilitado para Exchange (buzón de recursos) |
| Conferencia de acceso telefónico local            | Habilitar reuniones iniciadas *directamente desde* la consola salas de Microsoft Teams con coordenadas de conferencia de acceso telefónico local | Habilitado para audioconferencias                                          |
| Llamadas RTC salientes o entrantes | Habilitar la consola salas de Microsoft Teams para realizar y recibir llamadas RTC                                         | Habilitado para sistema telefónico                                                |

Para obtener más información sobre las cuentas de Salas de Microsoft Teams, vea [Configurar cuentas para salas de Microsoft Teams.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![compatibilidad con escenarios](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida qué escenarios admitirá e identifique los requisitos de licencia para sus cuentas de servicio de Salas de Microsoft Teams.</li></ul>| 
| ![preparar el equipo host](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepararse para hospedar cuentas de máquina y servicio.</li></ul>| 


_Tabla de planificación de cuentas de servicio de Microsoft Teams Rooms de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Capacidades de sala futuras**                                                 | **Características de la cuenta salas de Microsoft Teams**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Sede de Londres | Curie         | Medio        | 1 pantalla, audio y vídeo más presentación <br>Acceso a conferencias de acceso telefónico local<br> Acceso RTC  | Habilitado para Skype Empresarial, habilitado para Exchange (buzón de recursos) <br>Habilitado para audioconferencias <br>Habilitado para sistema telefónico |
| Sydney HQ | Hill          | Grande         | 2 pantallas, audio y vídeo más presentación<br>Acceso a conferencias de acceso telefónico local<br> Acceso RTC  | Habilitado para Skype Empresarial, habilitado para Exchange (buzón de recursos)<br> Habilitado para audioconferencias <br>Habilitado para sistema telefónico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Prepararse para hospedar cuentas de equipo y servicio de Salas de Microsoft Teams (opcional)

Para que pueda administrar e informar sobre su equipo y cuentas de servicio de Salas de Microsoft Teams, prepare sus cuentas locales de Active Directory o Azure Active Directory (Azure AD). 

Defina un grupo local de Active Directory o Azure AD para agregar todas las cuentas de servicio (usuario) de Salas de Microsoft Teams y, a continuación, cree informes de uso con el cmdlet de PowerShell de Get-CSUserSession en la implementación de Salas de Microsoft Teams. Por ejemplo, cree un grupo denominado SkypeRoomSystemsv2-Service-Accounts. 


Defina una unidad organizativa en su jerarquía local de Active Directory o Azure AD para que tenga todas las cuentas de equipo de Salas de Microsoft Teams (si están unidas al dominio) y una unidad organizativa para mantener todas las cuentas de usuario de Salas de Microsoft Teams. Si crea una unidad organizativa para las cuentas de equipo salas de Microsoft Teams, considere deshabilitar la herencia para asegurarse de que solo aplica las directivas que pretendía aplicar a los salas de Microsoft Teams unidos al dominio. 

Cree un objeto de directiva de grupo asignado a la unidad de organización que contiene las cuentas de equipo de Salas de Microsoft Teams. Use esta opción para: 

-   [Establecer la configuración de la cuenta local y de energía.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Habilitar Windows Update.
-   Habilitar la comunicación remota de PowerShell. Puede configurar un script de inicio para ejecutar un script: Enable-PSRemoting -Force

Puede usar PowerShell para realizar varias actividades de administración remota, como obtener y configurar información de configuración. La comunicación remota de  PowerShell debe habilitarse antes de que se pueda llevar a cabo cualquier administración remota de PowerShell y debe considerarse como parte de los procesos de implementación o configurarse a través de la directiva de grupo. Para obtener más información sobre estas capacidades y habilitarlas, vea [Mantenimiento y operaciones.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configuración e implementación 

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

-   Aprovisionamiento de cuentas
-   Instalación del software del dispositivo
-   Implementación de dispositivos
-   Configuración de dispositivos periféricos y aplicaciones de Microsoft Teams Rooms
-    Pruebas
-   Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de cuentas 

Cada dispositivo de Salas de Microsoft Teams requiere una cuenta de recursos dedicada y única que debe estar habilitada tanto para Microsoft Teams como para Skype Empresarial y Exchange. Esta cuenta debe tener un buzón de sala hospedado en Exchange y estar habilitado como sala de reuniones en la implementación de Teams o Skype Empresarial. En el lado de Exchange, el procesamiento del calendario debe configurarse para que el dispositivo pueda aceptar automáticamente las solicitudes de reunión entrantes. Para obtener más información sobre cómo crear estas cuentas, vea [Configurar cuentas para salas de Microsoft Teams.](rooms-configure-accounts.md) 

**Sugerencia profesional:** haga que los nombres para mostrar de estas cuentas describen y comprendan fácilmente. Estos son los nombres que verán los usuarios al buscar y agregar sistemas de salas de Microsoft Teams a las reuniones. Algunas organizaciones usan el nombre del salón del sitio de la convención (capacidad máxima de sala)-RS, por lo que, por ejemplo, Curie,una sala de conferencias de 12 personas en Londres, podría tener el nombre para mostrar - LON-CURIE(12)-RS. 

|    |     |
|-----------|------------|
| ![decidir convención de nomenclatura](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura para sus cuentas de Salas de Microsoft Teams.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>| 
| ![pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la implementación del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalación del software del dispositivo 

Al planear la implementación de Salas de Microsoft Teams, tiene muchas opciones que considerar para instalar el software necesario. Los escenarios y enfoques comunes se describen en la tabla siguiente. 

| **Escenario**            | **Enfoque**         |
|-------------------------|-----------------------|   
|Implementar algunos dispositivos de Microsoft Teams Rooms (<10). | Si usa salas de Microsoft Teams basadas en Surface Pro, siga las instrucciones [de instalación para una instalación por dispositivo.](console.md) [Este práctico vídeo le guiará por el proceso.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si usa una solución integrada, implemente con la imagen del proveedor y configure la configuración según sea necesario. |
| Implementar entre 10 y 50 dispositivos de un único proveedor.     | Cree una imagen basada en WIM, haga una pausa después del paso [6](console.md)en las instrucciones y capture una imagen de distribución que se usará con la tecnología de distribución de clonación.    |
| Implementar más de 50 dispositivos de Salas de Microsoft Teams, implementar dispositivos de más de un proveedor o requerir agentes específicos de la organización como parte de la implementación. | Use una plataforma de distribución y compilación de software basada en secuencia de tareas, como [Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Sugerencia profesional:** cada salas de Microsoft Teams debe tener un nombre de equipo válido y único en la red. Muchos sistemas de supervisión y alertas muestran el nombre del equipo como un identificador de clave, por lo que es importante desarrollar una convención de nomenclatura para las implementaciones de Salas de Microsoft Teams que permita al personal de soporte técnico localizar fácilmente los salas de Microsoft Teams que se han marcado como que requieren una acción. Un ejemplo puede ser usar un patrón de MTR-*Nombre del* salón - *de sitio* (MTR-LON-CURIE). 

Como parte de la implementación, también tendrá que considerar su estrategia para administrar y configurar las cuentas [locales](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) creadas por el instalador de aplicaciones salas de Microsoft Teams.

Proporcionamos instrucciones sobre cómo usar el Monitor de [Microsoft Azure](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para supervisar la implementación de Salas de Microsoft Teams e informar sobre la disponibilidad, los errores de hardware y software y la versión de la aplicación Salas de Microsoft Teams. Si decide usar Microsoft Operations Management Suite, debe instalar el agente de Operations Management Suite como parte del proceso de instalación del software y configurar la información de conexión del área de trabajo para el área de trabajo. 

Una consideración adicional es si los salas de Microsoft Teams se unirán al dominio. Encontrará información sobre las ventajas de la unión de dominios en las consideraciones de unión a dominios de Sistema de [salón de Skype.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![nombres de dispositivos de puntos de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura de dispositivos de Microsoft Teams Rooms que se usará durante la implementación.</li><li>Decida si se unirá a los dispositivos de Salas de Microsoft Teams a su dominio y cómo administrar y configurar cuentas locales. </li><li>Decida si usará Operations Management Suite para supervisar la implementación de Salas de Microsoft Teams.</li><li>Decida qué método usará para implementar el software y los agentes en el sistema salas de Microsoft Teams en preparación para la implementación del dispositivo. </li></ul>| 
| ![dispositivo de plan de pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear el enfoque de implementación de dispositivos.</li></ul>| 


### <a name="device-deployment"></a>Implementación de dispositivos

Después de implementar el software en las unidades salas de Microsoft Teams, cree su plan para enviar los dispositivos y sus dispositivos periféricos asignados a sus salas y, a continuación, continúe con la instalación y configuración. 


|    |     |
|-----------|------------|
| ![administrar la implementación de sitio a sitio](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará la implementación de sitio por sitio.</li><li> Identifique los recursos que instalarán los dispositivos microsoft Teams Rooms en el sitio y realice la configuración y las pruebas.</li></ul>| 
| ![iniciar pruebas de dispositivos](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Iniciar pruebas de dispositivos.</li></ul>| 

_Tabla de implementación de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Sistema salas de Microsoft Teams**  | **Dispositivos periféricos**  | **Nombre del equipo de Microsoft Teams Rooms**  | **Cuenta de recursos salas de Microsoft Teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Sede de Londres | Curie         | Medio        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configuración de dispositivos periféricos y aplicaciones de Microsoft Teams Rooms 

Después de implementar físicamente cada sistema salas de Microsoft Teams y conectar los dispositivos periféricos compatibles, deberá configurar la aplicación Salas de Microsoft Teams para asignar la cuenta de recursos y la contraseña de Salas de Microsoft Teams creadas anteriormente, para permitir que el sistema salas de Microsoft Teams inicie sesión en Microsoft Teams o Skype Empresarial y Exchange. Es clave aprovechar periféricos de audio y vídeo USB certificados vinculados en otra parte del documento. No hacerlo puede provocar un comportamiento impredecible. 

Puede configurar manualmente cada sistema de salas de Microsoft Teams. Como alternativa, puede usar un archivo de configuración XML de Salas de Microsoft Teams almacenado de forma centralizada para administrar la configuración de la aplicación y aprovechar un script de GPO de inicio para volver a aplicar la configuración que desee, cada vez que se inicie el sistema salas de Microsoft Teams. 

Para obtener más información sobre cómo usar el archivo de configuración XML, vea Administrar una configuración de consola de Microsoft Teams Rooms de forma [remota con un archivo de configuración XML.](xml-config-file.md) 

Puede usar [PowerShell remoto](rooms-operations.md#remote-management-using-powershell) para extraer la configuración de Salas de Microsoft Teams para informar de las necesidades. 

|    |     |
|-----------|------------|
| ![configurar el punto de decisión](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si configurará manualmente cada sistema salas de Microsoft Teams o usará un archivo XML central (uno por dispositivo de Salas de Microsoft Teams).</li></ul>| 
| ![enfoque remoto de los pasos siguientes](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Definir el enfoque de administración remota.</li></ul>| 

### <a name="testing"></a> Pruebas

Después de implementar el sistema salas de Microsoft Teams, debe probarlo. Compruebe que las funcionalidades enumeradas en la ayuda de Salas de [Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) están funcionando en el dispositivo implementado. Se recomienda encarecidamente que el equipo de implementación compruebe que los salas de Microsoft Teams inician sesión en El conjunto de aplicaciones de administración de operaciones de Microsoft (si se usa). También es importante que realice una serie de llamadas de prueba y reuniones para comprobar la calidad. Para obtener más información, vea esta lista [de comprobación de implementación útil.](console.md#microsoft-teams-rooms-deployment-checklist)

Le recomendamos que, como parte de la implementación general de Teams o Skype Empresarial, configure la creación de archivos para el Panel de calidad de llamadas (CQD), supervise las tendencias de calidad y participe en el proceso de revisión de calidad de la experiencia. Para obtener más información, vea [Mejorar y supervisar la calidad de las llamadas de Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, querrá actualizar el registro de activos con el nombre de la sala, el nombre del dispositivo Salas de Microsoft Teams, la cuenta de recursos salas de Microsoft Teams que ha iniciado sesión y los dispositivos periféricos asignados (y los puertos USB que usan). 

_Tabla de activos de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Microsoft Teams Rooms no en serie.**  | **Dispositivos periféricos/ números de serie./ Puertos**  | **Nombre del equipo de Microsoft Teams Rooms**  | **Cuenta de servicio salas de Microsoft Teams**  | **Fecha implementada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Sede de Londres | Curie         | Medio        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


