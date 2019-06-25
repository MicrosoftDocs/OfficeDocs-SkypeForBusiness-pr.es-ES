---
title: Implementar salas de Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este artículo para obtener información sobre la implementación de salas de Microsoft Teams.
ms.openlocfilehash: 4af4412d65fa74532b04ad5abb63326ee4c7c58b
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198480"
---
# <a name="deployment-overview"></a>Introducción general a la implementación

La implementación de salas de Microsoft Teams se divide esencialmente en fases:

- Confirmar que las ubicaciones de implementación (salas) cumplen las dependencias de implementación
- Crear cuentas de Microsoft Teams o Skype empresarial y de Exchange y asignarlos a los dispositivos de consola (consulte [configurar cuentas para salas de Microsoft Teams](room-systems-v2-configure-accounts.md))
- Volver a Imaging Microsoft Surface tablets para trabajar como consolas de salas de Microsoft Teams (consulte [configurar una consola de salas de Microsoft Teams](console.md) o implementar la [Guía de implementación masiva de salones de Microsoft](room-systems-scale.md)Teams)
- Faculta Configuración de Microsoft Operations Management Suite para sus sistemas (consulte implementación de la [Administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md)
- Configurar consolas en salas de reuniones y conectar los dispositivos periféricos que necesita (consulte la documentación de OEM de su conjunto de dispositivos)

Se pueden usar Tech Techs para la última tarea, pero el Departamento de TI de su organización tendrá que realizar las otras partes del proceso. 


## <a name="site-readiness"></a>Disponibilidad del sitio 

Mientras los dispositivos ordenados se entreguen a su organización, trabaje con su equipo de redes e instalaciones y equipos de AV para asegurarse de que se cumplan las dependencias de implementación y de que todos los sitios y salas estén listos en términos de energía, redes y pantalla. Además, asegúrese de que se cumplan los requisitos de instalación física. Para tener en cuenta las consideraciones de instalación física, visite el sitio del proveedor y aproveche la experiencia de su equipo antivirus al instalar y montar pantallas y cableado.

Puede obtener más información sobre estas dependencias en los vínculos de la guía de planificación a continuación:

-   [Comprobar la disponibilidad de red](srs-v2-prep.md#check-network-availability) 
-   [Certificados](srs-v2-prep.md#certificates)
-   [Proxy](srs-v2-prep.md#proxy)

**Sugerencia** : Si tiene previsto usar servidores proxy para proporcionar acceso a Microsoft Teams o a Skype empresarial online, primero [revise este artículo](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Tenga en cuenta que cuando se trata de tráfico de Skype empresarial por servidores proxy, se recomienda omitir los servidores proxy por completo. El tráfico de Skype empresarial ya está cifrado, por lo que los servidores proxy no lo hacen más seguro. Como parte de su implementación más amplia, le recomendamos que siga las instrucciones de [evaluar mi entorno](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) para planear el ancho de banda y evaluar la idoneidad de su red para el tráfico en tiempo real.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que sus sitios cumplen los requisitos clave para salas de Microsoft Teams.</li><li>Confirme que ha proporcionado suficiente ancho de banda para cada sitio.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comience a planificar la implementación y la configuración del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Preparación del servicio

Para prepararse para la implementación de salas de Microsoft Teams, haga lo siguiente:

-   Defina las características de la cuenta de servicio salas de Microsoft Teams.
-   Prepare una unidad organizativa y un grupo de Active Directory para almacenar las cuentas de equipo y de servicio de Microsoft Teams y, opcionalmente, preparar objetos de directiva de grupo (GPO) para habilitar la comunicación remota de PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir las características de la cuenta de servicio salas de Microsoft Teams 

En función de los escenarios de colaboración que haya decidido habilitar con la implementación de salas de Microsoft Teams, tendrá que determinar las características y capacidades que asigne a cada cuenta de servicio salas de Microsoft teams que habilite.

| **Escenario** | **Descripción** | **Característica de cuenta de servicio de salas de Microsoft Teams** |
|---------- |------------- | --- |
| Reuniones interactivas            | Usar la voz, el vídeo y la pantalla compartida; Cómo convertir las salas de Microsoft Teams en un recurso de bookable                     | Habilitado para Skype empresarial, habilitado para Exchange (buzón de recursos) |
| Conferencia de acceso telefónico local            | Habilitar reuniones iniciadas *directamente* desde la consola de salas de Microsoft Teams con las coordenadas de conferencia de acceso telefónico local | Habilitado para conferencias de audio                                          |
| Llamadas RTC entrantes o salientes | Habilitar la consola de salones de Microsoft Teams para realizar y recibir llamadas RTC                                         | Habilitado para el sistema telefónico                                                |

Para obtener más información sobre las cuentas de salas de Microsoft Teams, vea [configurar cuentas para salas de Microsoft Teams](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida qué escenarios admitirá e identifique los requisitos de licencias para las cuentas de servicio de salas de Microsoft Teams.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepararse para hospedar cuentas de equipo y de servicio.</li></ul>| 


_Ejemplo de tabla de planeación de cuentas de servicio de salones de Microsoft Teams_

| **Sitio**  | **Nombre del salón** | **Tipo de habitación** | **Capacidades de la sala en el futuro**                                                 | **Características de la cuenta salas de Microsoft Teams**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| HQ de Londres | Curie         | Medio        | 1 Presentación de pantalla, audio y vídeo <br>Acceso a conferencias de acceso telefónico local<br> Acceso a través de RTC  | Habilitado para Skype empresarial, habilitado para Exchange (buzón de recursos) <br>Habilitado para conferencias de audio <br>Habilitado para el sistema telefónico |
| HQ de Sydney | Arrancar          | Grande         | 2 pantallas, presentación de audio y vídeo Plus<br>Acceso a conferencias de acceso telefónico local<br> Acceso a través de RTC  | Habilitado para Skype empresarial, habilitado para Exchange (buzón de recursos)<br> Habilitado para conferencias de audio <br>Habilitado para el sistema telefónico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Prepararse para hospedar las cuentas de servicio y máquina de las salas de Microsoft Teams (opcional)

Para habilitar la administración y el informe de las cuentas de servicio y del equipo de las salas de Microsoft Teams, prepare su Active Directory local o Azure Active Directory (Azure AD). 

Defina un Active Directory local o un grupo de Azure AD para agregar todas las cuentas del servicio de salones de Microsoft Teams (usuario) a y, a continuación, cree informes de uso mediante el cmdlet de PowerShell Get-CSUserSession en la implementación de Microsoft Teams Rooms. Por ejemplo, cree un grupo denominado SkypeRoomSystemsv2-Service-accounts. 


Defina una unidad organizativa en su jerarquía de Active Directory o de Azure AD local para mantener las cuentas de equipo de las salas de Microsoft Teams (si se han unido al dominio) y una unidad organizativa que contenga todas las cuentas de usuario de salas de Microsoft Teams. Si crea una unidad organizativa para las cuentas de equipos de las salas de Microsoft Teams, considere la posibilidad de deshabilitar la herencia para asegurarse de que aplica solo las directivas que pretendías aplicar a las salas de Microsoft Teams Unidas al dominio. 

Cree un objeto de directiva de grupo asignado a la unidad de la organización que contiene las cuentas de equipo de las salas de Microsoft Teams. Use esta para: 

-   [Establecer la configuración de la cuenta local y de la energía](room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Habilitar Windows Update.
-   Habilitar la comunicación remota de PowerShell. Puede configurar un script de inicio para que ejecute un script simple: enable-PSRemoting-Force

Puede usar PowerShell para realizar una serie de actividades de administración remota, entre las que se incluye la obtención y configuración de la información de configuración. La comunicación remota de PowerShell debe habilitarse *antes* de que se pueda realizar la administración remota de PowerShell y debe considerarse como parte de los procesos de implementación o configurarse mediante la Directiva de grupo. Para obtener más información sobre estas funciones y habilitarlas, consulte [mantenimiento y operaciones](room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuración e implementación 

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

-   Aprovisionamiento de la cuenta
-   Instalación del software del dispositivo
-   Implementación de dispositivos
-   Configuración de dispositivos periféricos y aplicaciones de salas de Microsoft Teams
-    Pruebas
-   Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de la cuenta 

Cada dispositivo de salas de Microsoft Teams necesita una cuenta de recursos exclusiva y exclusiva que deba habilitarse para Microsoft Teams o Skype empresarial y Exchange. Esta cuenta debe tener un buzón de sala hospedado en Exchange y habilitarse como sala de reuniones en la implementación de Teams o Skype empresarial. En el lado de Exchange, el procesamiento del calendario se debe configurar para que el dispositivo pueda aceptar automáticamente las convocatorias de reunión entrantes. Para obtener más información sobre la creación de estas cuentas, vea [configurar cuentas para salas de Microsoft Teams](room-systems-v2-configure-accounts.md). 

**Sugerencia Pro** : haga que los nombres para mostrar de estas cuentas sean descriptivos y sean fáciles de comprender. Estos son los nombres que los usuarios verán al buscar y agregar sistemas de salas de Microsoft Teams a reuniones. Algunas organizaciones usan el*nombre del salón*de *sitio*-de la Convención (*capacidad máxima*de la sala)-RS, por lo que, por ejemplo Curie, un salón de conferencia de 12 personas en Londres, puede tener el nombre para mostrar Lon-Curie (12)-RS. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la Convención de nomenclatura para sus cuentas de salas de Microsoft Teams.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comience a planificar la implementación del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalación del software del dispositivo 

Al planear la implementación de salas de Microsoft Teams, dispone de varias opciones para instalar el software requerido. En la tabla siguiente se describen los escenarios y métodos comunes. 

| **Escenario**            | **Llegando**         |
|-------------------------|-----------------------|   
|Implementar un pequeño número de dispositivos de salas de Microsoft Teams (<10). | Si usa salas de Microsoft Teams basadas en Surface Pro, siga las [instrucciones de instalación para una instalación por dispositivo](console.md). [Este práctico vídeo le guiará a través del proceso.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si usa una solución integrada, implemente con la imagen del proveedor y configure las opciones según sea necesario. |
| Implementar entre 10 y 50 dispositivos de un solo proveedor.     | Cree una imagen basada en WIM, PAUSE después del [paso 6 de la guía](console.md)y Capture una imagen de distribución para usarla con su tecnología de distribución de clonación.    |
| Implementar más de 50 dispositivos de salas de Microsoft Teams, implementar dispositivos de más de un proveedor o requerir agentes específicos de la organización como parte de la implementación. | Usar una plataforma de creación y distribución de software basada en secuencia de tareas, como [System Center Configuration Manager](room-systems-scale.md).  |

**Sugerencia Pro** : cada sala de Microsoft Teams debe tener un nombre de equipo válido y único en su red. Muchos sistemas de supervisión y alerta muestran el nombre de la máquina como un identificador de clave, por lo que es importante desarrollar una Convención de nomenclatura para las implementaciones de salas de Microsoft teams que permita al personal de soporte localizar fácilmente las salas de Microsoft teams que se han marcado como requerir una acción. Un ejemplo podría estar usando un patrón de MTR-*site*-*Room Name* (MTR-Lon-Curie). 

Como parte de la implementación, también debe considerar su estrategia para administrar y configurar las [cuentas locales](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) creadas por el instalador de la aplicación salas de Microsoft Teams.

Le proporcionamos instrucciones sobre cómo usar [Microsoft Azure monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para supervisar la implementación de salas de Microsoft Teams y el informe sobre disponibilidad, errores de hardware y software, y versión de la aplicación salas de Microsoft Teams. Si decide usar Microsoft Operations Management Suite, debe instalar el agente de Operations Management Suite como parte del proceso de instalación del software y configurar la información de conexión del área de trabajo para su área de trabajo. 

Otra consideración es si las salas de Microsoft Teams se unen al dominio. Puede encontrar información sobre las ventajas de las uniones de dominios en las [consideraciones relativas al dominio del sistema Room de Skype](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la Convención de nomenclatura de dispositivos de Microsoft Team Rooms que se utilizará durante la implementación.</li><li>Decida si unirá los dispositivos de salas de Microsoft Teams a su dominio y cómo administrar y configurar cuentas locales. </li><li>Decida si va a usar Operations Management Suite para supervisar la implementación de salas de Microsoft Teams.</li><li>Decida qué método usará para implementar el software y los agentes en el sistema de salas de Microsoft Teams en preparación para la implementación del dispositivo. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comience a planificar el método de implementación de dispositivos.</li></ul>| 


### <a name="device-deployment"></a>Implementación de dispositivos

Una vez que haya implementado el software en las unidades de salas de Microsoft Teams, cree su plan para enviar los dispositivos y sus dispositivos periféricos asignados a sus salas y, a continuación, proceda con la instalación y la configuración. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir quién administrará la implementación sitio a sitio.</li><li> Identifique los recursos que instalarán los dispositivos de salas de Microsoft Teams en el sitio y lleven a cabo la configuración y las pruebas.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Inicie las pruebas del dispositivo.</li></ul>| 

_Tabla de implementación de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de habitación** | **Sistema de salas de Microsoft Teams**  | **Dispositivos periféricos**  | **Nombre del equipo de las salas de Microsoft Teams**  | **Cuenta de recursos de salas de Microsoft Teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| HQ de Londres | Curie         | Medio        |                                   |                  |                                          |                                             |
| HQ de Sydney | Arrancar          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configuración de dispositivos periféricos y aplicaciones de salas de Microsoft Teams 

Una vez que se haya implementado físicamente cada sistema de salas de Microsoft Teams y los dispositivos periféricos compatibles estén conectados, tendrá que configurar la aplicación salas de Microsoft Teams para asignar la cuenta de recursos de las salas de Microsoft Teams y la contraseña creada anteriormente. , para habilitar el sistema Microsoft Teams Rooms para iniciar sesión en Microsoft Teams o Skype empresarial y Exchange. Es clave para aprovechar los periféricos de audio y vídeo USB certificados que se encuentran en otra parte del documento. Si no lo hace, puede provocar un comportamiento impredecible. 

Puede configurar manualmente cada sistema de salas de Microsoft Teams. Como alternativa, puede usar un archivo de configuración XML de las salas de almacenamiento centralizado por Microsoft Teams para administrar la configuración de la aplicación y aprovechar un script de inicio de sesión de GPO para volver a aplicar la configuración que desee cada vez que se inicie el sistema de salas de Microsoft Teams. 

Para obtener más información sobre cómo usar el archivo de configuración XML, consulte [administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML](xml-config-file.md). 

Puede usar [PowerShell remoto](room-systems-v2-operations.md#remote-management-using-powershell) para extraer la configuración de salas de Microsoft Teams para informar de las necesidades. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si va a configurar manualmente cada sistema de salas de Microsoft Teams o usar un archivo XML central (uno por dispositivo de salas de Microsoft Teams).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Defina su enfoque de administración remota.</li></ul>| 

### <a name="testing"></a> Pruebas

Después de implementar el sistema de salas de Microsoft Teams, debe probarlo. Compruebe que las funciones que se enumeran en la [ayuda de Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estén trabajando en el dispositivo implementado. Recomendamos encarecidamente que el equipo de implementación Verifique que las salas de Microsoft Teams estén iniciando sesión en Microsoft Operations Management Suite (si se usa). También es importante que realices una serie de llamadas y reuniones de prueba para comprobar la calidad. Para obtener más información, consulte esta [útil lista de comprobación de implementación](console.md#microsoft-teams-rooms-deployment-checklist).

Le recomendamos que, como parte de los equipos generales o de la implementación de Skype empresarial, configure los archivos de compilación para el panel de calidad de llamadas (CQD), tendencias de calidad del monitor y participe en el proceso de revisión de la calidad de la experiencia. Para obtener más información, consulta la [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide). 

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, deseará actualizar el registro de activos con el nombre del salón, el nombre del dispositivo de las salas de Microsoft Teams, la cuenta de recursos de salas de Microsoft Teams en la que ha iniciado sesión y los dispositivos periféricos asignados (y los puertos USB que usan). 

_Tabla de activos de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de habitación** | **Número de serie de salas de Microsoft Teams**  | **Dispositivos periféricos/números de serie/puertos serie**  | **Nombre del equipo de las salas de Microsoft Teams**  | **Cuenta de servicio de salones de Microsoft Teams**  | **Fecha de implementación** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| HQ de Londres | Curie         | Medio        |                                          |                                          |                                          |                                            |                   |
| HQ de Sydney | Arrancar          | Grande         |                                          |                                          |                                          |                                            |                   |


