---
title: Implementación de salas de equipos de Microsoft
ms.author: Turgayo
author: Turgayo
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este artículo para obtener más información sobre la implementación de salas de equipos de Microsoft.
ms.openlocfilehash: c005f9c0bdd087c90746ff55a322a087da83032e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214901"
---
# <a name="deployment-overview"></a>Introducción general a la implementación

Implementación de salones de los equipos de Microsoft básicamente se divide en fases:

- Para confirmar que las ubicaciones de implementación (salones) cumplen las dependencias de implementación
- Creación de Skype para cuentas empresariales y de Exchange y asignarlos a los dispositivos de consola (vea [Configurar cuentas para salas de equipos de Microsoft](room-systems-v2-configure-accounts.md))
- Restaurar Microsoft Surface tabletas para que funcionen como consolas de salas de equipos de Microsoft (vea [Configure una consola de salas de equipos de Microsoft](console.md) o la [Guía de implementación de masa de implementar salones de los equipos de Microsoft](room-systems-scale.md))
- (Opcional) Configuración de conjunto de aplicaciones de administración de operaciones de Microsoft para los sistemas (consulte [administración de implementación de salas de equipos de Microsoft con el Monitor de Azure](azure-monitor.md))
- Configuración de consolas en las salas de reuniones y conectar los dispositivos periféricos que necesita (consulte la documentación de OEM para el conjunto de dispositivos)

Técnicos de AV se pueden usar para la última tarea, pero la organización necesita hacer las demás partes del proceso de departamento de TI. 


## <a name="site-readiness"></a>Preparación del sitio 

Mientras se entregan los dispositivos ordenados en su organización, trabajar con su red y las instalaciones y equipos de AV para asegurarse de que se cumplen las dependencias de implementación y cada sitio y sala está listo en términos de alimentación, redes y mostrar. Además, asegúrese de que se cumplen los requisitos de instalación física. Las consideraciones de instalación física, visite el sitio del proveedor y sacar provecho de la experiencia de su equipo de AV al instalar y pantallas de montaje y ejecuta cableado.

Puede encontrar más información acerca de estas dependencias en los siguientes vínculos planeación instrucciones:

-   [Comprobar la disponibilidad de red](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#check-network-availability) 
-   [Certificados](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#certificates)
-   [Proxy](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#proxy)

**Sugerencia pro** - si va a utilizar los servidores proxy para proporcionar acceso a los equipos o Skype de negocio en línea, primero [Revise este artículo](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Tenga en cuenta que cuando se trata de Skype para el tráfico de negocios a través de servidores proxy, se recomienda no usar servidores proxy por completo. Skype para el tráfico de negocio ya está cifrada, por lo que los servidores proxy no que sea más seguro. Como parte de su Skype más amplia para la implementación empresarial, se recomienda que siga las instrucciones en [evaluar mi entorno](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) de ancho de banda de planeación y evaluación de idoneidad de su red para el tráfico en tiempo real. Para todo el planeamiento de ancho de banda, use el [Organizador de la red de MyAdvisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). (Se recomienda crear un rol de salas de equipos de Microsoft para reflejar el uso previsto de salas de equipos de Microsoft [vídeo, uso compartido de la pantalla, audio] y asignar a un número de usuarios que coincide con el número de unidades locales de los equipos de Microsoft se implemente en cada sitio). 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos claves para salas de equipos de Microsoft.</li><li>Confirme que ha proporcionado suficiente ancho de banda para cada sitio.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empezar a planear la configuración y la implementación de dispositivos.</li></ul>| 

**Sugerencia Pro-** Desde una perspectiva de planeación de sitio por sitio, que podrían resultarle útiles los siguientes activos. Deben cubren algo más que los salones de los equipos de Microsoft y se pueden usar en una implementación completa de Skype para empresarial en línea:

-   [Guía de entrega de planeación implantación y migración del sitio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [Sitio de implantación y planificación de la migración - guía](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > En la guía, complete las tareas en la sección "4.3 – > salas de conferencias" en la hoja de "4-extremos" para cada sitio donde va a implementar dispositivos de salas de equipos de Microsoft. Esto le permitirá usar la cuenta de forma masiva script más adelante en el proceso de aprovisionamiento. 

## <a name="service-readiness"></a>Preparación del servicio

Para prepararse para la implementación de salas de equipos de Microsoft, realice la siguiente clave, tareas centrales:

-   Defina las funciones de cuenta de servicio de salas de equipos de Microsoft.
-   Preparar una unidad organizativa y grupo de Active Directory para mantener el equipo de salas de equipos de Microsoft y las cuentas de servicio y, opcionalmente, preparar objetos de directiva de grupo (GPO) para habilitar la comunicación remota de PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir las características de cuenta de servicio de salas de equipos de Microsoft 

En función de los escenarios de colaboración que ha decidido habilitar con la implementación de salas de equipos de Microsoft, deberá determinar las características y capacidades que asignar a cada cuenta de servicio de salas de equipos de Microsoft que se habilite.

| **Escenario** | **Descripción** | **Característica de cuenta de servicio de salas de equipos de Microsoft** |
|---------- |------------- | --- |
| Reuniones interactivas            | Uso de voz, vídeo y uso compartido de pantalla; hacer que las salas de los equipos de Microsoft un recurso bookable                     | Habilitado para Skype para la empresa, habilitado para Exchange (buzón de recursos) |
| Conferencia de acceso telefónico local            | Habilitar reuniones iniciarse *directamente* desde la consola de salas de equipos de Microsoft con las coordenadas de la conferencia de acceso telefónico | Habilitado para conferencias de Audio                                          |
| Llamar a RTC de salida o entrada | Habilitar la consola de salas de equipos de Microsoft para realizar y recibir llamadas de RTC                                         | Habilitado para el sistema telefónico                                                |

Para obtener más información acerca de las cuentas locales de los equipos de Microsoft, consulte [Configurar cuentas para salas de equipos de Microsoft](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir qué escenarios se admiten e identificar requisitos de licencia para las cuentas de servicio de salas de equipos de Microsoft.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Preparación para hospedar la máquina y las cuentas de servicio.</li></ul>| 


_Cuenta de servicio de ejemplo salones de los equipos de Microsoft planeación de tabla_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Capacidades de sala futuras**                                                 | **Características de la cuenta de salas de equipos de Microsoft**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| HQ de Londres | Curie         | Medio        | 1 pantalla, audio y vídeo plus presentación <br>Acceso telefónico<br> Acceso de RTC  | Habilitado para Skype para la empresa, habilitado para Exchange (buzón de recursos) <br>Habilitado para conferencias de Audio <br>Habilitado para el sistema telefónico |
| HQ Sidney | Hill          | Grande         | 2 pantallas, audio y vídeos plus presentación<br>Acceso telefónico<br> Acceso de RTC  | Habilitado para Skype para la empresa, habilitado para Exchange (buzón de recursos)<br> Habilitado para conferencias de Audio <br>Habilitado para el sistema telefónico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparación para hospedar la máquina de salas de equipos de Microsoft y (opcionales) de las cuentas de servicio

Para poder administrar e informar sobre sus salones de los equipos de Microsoft cuentas de servicio y equipos, preparar su local de Active Directory o Azure Active Directory (AD Azure). 

Definir un grupo de Active Directory o Azure AD local para agregar todas las cuentas de servicio (usuario) de salas de equipos de Microsoft a y, a continuación, crear informes de uso mediante el cmdlet Get-CSUserSession PowerShell a través de la implementación de salas de equipos de Microsoft. Por ejemplo, cree un grupo denominado SkypeRoomSystemsv2 cuentas de servicio. 


Defina una unidad organizativa en la jerarquía de Active Directory o Azure AD local para contener todas las cuentas de máquina de salas de equipos de Microsoft (si se está unido al dominio) y una unidad organizativa para que contenga todas las cuentas de usuario de salas de equipos de Microsoft. Si crea una unidad organizativa para las cuentas de máquina de salas de equipos de Microsoft, considere la posibilidad de deshabilitar la herencia para asegurarse de que se aplican sólo a las directivas pensado para aplicar a las salas de los equipos de Microsoft unido a un dominio. 

Crear un objeto de directiva de grupo asignado a la unidad organizativa que contiene las cuentas de equipo de salas de equipos de Microsoft. Utilice esta página para: 

-   [Establecer la energía y la configuración de la cuenta local](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Habilitar la actualización de Windows.
-   Habilitar la comunicación remota de PowerShell. Puede configurar un script de inicio para ejecutar una secuencia de comandos simple: Enable-PSRemoting - Force

Puede usar PowerShell para llevar a cabo un número de actividades de administración remota, incluidas la obtención y definición de información de configuración. Comunicación remota de PowerShell debe ser habilitado *antes de* cualquier PowerShell administración remota puede tardar colocar y se deben considerar como parte de los procesos de implementación o configurados a través de directiva de grupo. Para obtener más información acerca de estas funciones y permitirles, vea [operaciones y mantenimiento](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuración e implementación 

Planeación de configuración e implementación trata las siguientes áreas clave:

-   Aprovisionamiento de cuentas
-   Instalación de software de dispositivo
-   Implementación de dispositivos
-   Aplicación de salas de equipos de Microsoft y la configuración de dispositivo periférico
-    Pruebas
-   Administración de activos

### <a name="account-provisioning"></a>Aprovisionamiento de cuentas 

Cada dispositivo de salas de equipos de Microsoft requiere una cuenta de recurso dedicado y únicos que debe estar habilitada para ambos Skype para empresas y Exchange. Esta cuenta debe tener un buzón de sala hospedado en Exchange y estar habilitada como una sala de reuniones en la Skype para la implementación de la empresa. En el lado de Exchange, debe configurarse el procesamiento del calendario para que el dispositivo puede aceptar automáticamente convocatorias de reunión entrantes. Para obtener más información acerca de cómo crear estas cuentas, vea [Configurar cuentas para salas de equipos de Microsoft](room-systems-v2-configure-accounts.md). 

**Sugerencia pro** – Asegúrese de nombres de la presentación para estas cuentas descriptivo y fácil de entender. Estos son los nombres que los usuarios verán cuando busca y adición de sistemas de salas de equipos de Microsoft a las reuniones. Algunas organizaciones utilizan la convención de *sitio*-*Nombre del salón*(*Capacidad de la sala Max*)-RS, por ejemplo Curie — una sala de conferencias de 12-persona en Londres, podría tener el nombre para mostrar LON CURIE (12)-RS. 

Si su organización tiene muchos salas de conferencias que requieren varios, aprovisionadas cuentas, es posible que desea utilizar [Skype salón de sistemas de cuentas de aprovisionamiento de secuencias de comandos](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5) para aprovisionar de forma masiva varias cuentas de servicio de forma automática.


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir la convención de nomenclatura para las cuentas locales de los equipos de Microsoft.</li><li>Decidir si podrá crear cuentas individuales o usar los scripts de aprovisionamiento de forma masiva.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empezar a planear la implementación de dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalación de software de dispositivo 

Al planear la implementación de salas de equipos de Microsoft, tienen un número de opciones que se deben considerar al instalar el software requerido. En la siguiente tabla se describen los escenarios y los enfoques comunes. 

| **Escenario**            | **Enfoque**         |
|-------------------------|-----------------------|   
|Implementación de un número reducido de dispositivos de salas de equipos de Microsoft (<10). | Si usa Surface Pro basado en salas de equipos de Microsoft, siga las [instrucciones de instalación para un dispositivo por instalación](console.md). [En este vídeo práctico le guiará por el proceso.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si utiliza una solución integrada, implementar mediante el uso de la imagen del proveedor y configuración según sea necesario. |
| Implementación de entre 10 y 50 dispositivos desde un único proveedor.     | Crear una imagen de WIM, pausa después del [paso 6 en la guía](console.md)y capturar una imagen de distribución para usarse con la tecnología de clonación de distribución.    |
| Implementación de más de 50 dispositivos de salas de equipos de Microsoft, implementación de los dispositivos de más de un proveedor o que requieren a los agentes específicos de la organización como parte de la implementación. | Use una tarea basada en el secuenciador de compilación y distribución plataforma de software, como [System Center Configuration Manager](room-systems-scale.md).  |

**Sugerencia pro** - Each salones de los equipos de Microsoft debe tener un nombre de equipo válido y único en la red. Muchos de supervisión y alertas de sistemas muestran el nombre del equipo como un identificador de clave, por lo que es importante desarrollar una convención de nomenclatura para las implementaciones locales de los equipos de Microsoft que permite que el personal de soporte técnico localizar fácilmente las salas de los equipos de Microsoft que se ha marcado como la necesidad de realizar una acción. Un ejemplo que esté utilizando un patrón de MTR*sitio*-*Nombre del salón* (MTR-LON-CURIE). 

Como parte de la implementación, también necesitará tener en cuenta su estrategia para administrar y configurar las [cuentas locales](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) que se crean mediante el instalador de la aplicación de salas de equipos de Microsoft.

Se proporcionan instrucciones sobre cómo usar el [Monitor de Microsoft Azure](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para supervisar la implementación de salas de equipos de Microsoft e informar sobre disponibilidad, errores de hardware y software y versión de la aplicación de salas de equipos de Microsoft. Si decide utilizar el paquete de administración de operaciones de Microsoft, debe instalar al agente de conjunto de aplicaciones de administración de operaciones como parte del proceso de instalación de software y configurar la información de conexión de área de trabajo para el área de trabajo. 

Una consideración adicional es que si las salas de los equipos de Microsoft dejará de estar unido a un dominio. Información acerca de las ventajas de unirse a dominio puede encontrarse en [Consideraciones unirse de dominio del sistema de sala de Skype](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir la convención de nomenclatura de dispositivo de salas de equipos de Microsoft que se usará durante la implementación.</li><li>Decidir si podrá unirse a dispositivos de salas de equipos de Microsoft para su dominio y cómo administrar y configurar las cuentas locales. </li><li>Decidir si debe usar el conjunto de aplicaciones de administración de operaciones para supervisar la implementación de salas de equipos de Microsoft.</li><li>Decidir qué método utilizará para implementar el software y los agentes en el sistema de salas de equipos de Microsoft en la preparación para la implementación de dispositivos. </li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empezar a planear el método de implementación de dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implementación de dispositivos

Una vez que haya implementado el software de las unidades locales de los equipos de Microsoft, cree el plan a se suministran los dispositivos y los dispositivos periféricos asignados a los salones y, a continuación, continúe con la instalación y configuración. 


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir quién va a administrar la implementación de sitio por sitio.</li><li> Identificar los recursos que van a instalar los dispositivos de salas de equipos de Microsoft en el sitio y realizar la configuración y las pruebas.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Iniciar las pruebas de dispositivo.</li></ul>| 

_Tabla de ejemplo de implementación_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Sistema de salas de equipos de Microsoft**  | **Dispositivos periféricos**  | **Nombre del equipo de salas de equipos de Microsoft**  | **Cuenta del recurso salones de los equipos de Microsoft**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| HQ de Londres | Curie         | Medio        |                                   |                  |                                          |                                             |
| HQ Sidney | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Aplicación de salas de equipos de Microsoft y la configuración de dispositivo periférico 

Después de cada salones de los equipos de Microsoft se ha implementado físicamente sistema y los dispositivos periféricos compatibles conectados, que necesitará para configurar la aplicación de salas de equipos de Microsoft para asignar la cuenta del recurso salones de los equipos de Microsoft y la contraseña que creó anteriormente , para habilitar el sistema de salas de equipos de Microsoft iniciar sesión en Skype para empresas y Exchange. Lo s clave para sacar provecho de Skype para la empresa certificada periféricos USB audio y vídeos vinculados en otro lugar del documento. De no hacerlo, se puede producir un comportamiento inesperado. 

Puede configurar manualmente cada sistema de salas de equipos de Microsoft. Como alternativa, puede usar un almacenada centralmente, salas de equipos por Microsoft: archivo de configuración XML para administrar la configuración de la aplicación y sacar provecho de una secuencia de comandos de GPO de inicio para volver a aplicar la configuración que desea, cada vez que se inicia el sistema de salas de equipos de Microsoft. 

Para obtener más información acerca de cómo usar el archivo de configuración XML, consulte [administrar una configuración de la consola Microsoft salones de los equipos de forma remota con un archivo de configuración XML](../../manage/skype-room-systems-v2/xml-config-file.md). 

Puede usar [PowerShell remoto](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell) para la configuración de salas de equipos de Microsoft para las necesidades de informes de extracción. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decidir si podrá configurar cada sistema de salas de equipos de Microsoft manualmente o usar un archivo XML central (una por dispositivo de salas de equipos de Microsoft).</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Definir el enfoque de administración remota.</li></ul>| 

### <a name="testing"></a> Pruebas

Después de que se ha implementado el sistema de salas de equipos de Microsoft, debe ponerlo a prueba. Compruebe que las capacidades que aparece en la [Ayuda de salas de equipos de Microsoft](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) están trabajando en el dispositivo implementado. Se recomienda encarecidamente que el equipo de implementación de comprobar que las salas de los equipos de Microsoft es registro al conjunto de aplicaciones de administración de operaciones de Microsoft (si se utiliza). También es importante que realice un número de llamadas de prueba y las reuniones para comprobar la calidad. Para obtener más información, consulte esta [lista de comprobación de implementación útiles](console.md#microsoft-teams-rooms-deployment-checklist).

Se recomienda que como parte de la Skype general para la implantación de negocio, configurar los archivos de creación para el panel de calidad de llamadas (CQD), supervisar las tendencias de calidad y participar en el proceso de revisión de calidad de experiencia. Para obtener más información, consulte la [Guía de revisión de calidad de experiencia](https://aka.ms/qerguide). 

**Sugerencia pro** – la [Matriz de pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) disponible desde [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) contiene una ficha con un número de pruebas de salones de los equipos de Microsoft que se debe revisar con como parte de las pruebas. 

### <a name="asset-management"></a>Administración de activos 

Como parte de la implementación, querrá actualizar el registro de activos con el nombre del salón, el nombre de dispositivo de salas de equipos de Microsoft, la cuenta del recurso ha iniciado sesión salones de los equipos de Microsoft y asignado dispositivos periféricos (y qué puertos USB usan). 

_Tabla de ejemplo de activos_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Salones de los equipos de Microsoft no en serie.**  | **Dispositivos periféricos / serie Nº / puertos**  | **Nombre del equipo de salas de equipos de Microsoft**  | **Cuenta de servicio de salas de equipos de Microsoft**  | **Fecha de implementada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| HQ de Londres | Curie         | Medio        |                                          |                                          |                                          |                                            |                   |
| HQ Sidney | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


